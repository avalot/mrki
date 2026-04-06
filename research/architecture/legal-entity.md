# Legal Entity Structure: Decision Framework

## The Models

### 1. Nonprofit Foundation (Signal, Linux Foundation, Apache, Mozilla)

501(c)(3) or Swiss *Stiftung*. Board owns IP/trademarks, employs devs, stewards protocol.

- **Decapitation: MODERATE.** Single entity with jurisdiction and bank accounts. Mozilla nearly died from Google dependency. Signal depends on one $105M loan. Apache/Linux Foundation resilient via broad membership -- but any foundation can be sued, sanctioned, or defunded.
- **Teen governance: MODERATE.** Florida allows board members at 15+; most states don't prohibit minors but they can't sign binding contracts. Practical path: adult board + Youth Advisory Council with bylaws-mandated influence.
- **Revenue fit: GOOD.** Foundation doesn't capture relay revenue -- stewards protocol only. Relay economics independent.
- **Cost.** US: $5-15K, 3-12 months. Swiss: CHF 50K endowment + CHF 6-10K formation + ~CHF 10K/year. Swiss is pricier but offers privacy, neutrality, FADP alignment.

### 2. Cooperative (Stocksy, Mondragon)

Members (users/relay operators) own entity. One-member-one-vote. Surplus reinvested or distributed.

- **Decapitation: MODERATE-HIGH.** No single owner to pressure, but still one legal entity. Seizing it doesn't seize member relationships.
- **Teen governance: POOR.** Most jurisdictions require legal capacity to contract. Minors can't be full members without guardianship structures. "Associate members" without votes defeats the purpose.
- **Revenue fit: GOOD.** Relay operators as members fits naturally.
- **Cost.** $2-10K. Ongoing democratic administration overhead.

### 3. DAO / Digital Cooperative

Off-chain voting wrapped in Wyoming DUNA, DAO LLC, or Swiss association.

- **Decapitation: HIGH (theory).** Distributed governance -- but legal wrappers reintroduce jurisdictional targets.
- **Teen governance: POOR.** No framework addresses minors. Token governance excluded by Mrki principle. Non-token DAOs untested for minor participation.
- **Revenue fit: MODERATE.** Treasury without tokens is awkward. Novel legal territory.
- **Cost.** Wyoming: $1-5K. Swiss association: CHF 0. But legal uncertainty adds ongoing counsel costs.

### 4. Multi-Entity (Bluesky model)

Foundation stewards protocol. Company builds default app. Relay network independent. (Free Our Feeds is campaigning for exactly this split for AT Protocol.)

- **Decapitation: HIGH.** Three independent failure points. Kill company -- protocol survives. Kill foundation -- app survives. Kill both -- relay network continues.
- **Teen governance: GOOD.** Teens govern on-protocol via signed governance events. Foundation bylaws commit to honoring protocol votes. No need for teens to be corporate officers.
- **Revenue fit: EXCELLENT.** Company earns from app. Foundation receives grants. Relays earn independently. Clean separation.
- **Cost: HIGHEST.** $15-30K for two entities. But company can form later.

### 5. No Entity (Pure Protocol)

Publish spec, release reference implementation, walk away. Email, BitTorrent.

- **Decapitation: MAXIMUM.** Nothing to kill. Email survived 50 years ownerless.
- **Teen governance: N/A.** No structure means no governance integration. Contradicts Mrki's core promise.
- **Revenue fit: GOOD.** But no one funds development. Email stagnated. XMPP fragmented. IRC declined while Discord centralized.

## Jurisdiction

| Factor | Switzerland | US | EU (NL/Estonia) | UK |
|---|---|---|---|---|
| Privacy | FADP (GDPR-like, less punitive) | Weak; state patchwork | GDPR (strict) | UK GDPR + AADC |
| Teen platform risk | Moderate | High (COPPA, AG lawsuits) | Moderate-High (DSA) | High (Online Safety Act) |
| Political neutrality | High | Low | Moderate | Moderate |
| Foundation cost | CHF 50K+ | $5-15K | ~EUR 5K (NL stichting) | ~GBP 3K |

Switzerland best balances privacy, neutrality, and cost. US has strongest speech protections but highest litigation risk. EU is where users are (GDPR applies regardless).

## Teen Governance: The Real Answer

No jurisdiction allows 13-year-olds fiduciary board positions. The solution: **protocol-level governance is the real power; the legal entity's bylaws bind it to honor that governance.** Teens vote on-protocol via signed governance events. The foundation executes. This sidesteps minor capacity issues entirely.

Supplementary: Youth Advisory Council with bylaws-mandated veto. Age-tiered membership with full voting at 16-18.

## Decision Framework

Score 1-5, weighted:

| Criterion | Weight | Question |
|---|---|---|
| Decapitation resistance | 5 | Can the network survive the entity's death? |
| Teen governance | 5 | Can teens have real, binding influence? |
| Revenue compatibility | 4 | Works with distributed relay economics? |
| Jurisdictional resilience | 4 | Jurisdiction won't become hostile? |
| Formation speed | 3 | Launch within 6 months? |
| Legal precedent | 3 | How much legal novelty? |
| Governance evolution | 3 | Adapts from 500 to 5M users? |
| Formation cost | 2 | Affordable with seed funding? |

**Elimination rules:** Below 3 on any weight-5 criterion = eliminated. Token governance = eliminated. Advisory-only teen role = deprioritized.

**Likely trajectory (not a decision):** Multi-entity + protocol-level teen governance in Switzerland scores highest. Pure foundation simpler for years 1-3. No-entity eliminated by teen governance requirement. Cooperative eliminated by minor membership constraints. DAO eliminated by legal immaturity. Real question: Swiss foundation now, commercial entity later.

---

Sources:
- [Signal Foundation](https://en.wikipedia.org/wiki/Signal_Foundation)
- [Minors on Nonprofit Boards](https://nonprofitlawblog.com/youth-board-members-can-minors-serve-on-a-nonprofit-board/)
- [Youth Board Law](https://nonprofitquarterly.org/young-people-on-nonprofit-boards-good-idea-but-know-the-law/)
- [Swiss Foundation Guide](https://foundation-switzerland.com/swiss-foundation-complete-guide/)
- [Swiss Foundation Cost](https://foundation-switzerland.com/swiss-foundation-cost-fees-capital-requirements/)
- [Wyoming DAO LLC](https://www.legalnodes.com/article/wyoming-dao-llc)
- [Wyoming DUNA Guide](https://astraea.law/insights/dao-llc-formation-wyoming-duna-guide-2025)
- [DAOs in Switzerland](https://vectra-advisors.com/understanding-daos-and-legal-wrappers-in-switzerland/)
- [Free Our Feeds (TechCrunch)](https://techcrunch.com/2025/01/13/free-our-feeds-campaign-aims-to-billionaire-proof-blueskys-tech/)
- [Protect the AT Protocol (MIT Tech Review)](https://www.technologyreview.com/2025/01/17/1110063/we-need-to-protect-the-protocol-that-runs-bluesky/)
- [Linux Foundation 2025 Report](https://www.linuxfoundation.org/resources/publications/linux-foundation-annual-report-2025)
- [Open Source Foundations Study](https://livablesoftware.com/study-open-source-foundations/)
- [Best DAO Jurisdictions](https://lawrange.net/en/where-to-open-a-dao-company/)
