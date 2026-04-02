# Protocol Choice: Build, Extend, or Hybrid?

## What We Need From a Protocol

Mrki's architecture demands: signed immutable events, keypair identity, relay mesh with heterogeneous node types, Bluetooth TAZ (local mesh with deferred sync), convergent reputation computed from event history, community governance voting, age-verification signals, AI enrichment metadata, and an economics layer for relay payments. Any protocol we adopt must either support these or be extensible enough to add them.

---

## Option Analysis

### 1. Nostr (Extend via NIPs)

**Technical fit: HIGH.** Nostr's core is almost identical to ours: JSON events with `id`, `pubkey`, `kind`, `content`, `tags`, `sig`. Identity = keypair. Events are signed and immutable. Relays store and forward events. NIPs (Nostr Implementation Possibilities) are the extension mechanism — numbered proposals that define new event kinds, tag conventions, and relay behaviors. There are 100+ NIPs covering DMs (NIP-04/44), replaceable events (NIP-16), relay lists (NIP-65), zaps/payments (NIP-57), and more.

**What maps cleanly:** Event structure, keypair identity, relay architecture, encrypted DMs, profile metadata, replaceable events.

**What we'd add as custom NIPs:** Reputation snapshots (new event kind), governance votes (new event kind), age-verification signals (encrypted event kind), TAZ local-only markers (tag convention), AI enrichment scores (new event kind attached to scored events), relay payment negotiation (new event kind), node capability advertisement.

**Ecosystem leverage: MODERATE.** Dozens of relay implementations (Go, Rust, Python), 50+ clients, established libraries (nostr-tools, rust-nostr). We'd get relay infrastructure, key management patterns, and developer familiarity for free.

**Hidden assumptions:** Nostr assumes relays are simple store-and-forward — no computation. Our AI enrichment and reputation computation nodes are "smart relays" that Nostr doesn't anticipate. Nostr has no concept of structured relay hierarchies (phone/home/community/anchor). NIP-57 zaps depend on Lightning/Bitcoin — misaligned with our "no blockchain" principle.

**Risk:** Nostr's ecosystem is Bitcoin-culture-adjacent. Community norms may resist teen-safety features. NIPs we propose may not get upstream adoption, forking us from the ecosystem.

### 2. ActivityPub

**Technical fit: LOW.** ActivityPub is actor-to-actor messaging on top of HTTP, designed around servers that host user accounts. Identity is `user@server.tld`, not keypairs. There is no concept of signed immutable events — activities are mutable JSON-LD objects. Federation is server-to-server, not event-mesh.

**Architectural mismatches:** Server-centric identity (conflicts with "every user is a node"), no native crypto signatures on content, no offline/Bluetooth capability, mutable objects (conflicts with immutable event log), heavyweight JSON-LD serialization, inbox/outbox model assumes always-online servers.

**Extension cost: VERY HIGH.** Bolting on keypair identity, signed events, Bluetooth TAZ, and convergent reputation would require replacing ActivityPub's core assumptions. You'd be wearing ActivityPub as a skin over a fundamentally different protocol.

**Interop value: LOW for our use case.** Mastodon/Lemmy interop sounds appealing but their users are adults. Teen platform interoperating with adult fediverse creates moderation and safety headaches that outweigh the network benefit.

**Risk:** Massive engineering cost for marginal interop value. The protocol fights our architecture at every turn.

### 3. AT Protocol (Bluesky)

**Technical fit: MODERATE.** AT Protocol has personal data repositories (signed Merkle trees of records per user) — closer to our "your data is yours" model. Identity uses DIDs (decentralized identifiers). The data model is schema-driven (Lexicons).

**What's good:** Signed data repositories, portable identity via DID, schema-driven extensibility, content labeling system (could map to age-gating and moderation).

**Hidden assumptions:** AT Protocol assumes always-online infrastructure: BGS (Big Graph Service) for firehose aggregation, AppView servers for indexing, PLC directory for DID resolution. This is fundamentally a "small number of large servers" architecture, not a mesh. No concept of phone-as-relay or Bluetooth. Lexicon schemas must be registered in a global namespace tied to domain names. The protocol is complex — implementing a conformant PDS is substantial engineering.

**Extension cost: HIGH.** We'd need to build our own relay mesh on top of AT Proto's data model, implement Bluetooth sync for repositories, add reputation/governance as custom Lexicons, and run our own infrastructure stack that diverges from Bluesky's.

**Interop value: LOW-MODERATE.** Bluesky interop is theoretically interesting but practically premature — AT Protocol is still evolving rapidly and Bluesky controls the spec.

**Risk:** Coupling to a protocol controlled by a single company. Complexity tax on a small team. The "decentralized" claims are aspirational — in practice, Bluesky runs the infrastructure.

### 4. Custom Protocol

**Technical fit: PERFECT (by definition).** We design exactly what we need: event structure, relay hierarchy, TAZ sync, reputation primitives, governance voting, age signals, AI enrichment metadata, payment negotiation.

**Extension cost: ZERO (it's all ours).** But the upfront design and implementation cost is real.

**Ecosystem leverage: ZERO.** No existing relays, libraries, clients, or developer familiarity. Everything from scratch.

**Risk:** Ecosystem bootstrapping is the main cost. No battle-tested implementations. Protocol design mistakes are expensive to fix. "Not invented here" perception may slow developer adoption.

### 5. Hybrid: Nostr Core + Custom Event Kinds

**Technical fit: HIGH.** Use Nostr's event structure, signing scheme, and relay protocol as the base layer. Add custom event kinds (reputation, governance, TAZ, AI scores, age verification) in our own NIP-range. Nostr explicitly supports this — unknown event kinds are ignored by clients that don't understand them.

**What we get for free:** Event serialization, signature verification, relay communication (WebSocket + subscription filters), key management patterns, existing libraries, basic relay implementations to fork.

**What we build ourselves:** TAZ/Bluetooth sync layer, smart relay logic (AI enrichment, reputation computation), relay hierarchy and capability negotiation, payment protocol (replacing zaps with non-crypto payments), age-verification event handling.

**Interop:** Mrki posts could appear on standard Nostr clients (as plain posts). Nostr users could interact with Mrki content at a basic level. Our custom event kinds are invisible to standard clients but don't break anything.

**Risk:** Nostr protocol changes could break assumptions. We'd maintain a fork-distance from mainline Nostr that grows over time. But starting Nostr-compatible is strictly better than starting from zero.

---

## Decision Framework

Score each option 1-5 on these criteria, weighted by priority:

| Criterion | Weight | Question |
|---|---|---|
| **Architecture alignment** | 5 | How much of our architecture works without modification? |
| **Time to MVP** | 5 | How fast can a small team ship the core loop? |
| **Teen safety expressiveness** | 4 | Can reputation, age-gating, and governance be first-class? |
| **Offline/TAZ capability** | 4 | Does the protocol support or obstruct Bluetooth mesh? |
| **Ecosystem bootstrapping cost** | 3 | How much infrastructure do we build vs. reuse? |
| **Interop value for teens** | 2 | Does compatibility with X bring users we actually want? |
| **Long-term protocol control** | 3 | Can we evolve the protocol without permission from others? |
| **Developer hiring/onboarding** | 2 | Can new engineers learn the protocol quickly? |

**Process:** Have each technical team member score independently. Discuss where scores diverge by more than 2 points. The option with the highest weighted score wins — but any option scoring below 3 on a weight-5 criterion is eliminated regardless of total score.

**Key question to resolve first:** Is Nostr-ecosystem interop valuable enough to justify inheriting its assumptions? If yes, go hybrid. If no, the choice is between hybrid (for ecosystem leverage) and custom (for total control). ActivityPub and AT Protocol should be eliminated early — the architectural mismatch is fundamental.
