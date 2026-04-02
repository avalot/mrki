# Technical Architecture: Distributed Event Mesh

## Design Principles

1. **Protocol, not platform** — we're building an open protocol with a great default app, not a centralized service
2. **Every user is a node** — the app itself is a relay; the network is the users
3. **Immutable signed events** — every action is a cryptographically signed, append-only event
4. **Intentional pace** — delay is a feature, not a bug; the architecture enforces thoughtful tempo
5. **Decapitation-resistant** — no single entity can kill the network
6. **AI enhances, never required** — the network functions without any AI nodes
7. **Economics without tokens** — relay operators earn revenue, no blockchain, no speculation

---

## Layer 1: The Protocol

Every action is a signed, immutable event:

```
{
  id: hash(content + author + timestamp),
  author: public_key,
  kind: "post" | "thank" | "dm" | "flag" | "vote" | "event" | ...,
  content: encrypted_or_plain,
  timestamp: unix_ts,
  references: [event_ids...],
  signature: ed25519(private_key, serialized)
}
```

- **Identity = keypair**, generated on device. No server owns your identity.
- **Display name / avatar = a special event** that updates your profile. Change anytime. Keypair stays the same.
- **Phone/email = optional anchor** for account recovery and age verification, stored as an encrypted event only you and the verification service can read.
- **Events are immutable and signed.** You can't fake someone else's events. You can't alter history. The whole network is an audit trail.

---

## Layer 2: The Relay Mesh

Every node is a relay. Relays store events, forward them to other relays, and serve them to clients. Nodes differ in capacity:

| Node type | What it is | What it does | Who runs it |
|---|---|---|---|
| **Phone node** | The app itself | Stores your events + friends' events. Relays via internet + Bluetooth. Minimal resources. | Every user |
| **Home node** | An app on a laptop/desktop/Raspberry Pi | Stores more events, relays for your neighborhood/community. Always-on if the machine is on. | Any user who wants to contribute |
| **Community node** | A cheap VPS or donated server | Stores events for a city/region/topic community. Runs AI enrichment. Serves as a reliable relay. | Community organizers, small orgs, anyone with €5/month for a VPS |
| **Anchor node** | Run by the project | Bootstrapping, discovery, fallback. The network works without these — they just make the first connection easier. | Mrki project (early days), eventually unnecessary |

**Setting up a node = downloading the app and checking "I want to relay."** That's it. The app handles peer discovery, event syncing, and storage management automatically.

For a home/community node: download a second app (or toggle a setting), point it at more storage, done. No Docker, no config files, no terminal.

---

## Layer 3: Bluetooth TAZ (Temporary Autonomous Zones)

When phones are nearby, they form a Bluetooth Low Energy mesh:

```
Phone A ←BLE→ Phone B ←BLE→ Phone C
         ↕                    ↕
      Phone D              Phone E
```

- **DMs between nearby users go over Bluetooth** — zero internet needed, zero server involvement, near-instant
- **Local group chat** forms automatically when multiple Mrki users are nearby (opt-in)
- **Events signed locally** — real events with real signatures, just not yet propagated to the wider network
- **Sync to the mesh when connectivity returns** — events created in the TAZ are timestamped and signed, slotting into the global event stream naturally. Reputation effects apply retroactively
- **Plausible ephemerality** — TAZ events can be marked "local-only" by participants. If all participants agree, events stay on their devices and never sync. But if anyone chooses to sync, they can — honesty is enforced by social norms, not the protocol

### TAZ Use Cases

- **Concert/festival** — hundreds of teens at the same event, chatting without cell service
- **School hallway** — quick coordination without data leaving the building
- **Protest/march** — communication without relying on infrastructure that could be shut down
- **Rural areas** — poor connectivity but friends are physically nearby

---

## Layer 4: AI as a Distributed Service

AI can't run on phones (yet). But it doesn't need to run centrally either.

**AI enrichment nodes** are community nodes that volunteer GPU/API access:

- **Moderation scoring** — content passes through an AI scorer before wider distribution. If no AI node is available, content still propagates — it just hasn't been scored yet, and recipients' clients show an "unreviewed" indicator
- **Age-appropriateness** — AI nodes score content for age brackets. The community's kid-flags train the model over time
- **Ad detection** — pattern matching + AI to catch covert advertising
- **Creative assistance** — AI helps users draft, translate, illustrate. A service offered by community nodes, not a platform feature
- **Reputation computation** — AI nodes aggregate event history into reputation scores. Multiple nodes can compute independently; divergence is a signal that something is wrong

**Key principle: AI enhances but is never required.** The network functions without any AI nodes. Content just arrives unscored, and moderation falls back to community flags only.

---

## Layer 5: Reputation as Consensus

In a distributed system, reputation is a **computation that multiple nodes must agree on**.

### Approach: Convergent Reputation

- Reputation is computed from the event stream — a **deterministic function of all events involving a user**
- Any node with sufficient event history can compute it
- Nodes share reputation snapshots (themselves signed events). If two nodes disagree, the one with more complete event history wins
- **Your reputation is portable** — derived from your signed events, not stored in someone else's database
- **Liars lose credibility** — if you flag something and the community disagrees, your future flags carry less weight. Computable from event history

### Bootstrapping

New users have no reputation. Solution:
- Reputation starts at a baseline
- First actions are rate-limited (can't mass-post, can't mass-flag)
- As positive signal accumulates, limits relax

---

## Layer 6: Economics Built Into the Protocol

No tokens. No blockchain. No speculation. Just services that cost money.

- **Running a relay costs resources** (storage, bandwidth, compute). Relays can charge — but the **price is transparent and competitive**
- **Users pay relays, not "the platform."** Your subscription goes to the relays you use. Run your own relay → your cost is just hosting
- **Revenue distribution is automatic**: your €5/month is split among relays that stored and served your events, proportional to usage. Relay operators see exactly what they earn
- **Community nodes running AI enrichment** can charge a small premium. Communities vote on which AI services they want and what they're willing to pay
- **Referral economics still work**: invite someone → their future relay payments partially credit you as free months. The relay network benefits from more users, so this is positive-sum

---

## Layer 7: The Slow Path (Pacing by Design)

The distributed architecture makes intentional delay *easier*:

- **Posts propagate through relays** — each relay processes, scores, and forwards. This takes time naturally. We lean into it
- **AI enrichment adds deliberate delay** — content is held for reflection/scoring before wider distribution
- **Clients control consumption pace** — the app presents a **daily digest** or **finite feed**, not infinite scroll. Even if a relay has 1000 new events, the client shows you 20 and says "that's enough for now"
- **Proximity accelerates selectively** — nearby relays (including Bluetooth) have shorter propagation paths

### Delay Spectrum

| Content type | Propagation | Rationale |
|---|---|---|
| Bluetooth DM (nearby) | Instant | Direct device-to-device |
| Internet DM | Seconds | One relay hop, lightweight moderation |
| Event coordination (nearby) | Seconds–minutes | Proximity-dependent, time-sensitive |
| Post to group | Minutes to hours | Multi-relay propagation + AI enrichment |
| Post to broad audience | Hours to next digest | Deliberate pacing, deeper review |
| Governance vote | 24–72 hour window | Deliberation, not impulse |

---

## Open Questions

1. **Protocol spec format**: define our own, or extend an existing one (Nostr NIPs, ActivityPub, AT Protocol)? Nostr is closest but lacks reputation and governance primitives.
2. **Key management for teens**: keypairs are powerful but losable. Recovery mechanism needed that doesn't reintroduce centralization. Social key recovery (N-of-M friends can help you recover)?
3. **Relay incentive alignment**: how to prevent a relay cartel or race-to-bottom pricing? Community choice + transparent pricing might be enough.
4. **Event storage growth**: immutable = ever-growing. Pruning strategies? Archival tiers? Or is storage cheap enough at our scale?
5. **Bluetooth range/reliability**: BLE mesh networking is still flaky in practice. What's the fallback UX when Bluetooth fails?
6. **Legal entity**: who stewards the protocol? A foundation? A cooperative? This matters for the "no decapitation" guarantee.
