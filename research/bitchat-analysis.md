# BitChat Analysis for Mrki TAZ

## What Is BitChat?

BitChat is a Bluetooth mesh chat app created by Jack Dorsey (co-founder of Twitter/X and Block, Inc.), announced July 2025. It enables offline, serverless text messaging over BLE with no accounts, no phone numbers, and no internet required. The tagline is "bluetooth mesh chat, IRC vibes." It is developed under the GitHub org "permissionlesstech."

The iOS app (bitchat mesh) shipped on the App Store in late July 2025. An Android version followed. Both are open source: the iOS repo uses The Unlicense (public domain), the Android repo was updated from MIT to GPLv3.

## Transport and Architecture

- **Primary transport**: Bluetooth Low Energy (BLE). Each device acts as both peripheral and central, discovering peers and relaying messages.
- **Mesh topology**: Flooding gossip with TTL-based hop limiting (max 7 hops, ~30m per hop, theoretical 300m max range). Bloom filter deduplication prevents routing loops.
- **Hybrid mode**: Also supports Nostr relay channels for internet-connected communication (geohash-based location channels added in v1.3.0). This is not a pure mesh project — it has an internet fallback.
- **Protocol**: Binary protocol optimized for BLE constraints. Fixed 13-byte headers, fragmentation support, 256 message types. Packets padded to standard block sizes (256/512/1024/2048 bytes) for traffic analysis resistance.

## Encryption

Uses the Noise Protocol Framework (Noise_XX_25519_ChaChaPoly_SHA256). Two persistent keypairs per device: Curve25519 for Noise handshakes, Ed25519 for signing. ChaCha20-Poly1305 AEAD encryption with forward secrecy per session.

**Security concerns (verified)**: Shortly after launch, a researcher demonstrated user impersonation — communicating with a target's contacts while appearing as them. Dorsey acknowledged the app was a work-in-progress without external security review. The whitepaper itself notes identity binding is application-layer only; users must verify fingerprints out-of-band to prevent MITM. No formal security proofs exist.

## iOS Background BLE Problem

**BitChat does not solve this problem.** The whitepaper explicitly defers platform-specific constraints to the implementation layer and contains no discussion of iOS background BLE restrictions. At launch, there was a confirmed bug preventing iOS-to-Android connectivity. The app requires foreground usage for reliable BLE operation on iOS — the same fundamental limitation documented in our BLE mesh viability assessment.

## Scale and Real-World Usage

- No documented device count limits in the protocol spec. The 7-hop TTL and flooding gossip topology suggest practical limits similar to other BLE mesh apps (functional at 5-20 devices, degraded at 50+, likely unusable at 100+).
- Significant real-world adoption during internet shutdowns: ~70K downloads in Madagascar during September 2025 protests, ~50K in Nepal same month, reported uptake in Uganda and Iran during 2026 blackouts. Total ~360K downloads by late September 2025.

## Development State

Experimental/early-stage. The project is active and shipping updates, but Dorsey himself described it as a work-in-progress. Known security vulnerabilities remain. The Nostr integration suggests the team recognizes pure BLE mesh is insufficient for reliable messaging.

## Relevance to Mrki TAZ

**What BitChat validates**: There is real user demand for offline, local, serverless communication — especially during internet shutdowns and at gatherings. The 70K Madagascar downloads in one week prove the use case.

**What BitChat confirms about our approach**: BitChat hits exactly the limitations our BLE research predicted. It does not solve iOS background BLE. It added Nostr (internet relay) as a fallback, essentially acknowledging BLE-only mesh is not sufficient. The impersonation vulnerability echoes the Bridgefy pattern of mesh crypto being hard to get right.

**Integration potential**: Low. BitChat's protocol is interesting but our architecture already has a signed-event protocol and relay system. BitChat's Unlicense means we could study or borrow protocol ideas freely. But the BLE transport layer has the same iOS limitations we already ruled out. The Nostr integration is orthogonal to our relay mesh.

**Recommendation**: BitChat reinforces our existing strategy — build on WiFi Aware (iOS 26+) rather than BLE for TAZ, use internet relay as the primary transport, and treat local communication as an invisible acceleration layer. BitChat's real-world adoption data is useful for validating TAZ demand to stakeholders.

Sources:
- [BitChat GitHub (iOS/macOS)](https://github.com/permissionlesstech/bitchat)
- [BitChat GitHub (Android)](https://github.com/permissionlesstech/bitchat-android)
- [BitChat Whitepaper](https://github.com/permissionlesstech/bitchat/blob/main/WHITEPAPER.md)
- [9to5Mac: BitChat App Store debut](https://9to5mac.com/2025/07/28/bitchat-mesh-jack-dorseys-bluetooth-messaging-app-debuts-on-the-app-store/)
- [CNBC: Jack Dorsey launches Bluetooth messaging rival](https://www.cnbc.com/2025/07/07/jack-dorsey-whatsapp-bluetooth.html)
- [TechCrunch: Jack Dorsey working on bitchat](https://techcrunch.com/2025/07/07/jack-dorsey-working-on-bluetooth-messaging-app-bitchat/)
- [Mobile Hacker: Offline encrypted messaging with Bitchat](https://www.mobile-hacker.com/2025/07/10/offline-encrypted-and-private-messaging-using-new-bitchat-bluetooth-app/)
- [BISI: Bitchat and Internet Shutdowns](https://bisi.org.uk/reports/bitchat-bluetooth-mesh-networks-and-internet-shutdowns)
- [BitChat Mesh Networking blog post](https://bitchat.online/2025/07/23/mesh-networking-via-bluetooth-bitchats-smart-connectivity/)
