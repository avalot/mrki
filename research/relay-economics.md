# Relay Economics: Incentive Alignment and Market Risks

## 1. Cartel Risk

**Precedents:** Email hosting consolidated to 3 providers (Google, Microsoft, Apple) not through collusion but through economies of scale and network effects. Mastodon instances show the opposite: fragmentation with no coordination, leading to uneven quality. Neither outcome is good.

**What actually prevents cartels:** Low barrier to entry. If 5 big relays collude on pricing, anyone with a EUR 5/month VPS can undercut them. The protocol guarantees data portability (events are signed, stored across relays), so switching cost is near-zero. This is the key structural defense: cartels only hold when switching is expensive or supply is constrained.

**Hidden assumption:** That relay operation stays simple. If it becomes complex (compliance, AI models, moderation tooling), barriers rise and consolidation follows. The protocol must keep "run a basic relay" trivially easy.

**Risk for Mrki:** Teen users won't comparison-shop relays. Their client app picks relays automatically. Whoever controls the default relay selection algorithm controls the market. This is the real cartel vector -- not relay operators colluding, but the client app becoming a gatekeeper.

## 2. Race to Bottom

**Precedent:** [95% of Nostr relays can't cover costs](https://dev.to/jonathan_greenallidoizc/95-of-nostr-relays-cant-cover-costs-heres-why-that-matters-189l). A third have shut down. Free relays absorb spam, burn through storage, and die. Paid relays struggle because users won't pay for infrastructure they can't see.

**Why it happens:** Relay service is commodity bandwidth + storage. No differentiation means price competition to zero. Tor has the same problem: [relay operators subsidize the network from personal funds](https://blog.torproject.org/two-incentive-designs-tor/), and growth in demand outpaces growth in volunteer capacity.

**What prevents it:** Differentiation. Relays that offer AI enrichment, better uptime, geographic locality, or moderation quality can charge premiums. The protocol should make relay quality visible (uptime stats, latency, enrichment services) so the market can price on value, not just cost.

**Hidden assumption:** That teens (or their parents) care about relay quality at all. They probably don't. The client app must abstract this while still routing payments to quality relays.

## 3. Free-Rider Problem

**Precedent:** Tor runs on volunteers. It works, but barely -- [the network is perpetually under-resourced](https://blog.torproject.org/tor-incentives-research-roundup-goldstar-par-braids-lira-tears-and-torcoin/). Mastodon instances survive on [admin donations and goodwill](https://medium.com/@lim_nick/mastodon-systemic-sustainability-afe172699cb2), creating unpredictable funding.

**Mrki's structure:** Phone nodes and home nodes are free riders by design -- they contribute bandwidth but consume more than they provide. This is fine *if* community/VPS nodes have a viable revenue model. The question is whether EUR 5/month/user generates enough to sustain the paid tier.

**Back-of-envelope:** 100K users x EUR 5/month = EUR 500K/month. If 200 community relays split this proportional to usage, that's ~EUR 2,500/relay/month -- well above VPS costs (~EUR 20-50/month). The math works at scale. It fails during the free period (pre-2028) when revenue is zero and relays must be subsidized or volunteer-run.

**Critical gap:** The 2024-2028 free period. Who funds relays when users pay nothing? Options: project funding from seed round, relay operators as ideological volunteers (Tor model), or anchor nodes run by the project.

## 4. Payment Mechanics

**The teen payment problem:** Minors in Europe can't hold PayPal accounts. Options that work for under-18s: parent-linked cards (Pixpay, Revolut Junior), Apple/Google family payment, or billing flows where the parent pays directly.

**How EUR 5 flows to relays:**

| Approach | Pros | Cons |
|---|---|---|
| **Central billing, distributed payout** | Simple UX, parent-friendly | Reintroduces central chokepoint |
| **Direct relay payment** | True decentralization | Teens can't manage multiple subscriptions |
| **Relay cooperative / aggregator** | Balances simplicity and distribution | Cooperative governance is hard |
| **Lightning Network** | Programmable micropayments | Teens don't have Bitcoin; UX is terrible |

**Pragmatic answer:** Central billing (parent pays EUR 5 via Stripe/card) with transparent, automatic distribution to relays based on usage. This is centralized payment with decentralized service -- the same model as app stores paying developers. Accept the tradeoff during growth phase; add decentralized payment rails later.

## 5. Transparency and Trust

**What users need to see:** Where their EUR 5 went, broken down by relay and service type. Public dashboards showing per-relay revenue, costs, and uptime. This exists in some form in Nostr (relay stats) and Mastodon (instance-level cost transparency from admins who share their hosting bills).

**What relay operators need:** Verifiable usage metrics so they can dispute underpayment. Auditable distribution algorithm (open-source, deterministic).

**Risk:** If the distribution algorithm is opaque, it becomes the same trust problem as ad-tech revenue sharing. The algorithm must be published, reproducible, and ideally computed by multiple independent parties.

## 6. Geographic Equity

**EUR 5/month is:** 0.15% of French median monthly income. In Morocco it's ~2%, in Senegal ~5%. For a platform targeting Francophone teens, this matters immediately.

**Options:** Regional pricing (common in SaaS/gaming), purchasing power parity tiers, or cross-subsidy (French users pay EUR 5, Senegalese users pay EUR 1, relays serving both get the same per-event rate from a pooled fund).

**Hidden risk:** Regional pricing creates arbitrage (VPN to cheap region). For a teen platform, the complexity of geographic pricing may not be worth it until international expansion actually happens.

## 7. AI Node Compensation

**GPU inference costs are collapsing:** [1,000x reduction in 3 years](https://www.gpunex.com/blog/ai-inference-economics-2026/), with H100 spot instances down 88%. This means AI enrichment nodes may become cheap to run, reducing the compensation problem.

**Models from GPU marketplaces:** [Akash Network uses reverse auctions](https://compute.exchange/blogs/the-rise-of-gpu-marketplaces-in-2026) (users post jobs, providers bid). Vast.ai uses a spot market. Both show that market-based pricing works for compute.

**For Mrki:** Communities vote on which AI services they want. AI nodes publish prices. The client routes enrichment requests to the cheapest node meeting quality thresholds. No central pricing needed -- but the community budget (portion of EUR 5/month allocated to AI) needs a governance mechanism.

---

## Decision Framework

When choosing between approaches for each issue above, evaluate against these criteria:

| Criterion | Question to answer |
|---|---|
| **Survives the free period** | Does this work pre-2028 when revenue is zero? |
| **Teen-compatible UX** | Can a 14-year-old use this without understanding relay economics? |
| **Parent-compatible billing** | Can a parent pay with a normal card and understand what they're paying for? |
| **Resists centralization** | Does this create a single point of control or failure? |
| **Resists consolidation** | Does this prevent 3 relays from capturing 90% of traffic? |
| **Scales down** | Does this work at 1,000 users, not just 100,000? |
| **Scales up** | Does this work at 1M users without redesign? |
| **Transparent** | Can any participant verify the money flows? |
| **Geographically fair** | Does this exclude teens in lower-income countries? |

**The core tension:** Decentralization of service vs. centralization of payment. Every distributed system that actually works for consumers (email, web hosting, app stores) ended up with centralized payment rails distributing to decentralized providers. Fighting this pattern costs UX. The question is whether Mrki accepts this tradeoff now and decentralizes payment later, or pays the UX cost upfront.

**The Nostr warning:** Building relay economics as an afterthought leads to 95% of relays running at a loss. Mrki must design the payment flow *into* the protocol from day one, even if the actual money doesn't flow until 2028.

Sources:
- [95% of Nostr Relays Can't Cover Costs](https://dev.to/jonathan_greenallidoizc/95-of-nostr-relays-cant-cover-costs-heres-why-that-matters-189l)
- [Tor Incentive Designs](https://blog.torproject.org/two-incentive-designs-tor/)
- [Tor Incentives Research Roundup](https://blog.torproject.org/tor-incentives-research-roundup-goldstar-par-braids-lira-tears-and-torcoin/)
- [Mastodon Systemic Sustainability](https://medium.com/@lim_nick/mastodon-systemic-sustainability-afe172699cb2)
- [Nostr Relay Incentive Research](https://research.dorahacks.io/2024/04/30/nostr-relay-incentive/)
- [AI Inference Economics: The 1,000x Cost Collapse](https://www.gpunex.com/blog/ai-inference-economics-2026/)
- [GPU Marketplaces in 2026](https://compute.exchange/blogs/the-rise-of-gpu-marketplaces-in-2026)
- [Nostr Empirical Analysis](https://arxiv.org/html/2402.05709v2)
