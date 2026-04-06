# UX Philosophy: Goals, Tensions & Tough Questions

This document does not prescribe solutions. It states what we want, names the tensions between those wants, and poses the questions our designs must answer. Any feature, mechanic, or interface we build should be testable against these.

---

## I. What We Want for the Person

### A teen on Mrki should be able to:

1. **Express who they are today** without being locked into who they were yesterday. Identity is fluid at this age. The platform must support experimentation without creating a permanent record that follows you into adulthood.

2. **Connect with close friends with the speed and ease their friendship demands.** Banter, inside jokes, rapid-fire nonsense — these are not shallow. They are the connective tissue of adolescent social life (Ito: "hanging out"). The platform must never make intimate communication feel heavy or costly.

3. **Find people who share their weird, specific passion** — whether that's mycology, speedrunning, zine-making, or urban planning. Interest-driven community is where the deepest developmental value lives (Ito: "geeking out"). The platform should make this discovery feel like luck, not like an algorithm.

4. **Contribute to something larger than themselves** — a project, a community, a governance decision, a creative work. Agency matters. A teen who helps shape the rules of their community is developing capacities that no amount of content consumption can provide.

5. **Be unreachable when they want to be.** Solitude is where identity forms (Turkle). The platform must make being offline feel normal, not like a social failure. No "last seen." No read receipts. No guilt mechanics.

6. **Encounter perspectives unlike their own** without feeling lectured or force-fed. Diversity of viewpoint should feel like discovery, not medicine.

7. **Make mistakes and recover from them.** Adolescence requires risk-taking. A platform that punishes every misstep with permanent reputation damage is as hostile as one that enables consequence-free cruelty. Graduated response. Room to learn.

---

## II. What We Want for the Community

### A community on Mrki should:

1. **Govern itself without producing tyrants.** Power must rotate. But rotation without continuity produces chaos. How do we build institutional memory that survives role transitions?

2. **Reward contribution without creating celebrities.** Reputation should empower helpful behavior, not create a visible status hierarchy. But invisible reputation is invisible power — and invisible power is unaccountable power (Freeman). How do we make the mechanism transparent without making the score a vanity metric?

3. **Grow without degrading.** Every successful community in history has faced an "Eternal September" moment when influx overwhelmed norms. How do we onboard newcomers into a culture without gatekeeping them out of it?

4. **Moderate itself without burning out its moderators.** Volunteer moderation is unsustainable (Wikipedia, Reddit). Paid governance roles solve this — but introduce the risk that governance becomes a job people cling to rather than a service they provide. How do we make DRI roles attractive enough to fill, but not attractive enough to hoard?

5. **Remain accountable to its members even as it scales.** Ostrom's third principle: those affected by the rules must be able to modify them. If protocol changes require foundation approval, the community is advisory, not sovereign. How do we make community governance genuinely binding?

6. **Resist capture by any single interest.** Not by advertisers (we have no ads). Not by the founding team (the protocol is open). Not by a clique of power users (reputation is invisible). Not by the loudest voices (pacing favors reflection over speed). But each of these defenses has a shadow: no ads means revenue depends on subscriptions; open protocol means forks can fragment; invisible reputation means unchecked power; pacing means the urgent gets delayed. How do we defend against capture without creating new vulnerabilities?

---

## III. What We Want for the Platform's Relationship to Attention

### The platform should:

1. **Treat attention as a commons, not a commodity.** Every public post is a request for collective attention — a withdrawal from a shared resource. The platform should make this visible without making it punitive.

2. **Have natural stopping points.** Infinite scroll is a design choice that says "your time doesn't matter." Finite feeds, daily digests, and "that's everything for now" are design choices that say "your time is yours." But: how do we build a platform that respects your time while still being somewhere you want to come back to?

3. **Make the cost of attention legible, not priced.** Weight-aware posting ("this will appear in 230 people's digests") may be more honest and less distorting than gratitude stamps. Making the cost visible lets the poster decide; pricing the cost decides for them. But: legibility without cost is just information. Does it change behavior, or just add noise?

4. **Not create a two-tier system of voice.** If posting publicly costs something (stamps, effort, time), and private messaging is free, we risk hollowing out the public commons as everyone retreats to DMs. The public square is where community forms. How do we keep it worth participating in?

5. **Pace communication without patronizing the communicator.** "Want to wait 5 minutes?" is a nudge. "You must wait 5 minutes" is a gate. The difference matters enormously to a teenager. How much of our pacing is invitation, and how much is imposition?

6. **Acknowledge that not all attention requests are equal** without building a system that silences the verbose, the expressive, or the neurodiverse. A long heartfelt post and a spam blast both "cost" attention — but they are not the same thing. Any cost-based system must distinguish signal from noise without becoming an arbiter of what's worth saying.

---

## IV. The Tensions We Must Hold (Not Resolve)

Some tensions cannot be resolved — they must be held in creative balance. Collapsing to either side is a design failure.

### 1. Safety vs. Agency
We want to protect teens from harm. We also want to give them real power. These pull in opposite directions. A platform that's too safe is a padded cell. A platform that's too free is 4chan. The answer is not a middle point — it's a structure where safety comes from community, not from restriction.

### 2. Slowness vs. Spontaneity
We want thoughtful, deliberate communication. We also know that rapid, playful, messy exchange is developmentally important and socially vital. The answer is not "slow everything down" — it's different speeds for different relationships and contexts. Close friends: fast. Public square: slow. But where is the line, and who draws it?

### 3. Equality vs. Earned Influence
We want every voice to matter. We also want reputation to mean something — to give weight to the voices of people who have contributed. These conflict. Pure equality means trolls have the same power as trusted contributors. Pure meritocracy means newcomers are silenced. How do we bootstrap newcomers into influence without devaluing the trust that veterans have earned?

### 4. Transparency vs. Gamification
We want the system to be legible — people should understand why things happen. But making reputation visible makes it a target for gaming (Stack Overflow). Making governance rules explicit makes them exploitable. Every transparency gain is a gamification risk. How do we make the mechanism visible without making the score a game?

### 5. Friction as Care vs. Friction as Exclusion
Friction can be a gift: "take a moment, this matters." Friction can also be a barrier: "you can't afford to speak here." The same mechanism serves both functions depending on who encounters it. How do we ensure friction falls equitably across economic class, communication style, neurodivergence, and cultural background?

### 6. Local Identity vs. Segregation
Proximity-based networks celebrate local community. But physical proximity mirrors physical segregation — by race, class, geography. If Mrki Lyon and Mrki Marseille become different worlds, we've replicated the problems of physical space in digital space. The "Diverse Perspectives Engine" is supposed to counteract this — but how hard do we push, and when does gentle nudging become force-feeding?

### 7. Community Sovereignty vs. Protocol Integrity
The community should govern itself. But the protocol must protect core values (no ads, no surveillance, reputation integrity). What happens when the community votes for something that violates the protocol's values? Who decides what's a legitimate governance decision and what's a threat to the platform's integrity? This is a constitutional question, not a UX question — but it has UX consequences.

### 8. Growth vs. Quality
Every historical precedent tells us: growth degrades community quality. MetaFilter stayed great by staying small. The WELL stayed great by staying small. We want to serve millions of teens. How do we grow without becoming what we replaced? "Nested communities" (Ostrom) is an architectural answer — but the UX must make nested governance feel natural, not bureaucratic.

---

## V. Tough Questions for Every Feature We Build

Before shipping any feature, ask:

1. **Who does this exclude?** Every mechanic has a shadow. Stamps exclude the poor. Slowness excludes the urgent. Reputation excludes the new. Pseudonymity excludes the accountable. Name the shadow.

2. **Does this produce resonance or just delay?** (Rosa) A feature that slows things down without creating genuine connection is alienation at a different tempo. Delay is not a virtue. Connection is.

3. **Would a 14-year-old choose this, or only tolerate it?** If the answer is "tolerate," the feature will be worked around, resented, or abandoned. Teens are not a captive audience — they will leave if the platform feels like a chore designed by adults who think they know better.

4. **Does this survive Eternal September?** A feature that works for 500 founding citizens may collapse at 50,000. How does it degrade? Can it adapt? Does it need to be redesigned, or does it scale naturally?

5. **Can this be enshittified?** If someone with wrong incentives took control, could they use this feature to extract value? Internal currencies can be inflated. Reputation systems can be weaponized. Governance roles can be captured. Design for the benevolent case, but stress-test for the malevolent one.

6. **Is this for the teens, or for our thesis?** We have strong beliefs about what a platform should be. So do the teens who will use it. When those conflict, who wins? If the answer is always "our thesis," we're building a monument to our values, not a platform for theirs.

---

## VI. What We Don't Know (And Must Learn by Building)

The research is clear on what harms. It is nearly silent on what flourishing looks like in digital communities, especially for teens. There is no empirical precedent for:

- Teen-governed digital commons at scale
- Paid rotating governance roles in online communities
- Gratitude-based posting economics
- Distributed reputation computed by independent AI nodes
- Intentional-pace social platforms that reach mainstream adoption

We are designing in the dark on these questions. That means: **build measurement into everything.** Not engagement metrics — those are the old game. Measure what we actually care about: Are people making real friends? Are they building things? Are they showing up IRL? Are they sleeping enough? Are they coming back because they want to, not because they're hooked?

If we can't measure it, we can't know if we're succeeding. And if we're not measuring the right things, we'll optimize for the wrong ones — which is exactly how every platform before us went wrong.
