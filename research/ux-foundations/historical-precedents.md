# Domain 7: Historical Precedents -- What Worked, What Died, What Degraded

## Field Overview

The history of online communities is a thirty-year experiment in how social spaces form, thrive, and decay. Internet historians (Fred Turner, Kevin Driscoll, Katie Hafner), platform critics (Cory Doctorow, Tim Wu), and community scholars (Amy Jo Kim, Clay Shirky) have documented a recurring arc: small communities built around shared purpose attract devoted users, grow through network effects, face pressure to monetize, and either resist that pressure (surviving small) or succumb to it (growing large, then degrading). The central theoretical contribution of the last decade is Doctorow's *enshittification* framework, which names the three-stage mechanism: platforms first attract users with quality, then exploit users to serve business customers, then exploit everyone to extract maximum shareholder value. But enshittification is not fate -- several communities have resisted it for decades, and their structural properties are instructive.

## Key Cases and What They Teach

**Early Facebook (2004-2009).** Facebook launched as TheFacebook at Harvard in 2004, limited to .edu addresses. Its college-exclusive design created natural identity verification and shared context. By June 2004, 250,000 students across 34 schools had joined. The critical inflection came in September 2006 when registration opened to anyone over 13. Early users reported it was "losing its exclusivity, losing what made it special." The News Feed (2006) shifted the platform from profile-driven self-expression to passive consumption. The Like button (2009) introduced quantified social approval. Beacon (2007) -- which automatically shared user activity from partner sites -- was an early enshittification move so blatant it was shut down within two years. *Lesson: gatekeeping and shared context create quality; removing gates and adding engagement metrics degrades it.*

**LiveJournal.** Founded 1999, LiveJournal pioneered long-form personal blogging with community features (friends lists, comment threads, interest-based groups). It thrived as a space for fan communities, LGBTQ+ writers, and personal diarists. Sold to Six Apart in 2005, licensed to Russian company SUP Media in 2006, fully sold to SUP in 2007. Nearly 500 blogs were immediately banned. The 2016 server relocation to Russia and 2017 terms-of-service change to comply with Russian law (including anti-LGBTQ+ "gay propaganda" restrictions) triggered a mass exodus. *Lesson: ownership structure determines community fate; a community built on trust can be destroyed overnight by an ownership change that violates that trust.*

**Flickr (pre-Yahoo).** Launched 2004 by Ludicorp as a photo-sharing community for serious amateur photographers. Its "interestingness" algorithm surfaced quality based on engagement patterns rather than recency alone -- an early example of algorithmic curation that served users rather than advertisers. Yahoo acquired it in 2005 for $22-35 million. Initial years were strong, but Yahoo drained Flickr's engineering team, launched a mobile app in late 2009 that stripped out core features (no interestingness, no EXIF data, 600px max), and failed to compete with Instagram's mobile-first approach. Founders left in 2008. *Lesson: a good algorithm can serve a community, but corporate neglect kills faster than corporate exploitation.*

**MetaFilter.** Founded 1999 by Matt Haughey. Introduced a $5 lifetime membership fee in 2004 -- not for revenue but as a deliberate friction barrier. Haughey: "I want it to be like a coffee, like an expensive coffee price." The fee worked: it kept spammers and trolls out while being low enough not to exclude serious participants. Peak was ~8,100 monthly active users in 2011; currently ~2,900. In 2022, ownership transferred to Jessamyn West; in 2024, the site began transitioning to a non-profit community foundation. *Lesson: small friction produces outsized quality filtering; sustainable communities can be small; non-profit governance protects mission.*

**The WELL (1985-present).** Founded by Stewart Brand and Larry Brilliant as the Whole Earth 'Lectronic Link. Its founding principle -- "You Own Your Own Words" (YOYOW) -- established both copyright ownership and personal responsibility in a single phrase. Combined with a no-anonymity policy, this created accountability. The community attracted "a highly creative, iconoclastic group" through selective invitation of hosts -- artists, intellectuals, journalists -- creating what was compared to a "Parisian salon." Still operating after 40 years. *Lesson: identity accountability plus intellectual curation creates durable culture; a clear founding ethic acts as a constitution.*

**Scuttlebutt (SSB).** Created 2014 by Dominic Tarr while living on a sailboat with unreliable internet. Each account is a cryptographic keypair with an append-only log stored locally. Users only download feeds from people they follow (and optionally friends-of-friends), which architecturally prevents spam and harassment. Data syncs over LAN, Bluetooth, or sneakernet. No central server, no corporate entity to enshittify. *Lesson: architectural decisions can make enshittification structurally impossible; offline-first design produces resilience and intentionality. Directly relevant to Mrki's distributed design.*

**Are.na.** A 14-year-old platform built around "blocks" (content) and "channels" (collections). No personalized algorithms, no ads, paid model. Attracts "connected knowledge collectors" -- researchers, artists, designers. Functions as a communal file system rather than a social feed. *Lesson: building for a specific activity (collecting, connecting ideas) rather than generic "socializing" produces clearer purpose and more durable engagement.*

**Ravelry.** Launched 2007 for fiber arts (knitting, crochet). Nearly 9 million registered users, ~1 million monthly active. Volunteer moderators run distributed moderation across thousands of groups. 7,000 new projects and 80,000 favorites daily. Small core team, massive volunteer infrastructure. Users contribute patterns, translations, forum moderation, and wiki documentation. *Lesson: passion-centered communities generate free labor willingly; distributed volunteer moderation scales where paid moderation does not; giving users ownership of community infrastructure creates loyalty.*

**Craigslist.** Craig Newmark turned down billions in acquisition offers. Minimal monetization -- small fees on select categories specifically to prevent spam (e.g., charging apartment brokers to prevent posting the same ad repeatedly). Near-zero design changes since the 1990s. Newmark: "Do something simple and useful." *Lesson: refusing to optimize for growth is itself a design choice that preserves quality; "enough is enough" as an operating philosophy.*

## Patterns of Success (What Long-Lived Communities Share)

1. **Friction as filter.** MetaFilter's $5 fee, The WELL's real-name policy, Facebook's original .edu requirement, guild apprenticeships -- every durable community has a barrier that costs something (money, time, identity exposure, skill demonstration).

2. **Clear founding ethic.** YOYOW, Ravelry's craft-first identity, Craigslist's radical simplicity. A community needs a "constitution" that members can internalize and enforce laterally.

3. **Distributed governance.** Ravelry's volunteer moderators, kibbutzim's rotating roles, BBS sysop autonomy, guild self-regulation. Communities that rely on a single authority figure are fragile; communities that distribute moderation and governance are resilient.

4. **Ownership aligned with mission.** MetaFilter's transition to a non-profit foundation, Craigslist's refusal to sell, The WELL's longevity under stewardship-minded owners. When ownership is extractive, community is a resource to mine.

5. **Specific purpose over general socializing.** Ravelry (fiber arts), Are.na (knowledge collecting), Flickr (photography), guilds (craft mastery). Purpose creates norms; generality creates anomie.

6. **Small or bounded scale.** MetaFilter peaked at 8,100 MAU. The WELL remains intentionally small. Cohousing communities cap at ~30 households. Human-scale communities can self-regulate; city-scale communities require surveillance.

## Patterns of Failure (What Kills Communities)

1. **The enshittification cycle.** Doctorow's three stages: serve users, exploit users for business customers, exploit everyone for shareholders. Requires: two-sided market position, removal of competitive/regulatory discipline, lock-in. Structurally, it is enabled by centralized control of value allocation.

2. **Eternal September.** When gatekeeping collapses, newcomers overwhelm norms faster than they can be transmitted. AOL's 1993 Usenet access is the canonical case. The existing community is "crushed under the sheer number of new users" who aren't socialized into existing norms.

3. **Ownership transfer to misaligned parties.** LiveJournal to SUP Media. Flickr to Yahoo. The community's values become subordinate to the owner's incentives.

4. **Metric capture.** Facebook's Like button, engagement-optimized feeds. When a community optimizes for measurable engagement rather than unmeasurable quality, Goodhart's Law applies: the metric becomes the target and ceases to be a good metric.

5. **Mobile neglect or misadaptation.** Flickr lost to Instagram by launching a crippled mobile app three years late. Platform transitions are existential moments.

## Live Dialectics

- **Growth vs. quality.** Every successful community faces the question: do we grow or do we preserve? There is no stable equilibrium -- the choice must be actively managed through friction, caps, or segmentation.
- **Openness vs. gatekeeping.** Eternal September shows the cost of total openness; but excessive gatekeeping produces insularity and elitism. MetaFilter's $5 is an elegant middle path.
- **Algorithmic curation vs. chronological feeds.** Flickr's "interestingness" showed algorithms can serve communities; Facebook's News Feed showed they can destroy them. The difference is who the algorithm serves.
- **Anonymity vs. accountability.** The WELL's real-name policy created quality discourse but excluded people who need anonymity for safety. Pseudonymity (stable identity without real-name exposure) may be the synthesis.

## Paradigm Challengers

Scuttlebutt challenges the assumption that social networks need servers. Are.na challenges the assumption that social platforms need algorithms or ad revenue. Craigslist challenges the assumption that platforms must optimize and grow. MetaFilter challenges the assumption that free access is required for scale. Ravelry challenges the assumption that volunteer moderation cannot scale. Collectively, they demonstrate that the dominant model (centralized, ad-funded, growth-obsessed, algorithmically-sorted) is a choice, not an inevitability.

## Design Principles for Mrki

1. **Build enshittification resistance into architecture, not policy.** Like Scuttlebutt, Mrki's distributed protocol makes value extraction structurally difficult. This is stronger than any policy commitment.
2. **Friction is a feature.** The postage system and postal pacing are direct descendants of MetaFilter's $5 fee and The WELL's real-name requirement. Frame them as quality filters, not barriers.
3. **Distribute governance early.** Ravelry's volunteer moderation and kibbutzim's rotating roles show that distributed governance scales. Mrki's rotating governance roles should be treated as load-bearing architecture, not decoration.
4. **Protect against ownership capture.** LiveJournal's destruction by SUP Media is the clearest cautionary tale. Open-source licensing and community foundation structures (as MetaFilter is now pursuing) provide protection.
5. **Optimize for purpose, not engagement.** Are.na and Ravelry thrive because they serve specific activities. Mrki should resist becoming a generic social feed and instead center on activities teens actually value.
6. **Plan for Eternal September.** Growth will test norms. Design onboarding that transmits culture (guild apprenticeship model), and consider graduated access (earn posting privileges through participation).
7. **Make the founding ethic legible.** The WELL's YOYOW survived 40 years because it was short, memorable, and enforceable. Mrki needs an equivalent constitutional phrase.

## Critical Tensions

- **Teen accessibility vs. quality friction.** Teens have less money and less patience for barriers. A $5 fee or complex onboarding could exclude the very population Mrki serves. The friction must be non-monetary (time, effort, social vouching) rather than financial.
- **Distributed architecture vs. safety obligations.** Scuttlebutt's design makes censorship impossible -- but it also makes removing CSAM or harassment content impossible. Mrki must solve the moderation problem that pure decentralization punts on.
- **Nostalgia bias.** Much "what worked" discourse romanticizes early internet communities that were small, white, male, educated, and English-speaking. The WELL's "Parisian salon" was exclusive in ways that aren't acceptable models for a teen platform serving diverse populations.
- **Survivorship bias.** We study MetaFilter and The WELL because they survived. Thousands of BBS systems, IRC channels, and small forums also had friction, purpose, and good norms -- and died anyway due to technical obsolescence, operator burnout, or simple bad luck.

## Blindspots

- **Non-English community histories.** Nearly all documented cases are from the Anglophone internet. Japanese (2channel/5channel, Mixi), Korean (Cyworld), Chinese (early Weibo communities), and Latin American (Orkut in Brazil) community histories offer different structural lessons that this analysis does not cover.
- **Communities that died silently.** The historical record privileges communities that were written about, typically by journalists and academics in San Francisco and New York. Rural BBS cultures, teen-specific forums (Neopets communities, Habbo Hotel governance), and non-elite communities are understudied.
- **The role of moderation labor.** Ravelry's volunteer moderators are celebrated, but volunteer moderation is also unpaid emotional labor that burns people out. The sustainability of distributed moderation over decades is less proven than it appears.
- **Economic sustainability.** MetaFilter's $5 fee and Craigslist's minimal monetization work at small scale. Whether mission-aligned economic models can sustain a platform serving millions of teens (with associated legal, safety, and infrastructure costs) is an open question.
- **The "just be small" fallacy.** Several success stories here survived by staying small. But Mrki aspires to serve teens broadly, which means confronting scale problems that MetaFilter and The WELL never had to face.

---

Sources:
- [Enshittification - Wikipedia](https://en.wikipedia.org/wiki/Enshittification)
- [Doctorow's McLuhan Lecture on Enshittification](https://doctorow.medium.com/my-mcluhan-lecture-on-enshittification-ea343342b9bc)
- [MetaFilter - Wikipedia](https://en.wikipedia.org/wiki/MetaFilter)
- [MetaFilter's $5 Fee Discussion - Tildes](https://tildes.net/~tech/1m2a/does_metafilters_5_entry_fee_succeed_in_enforcing_good_behaviour_also_metafilter_is_small)
- [The Once and Future MetaFilter](https://mssv.net/2019/07/11/the-once-and-future-metafilter/)
- [The WELL - YOYOW](https://www.well.com/articles/community-guidelines/yoyow/)
- [The WELL - Britannica](https://www.britannica.com/topic/The-WELL-Internet-community)
- [History of Facebook - Wikipedia](https://en.wikipedia.org/wiki/History_of_Facebook)
- [Facebook's First Users Look Back - Harvard Crimson](https://www.thecrimson.com/article/2014/2/4/facebook-ten-years-feature-1/)
- [Secure Scuttlebutt - Wikipedia](https://en.wikipedia.org/wiki/Secure_Scuttlebutt)
- [Scuttlebutt Protocol Guide](https://ssbc.github.io/scuttlebutt-protocol-guide/)
- [Eternal September - Wikipedia](https://en.wikipedia.org/wiki/Eternal_September)
- [Whatever Happened to LiveJournal - History of the Web](https://thehistoryoftheweb.com/postscript/whatever-happened-livejournal/)
- [How Yahoo Killed Flickr - Gizmodo](https://gizmodo.com/how-yahoo-killed-flickr-and-lost-the-internet-5910223)
- [Flickr Turns 10 - Time](https://time.com/6855/flickr-turns-10-the-rise-fall-and-revival-of-a-photo-sharing-community/)
- [Ravelry - Wikipedia](https://en.wikipedia.org/wiki/Ravelry)
- [Craigslist: Doing Well by Doing Good vs Enshittification - Craig Newmark](https://www.linkedin.com/pulse/craigslist-doing-well-good-vs-enshittification-craig-newmark)
- [The Case for "Bad" Design - The Ringer](https://www.theringer.com/2017/05/04/tech/craigslist-case-for-bad-design-silicon-valley-67e9e933764e)
- [Guilds in Medieval Europe - Wikipedia](https://en.wikipedia.org/wiki/Guilds_in_medieval_Europe)
- [BBS Distributed Moderation - Kevin Driscoll](https://ahc-ch.ch/wp-ahc21/wp-content/uploads/21-1-Driscoll.pdf)
- [Are.na - Dazed](https://www.dazeddigital.com/life-culture/article/69298/1/5-social-media-platforms-actually-social-perfectly-imperfect-cosmos)
- [Cohousing and Kibbutzim - Cohousing Association](https://www.cohousing.org/mission-driven-communities-in-israel-a-model-for-the-united-states/)
