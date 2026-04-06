# Economics of Attention, Digital Externalities & Alternative Currencies

## Field Overview

Attention economics, rooted in Herbert Simon's 1971 observation that "a wealth of information creates a poverty of attention," treats human attention as the binding scarce resource in information-rich environments. The field intersects with ecological economics (carbon externalities of digital infrastructure), mechanism design (how to price what markets currently ignore), and behavioral economics (how micro-costs reshape human choice in nonlinear ways). The central design question for Mrki is whether digital communication externalities — attention cost, cognitive load, bandwidth, carbon — can be made visible and priced without creating inequality or silencing the people most worth hearing.

## Key Thinkers and Positions

**Herbert Simon** (1971) established the foundational insight: information consumes the attention of its recipients, therefore an abundance of information creates a poverty of attention. This reframes the problem: the scarce resource isn't content, it's the capacity to process it. Every public post on a social platform is an implicit request for collective attention — a withdrawal from a shared commons.

**Tim Wu** (*The Attention Merchants*, 2016; ["Blind Spot: The Attention Economy and the Law"](https://scholarship.law.columbia.edu/faculty_scholarship/2029/)) traces how attention was industrialized — first by newspapers, then radio, TV, and finally platforms. Wu identifies "attention brokers" (Facebook, Google) who extract attention and resell it to advertisers. His key insight for Mrki: the attention economy is not inevitable; it was constructed through specific business model choices, and can be un-constructed through different ones.

**Jaron Lanier** (*Who Owns the Future?*, 2013) argues that the digital economy systematically destroys middle-class value by making information free while concentrating wealth in "siren servers." His proposed remedy — [micropayments for data and creative contributions](https://www.niemanlab.org/2013/05/jaron-lanier-wants-to-build-a-new-middle-class-on-micropayments/) — directly prefigures Mrki's "gratitude stamps." However, Lanier's framing is economic (pay people for data), while Mrki's is social (make the cost of attention visible). These are different mechanisms with different failure modes. Lanier and Glen Weyl later refined this into ["data dignity"](https://eliassi.org/lanier_and_weyl_hbr2018.pdf) — the idea that people should have economic rights over information derived from their lives.

**Yochai Benkler** (*The Wealth of Networks*, 2006) provides the counterpoint: commons-based peer production works precisely because it avoids pricing. Wikipedia, Linux, and open-source culture thrive on gift economics. Introducing micro-costs risks converting social motivation into market motivation — which behavioral economics shows can backfire catastrophically (Gneezy & Rustichini's daycare study: fining parents for late pickup *increased* lateness by converting a social obligation into a market transaction).

**Cory Doctorow** coined ["enshittification"](https://en.wikipedia.org/wiki/Enshittification) (2022) to describe the lifecycle of platforms: first good to users, then exploitative of users to serve business customers, then exploitative of everyone to extract maximum value. The mechanism is structural — platforms degrade because switching costs trap users and shareholders demand growth. Doctorow's prescription (mandated interoperability, competition, regulation) is about structural discipline, not pricing. For Mrki, the lesson is: any internal currency can itself become a vector for enshittification if the platform controls the mint.

**Dan Ariely** (["Zero as a Special Price"](https://web.mit.edu/ariely/www/MIT/Papers/zero.pdf), 2007) demonstrated the **zero-price effect**: reducing a price from 1 cent to free produces a dramatically larger behavioral shift than reducing from 2 cents to 1 cent. Free is not just a low price — it triggers a qualitatively different psychological response, activating social norms instead of market norms. This is the most important empirical finding for Mrki's postage system: *any* non-zero cost for posting, no matter how small, shifts the interaction from "social gift" to "market transaction." The question is whether this shift is desirable (it reduces spam and encourages thoughtfulness) or destructive (it commodifies self-expression).

**Kate Raworth** (*Doughnut Economics*, 2017) and **E.F. Schumacher** (*Small is Beautiful*, 1973) contribute the ecological economics frame: economic activity has both a social floor (below which people lack what they need) and an ecological ceiling (above which planetary systems break). A postage system must operate within this doughnut — costly enough to make externalities visible, cheap enough not to exclude anyone.

## What Works (Evidence-Based)

**MetaFilter's $5 fee.** Since 2004, MetaFilter has charged a [one-time $5 fee for new accounts](https://www.managingcommunities.com/2014/10/16/online-community-metafilter-charges-5-for-new-accounts/). Research on MetaFilter's "[deliberate barriers to participation](https://digitalcommons.unomaha.edu/cgi/viewcontent.cgi?httpsredir=1&article=1063&context=compscifacpub)" found that the fee successfully discouraged drive-by trolls and spammers while not deterring committed participants. The community maintained remarkably high discussion quality for two decades. Recently, the [$5 barrier has been noted as an accidental AI-bot repellent](https://www.metafilter.com/212690/The-5-paywall-was-accidentally-the-greatest-AI-repellent-ever-invented). Key distinction: MetaFilter's fee is an *entry* cost (one-time, to join), not a *per-action* cost. Entry costs select for commitment; per-action costs shape ongoing behavior. These are different mechanisms.

**Hashcash and proof-of-work anti-spam.** Proposed by Adam Back in 1997, [Hashcash](https://en.wikipedia.org/wiki/Hashcash) required senders to perform a computational proof-of-work before sending email — a "postage" paid in CPU cycles rather than money. The concept, originating from [Dwork and Naor's 1992 paper](https://en.wikipedia.org/wiki/Cost-based_anti-spam_systems) "Pricing via Processing," was elegant: it imposed negligible cost on individual senders but prohibitive cost on mass spammers. It largely failed in practice — not because the mechanism was wrong, but because (a) email clients never adopted it universally, (b) botnets made computational cost cheap for spammers, and (c) the coordination problem was unsolvable without a central authority. Bitcoin later repurposed the same proof-of-work concept for a different problem. The lesson: postage works against spam *only if everyone participates*; partial adoption creates a two-tier system.

**Hubski's sharing model.** [Hubski](https://en.wikipedia.org/wiki/Hubski) (founded 2010) implemented a user-following model where posts propagate through shares rather than algorithmic feeds. Votes are weighted by user authority. This is a non-monetary attention-pricing system: your reach is earned through the quality of your past sharing, not purchased. It produces good discussion quality but limits growth — the mechanism selects for a specific type of engaged, thoughtful user while remaining obscure to the mainstream.

## What Fails (Cautionary)

**Email postage proposals.** Multiple proposals in the 2000s (including [Microsoft's "penny stamp" concept backed by Bill Gates](https://www.technologyreview.com/2004/03/26/274898/a-better-way-to-squelch-spam/)) attempted to add monetary postage to email. All failed. The reasons are instructive: (1) they required universal adoption to work, (2) they disadvantaged legitimate bulk senders (nonprofits, mailing lists) along with spammers, (3) they created equity concerns — even tiny costs disproportionately burden users in low-income countries, and (4) the coordination problem between competing email providers was unsolvable. Mrki avoids some of these by being a closed platform (universal adoption is guaranteed within the system), but the equity concern remains.

**Commodifying social norms.** Ariely and Heyman (2004) showed that people exert *higher* effort under social contracts (no money involved) than when small monetary amounts are introduced. Once you frame an interaction in market terms, social motivation evaporates and doesn't return even if you remove the price. This is the deepest risk for Mrki: gratitude stamps are framed as social ("gratitude") but function as economic (they're scarce, rationed, and spent). If users perceive them as currency rather than ritual, the social frame collapses.

**Carbon labeling fatigue.** Research on making [digital carbon footprints visible](https://www.nature.com/articles/s41467-024-47621-w) shows a tension: awareness matters, but individual action framing creates guilt without agency. A single text post emits roughly [0.014 grams of CO2](https://www.cloudzero.com/blog/tech-carbon-footprint/) — essentially nothing. Framing this as meaningful environmental action is misleading. The honest version: media-heavy posts (images, video) have genuine bandwidth and storage costs; text posts don't. Weight-based pricing is defensible on attention-externality grounds but dishonest on carbon grounds for text.

## Live Dialectics

**Micropayments (Lanier) vs. commons (Benkler).** Lanier wants to price everything to create fair markets; Benkler shows that pricing can destroy the intrinsic motivation that makes commons work. The resolution isn't choosing one — it's recognizing that *different activities* belong in different frames. DMs are gifts (commons frame). Public posts request collective attention (market frame). Mrki's free-DMs-but-paid-public-posts may actually be the right split.

**Visible externalities vs. anxiety/guilt.** Making costs visible can produce informed choice (Thaler's "libertarian paternalism") or paralysis and guilt. Carbon labels on food had [modest behavioral effects](https://www.carbonmark.com/post/the-carbon-footprint-of-digital-products-and-how-to-act-on-it) and risked shifting blame from systems to individuals. For teens especially, visible cost systems risk making self-expression feel burdensome.

**Postage as equalizer vs. postage as barrier.** Email postage proposals consistently foundered on equity. A flat cost per post is regressive — it's the same absolute cost but a higher relative cost for those with fewer stamps. If gratitude stamps are earned through engagement, then quiet users or newcomers face a cold-start problem; if distributed equally, prolific users are rationed.

## Paradigm Challengers

**Nick Couldry** argues that "data dignity" (Lanier's framework) misidentifies the problem. The harm isn't that people aren't paid for their data — it's that datafication itself colonizes social life. Paying people for data normalizes the extraction. Applied to Mrki: pricing attention in stamps may normalize the idea that all communication has a transactional cost, which is itself corrosive to the social fabric you're trying to build.

**Vitalik Buterin** has explored mechanism design for digital commons — quadratic voting, quadratic funding, Harberger taxes. These mechanisms attempt to reveal true preferences while preventing plutocracy. Quadratic pricing (cost increases with the square of quantity) is particularly relevant: your first post is cheap, your tenth is expensive. This naturally limits flooding without silencing anyone entirely.

**Doctorow's structural critique** challenges whether *any* internal currency system is safe from enshittification. If the platform controls stamp issuance, it controls the economy. Today stamps are generous; tomorrow, when growth targets demand it, they could be scarce. The only defense is making the currency system itself transparent, auditable, and ideally governed by users rather than the platform.

## Design Principles for Mrki

1. **Separate entry costs from per-action costs.** MetaFilter's success was an entry barrier (one-time, selecting for commitment). Per-action postage is a different and riskier mechanism — use it sparingly and for the right reasons.

2. **Frame stamps as ritual, not currency.** The "gratitude" framing is powerful but fragile. If stamps are ever tradeable, accumulable, or displayed as status, the social frame collapses into a market frame. Keep them non-fungible, non-displayable, and tied to the act of posting rather than the act of earning.

3. **Use quadratic pricing, not flat pricing.** Charge near-zero for the first few daily posts, escalating for each additional one. This limits flooding without silencing anyone. The verbose kid pays more per-post on the margin, but their first several posts are essentially free.

4. **Be honest about carbon.** Text posts have negligible carbon footprint. Don't pretend otherwise. Instead, frame weight-based costs honestly: heavy media costs more because it demands more collective attention, storage, and bandwidth — not because of carbon.

5. **Universal basic stamps.** Every user gets enough daily stamps to participate meaningfully. Additional stamps are earned through receiving gratitude, not through payment. This preserves the social commons while making excessive posting costly on the margin.

6. **Keep the mint transparent.** If the platform controls stamp issuance, publish the algorithm. Better yet, make issuance rules governable by the community. The moment stamp economics become opaque, Doctorow's enshittification dynamic activates.

7. **Protect the free-DM / paid-public split.** This maps well onto the commons/market distinction. Private conversation is gift exchange; public posting is a claim on collective attention. Different norms, different costs.

## Critical Tensions

**Gratitude stamps may punish the most communicative kids.** Neurodiverse users, extroverted teens, those processing difficult experiences through writing — these users post more. A per-post cost system systematically taxes them. Quadratic pricing mitigates but doesn't eliminate this. The fundamental question: is prolific posting an externality to be discouraged, or a form of participation to be celebrated?

**The zero-price boundary is a one-way door.** Ariely's research shows that introducing any cost shifts the frame from social to market — and removing the cost later doesn't restore the social frame. If Mrki launches with postage and it damages the community, removing it won't undo the damage. This argues for launching with very generous stamp allocations and tightening only if clear evidence of externalities emerges.

**Free DMs and paid public posts may discourage public contribution.** If posting publicly has a cost but messaging privately doesn't, rational users migrate to DMs, group chats, and private channels. The public commons hollows out. This is already the dominant pattern on Discord and WhatsApp — vibrant private groups, dead public squares. The postage system must not accelerate this drift.

**Who gets priced out?** Even in a closed ecosystem with no real money, stamp scarcity creates winners and losers. Users who receive lots of gratitude get more stamps; users who don't receive gratitude post less; a Matthew Effect emerges. The system must have strong redistributive mechanics (universal daily allocation, caps on accumulation) or it reproduces the inequality it claims to oppose.

## Blindspots

**Cultural variation in communication norms.** All the research cited here is from Western, English-speaking contexts. Communication norms vary dramatically across cultures — what counts as "too much" posting, appropriate expression of gratitude, comfort with transactional framing. Mrki's European launch context (Croatia, EU) may interact differently with postage mechanics than US-centric research predicts.

**Age-specific behavioral economics.** Most behavioral economics research uses adult subjects. Teens have different relationships with scarcity, cost, social norms, and fairness. The zero-price effect may be stronger or weaker for 13-year-olds. We don't know. This is a genuine research gap.

**Accessibility and disability.** Weight-based posting costs (heavier media costs more) may inadvertently penalize users who communicate primarily through voice notes, images, or video — which includes many users with learning disabilities or those who find text-based communication difficult.

**The "postage" metaphor itself.** Postal systems historically were instruments of state power and surveillance. Letters were opened, censored, taxed by authorities. The metaphor carries connotations of control that may undermine Mrki's self-governance ethos if users perceive stamps as the platform monitoring and taxing their speech.

Sources:
- [Cost-based anti-spam systems - Wikipedia](https://en.wikipedia.org/wiki/Cost-based_anti-spam_systems)
- [Hashcash - Wikipedia](https://en.wikipedia.org/wiki/Hashcash)
- [A Better Way To Squelch Spam? - MIT Technology Review](https://www.technologyreview.com/2004/03/26/274898/a-better-way-to-squelch-spam/)
- [Attention economy - Wikipedia](https://en.wikipedia.org/wiki/Attention_economy)
- [Tim Wu - "Blind Spot: The Attention Economy and the Law"](https://scholarship.law.columbia.edu/faculty_scholarship/2029/)
- [Rethinking the cognitive foundations of the attention economy](https://www.tandfonline.com/doi/full/10.1080/09515089.2025.2502428)
- [MetaFilter charges $5 for new accounts](https://www.managingcommunities.com/2014/10/16/online-community-metafilter-charges-5-for-new-accounts/)
- [Deliberate Barriers to User Participation on MetaFilter](https://digitalcommons.unomaha.edu/cgi/viewcontent.cgi?httpsredir=1&article=1063&context=compscifacpub)
- [The $5 paywall as AI-repellent - MetaFilter](https://www.metafilter.com/212690/The-5-paywall-was-accidentally-the-greatest-AI-repellent-ever-invented)
- [Jaron Lanier wants to build a new middle class on micropayments](https://www.niemanlab.org/2013/05/jaron-lanier-wants-to-build-a-new-middle-class-on-micropayments/)
- [Lanier & Weyl - A Blueprint for a Better Digital Society (HBR)](https://eliassi.org/lanier_and_weyl_hbr2018.pdf)
- [Should We Treat Data as Labor? - AEA](https://www.aeaweb.org/articles?id=10.1257/pandp.20181003)
- [Enshittification - Wikipedia](https://en.wikipedia.org/wiki/Enshittification)
- [Doctorow - Big Tech's "attention rents"](https://doctorow.medium.com/big-techs-attention-rents-fe97ba3fad90)
- [Ariely - Zero as a Special Price (PDF)](https://web.mit.edu/ariely/www/MIT/Papers/zero.pdf)
- [Zero Price Effect - The Decision Lab](https://thedecisionlab.com/reference-guide/psychology/zero-price-effect)
- [The environmental sustainability of digital content consumption - Nature](https://www.nature.com/articles/s41467-024-47621-w)
- [Tech Carbon Footprint - CloudZero](https://www.cloudzero.com/blog/tech-carbon-footprint/)
- [Carbon Footprint of Social Media Platforms - MDPI](https://www.mdpi.com/2071-1050/14/4/2195)
- [Hubski - Wikipedia](https://en.wikipedia.org/wiki/Hubski)
- [The Psychology of Free - St. Louis Fed](https://www.stlouisfed.org/publications/page-one-economics/2025/apr/psychology-of-free-how-price-of-zero-influences-decisionmaking)
