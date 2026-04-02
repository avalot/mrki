# Event Storage Growth in an Immutable Event Stream

Research for ARCHITECTURE.md open question #4.

---

## 1. Scale Estimation

Assumptions: 500K users by year 3, average 30 events/day (midpoint of 20-50), average text event ~500 bytes signed+serialized.

| Timeframe | Users (avg) | Events/day | Text-only/year | With media (10% events have 200KB avg) |
|---|---|---|---|---|
| Year 1 | 100K | 3M | ~550 GB | ~22 TB |
| Year 3 | 500K | 15M | ~2.7 TB | ~110 TB |
| Year 5 | 1M | 30M | ~5.5 TB | ~220 TB |

**Cost at current rates** (2025-2026 prices):
- Hot SSD: ~$0.08/GB/mo. 110 TB = ~$8,800/mo
- Warm object storage (S3/Backblaze B2): ~$0.005/GB/mo. 110 TB = ~$550/mo
- Cold archival (Glacier/Wasabi): ~$0.002/GB/mo. 110 TB = ~$220/mo

**Key insight**: text events are trivial (~2.7 TB at year 3). Media dominates. The storage problem is really a media storage problem.

**Hidden assumption**: the 10% media rate and 200KB average size are conservative. If Mrki encourages image-heavy posts, multiply by 5-10x.

---

## 2. Tiered Storage

How event-sourced systems handle this:

- **Kafka**: configurable retention (time or size), then segments are deleted or compacted. Log compaction keeps latest value per key. Not truly immutable.
- **EventStore**: no built-in tiering. Projections let you derive read models, then old streams can be truncated (breaking immutability).
- **Datomic**: excision (explicit removal) exists but is treated as exceptional. Storage grows forever by design; relies on cheap storage.

**Pattern that emerges**: all production event-sourced systems eventually compromise on pure immutability. They either delete, compact, or tier. The question is where you draw the line.

**Trade-off**: tiering requires a policy engine ("which events go cold?"). Policy bugs can make data inaccessible when needed. Tiering also breaks the simplicity of "one log, one truth."

---

## 3. Pruning Strategies

Events potentially safe to prune:
- Ephemeral TAZ events where all parties opted for local-only
- Superseded profile updates (keep latest, prune intermediate)
- Typing indicators, read receipts, presence signals (if modeled as events)
- Expired governance votes after results are finalized and signed

**Tension with immutability**: pruning signed events means any node that kept them can prove you "lied" about your log. This is tolerable if pruning is a known protocol-level operation, not hidden.

**Reputation risk**: if a "flag" event is pruned, the flagger's reputation impact disappears. Solution: never prune events that feed reputation computation, or compute reputation snapshots first.

**Failure mode**: eager pruning of "unimportant" events that later turn out to matter (e.g., a deleted typing-indicator event was the only evidence of harassment timing).

---

## 4. Distributed Storage Benefits

In Mrki's relay mesh, no single node stores everything. This changes the calculus fundamentally:

- **Phone nodes**: store own events + friends' events. Maybe 1-5 GB per user.
- **Community nodes**: store events for a geographic region or topic. Maybe 50-500 GB each.
- **Anchor nodes**: store a broad index, not necessarily full content.

**Specialization patterns**:
- Geographic: "Paris relay" stores events from Paris-area users
- Temporal: "Archive relay" stores events older than 6 months
- Social-graph: a relay stores events for a connected cluster of users
- Media-only: a relay that only stores media blobs, referenced by hash

**This means**: 110 TB at year 3 is spread across potentially thousands of relays. If 2,000 community nodes each store 50 GB, that is 100 TB of capacity with natural redundancy. The cost is borne by operators, not centrally.

**Failure mode**: popular users' events get replicated widely (good for availability), unpopular users' events exist on very few relays (fragile). Need a minimum-replication guarantee.

---

## 5. Content-Addressable Storage

Events identified by `hash(content + author + timestamp)` per the architecture.

- **Deduplication is free**: if two relays receive the same event, they store it once.
- **Media separation**: event contains hash reference to media blob. Media stored in CAS (IPFS, S3, relay-hosted). Event log stays small; media lives separately.
- **Integrity verification**: any node can verify any event by recomputing its hash.
- **Garbage collection becomes possible**: media blobs not referenced by any non-pruned event can be collected.

**Trade-off**: CAS makes dedup easy but makes deletion hard. You cannot delete a blob if you do not know every reference to it across the entire mesh. This matters for GDPR right-to-erasure.

---

## 6. Phone Node Constraints

Reasonable budget: **2-3 GB** (phones have 64-256 GB; users tolerate apps using 1-5 GB).

Eviction strategy (priority order):
1. **Own events**: never evict (this is your authoritative copy)
2. **Close friends' recent events**: keep last 30 days
3. **Group events you participate in**: keep last 7 days
4. **Media thumbnails**: keep; evict full-resolution
5. **Everything else**: evict LRU

**Failure mode**: if a user's phone is their only relay and they lose it, their events are gone. Mitigation: the protocol should encourage syncing to at least one non-phone relay before an event is considered "durable."

---

## 7. Reputation vs. Storage

Reputation is a deterministic function of events. If events are pruned, reputation becomes unverifiable.

**Snapshot approach**:
1. Periodically (weekly/monthly), compute a reputation snapshot: `{user, score, inputs_summary, computed_at, computed_by, signature}`
2. Multiple nodes compute independently. Agreement = confidence.
3. Snapshot is itself a signed event in the log.
4. Once a snapshot exists and is widely replicated, the underlying events *can* be archived/pruned from hot storage.
5. Anyone who disputes the snapshot can request the underlying events from archival relays.

**Trade-off**: snapshots introduce trust in the computing node. Mitigated by requiring multiple independent computations. But this means reputation becomes a social consensus, not a pure derivation.

**Failure mode**: a malicious node publishes a wrong snapshot. If no other node has the underlying events to dispute it, the wrong score persists.

---

## 8. Precedents

| System | Strategy | Lesson for Mrki |
|---|---|---|
| **Git** | Pack files compress history; shallow clones skip old commits; `gc` removes unreachable objects | Shallow sync is viable: phone nodes can do shallow clones |
| **IPFS** | Pins keep data; unpinned data is garbage-collected; no one stores everything | Explicit pinning model maps to relay subscription |
| **Secure Scuttlebutt** | Each user has an append-only log; storage grows forever; no pruning | Works at small scale (~20K users); unclear if it survives 500K |
| **Nostr** | Relays independently choose what to store and for how long; no guarantees | Flexible but fragile; events disappear when relays shut down |
| **Bitcoin** | Full nodes store everything (600+ GB); light nodes store headers only; UTXO set is the "snapshot" | UTXO model is analogous to reputation snapshots |

**Common theme**: every system eventually introduces node specialization (full vs. light) and accepts that not every node stores everything.

---

## Decision Framework

When choosing a storage strategy, evaluate against these criteria:

1. **Reputation integrity**: can reputation still be computed or verified after the strategy is applied? This is non-negotiable for Mrki.
2. **Minimum replication factor**: how many independent copies of each event exist? Below 3 is fragile. Below 1 is data loss.
3. **Recovery path**: if a relay goes down, can its events be reconstructed from other relays? What is the time-to-recovery?
4. **GDPR compliance**: can a user's data be erased? Immutability and right-to-erasure are in direct tension. Content-addressable storage makes this harder. Encryption with key destruction is the likely answer.
5. **Operator cost curve**: does the strategy keep per-relay costs under the ~5 EUR/month community-node target? If a relay must store 500 GB to be useful, the bar is too high.
6. **Phone feasibility**: does the strategy work within 2-3 GB on a phone? If phone nodes become useless, the "every user is a node" principle collapses.
7. **Complexity budget**: tiering, pruning, and snapshotting all add protocol complexity. Each new mechanism is an attack surface and a source of bugs. Prefer fewer, simpler mechanisms.
8. **Adversarial robustness**: can a malicious relay exploit the strategy to corrupt reputation, hide evidence of abuse, or cause data loss for targeted users?

**The core tension**: immutability wants to keep everything forever; practicality demands shedding weight. The resolution is likely **media separation + reputation snapshots + relay specialization + phone-as-light-node**. But each of those is a design decision with second-order consequences that need prototyping.
