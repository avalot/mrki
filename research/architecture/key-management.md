# Key Management for Teenagers

Open question from ARCHITECTURE.md: "keypairs are powerful but losable. Recovery mechanism needed that doesn't reintroduce centralization."

## Approach Analysis

### 1. Social Key Recovery (Shamir's Secret Sharing)

Split the private key into N shares; any M of N reconstruct it. Give shares to trusted friends.

- **Security**: Collusion of M friends = full key theft. Friends don't know they hold power unless told. A breakup or social fallout creates adversaries who hold shares.
- **UX**: Requires teens to understand the concept, select guardians, and coordinate recovery. Recovery requires M friends to be reachable, still have their device, and cooperate. Realistic for 16+; questionable for 13-year-olds.
- **Failure modes**: Friend group turnover is high at this age. A teen who changes schools may lose contact with all share-holders. Share-holders lose their own devices. No way to revoke a share once given.
- **Centralization risk**: None inherent, but a "share management service" would likely emerge.
- **Hidden assumptions**: Teens have M friends they trust with something irreversible. Friendships are stable enough for the key's lifetime.
- **Precedent**: Dark Crystal (SSB ecosystem) implemented this. Adoption was minimal even among crypto-literate adults. Keybase tried social proofs but not SSS for recovery.

### 2. Seed Phrase / Mnemonic

12-24 word backup phrase written on paper or stored somewhere.

- **Security**: Anyone who sees the phrase has the key. Physical security depends entirely on the teen's environment.
- **UX**: Crypto wallets have trained a generation on this, but loss rates are staggering. Chainalysis estimates ~20% of all Bitcoin is in lost wallets. Teens sharing bedrooms have no secure storage. A parent cleaning a room throws away the paper.
- **Failure modes**: Lost, thrown away, photographed by someone else, posted on social media by mistake. The phrase is either accessible (and vulnerable) or hidden (and forgettable).
- **Centralization risk**: None.
- **Hidden assumptions**: The teen has a private, persistent physical space. The teen understands that this phrase IS their identity.
- **Precedent**: Every crypto wallet. The loss rate among adults is already unacceptable for a social platform; for teens it would be worse.

### 3. Device-Based Recovery (Multi-Device)

Key exists on multiple devices. Lose one, recover from another.

- **Security**: Each device is an attack surface. Theft of any device = key compromise (unless each copy is passphrase-encrypted).
- **UX**: Natural for teens with phone + laptop. Zero ceremony. But many teens (especially 13-14) have only one device. Low-income teens almost certainly have one.
- **Failure modes**: Single-device teens have no recovery. All devices lost simultaneously (house fire, confiscation) = total loss.
- **Centralization risk**: None.
- **Hidden assumptions**: Teens own multiple internet-connected devices. This correlates with income and age, creating an equity gap in identity resilience.
- **Precedent**: Apple Keychain sync, Signal device linking. Works well when the assumption holds.

### 4. Custodial Recovery via Parent Email

Encrypted key backup sent to parent. Recovery requires teen's passphrase + the backup from the parent's email.

- **Security**: Parent cannot access the key without the passphrase (if the encryption is sound). But a determined parent could withhold the backup as leverage. A compromised parent email exposes the encrypted blob (still passphrase-protected).
- **UX**: Simple to set up. Recovery is a conversation with a parent, which is natural for younger teens. But some teens need privacy FROM parents (LGBTQ+ teens, teens in abusive homes). Making this the only path is dangerous.
- **Failure modes**: Parent email gets hacked. Parent loses access to their own email. Parent-teen relationship breaks down. Teen forgets passphrase. Parent doesn't understand what to do.
- **Centralization risk**: Low, but creates a parental chokepoint. A parent who disapproves of the platform can refuse to help recover.
- **Hidden assumptions**: The teen has a trustworthy parent with a functioning email account. This is often true and sometimes catastrophically false.
- **Precedent**: Apple's recovery contacts. Works for most families; fails for the families that need privacy most.

### 5. Relay-Assisted Recovery

A relay stores an encrypted key backup. Recovery requires passphrase + relay cooperation.

- **Security**: The relay holds an encrypted blob it cannot read. But it can refuse to return it (censorship), or be compelled by a government to hand it over (still encrypted, but now a target). Rate-limiting recovery attempts prevents brute-force on the passphrase.
- **UX**: Invisible to the user. Set a passphrase once, recover anywhere. This is what users expect from "normal" apps.
- **Failure modes**: Relay goes offline. Relay operator disappears. Passphrase forgotten (the dominant failure mode). If a single relay, it's a single point of failure. If multiple relays hold copies, availability improves but attack surface grows.
- **Centralization risk**: Significant. Whichever relay holds your backup has power over your identity continuity. The anchor nodes from the architecture become de facto identity providers.
- **Hidden assumptions**: At least one relay is honest, available, and long-lived. The teen remembers a passphrase they set months or years ago.
- **Precedent**: Signal's SVR (Secure Value Recovery) uses SGX enclaves. WhatsApp's encrypted backups use HSMs at Facebook. Both are centralized in practice.

### 6. Key Rotation / Identity Continuity

Don't recover old keys. Generate a new keypair. Friends vouch "new key = same person." Old key is retired. Reputation transfers via attestation.

- **Security**: No secret material to steal or lose retroactively. The vulnerability is the vouching process: can an attacker convince M friends to vouch for a fake "new key"? Social engineering is the attack vector, not cryptography.
- **UX**: Elegant. "I lost my phone" triggers a flow, not a crisis. The teen creates a new identity, reaches out to friends through any channel, and friends confirm. This matches how teens already re-establish identity (new phone number, new account on other platforms, tell your friends).
- **Failure modes**: A teen with no remaining friends on the platform cannot recover (the "new school" problem). An attacker who compromises the social graph can steal an identity. Old signed events reference a now-retired key; verification requires a chain of rotation events.
- **Centralization risk**: None, if vouching is peer-to-peer. Some if a "rotation oracle" is introduced to adjudicate disputes.
- **Hidden assumptions**: The teen has enough active friends to meet the vouching threshold. The protocol handles key succession cleanly (old events remain verifiable via the rotation chain). Reputation transfer is accepted as legitimate by the community.
- **Precedent**: PGP web of trust (failed due to UX). Keybase (succeeded briefly, acquired by Zoom). Nostr NIP-41 proposes key migration but is not widely implemented. The concept is sound; no one has shipped it well for consumers.

### 7. Hybrid Approaches

The approaches above are not mutually exclusive. Likely combinations:

- **Default: device-based + relay-assisted** for seamless UX, with relay backup as invisible fallback.
- **Opt-in: social recovery or parent recovery** as additional safety nets. Let the teen choose their trust model.
- **Last resort: key rotation with friend vouching** when all else fails. Identity survives even if the key doesn't.

This layered model means: device sync handles 80% of cases, encrypted backup handles 15%, and social recovery or rotation handles the remaining 5%.

## Decision Framework

Do not pick an approach. Instead, evaluate any proposal against these criteria:

| Criterion | Question to ask |
|---|---|
| **Equity** | Does this work for a 13-year-old with one phone and an unstable home? |
| **Failure rate** | What percentage of users will lose access within 2 years? Is that acceptable? |
| **Coercion resistance** | Can a parent, school, or government force recovery against the teen's will? |
| **Collusion resistance** | Can any group of N people steal someone's identity? |
| **Ceremony cost** | How many steps at setup? How many at recovery? Will a teen actually do them? |
| **Centralization creep** | Does this create an entity that could become a de facto identity provider? |
| **Degradation path** | When recovery partially fails (e.g., 2 of 3 friends reachable), what happens? |
| **Protocol fit** | Does this work with signed immutable events and the relay mesh? Do old events remain verifiable? |
| **Precedent honesty** | Has anyone shipped this to non-technical users? What was the actual loss/recovery rate? |
| **Composability** | Can this be combined with other approaches without creating contradictions? |

The likely answer is a hybrid with sensible defaults and progressive disclosure: simple for young/new users, more control for older/experienced ones. The hard design work is choosing what the default is and what "simple" means when the stakes are identity loss.
