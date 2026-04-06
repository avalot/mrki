# Domain 1: Attention Economy, Persuasive Technology & Digital Wellbeing

## Field Overview

The study of how digital platforms capture and monetize human attention sits at the intersection of media studies, HCI, behavioral psychology, and public health. The field has matured from early "captology" (Fogg's term for computers as persuasive technology) through a period of public reckoning (The Social Dilemma, congressional hearings) into a more empirically rigorous but politically polarized phase. The central tension is no longer whether platforms influence behavior -- they demonstrably do -- but whether that influence constitutes a public health crisis or a modest effect inflated by moral panic, and whether design interventions or policy restrictions are the appropriate response.

## Key Thinkers and Positions

**B.J. Fogg** (Stanford Persuasive Technology Lab): Originator of the Behavior Model (B=MAP: Behavior occurs when Motivation, Ability, and a Prompt converge). Fogg's framework, developed in 2007, remains the canonical explanation of how platforms engineer habitual use. Social platforms systematically maximize all three variables: motivation through social approval/rejection dynamics that trigger dopamine release, ability through frictionless interfaces, and prompts through notifications. Fogg himself warned as early as 2006 about the damage persuasive technology could do, making him an ambivalent figure -- the person who gave Silicon Valley its behavioral playbook and then expressed regret about how it was used.

**Tristan Harris** (Center for Humane Technology): Former Google design ethicist who became the field's most prominent public advocate. Harris frames the problem as a "race to the bottom of the brain stem" -- platforms competing to exploit cognitive vulnerabilities. CHT's design principles center on two pillars: knowing human limits (respecting cognitive and emotional vulnerabilities) and thinking in systems (understanding second-order effects). CHT has recently pivoted toward AI risks under their "AI and What Makes Us Human" initiative, which may dilute their social media focus but reflects a genuine expansion of the attention economy problem.

**Nir Eyal** (author, "Hooked" and "Indistractable"): A uniquely contradictory figure. "Hooked" (2014) provided a four-step model (Trigger-Action-Variable Reward-Investment) for building habit-forming products; "Indistractable" (2019) then argued users bear primary responsibility for managing distraction. Critics draw explicit parallels to tobacco industry strategy: democratize the addiction mechanism, then emphasize personal responsibility. The fundamental critique is that Eyal's solutions (change your settings, build routines) assume a level of digital literacy and executive function that many users -- especially adolescents with immature prefrontal cortices -- do not possess.

**Adam Alter** (NYU, "Irresistible"): Identifies the removal of "stopping cues" as a core addiction mechanism. Traditional media had natural stopping points (end of a chapter, end of a TV episode); platforms deliberately eliminate these through infinite scroll, autoplay, and bottomless feeds. Alter's framework is useful for Mrki because it implies the inverse: reintroducing stopping cues (finite feeds, daily digests, postage costs) should disrupt compulsive loops.

**Jonathan Haidt** (NYU, "The Anxious Generation") and **Jean Twenge** (San Diego State, "iGen"): The alarm camp. Haidt argues that the period 2010-2015 saw a "rewiring of childhood" as smartphones and social media displaced unstructured play, sleep, and face-to-face interaction. Twenge's data shows unprecedented rises in teen depression, anxiety, and self-harm concurrent with smartphone adoption post-2012. Their policy wins are substantial: phone-free schools adopted across most US states by 2025, Australia's under-16 social media ban enacted December 2025. However, their causal claims remain contested.

**Amy Orben** (Cambridge) and **Andrew Przybylski** (Oxford Internet Institute): The nuance camp. Their "Goldilocks hypothesis" (2017, n=120,115) found that moderate digital engagement (1-2 hours/day) showed no negative association with wellbeing, and that the overall correlation between screen time and wellbeing was comparable to the correlation between wearing glasses and wellbeing. Przybylski emphasizes methodological quality over study count: "It doesn't matter if there's 19 studies in one direction and three in another, if those three studies are done well." Orben's specification-curve analyses demonstrate that researcher degrees of freedom in analytic choices can flip results from harmful to benign.

## What Works (Evidence-Based Findings)

**Social media restriction reduces depression specifically.** A meta-analysis of 10 RCTs (N=1,491) found reducing social media use significantly decreases depressive symptoms (g=0.25, p<0.001). This is a small-to-medium effect, but it is causal evidence from randomized designs, which is rare in this field.

**Notification batching improves wellbeing modestly.** Delivering notifications in batches rather than real-time reduces interruption-driven stress and promotes more focused engagement. Effect sizes are small (roughly 1 point between groups on wellbeing scales), but the mechanism is sound: fewer prompts means fewer impulsive check-ins.

**Design friction improves content recall.** A 2024 study (MuC conference, n=30) found that requiring users to react to each post before scrolling to the next significantly improved memory of content, suggesting friction disrupts the "normative dissociation" -- the trance-like state of mindless scrolling that suppresses self-awareness and memory formation.

**Gratitude interventions promote prosocial behavior.** A 2024 study in Nature's Scientific Reports confirmed that gratitude promotes prosocial behavior even in uncertain situations. Digital gratitude reflections were associated with more prosocial and socially oriented language (2025 study), suggesting that Mrki's "Thank" mechanic has empirical grounding as a prosocial design primitive.

**Delays before posting increase reflection.** A Chrome plugin introducing a 10-second delay before uploading Facebook posts increased self-reflection and helped users avoid heated discussions. This provides direct evidence for Mrki's intentional propagation delay.

## What Fails (Cautionary Findings)

**Friction causes frustration and autonomy backlash.** The same 2024 design friction study found that a majority of participants found the friction interface frustrating. A 2025 study on active nudging found that perceived infringement on autonomy undermined long-term sustainability of friction-based interventions. This is the single most important cautionary finding for Mrki: friction that feels imposed rather than chosen will be rejected.

**Broad wellbeing measures show null or tiny effects from restriction.** A systematic review and meta-analysis of 10 studies (N=4,674) found no significant effects of social media abstinence on positive affect, negative affect, or life satisfaction. The depression finding above is specific; general wellbeing does not reliably improve when social media is removed. This suggests the problem is not social media per se but specific design patterns within it.

**Age-verification bans face massive compliance failure.** Australia's under-16 ban removed 4.7 million accounts by March 2026, but many children retained accounts, created new ones, or passed age checks. Only 33% of Australians were confident the ban would be effective. Policy-level abstinence models face the same problems as drug abstinence models: they push behavior underground rather than reshaping it.

**Algorithmic "meaningful interaction" pivots backfired.** Facebook's 2018 algorithm change to boost "meaningful social interactions" (prioritizing comments and emotional reactions over passive likes) inadvertently amplified outrage content, because the most-commented posts were also the angriest. This is a direct warning for any platform that tries to optimize for "engagement quality" -- the metric will be gamed.

## Live Dialectics (Unresolved Tensions)

**Haidt/Twenge vs. Orben/Przybylski:** Is social media causally harming teens, or are we in a moral panic with tiny effect sizes? The honest answer: both camps have legitimate points. Haidt's temporal correlation is striking and the RCT evidence on depression is real, but Orben's point about researcher degrees of freedom and Przybylski's insistence on methodological rigor expose genuine weaknesses in the alarm narrative. The emerging synthesis is that social media is probably modestly causal for specific vulnerable subpopulations (those with pre-existing anxiety, high neuroticism, or social isolation) rather than universally harmful.

**Fogg (design determines behavior) vs. individual agency:** Eyal's position that users can simply choose to be "indistractable" is undermined by the neurodevelopmental reality that adolescent prefrontal cortices are not fully developed until the mid-20s, making teens structurally more vulnerable to variable-reward schedules. But the design-determinism position also overstates the case: users are not passive victims, and heavy-handed paternalism breeds resentment. The productive middle ground is designing environments that make healthy choices easier without removing agency -- "libertarian paternalism" or "choice architecture" applied to social platforms.

**Abstinence vs. harm reduction:** Australia's ban represents the abstinence model; Mrki's design represents harm reduction. The evidence increasingly favors harm reduction: teaching cognitive and behavioral strategies for healthy engagement appears more effective long-term than outright restriction, and restriction-based interventions show weaker effects for younger users than older ones.

## Paradigm Challengers (Radical or Unfashionable Positions)

**Lorenzo Manuali's "Addictive Motivational Scaffolds" (Synthese, 2025):** Proposes that addiction is not merely psychological but structurally embedded in platform architecture through four mechanisms: (1) quantified metrics, (2) reward uncertainty, (3) short time-horizon to reward, and (4) physically salient features. This framework, drawing on 4E cognition and psychiatric externalism, argues that addiction is partly constituted by the external environment, not just triggered by it. Radical implication for Mrki: if you remove all four scaffolds (no quantified metrics, no variable rewards, long time-horizons via postal pacing, reduced salience via digest delivery), you may structurally prevent addiction rather than merely discouraging it.

**The "displacement" counter-narrative:** Some researchers argue the real harm is not what social media does but what it displaces -- sleep, exercise, face-to-face interaction, unstructured play. If this is correct, then Mrki's design should be evaluated not by whether it reduces "screen time" but by whether it leaves room for offline life. Postal pacing and daily digests implicitly address this by making the platform temporally bounded.

**Collective vs. individual framing:** Most interventions target individual behavior (use your phone less, disable notifications). A growing minority argues the problem is collective: attention is a commons being strip-mined by extractive business models, and the solution must be structural (regulation, alternative ownership models, platform cooperativism) rather than individual willpower.

## Design Principles for Mrki

1. **Reintroduce stopping cues.** Finite feeds, daily digests, and postage costs all serve as natural stopping points that infinite-scroll platforms deliberately eliminate. The evidence supports this: stopping cues disrupt compulsive loops.

2. **Delay as a feature, not a bug.** The 10-second posting delay study and the broader slow-technology literature support Mrki's postal pacing model. Delay increases reflection, reduces reactive posting, and creates temporal boundaries that protect offline time.

3. **Replace quantified metrics with qualitative signals.** "Thank" instead of "Like" removes two of Manuali's four addictive scaffolds (quantified metrics and short reward time-horizon) while preserving social feedback. Do not display Thank counts publicly; the signal should be private between sender and receiver.

4. **Make friction feel chosen, not imposed.** The autonomy backlash finding is critical. Mrki's friction (postage, delay, finite feeds) must be framed as a community value rather than a restriction -- "this is how we do things here" rather than "this is what we prevent you from doing." Onboarding should explain the philosophy, not just enforce the rules.

5. **Design for the displacement test.** The platform succeeds not when teens use it more, but when it coexists healthily with sleep, schoolwork, physical activity, and face-to-face relationships. Daily digest delivery implicitly passes this test by making the platform a bounded daily ritual rather than an always-on attention drain.

6. **Batch, don't stream.** Notification batching has modest but real wellbeing benefits. Mrki's digest model is an extreme version of batching, and the evidence suggests this direction is correct even if the effect sizes are small individually.

7. **Prosocial mechanics over engagement mechanics.** Gratitude-based interactions have empirical support for promoting prosocial behavior. The "Thank" mechanic and postage system (spending gratitude currency) align with this evidence.

## Critical Tensions (Where Principles Conflict)

**Friction vs. adoption:** Every piece of friction that improves wellbeing also creates a barrier to initial adoption. Teens comparing Mrki to Instagram will experience the delay and postage costs as inconvenience before they experience them as liberation. The platform must be compelling enough in other dimensions (community quality, identity expression, local relevance) to survive the friction penalty during onboarding.

**Autonomy vs. protection:** Teens need both agency and guardrails. Too much protection feels paternalistic (the autonomy backlash); too much agency leaves vulnerable users exposed to the same compulsive patterns that mainstream platforms exploit. Mrki's design must thread this needle by making healthy defaults easy to keep while allowing some user customization.

**Measurability vs. anti-metrics philosophy:** If Mrki removes quantified metrics for users, how does the platform itself measure whether its interventions work? Internal analytics are necessary for iteration, but they must not leak into user-facing features that recreate status hierarchies.

**Community norms vs. scale:** Small communities self-regulate effectively; large ones require algorithmic or structural assistance. Mrki's local-first, distance-delayed model may naturally constrain community size, but if the platform succeeds, growth pressure will test whether postal pacing scales or becomes a bottleneck.

## Blindspots (What This Field Misses)

**Cultural variation:** Nearly all major studies are WEIRD (Western, Educated, Industrialized, Rich, Democratic). Teen digital culture in the Global South, where mobile-first platforms serve fundamentally different social functions (economic participation, educational access, family coordination), is almost entirely unstudied in the wellbeing literature. Mrki's assumptions about "healthy engagement" may not generalize.

**Neurodivergent users:** ADHD, autism spectrum, and anxiety disorders interact with platform design in complex ways that are barely studied. Some neurodivergent users report that social media is their primary mode of social connection; friction and delay may disproportionately harm the users who most need digital social support.

**Economic class:** The attention economy critique implicitly assumes users have rich offline alternatives. For teens in under-resourced communities, social media may be the primary site of social capital formation, creative expression, and information access. "Use your phone less" is a class-privileged prescription.

**The content question:** This entire field focuses on structural and behavioral mechanisms (scroll, notify, reward) while largely ignoring what people actually see and share. A platform with perfect anti-addictive design but toxic content still fails; a platform with mildly addictive design but genuinely nourishing content might succeed. Mrki's focus on structural design should not crowd out attention to content culture and community norms.

**Long-term developmental effects:** Almost all studies are short-term (weeks to months). We have essentially no evidence about what years of friction-based or delay-based social media use does to adolescent development compared to years of conventional social media use. Mrki is, in this sense, an experiment without a control group.

---

Sources:
- [Umbrella Review of Interventions for Digital Addiction (PMC, 2025)](https://pmc.ncbi.nlm.nih.gov/articles/PMC11862776/)
- [Meta-analysis of Social Media Restriction RCTs (ScienceDirect, 2025)](https://www.sciencedirect.com/science/article/pii/S2666560325000714)
- [Social Media Abstinence and Wellbeing Meta-analysis (Nature Scientific Reports, 2025)](https://www.nature.com/articles/s41598-025-90984-3)
- [Reducing Social Media Use Decreases Depression: Meta-Analysis of RCTs (MDPI, 2024)](https://www.mdpi.com/2254-9625/15/11/222)
- [Design Frictions on Social Media (MuC 2024)](https://dl.acm.org/doi/10.1145/3670653.3677495)
- [Addictive Motivational Scaffolds and Social Media (Synthese, 2025)](https://link.springer.com/article/10.1007/s11229-025-05312-z)
- [Notification-Disabling Intervention and Digital Wellbeing (2024)](https://www.tandfonline.com/doi/full/10.1080/15213269.2024.2334025)
- [Batching Smartphone Notifications (Computers in Human Behavior)](https://www.sciencedirect.com/science/article/abs/pii/S0747563219302596)
- [Active Nudging for Digital Wellbeing (Frontiers in Psychiatry, 2025)](https://www.frontiersin.org/journals/psychiatry/articles/10.3389/fpsyt.2025.1602997/full)
- [Longitudinal Investigation of Design Frictions (CHI 2024)](https://dl.acm.org/doi/10.1145/3613904.3642370)
- [Goldilocks Hypothesis: Przybylski & Weinstein (2017)](https://journals.sagepub.com/doi/10.1177/0956797616678438)
- [Orben & Przybylski: Screens, Teens, and Wellbeing (2019)](https://journals.sagepub.com/doi/10.1177/0956797619830329)
- [Gratitude Promotes Prosocial Behavior (Nature Scientific Reports, 2024)](https://www.nature.com/articles/s41598-024-65460-z)
- [Digital Gratitude and Prosocial Intentions (SAGE, 2025)](https://journals.sagepub.com/doi/10.1177/21582440251385690)
- [Australia Social Media Age Restrictions (eSafety Commissioner)](https://www.esafety.gov.au/about-us/industry-regulation/social-media-age-restrictions)
- [Australia Ban Compliance Review (Lancet Regional Health, 2026)](https://www.thelancet.com/journals/lanwpc/article/PIIS2666-6065(26)00022-2/fulltext)
- [Emotional Reinforcement Mechanism of Social Media Addiction (PMC, 2025)](https://pmc.ncbi.nlm.nih.gov/articles/PMC12108933/)
- [Problematic Social Media Use Interventions for Adolescents (Current Psychiatry Reports, 2025)](https://link.springer.com/article/10.1007/s11920-025-01619-3)
- [Center for Humane Technology](https://www.humanetech.com/)
- [Fogg Behavior Model (Stanford Behavior Design Lab)](https://behaviordesign.stanford.edu/resources/fogg-behavior-model)
- [Haidt/Twenge Debate Coverage (Platformer)](https://www.platformer.news/anxious-generation-jonathan-haidt-debate-critique/)
- [NPR: Did Social Media Break a Generation?](https://www.npr.org/transcripts/nx-s1-5719349)
