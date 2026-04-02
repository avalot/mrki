# BLE Mesh for TAZ: Viability Assessment

## 1. What Actually Works Today

**Phones cannot be BLE Mesh nodes.** The Bluetooth Mesh Profile requires always-on relay listening. Neither iOS nor Android implement this natively — phones can only act as proxy clients to a mesh, not mesh participants. The usable payload per BLE mesh packet is 11-15 bytes after headers, encryption, and TTL overhead. This rules out the Bluetooth SIG Mesh Profile for phone-to-phone messaging entirely.

What phones *can* do: BLE peripheral/central advertising and GATT connections. This is point-to-point or star topology, not true mesh. You build "mesh-like" behavior in your application layer by having phones relay messages manually — which is exactly what Bridgefy, Briar, and FireChat did.

**Range**: 10-30m indoors realistic, up to 100m outdoors line-of-sight. **Throughput**: ~2 Mbps theoretical for BLE 5.x, but real application throughput for mesh-relayed messages is measured in bytes/sec, not megabytes. Text messages only.

## 2. iOS Background Problem (The Showstopper)

iOS aggressively restricts background BLE:
- Background scanning requires declaring exact service UUIDs in Info.plist — no general discovery
- Background advertising puts service UUIDs in an "overflow area" **invisible to Android devices**
- Non-connectable advertisements are suppressed entirely when backgrounded
- No persistent background execution without workarounds

COVID contact tracing apps hit this wall. TraceTogether (Singapore) required the app to stay in foreground on iOS. The UK NHS app used "keepalive" notifications between iOS devices to stay awake longer — a fragile hack. Apple/Google ultimately had to build Exposure Notification as an OS-level API to make it work.

**Android** is far more permissive — background BLE scanning and advertising work reliably with a foreground service notification.

**Cross-platform pain**: iOS backgrounded + Android = broken discovery. This is not a bug to fix; it is Apple's deliberate design.

## 3. Mesh Scale and Failure Modes

| Scale | Reality |
|---|---|
| 5-8 devices | Works well. Small friend group in a hallway. |
| 20-50 devices | Marginal. Message latency increases, packet collisions on BLE's 3 advertising channels. |
| 100+ devices | Network saturation. FireChat became unusable at Hong Kong protest density. Bridgefy degraded similarly in dense urban environments. |
| 500+ (concert) | Not viable with BLE alone. The 3 advertising channels are fully saturated. |

Dynamic mesh routing in a crowd where people are moving is an unsolved problem in practice. Partitioning is the norm, not the exception.

## 4. Security Lessons from Existing Projects

**Bridgefy** was catastrophically broken. Two research papers ([Royal Holloway 2021](https://eprint.iacr.org/2021/214.pdf), [ETH Zurich 2021](https://ethz.ch/content/dam/ethz/special-interest/infk/inst-infsec/appliedcrypto/education/theses/breaking-bridgefy-again.pdf)) demonstrated: user tracking via BLE identifiers, message impersonation, full message interception, and a single "zip bomb" message that could crash the entire network. Even after adopting libsignal, fundamental protocol flaws remained.

**Briar** is the success story — proper Tor integration, end-to-end encryption, no metadata leakage. But Briar is Android-only, partly because iOS background BLE is too restricted.

**FireChat** shut down in 2019 after the hype faded.

**Privacy concern for Mrki**: BLE advertising inherently broadcasts "I am running this app" to anyone scanning nearby. For a teen platform, this is a real risk — it reveals social platform membership to anyone with a BLE scanner.

## 5. The WiFi Aware Breakthrough (2025)

Apple introduced WiFi Aware in iOS 26 (WWDC 2025), required by the EU Digital Markets Act. This is a cross-platform peer-to-peer protocol that:
- Works simultaneously with existing WiFi connections
- Offers dramatically higher bandwidth than BLE
- Supports app-to-app pairing via DeviceDiscoveryUI
- Is interoperable with Android's WiFi Aware (available since Android 8)

**This changes the calculus significantly.** WiFi Aware was purpose-built for the exact use case Mrki needs. It is the first cross-platform, high-bandwidth, peer-to-peer transport that works on both iOS and Android without the background restrictions that cripple BLE.

Apple Multipeer Connectivity remains Apple-only and undocumented on the wire — not viable for cross-platform.

## 6. Battery Impact

BLE idle scanning: 0.1-0.5% battery/hour. Active mesh relaying (always listening + rebroadcasting): significantly higher, potentially 2-5%/hour depending on network density. COVID tracing apps that kept BLE active reported noticeable but not catastrophic drain — roughly 5-10% additional daily consumption.

Duty cycling (scan for 2s, sleep for 10s) reduces drain but increases discovery latency. For "instant DMs" this creates a tension between responsiveness and battery life.

## 7. Recommended Fallback UX

Based on every failed mesh project: **never promise local mesh to users.** Instead:
- Use local transport silently as an acceleration layer — messages go faster when nearby, but the UI does not change
- Show a subtle proximity indicator ("3 friends nearby") without implying a different communication mode
- All messages route through internet by default; local transport is an optimization, not a feature
- When offline, queue messages with clear "will send when connected" status
- Never surface "Bluetooth mesh" or "local network" in user-facing language

## Decision Framework

Evaluate BLE/local mesh features against these criteria:

| Criterion | Question |
|---|---|
| **User-facing vs invisible** | Does the feature require users to understand local networking, or is it transparent? Invisible features can ship earlier with lower risk. |
| **iOS background viability** | Can it work when the app is backgrounded on iOS? If not, it will fail for 50%+ of users. |
| **Cross-platform parity** | Does it work the same on iOS and Android? Asymmetric experiences breed confusion. |
| **Failure graceful** | When it fails (and it will), does the user notice? Silent fallback to internet = safe. Broken local chat = support tickets. |
| **Scale ceiling** | At what user density does it break? If it breaks at concert scale — the flagship use case — reconsider. |
| **Security audit cost** | Bridgefy proves that amateur mesh crypto is dangerous. What is the cost of doing this correctly? |
| **WiFi Aware readiness** | Is WiFi Aware on iOS 26 mature enough to bet on instead of BLE? Monitor adoption rates (requires iOS 26+). |
| **Regulatory exposure** | For a teen platform, does broadcasting BLE identifiers create GDPR/child-safety issues? |

**Suggested sequencing**: (1) Build the signed-event protocol and internet relay first. (2) Add WiFi Aware as an invisible acceleration layer once iOS 26 adoption reaches ~60% of target demographic. (3) Use BLE only as a fallback discovery mechanism for WiFi Aware pairing, never as a primary transport. (4) Treat the "concert with 1000 users" TAZ scenario as a Phase 3+ aspiration requiring dedicated infrastructure (portable WiFi access points, not phone mesh).

Sources:
- [10 Reasons BLE Mesh Has Struggled](https://argenox.com/blog/10-reasons-why-ble-mesh-has-struggled-to-gain-traction)
- [BLE Mesh in Mobile Devices Guide 2025](https://citrusdev.com.ua/bluetooth-mesh-in-mobile-devices-the-complete-guide-for-2025/)
- [Breaking Bridgefy (Royal Holloway 2021)](https://eprint.iacr.org/2021/214.pdf)
- [Breaking Bridgefy Again (ETH Zurich 2021)](https://ethz.ch/content/dam/ethz/special-interest/infk/inst-infsec/appliedcrypto/education/theses/breaking-bridgefy-again.pdf)
- [iOS BLE Scanning Guide (Punch Through)](https://punchthrough.com/ios-ble-scanning-guide/)
- [NHS COVID-19 Background Tracing Details](https://reincubate.com/blog/nhs-covid-19-background-tracing-details/)
- [WiFi Aware vs BLE for Mobile Mesh (Benoliel, 2025)](https://anthenor.medium.com/wi-fi-aware-or-bluetooth-low-energy-ble-for-mobile-mesh-ea11defcfd46)
- [Apple WiFi Aware Framework (WWDC 2025)](https://developer.apple.com/documentation/WiFiAware)
- [iOS 26 WiFi Aware Features (9to5Mac)](https://9to5mac.com/2025/06/20/ios-26-to-let-third-party-apps-build-their-own-airdrop-alternative/)
- [Briar Project](https://briarproject.org/how-it-works/)
- [Bluetooth Chat Apps Compared (BitChat, 2025)](https://bitchat.online/2025/07/22/bluetooth-chat-apps-compared-bitchat-bridgefy-briar-more/)
