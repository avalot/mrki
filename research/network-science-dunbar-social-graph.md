# Domain 6: Network Science, Dunbar Numbers & Social Graph Health

## Field Overview

Network science studies how the structure of connections between people shapes what flows through them: information, norms, emotions, disease, opportunity. The field converges from graph theory (mathematics), statistical mechanics (physics), and social structure (sociology). Its central insight for platform design is that **topology is destiny**---the shape of a network determines its behavior more than the intentions of any individual node. For a teen platform rejecting algorithmic amplification, this is the foundational science: if you get the graph structure right, healthy dynamics emerge without needing to police content at scale.

## Key Thinkers and Positions

**Robin Dunbar** established empirically that human cognitive architecture limits meaningful social relationships to approximately 150 (confirmed across 23 studies, median sample 5,457, largest 61 million individuals, spanning 2,000 years of cultures). These relationships organize into nested layers following a scaling ratio of roughly 3: **1.5** (intimate partner), **5** (support clique---people you'd turn to in devastating crisis), **15** (sympathy group---close friends who get most of your spare time), **50** (the birthday-party circle), **150** (casual friendships), **500** (acquaintances), **1,500** (faces you recognize). A 2025 PLOS ONE study revealed significant individual variation in how people allocate social energy across these layers, but the layered structure itself is remarkably stable. Dunbar's 2024 retrospective ("The Social Brain Hypothesis---Thirty Years On") reaffirmed the core finding.

**Albert-Laszlo Barabasi** demonstrated that most real-world networks are *scale-free*: a few hubs accumulate disproportionate connections through preferential attachment (new nodes connect to already-popular nodes). This "rich-get-richer" dynamic produces the power-law degree distributions seen on Twitter, Instagram, and YouTube. Scale-free networks are efficient for information spread but structurally generate inequality, celebrity concentration, and single points of failure.

**Mark Granovetter** showed in 1973 that *weak ties*---casual acquaintances---are disproportionately important for accessing novel information and opportunity. A massive 2022 LinkedIn experiment (20 million people, 5 years, 600,000 jobs) provided causal confirmation but with a critical refinement: the relationship is an inverted U. Moderately weak ties are optimal; the very weakest ties contribute little. This has direct implications for how a platform surfaces content from outside a user's immediate circle.

**Nicholas Christakis and James Fowler** established that behaviors, emotions, and health outcomes spread through social networks up to "three degrees of influence"---your friend's friend's friend affects your likelihood of obesity, smoking cessation, and happiness. Their work on the National Longitudinal Study of Adolescent Health confirmed these effects operate among teens. However, their methodology has faced sustained statistical critique, and the causal mechanisms (contagion vs. homophily) remain debated.

**Zeynep Tufekci** showed that networked movements can scale rapidly but lack the *organizational capacity* built through slow, structured relationship-building. The Arab Spring organizers had years of small-group conferences and blogger meetups before their visible moment. She introduced "network internalities"---the internal development of ties that allows networks to act effectively, not just gather attention. She also warned that building community on private platforms is like holding a protest in a shopping mall: convenient but precarious.

**Eli Pariser** coined "filter bubble" (2011), arguing algorithmic curation traps users in ideological echo chambers. A decade of empirical testing has complicated this: most users encounter more diverse media diets online than offline. But a 2024 cross-national study found that ideology-based recommendation *does* reinforce selective exposure, and a study of American Twitter users found ~34% of cross-partisan interactions were toxic rather than constructive. The problem is less "bubbles" than *asymmetric amplification*---algorithms don't just filter, they amplify the most engaging (often most outrageous) content.

## What Works (Evidence-Based)

- **Respecting Dunbar layers.** Platforms that let users organically maintain ~5 close / ~15 regular / ~50 extended contacts produce higher satisfaction and lower anxiety than those pushing unlimited connection accumulation.
- **Weak-tie bridging at controlled doses.** The LinkedIn experiment shows moderate exposure to outside-circle content drives opportunity and novelty. The inverted-U shape means *some* bridging is essential but flooding users with stranger content is counterproductive.
- **Community survival through norms, not just moderation.** Research on Reddit's r/NoSleep surviving massive growth identified three factors: strong organized moderation, clear enforced rules, and cultural onboarding that taught newcomers the norms before they could disrupt them.
- **Small-world topology.** Networks with high local clustering (tight friend groups) plus a few long-range bridges combine the trust of strong ties with the information diversity of weak ones. This is the healthiest known topology for balancing community cohesion and openness.

## What Fails (Cautionary)

- **Scale-free dynamics (preferential attachment).** When platforms let popularity compound without friction, they produce celebrity hubs, attention inequality, and fragile networks where removing a few nodes collapses information flow. Every major social platform exhibits this pathology.
- **Eternal September.** Over 70% of online communities experience significant engagement decline within a year of rapid growth. AOL's 1993 Usenet invasion is the archetype, but it recurs whenever growth outpaces norm transmission. The lesson: *growth rate must not exceed socialization rate*.
- **Three-degree contagion of negative behaviors.** Christakis and Fowler's work implies that toxic behavior in a teen network doesn't stay local---it propagates outward through friend-of-friend chains. A single aggressive node can poison a surprisingly large radius.
- **Algorithmic amplification of outrage.** Even without explicit filter bubbles, recommendation systems systematically surface high-arousal content, degrading discourse quality. Removing algorithmic curation (as Mrki does) eliminates this failure mode entirely.

## Live Dialectics

**Dunbar limits vs. platform growth incentives.** Every commercial platform profits from maximizing connections (more edges = more data = more ad targeting). Dunbar's research says humans cannot meaningfully maintain more than ~150 relationships. Mrki's architecture should enforce this tension *structurally*---not by forbidding connections but by making the cognitive cost of maintaining them visible and felt.

**Weak ties vs. strong ties.** Weak ties bring diversity and opportunity; strong ties provide emotional support and trust. Optimizing for one degrades the other. Mrki's proximity-based local layer naturally favors strong ties; the Diverse Perspectives Engine and daily digest serve the weak-tie function. The design question is the ratio and pacing of each.

**Network effects as growth engine vs. quality degrader.** Network effects create value (more users = more content = more utility) but simultaneously degrade quality (more users = more noise = norm erosion). Mrki's postage system and pacing mechanisms are a structural answer: they make growth *costly enough* that norm transmission can keep pace.

**Chronological/human curation vs. algorithmic curation.** At small scale, chronological feeds work. At Dunbar-scale networks, they still work. The problem only emerges at scale-free platform sizes where no human can process the firehose. Mrki's architecture, by keeping active networks near Dunbar scale, may avoid ever needing algorithmic curation.

## Paradigm Challengers

- **The 2025 Dunbar energy-allocation study** challenges the assumption that Dunbar layers are uniform---people vary significantly in how they distribute social energy. Some invest heavily in the inner 5 and neglect the outer layers; others spread thin. Platform design should accommodate this variation rather than imposing one model.
- **Barabasi's own recent work** suggests some real networks are not truly scale-free but exhibit more complex degree distributions. The "scale-free" label may be overfit.
- **Tufekci's capacity argument** challenges the assumption that networks are inherently good for collective action. Without organizational capacity built through slow, structured work, networked groups are *fragile*---they can mobilize but not sustain.

## Design Principles for Mrki

1. **Enforce Dunbar-aware graph structure.** Don't cap connections at 150, but make the cognitive and postage costs of maintaining connections beyond ~50 naturally felt. Let the inner 5 and 15 be effortless; make the outer layers require intentional investment.
2. **Prevent preferential attachment.** Reputation is invisible; there are no follower counts, no public metrics. This structurally prevents scale-free hub formation. New content reaches people through proximity and circle membership, not popularity.
3. **Bridge weak ties through the daily digest.** The Diverse Perspectives Engine serves exactly the function Granovetter identified: surfacing novel information from outside the user's cluster. The daily-digest pacing prevents flooding and respects the inverted-U finding.
4. **Pace growth below socialization rate.** Proximity-based onboarding (Bluetooth/WiFi) means new users arrive through physical-world social contexts where norms are already present. This is a structural Eternal September vaccine.
5. **Leverage three-degree contagion positively.** If gratitude and constructive norms propagate through friend-of-friend chains (as Christakis/Fowler predict), then Mrki's "thank" currency and reputation system can seed positive contagion deliberately.
6. **Preserve small-world topology.** High local clustering (proximity-based groups) plus controlled long-range bridges (digest, cross-circle surfacing) = the optimal network structure for health.

## Critical Tensions

- **Privacy vs. network health monitoring.** Detecting toxic contagion or graph pathologies requires *seeing* the graph. But surveillance of social structure is itself a harm, especially for teens. Mrki's invisible reputation system navigates this but creates opacity concerns.
- **Individual variation in Dunbar allocation.** Some teens will want 3 close friends and nothing else; others will want 100 acquaintances. A one-size-fits-all network structure will fail someone.
- **Weak-tie surfacing vs. safety.** Exposing teens to outside-circle content is how diversity enters---but it is also how harassment, radicalization, and predatory contact enter. The Diverse Perspectives Engine must be *curated bridging*, not random exposure.

## Blindspots

- **Most network science research is on adults.** Teen social networks have distinct properties: more volatile, more status-sensitive, more influenced by school/neighborhood structure. Dunbar's numbers may apply differently to developing brains with different social-cognitive capacities.
- **Proximity bias.** Bluetooth/WiFi-based networks will mirror the segregation of physical space. If a teen's neighborhood is racially or economically homogeneous, their Mrki network will be too---without deliberate countermeasures, proximity replicates inequality.
- **The absence of algorithmic amplification is not neutrality.** Chronological feeds and proximity-based surfacing have their own biases: they favor the prolific, the local, and the already-present. "No algorithm" is itself a design choice with distributional consequences.
- **Cross-cultural variation.** Dunbar's layers were validated across cultures, but the *content* of those layers varies enormously. What counts as a "close friend" in collectivist vs. individualist cultures differs, and Mrki's Croatian origin context may not generalize.
- **Network science tells you about structure, not meaning.** Two networks can be topologically identical but one is a support group and the other is a bullying ring. Structure is necessary but not sufficient for health---norms, culture, and content matter independently.

---

Sources:
- [Dunbar's number - Wikipedia](https://en.wikipedia.org/wiki/Dunbar's_number)
- [The social brain hypothesis -- thirty years on (2024)](https://www.tandfonline.com/doi/full/10.1080/03014460.2024.2359920)
- [Reflecting on Dunbar's numbers: Individual differences in energy allocation (2025, PLOS ONE)](https://journals.plos.org/plosone/article/file?type=printable&id=10.1371/journal.pone.0319604)
- [Beyond Dunbar circles: continuous description of social relationships (Nature, 2022)](https://www.nature.com/articles/s41598-022-06066-1)
- [Barabasi-Albert model - Wikipedia](https://en.wikipedia.org/wiki/Barab%C3%A1si%E2%80%93Albert_model)
- [Scale-Free Networks: A Decade and Beyond (Barabasi)](https://www.barabasi.com/media/pub_imports/files/303.pdf)
- [The strength of weak ties (Stanford Report, 2023)](https://news.stanford.edu/stories/2023/07/strength-weak-ties)
- [A causal test of the strength of weak ties (Science, 2022)](https://www.science.org/doi/10.1126/science.abl4476)
- [Social contagion theory: Christakis & Fowler (PMC)](https://pmc.ncbi.nlm.nih.gov/articles/PMC3830455/)
- [Three degrees of influence - Wikipedia](https://en.wikipedia.org/wiki/Three_degrees_of_influence)
- [Twitter and Tear Gas - Tufekci](https://www.twitterandteargas.org/)
- [Tufekci on protest movements and capacity (Zuckerman)](https://ethanzuckerman.com/2013/10/17/zeynep-tufekci-on-protest-movements-and-capacity-problems/)
- [Filter bubble effects: evidence from Germany and U.S. (2024)](https://www.tandfonline.com/doi/full/10.1080/1369118X.2024.2435998)
- [Surviving an Eternal September (CHI 2016)](https://dl.acm.org/doi/10.1145/2858036.2858356)
- [Better When It Was Smaller? Community content after massive growth](https://www.researchgate.net/publication/320238164_Better_When_It_Was_Smaller_Community_Content_and_Behavior_After_Massive_Growth)
- [Proximity-Based Social Networking in Urban Environments (Springer, 2021)](https://link.springer.com/chapter/10.1007/978-3-030-71288-4_4)
- [Understanding Bluetooth for representing real-life social networks (PMC)](https://pmc.ncbi.nlm.nih.gov/articles/PMC7425281/)
