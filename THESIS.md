# Mrki — Value Proposition Thesis

## The Moment

France is making ad-based, addictive social media illegal for under-15s. The EU will follow. But the law has a loophole: parents can override the ban. That means some teens get access, peer pressure kicks in, and everyone defects back to TikTok and Instagram.

**This is the breach.** For the first time, there is regulatory tailwind and parental willingness to pay for a social platform that isn't designed to extract attention and sell it to advertisers.

We know what social networks felt like before enshittification — they were genuinely great. The question is: can we build something that great, that *stays* great, because the business model never requires degradation?

**Yes. If you remove ads, you remove the incentive to make people angry, addicted, and lonely.**

---

## The Problem

Today's social platforms for teens are built on a single equation:

> **More time on screen → more ads served → more revenue**

This produces:
- Algorithmic amplification of outrage and envy
- Vanity metrics (likes, followers) that drive social anxiety
- Surveillance-grade data collection sold to advertisers
- Content designed to hook, not to help
- No incentive to ever let the user put the phone down

Parents know this. Regulators know this. Teens know this — they just don't have an alternative.

---

## The Solution: Mrki

A social and collaboration platform for teens (13–18) that is:

| Principle | How |
|---|---|
| **Ad-free** | Parent-paid subscription. No ads, no data sales, ever. |
| **Privacy-first** | Minimal data collection. No tracking. No profiling. Data belongs to the user. |
| **Self-moderated** | Community-driven moderation with reputation mechanics — not corporate censors, not unmoderated chaos. |
| **Anti-vanity** | You don't see other people's stats. No like counts. No follower leaderboards. |
| **Pro-connection** | Designed for IRL meetups, real friendships, diverse perspectives, and collaborative projects. |
| **Mindful by design** | Low friction for thoughtful behavior. High friction for attention-seeking and manipulation. |

---

## Core Mechanics

### 1. "Thank" instead of "Like"

There is no "like" button. There is a **"Thank"** — a private signal that says *"this was valuable to me."* Thanks are:
- **Private**: only the creator sees them (not counts, not who)
- **Weighted**: a thank from someone with high reputation carries more weight
- **Non-gameable**: you can't see your own thank count in aggregate; you see individual thanks as they arrive, then they fade

### 2. Reputation, Not Clout

Every user has a **reputation score** that is:
- **Invisible to others** — you never see someone else's number
- **Earned through behavior** — helping others, contributing to projects, showing up IRL, being thanked
- **Lost through harm** — flagged content, broken commitments, dishonesty
- **Self-reinforcing** — your reputation affects how much your flags, thanks, and moderation votes matter

This means: **liars lose credibility.** Trolls lose influence. Helpful people quietly gain more power to shape the community — without ever becoming "influencers."

### 3. IRL-First Design

The platform actively encourages meeting in person:
- **Proximity-aware groups** (without revealing exact location)
- **Event creation** with low-friction RSVPs
- **Check-in confirmation** (both parties confirm they met — no location tracking)
- **Project collaboration** with real-world components (build something, make something, go somewhere)

### 4. Diverse Perspectives Engine

Instead of filter bubbles, the platform:
- **Surfaces content from outside your circle** — gently, not forcefully
- **Rewards engaging with different viewpoints** — reading and thoughtfully responding to people unlike you
- **Flags echo chambers** — if a group becomes too homogeneous, the system nudges toward variety

### 5. Pre-Post Reflection

Before publishing, the platform asks:
- *"Is this something you'd say in person?"*
- *"Want to wait 5 minutes and re-read?"*

These are **optional, low-friction nudges** — not gatekeeping. But they're there, and they work.

### 6. Anti-Advertising Immune System

Any content that looks like covert advertising is:
- Flagged by the community
- Detected by automated systems
- Downgraded in visibility
- Repeated offenses affect reputation

**The platform has an immune response to ads.** This is a feature, not a bug.

---

## Business Model

### Revenue: Parent-Paid Subscription

| Tier | Price | What |
|---|---|---|
| **Core** | €5/month | Full platform access for one teen |
| **Family** | €9/month | Up to 3 teens |
| **Community** | €12/month | Up to 5 teens + school/org features |

**At 18, the user takes over the subscription** (or moves to a free tier with limited features, or the platform has evolved enough to offer freemium without ads).

### Why Parents Will Pay

1. **Regulatory push** — France (and soon the EU) is telling them existing platforms are harmful
2. **Peace of mind** — no ads, no data harvesting, no predatory engagement loops
3. **Visible value** — their teen is making real friends, working on real projects, going outside
4. **Social proof** — other parents in the school are doing it
5. **It's cheaper than therapy** — €5/month vs. the cost of social media-induced anxiety

### Unit Economics Target

- **CAC**: < €15 (school-network viral loops)
- **LTV**: €300+ (5-year average teen tenure × €5/month)
- **LTV:CAC**: > 20:1
- **Gross margin**: > 80% (low infrastructure cost, no content licensing, no ad-tech stack)

---

## MVP — What We Build First

### Phase 1: Core Loop (3 months)

The minimum product that tests the thesis:

1. **Profiles** — minimal, no vanity metrics visible to others
2. **Groups** — topic or location-based, self-moderated
3. **Posts** — text, images, links; with pre-post nudge
4. **Thanks** — private appreciation mechanic
5. **Reputation engine** — v1, invisible, behavior-based
6. **Moderation** — community flags + basic automated detection
7. **Parental dashboard** — subscription management, high-level activity summary (not surveillance)

### Phase 2: Stickiness (months 4–6)

8. **Projects** — collaborative spaces for building things together
9. **Events** — IRL meetup creation and confirmation
10. **Diverse perspectives** — cross-circle content surfacing
11. **School networks** — verified school-based groups

### Phase 3: Growth (months 7–12)

12. **API for educators** — schools can integrate projects/assignments
13. **Mentorship** — verified adults (teachers, coaches) in structured roles
14. **Creative tools** — built-in creation (not just consumption)
15. **Transition to 18+** — graceful aging-out with data portability

### Tech Stack (Lean)

- **Backend**: Go or Rust — fast, cheap to run, small team
- **Frontend**: React Native (cross-platform mobile) + web
- **Infrastructure**: Fly.io or similar — EU-hosted, GDPR-native
- **Database**: PostgreSQL + Redis
- **Moderation**: combination of community signals + lightweight ML
- **Auth**: age-verified onboarding with parental consent flow

---

## Go-To-Market: The School-Network Virus

### The Strategy

Social platforms are network-effect businesses. You can't launch to "all teens." You launch to **one school at a time**, and let it spread.

### Phase 1: Seed Schools (months 1–3)

1. **Partner with 5–10 schools in France** (where the regulation hits first)
2. **Work with one enthusiastic teacher per school** who runs a class project on the platform
3. **Offer the first semester free** for the entire school
4. **Parents get invited through a school-branded onboarding** — trust transfer from the school

### Phase 2: School-to-School Spread (months 3–6)

5. **Students have friends at other schools** — they invite them
6. **"Your friends at [School X] are on Mrki"** — the network effect starts
7. **Parent WhatsApp groups** become the B2B2C channel — one parent tells another
8. **Local press** covers the "school that quit Instagram" story

### Phase 3: City-Level Tipping Point (months 6–12)

9. **When 30%+ of a city's schools are on, it tips** — the remaining schools can't not join
10. **Expand to Belgium, Switzerland, Luxembourg** (French-speaking, similar regulatory environment)
11. **Then Germany, Spain, Italy** as EU regulation spreads

### Phase 4: Global (year 2+)

12. **US, UK, Australia, Japan** — everywhere parents are worried and willing to pay
13. **Localization** is straightforward — the platform is text-and-project-based, not content-licensed

### Viral Mechanics

- **School leaderboards** (how active is your school's community — NOT individual vanity)
- **Inter-school projects** (collaborate with the school across town)
- **Parent referral program** (invite another family, get a month free)
- **Student ambassador program** (teens who help onboard their friend group)

---

## Investment Thesis

### Why Now

1. **Regulatory catalyst**: France's law (2025–2026) creates the first real market for a non-ad teen platform. The EU will follow with the Digital Services Act enforcement.
2. **Parental willingness to pay**: for the first time, parents are being told by their government that existing platforms are harmful. This converts "concern" into "action."
3. **Teen fatigue**: Gen Z and Gen Alpha report increasing dissatisfaction with existing platforms. They want something different — they just don't have it.
4. **Technical feasibility**: building a social platform in 2026 is dramatically cheaper than in 2010. Cloud infrastructure, open-source tooling, and AI-assisted development mean a small team can move fast.
5. **Cultural moment**: there is a post-pandemic, post-enshittification hunger for genuine human connection online. The vibes are right.

### Market Size

- **Europe**: ~50M teens aged 13–18
- **Addressable (France first)**: ~8M teens
- **Penetration target (year 3)**: 5% of French teens = 400K users
- **Revenue at target**: €24M ARR (400K × €5/month × 12)
- **Global TAM**: 500M+ teens worldwide; €30B+ market at scale

### Competitive Landscape

| Competitor | Why We Win |
|---|---|
| Instagram/TikTok | Ad-based, regulatory headwind, can't credibly pivot to teen-safe |
| BeReal | No real community features, no collaboration, fading novelty |
| Discord | Unmoderated chaos, not designed for teens, no parental trust |
| Bark/Qustodio | Surveillance tools, not platforms — teens hate them |
| School LMS (Google Classroom) | Not social, not fun, institutional |

**Our wedge**: we are the only platform that is simultaneously **parent-trusted**, **teen-appealing**, and **ad-free by design**.

### Defensibility

1. **Network effects** — school-level lock-in is powerful
2. **Reputation data** — the reputation graph is a moat (non-exportable, non-copyable)
3. **Regulatory alignment** — we're built for the regulatory future; incumbents are built against it
4. **Cultural identity** — "I'm on Mrki" becomes a statement of values, like choosing Firefox over Chrome

### The Ask

**Seed round: €2–3M**

- 18 months of runway
- Team of 8–10 (engineering, design, community, one commercial lead)
- Launch in 10 French schools
- Target: 10K active users, 50+ schools, clear retention and engagement data
- Path to Series A at €15–20M valuation

---

## Pitch Deck Outline

### Slide 1: Cover
**Mrki** — The social platform teens deserve.

### Slide 2: The Problem
Social media is making teens miserable. Everyone knows it. Nobody has built the alternative.

### Slide 3: The Catalyst
France just made ad-based social media illegal for under-15s. The EU is next. For the first time, there's a market for something better.

### Slide 4: The Solution
Ad-free. Privacy-first. Self-moderated. Parent-paid.
A platform where "Thank" replaces "Like," reputation is invisible, and meeting IRL is the highest-status thing you can do.

### Slide 5: How It Works
Core mechanics: Thanks, Reputation, IRL-first, Diverse Perspectives, Pre-Post Reflection, Anti-Ad Immune System.

### Slide 6: Business Model
€5/month per teen, paid by parents. Family and school tiers. 80%+ gross margin. LTV:CAC > 20:1.

### Slide 7: Go-To-Market
School-by-school viral expansion. Start with 10 French schools. Spread through student networks and parent word-of-mouth.

### Slide 8: Market Size
8M French teens. 50M European teens. 500M+ globally. €30B+ TAM at scale.

### Slide 9: Competitive Landscape
The only platform that is parent-trusted, teen-appealing, and ad-free by design. Incumbents can't credibly pivot.

### Slide 10: Traction / Plan
Phase 1 MVP in 3 months. 10 seed schools. 10K users in 12 months.

### Slide 11: Team
[To be filled — need founder profiles]

### Slide 12: The Ask
€2–3M seed. 18 months runway. Build, launch, prove retention.

### Slide 13: Vision
A generation of teens who grew up on a platform that made them *better* — more connected, more thoughtful, more creative. Not more anxious, not more lonely, not more addicted.

**The internet was supposed to be this. Let's finally build it.**

---

## Open Questions

- **Name**: "Mrki" — does it work? (Short, memorable, no meaning to co-opt, easy to type)
- **Age verification**: how to do this without being invasive? (School-based verification could be the answer)
- **Transition at 18**: free tier? Adult pricing? Graceful exit with data portability?
- **Content moderation at scale**: how to keep self-moderation working as the platform grows?
- **International regulatory differences**: COPPA (US), Age Appropriate Design Code (UK), etc.
- **Monetization beyond subscriptions**: marketplace for teen-created content/products? Ethical sponsorships?
- **Open source?**: would open-sourcing the platform increase trust and defensibility?
