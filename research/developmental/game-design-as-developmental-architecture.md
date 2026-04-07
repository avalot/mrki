# Domain B: Game Design as Developmental Architecture

## Field Overview

Game design has spent decades solving a problem directly relevant to Mrki: how do you make progressive capability growth feel earned, exciting, and intrinsic rather than hollow and manipulative? The field divides sharply between **gamification** (bolting points, badges, and leaderboards onto existing activities) and **genuine progression design** (structuring environments so that growth is the experience itself). The former has largely failed. The latter produces systems people voluntarily spend thousands of hours in, building skills, communities, and identities.

The relevant bodies of knowledge span MMORPG design (World of Warcraft, FFXIV, EVE Online, Guild Wars 2), sandbox design (Minecraft), roguelike design (Hades, Celeste), flow psychology (Csikszentmihalyi), motivational frameworks (Deci & Ryan's Self-Determination Theory), and critical gamification studies (Deterding, Bogost).

## Key Thinkers and Frameworks

**Mihaly Csikszentmihalyi** -- Flow theory. The "flow channel" between boredom (skill exceeds challenge) and anxiety (challenge exceeds skill). Games maintain flow through dynamic difficulty, clear goals, and immediate feedback. Jenova Chen's MFA thesis (*Flow in Games*, 2006) formalized this for interactive design.

**Sebastian Deterding** -- Coined the academic definition of gamification ("use of game design elements in non-game contexts") then became its sharpest critic. His key distinction: gamification typically applies *game elements* (points, badges) without *game design* (meaningful choices, intrinsic challenge). His concept of "meaningful play" argues that engagement comes from the activity structure itself, not from rewards layered on top.

**Yu-kai Chou** -- Octalysis framework. Eight "Core Drives" of human motivation arranged on an octagon. Left-brain drives (logic, ownership, scarcity) are extrinsic; right-brain drives (creativity, social influence, unpredictability) are intrinsic. Top drives ("White Hat": meaning, accomplishment, empowerment) produce positive long-term engagement; bottom drives ("Black Hat": scarcity, avoidance, unpredictability) produce urgent but ultimately draining engagement. Critical insight: most corporate gamification uses only left-brain Black Hat drives (points you might lose, leaderboards that shame) -- the least sustainable quadrant.

**Jane McGonigal** -- *Reality Is Broken* (2011). Argued that games succeed because they provide what reality often lacks: clear goals, immediate feedback, voluntary participation, and a sense of epic meaning. Created SuperBetter, applying game structures to real health challenges. Her four defining traits of games: ultimate goal, rules, feedback system, voluntary participation.

**Deci & Ryan** -- Self-Determination Theory. Three innate psychological needs: autonomy, competence, and relatedness. Games that satisfy all three produce sustained intrinsic motivation. Games that substitute external rewards (badges, points) for these needs produce the "overjustification effect" -- extrinsic rewards crowd out intrinsic motivation.

## What Works

**Capability unlocking over point accumulation.** The most engaging progression systems give players *new things they can do*, not just higher numbers. In Zelda, a new item opens previously inaccessible areas. In FFXIV, completing the main story quest unlocks new jobs, dungeons, and systems. The reward is expanded possibility space, not a score. Each unlock meaningfully changes how you interact with the world.

**Multiple parallel progression paths.** WoW, FFXIV, and Guild Wars 2 all offer combat, crafting, social, exploration, and economic progression as distinct tracks. Players who dislike raiding can progress through crafting mastery or community leadership. EVE Online takes this furthest -- players can specialize as miners, traders, spies, diplomats, fleet commanders, or politicians. No single axis defines "success."

**Social progression through earned responsibility.** FFXIV's mentor system requires 1,000+ commendations and completion of extensive content before players can mentor newcomers (marked with a crown icon). This is not a badge -- it is access to a new communication channel (Novice Network) and a new duty roulette. The reward is the ability to help. WoW guilds organically develop raid leaders, officers, and class leads based on demonstrated competence, not appointment.

**EVE Online's Council of Stellar Management (CSM).** A player-elected body advising developers, running since 2008. Uses deliberative representative democracy. Ten elected members meet regularly with CCP developers. Provides genuine influence on game direction. Key lesson: governance structures work when they confer real power over real decisions, not advisory theater.

**Roguelike meta-progression and productive failure.** In Hades, each death unlocks new story, new weapons, new permanent upgrades. Failure is *literally the plot*. Research on "productive failure" (Kapur, 2008) shows that struggle before instruction produces deeper learning than instruction before practice. Roguelikes operationalize this: each run teaches patterns, and meta-progression ensures even "failed" runs advance the larger arc. The psychological key: failure must produce *information* and *narrative*, not just punishment.

**Minecraft's progression through mastery, not metrics.** No levels, no XP (beyond enchanting). Progression is learning to build more complex structures, mastering redstone logic, organizing multiplayer servers, creating collaborative builds. The progression is real -- you genuinely know more and can do more -- but it is never quantified by the game. Community recognition substitutes for system recognition.

## What Fails

**Badge-ification.** Foursquare is the canonical case. Initially, check-in badges and "mayorships" drove frantic engagement. Then novelty wore off. The badges were disconnected from any intrinsic value of the activity. Founders admitted the mechanics "started to break down" at scale. Enterprise gamification repeated this pattern: badges for logging in, completing compliance training, downloading PDFs. When the reward is disconnected from meaningful achievement, it actively undermines motivation through the overjustification effect.

**Points-and-leaderboards as sole motivators.** Leaderboards create a few winners and many losers. In enterprise gamification, they reliably motivate the top 10% and demoralize everyone else. The research is clear: competitive ranking works only when the population is already intrinsically motivated and competition is voluntarily entered.

**Hollow choice in skill trees.** When skill tree options are mathematically solved (one "correct" build), the appearance of choice becomes an illusion that breeds frustration. Meaningful skill trees require genuine tradeoffs -- choosing one path must meaningfully close or delay others, and multiple paths must be viable.

**Grind as padding.** When progression requires repetitive, low-challenge activity to fill time between meaningful milestones, players experience it as disrespect for their time. The distinction between "grind" and "practice" is whether the activity itself teaches something new or merely consumes time.

## Progression Models Worth Studying

| System | Model | Mrki Relevance |
|--------|-------|----------------|
| FFXIV Mentor System | Earn mentorship through demonstrated mastery (1000+ commendations, extensive content completion), gain access to Novice Network | Earned mentorship roles, not self-appointed |
| EVE Online CSM | Elected player council with real developer influence, deliberative democracy | Youth governance with genuine platform influence |
| Minecraft servers | Community-run governance, build-based reputation, emergent social hierarchy | Self-organized communities with organic leadership |
| Hades meta-progression | Every failure advances story and capability; death is narrative, not punishment | Making mistakes productive, not punitive |
| GW2 Mastery system | Post-level-cap progression through specific domain mastery (gliding, languages, mounts) | Horizontal progression -- breadth of capability, not just rank |
| WoW Guild progression | Organic emergence of raid leaders, officers, class mentors based on demonstrated competence | Role emergence through action, not appointment |

## Design Principles for Mrki

1. **Unlock capabilities, not badges.** Progression should open new things a user can *do*: moderate a discussion, organize an event, mentor a newcomer, access governance tools, launch a project with broader reach. The reward is expanded agency, not a trophy.

2. **Multiple progression axes.** Creative contribution, community support, governance participation, mentorship, project leadership, and skill domains should all be distinct progression paths. No single axis defines a user's "level."

3. **Make trust the currency, not points.** Trust accrues through consistent, observable behavior over time -- like reputation in a small town, not like a credit score. It should be contextual (trusted in governance != trusted in creative critique) and losable through behavior, not just accruable through activity.

4. **Design for flow, not completion.** The challenge level of available activities should scale with demonstrated capability. New users get structured, achievable tasks with clear feedback. Experienced users get open-ended, complex challenges. The platform should never feel like either a checklist or an impossible wall.

5. **Make failure productive, not punitive.** When a project fails or a governance proposal is rejected, the system should surface what was learned and what can be tried next -- the roguelike principle. Failure should advance the user's narrative arc, not reset their standing.

6. **Earned mentorship, not self-appointed authority.** Like FFXIV's mentor system, the ability to guide others should be unlocked through demonstrated competence and community recognition, not self-selection. The crown should mean something.

7. **Governance with real stakes.** Like EVE's CSM, youth governance should involve genuine decision-making power over real platform features, policies, and community resources. Advisory boards with no power breed cynicism faster than no board at all.

8. **Horizontal over vertical progression.** Avoid a single hierarchy where "level 50" users rule over "level 5" users. Prefer breadth: a user might be advanced in creative projects but new to governance, experienced in mentorship but just starting event organization. This prevents power concentration and keeps everyone a learner somewhere.

## Critical Tensions

**Legibility vs. authenticity.** Making progression visible (so users can see growth) risks reducing organic development to a metric. Minecraft's lack of progression metrics preserves authenticity but makes growth invisible to newcomers. FFXIV's explicit systems make growth legible but risk reducing mentorship to a checkbox. Mrki must find the middle: make capability visible without making it a score.

**Safety vs. meaningful stakes.** Real progression requires real failure. But teens on a social platform face real social consequences from failure. The roguelike model works because game-death has no real-world cost. Mrki must create contexts where failure is genuinely productive without being socially devastating -- closer to a practice room than a stage.

**Earned gatekeeping vs. exclusion.** Requiring demonstrated competence before unlocking mentorship or governance roles is sound design. But any gatekeeping system can reproduce existing inequalities -- users with more free time, better connectivity, or more social capital will progress faster. The system must distinguish between capability barriers (you need to learn this first) and access barriers (you need to have had this privilege first).

**Intrinsic vs. legible to outsiders.** If Mrki progression is genuinely intrinsic (you grow as a person, you can do more), it may be invisible to college admissions officers and employers -- the people teens need to impress. If it is made legible to outsiders (transcripts, portfolios, credentials), it risks becoming extrinsically motivated. This is the central design tension of the entire platform.

## Blindspots

**Cultural variation in progression models.** Nearly all referenced game design research comes from Western (US/Japan/EU) studios. Progression models, attitudes toward competition, and concepts of achievement vary significantly across cultures. Korean MMOs (MapleStory, Lineage) have different grind/reward philosophies. Chinese game design emphasizes different social dynamics. Mrki's global ambition requires studying non-Western progression design.

**Gender and progression.** MMORPG research skews heavily toward male-dominated gaming communities. Women and non-binary players often engage differently with progression systems, favoring social and creative progression over competitive ranking. The game design literature underrepresents these patterns.

**Disability and variable energy.** Flow theory assumes consistent cognitive capacity. Users with chronic illness, mental health challenges, or variable executive function may not fit the steady "skill vs. challenge" model. Progression design must account for variable engagement without penalizing absence.

**Age-appropriateness of failure.** Roguelike "failure is learning" works for adults with stable identities. For teens whose identity is actively forming, repeated visible failure in a social context carries different psychological weight. The productive-failure research is largely from controlled educational settings, not public social platforms.

**Dark patterns in progression design.** Game designers have refined techniques for making progression addictive (variable ratio reinforcement, loss aversion, sunk cost exploitation). These techniques are effective *because* they exploit real psychological mechanisms. Mrki must be vigilant that "genuine progression" does not inadvertently import manipulative retention mechanics from the games it studies.

---

## Sources

- [Deterding et al., "From Game Design Elements to Gamefulness"](https://dl.acm.org/doi/10.1145/2181037.2181040)
- [Deterding, "Gamification in Management: Between Choice Architecture and Humanistic Design"](https://journals.sagepub.com/doi/10.1177/1056492618790912)
- [Yu-kai Chou, Octalysis Framework](https://yukaichou.com/gamification-examples/octalysis-gamification-framework/)
- [Yu-kai Chou, "Creating Intrinsic Motivation via Octalysis"](https://yukaichou.com/gamification-study/create-intrinsic-motivation-octalysis-gamification/)
- [Jenova Chen, "Flow in Games" (MFA Thesis)](https://www.jenovachen.com/flowingames/Flow_in_games_final.pdf)
- [Cognitive Flow: The Psychology of Great Game Design](https://www.gamedeveloper.com/design/cognitive-flow-the-psychology-of-great-game-design)
- [Jane McGonigal, *Reality Is Broken*](https://www.amazon.com/Reality-Broken-Games-Better-Change/dp/0143120611)
- [EVE Online CSM (EVE University Wiki)](https://wiki.eveuniversity.org/Council_of_Stellar_Management)
- [EVE CSM: Politics of Creative Ownership](https://www.gamedeveloper.com/business/the-politics-of-creative-ownership-i-eve-online-i-s-council-of-stellar-management)
- [Ireland, "Democracy in a Virtual World: EVE Online's CSM" (thesis)](https://minds.wisconsin.edu/bitstream/handle/1793/90995/Ireland_uwm_0263m_10283.pdf)
- [FFXIV Mentor System](https://ffxiv.consolegameswiki.com/wiki/Mentor_System_and_Novice_Network)
- [Pathways to Mastery: Taxonomy of Player Progression Systems](https://www.intechopen.com/chapters/1221745)
- [Power Progression in Games (Gamedeveloper.com)](https://www.gamedeveloper.com/design/power-progression-in-games-crafting-rewarding-player-experiences)
- [Roguelike Learning (University XP)](https://www.universityxp.com/blog/2019/8/27/roguelike-learning)
- ["Failing Up: How Failure in a Game Environment Promotes Learning"](https://www.sciencedirect.com/science/article/pii/S1871187117301682)
- [Why Gamification Fails (Behavioral Strategy)](https://behavioralstrategy.com/failures/gamification-failures/)
- [Why Badges Fail in Gamification (Gamedeveloper.com)](https://www.gamedeveloper.com/design/why-badges-fail-in-gamification-4-strategies-to-make-them-work-properly)
- [Foursquare and Enterprise Gamification Lessons](https://centrical.com/what-foursquares-evolution-can-teach-us-about-enterprise-gamification/)
- [Minecraft Game Design Analysis](https://gamedesignskills.com/game-design/minecraft/)
- ["Gamification is not Working: Why?"](https://journals.sagepub.com/doi/abs/10.1177/15554120241228125)
