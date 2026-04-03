# Example: NordFlow — Full Recommendation-to-Debrief Flow

A fictional company walkthrough showing how strategy-please works end-to-end. NordFlow is made up, but the patterns are real. Every signal, recommendation, and output mirrors what happens in actual engagements.

---

## The company

**NordFlow** is a 12-person B2B SaaS company in Oslo building workflow automation for logistics companies. They have a working product, ~30 paying customers, and just closed a seed round. Revenue is growing but the founder can't explain why some deals close in two weeks while others take four months and die.

---

## Step 1: Onboarding (SETUP.md)

The founder opens strategy-please in Claude Code and says:

> "We're a logistics SaaS company. We just raised seed. Growth feels random and I don't know how to fix it."

Claude follows the setup flow, asks a few questions, and produces this profile:

### config/profile.md

```markdown
## Company

- **Name:** NordFlow
- **Website:** nordflow.io
- **Industry:** B2B SaaS / Logistics
- **Stage:** Early traction (post-seed)
- **Team size:** 12
- **Founded:** 2024

## What the company does

Workflow automation platform for logistics companies. Replaces manual coordination
between warehouse teams, drivers, and dispatchers with automated routing and real-time
status updates. Reduces coordination overhead by ~40% for mid-size logistics operators.

## Customers

- **Primary customer:** Operations managers at logistics companies (50-500 employees)
- **User vs. buyer:** Operations manager is the champion; CFO or CEO signs off on deals above 50k NOK/year
- **Current customer count:** ~30 paying
- **Best customers:** Mid-size operators (100-300 employees) with 3+ warehouse locations.
  They get the most value from the automation and have enough volume to justify the investment.

## Strategic context

- **What's working well:** Product is solid. Customers who onboard properly love it. Low churn among engaged accounts.
- **What feels stuck or unclear:** Growth is inconsistent. Some deals close fast, others drag forever. No clear pattern. Marketing is the founder posting on LinkedIn occasionally.
- **12-month vision:** 100 paying customers, 8M NOK ARR, ready for Series A conversations.
- **Upcoming decisions or milestones:** Need to hire first marketer. Series A prep in 6-8 months.

## What's been tried

Founder-led outbound via LinkedIn. Attended 2 logistics conferences (got 3 customers from
one, zero from the other). Tried a freelance content writer for 2 months — output was
generic and didn't land. Currently relying on referrals and founder network.

## Current maturity (estimated)

| Dimension | Score | Notes |
|-----------|-------|-------|
| 1. Strategic Clarity | 3 | Founder has a clear vision but it's in his head, not documented or shared |
| 2. Positioning and Messaging | 2 | Website describes features, not outcomes. Different team members pitch differently |
| 3. ICP Definition and Focus | 2 | Intuitive sense of best customers but no documented criteria |
| 4. Revenue Model and Pricing | 3 | Pricing exists and works, hasn't been optimized |
| 5. Content and Thought Leadership | 1 | Almost nothing. Sporadic LinkedIn posts |
| 6. Sales Process and Conversion | 2 | Founder-led, no structure, no qualification framework |
| 7. Competitive Awareness | 2 | Knows competitors exist, can't articulate specific differences |
| 8. Growth Engine and Distribution | 1.5 | Referrals and founder network only |
```

---

## Step 2: Workshop Recommendation (workshop-recommend)

The founder asks:

> "Growth feels random. We're closing some deals fast and others just die. What should we do?"

Claude maps the challenge:
- "Growth feels random" → Dim 8 (Growth Engine) and Dim 1 (Strategic Clarity)
- "Some deals close fast, others die" → Dim 3 (ICP) and Dim 6 (Sales Process)
- Root cause analysis: the inconsistent deal patterns suggest the company doesn't know which prospects are good fits. That's an ICP problem, not a sales process problem.

### Recommendation output

```
WORKSHOP RECOMMENDATION

Challenge: Inconsistent growth — some deals close easily, others drag and die,
with no clear pattern explaining the difference.

Primary dimension(s): Dim 3 (ICP Definition and Focus) — the inconsistent deal
patterns suggest NordFlow doesn't have clear criteria for which prospects are
good fits vs. poor fits. Dim 8 (Growth Engine) is a real gap too, but it's
downstream — you can't build a growth engine without knowing who to target.

Estimated maturity: Dim 3 at level 2 (intuitive sense, nothing documented).
Dim 8 at level 1.5 (referrals only, no system).

---

Recommended: ICP Discovery Workshop

Why this one: You described deals that close in two weeks alongside deals that
take four months and die. That variance almost always means some prospects are
great fits and others aren't — but you don't have criteria to tell the
difference upfront. ICP Discovery will make you analyze your actual customer
base: what the fast-close customers have in common, what the slow-death
prospects have in common, and build qualifying criteria from that evidence.

What you'll walk away with:
- A documented ICP with 2-3 segments, ranked by fit
- Qualifying criteria your team can apply to every new prospect
- A customer language bank (how your best customers describe the problem — useful
  for positioning and content later)
- Clear disqualifying criteria so you stop spending months on prospects that won't close

Format: 90 minutes. 2-4 participants (founder + anyone who talks to customers).
Self-facilitatable with the guide, though a facilitator would push harder on
the pattern extraction.

Startup format fit: This works as a focused 90-minute entry-point session. Run it
standalone, get the ICP definition, and decide from there whether broader work
(positioning, growth strategy) makes sense.

---

Why not the alternatives:

- Growth Channel Workshop: Your growth gap is real, but growth strategy without
  a defined ICP produces activity aimed at the wrong people. ICP first, then
  growth channels.

- Positioning Workshop: Your positioning needs work (website describes features,
  not outcomes). But positioning for whom? Define the customer first.

- Strategic Clarity Workshop: Your strategic clarity is actually decent (score 3).
  The vision is clear enough — the gap is in knowing who you're building for,
  not why you're building.

- Stakeholder Alignment: No evidence of team misalignment on direction. The issue
  is customer targeting, not internal disagreement.

---

What comes after: Positioning Workshop (half-day) to craft messaging that speaks
directly to the primary ICP. Then Growth Channel Workshop to build a systematic
way to reach them. That three-workshop sequence would address your core gaps.
```

---

## Step 3: Session Design (workshop-design)

The founder says: "Let's do the ICP Discovery workshop. It'll be me, our head of sales, and our customer success lead."

Claude produces a tailored session plan:

### Key adaptations

**Pre-work:**
- [ ] Each participant: identify your single best NordFlow customer and your single worst. Be ready to tell the story.
- [ ] Pull the customer list and sort by: time-to-close, contract value, and support ticket volume
- [ ] Markus (head of sales): bring notes on the last 3 deals that went cold

**Company-specific questions (adapted from generic prompts):**
- "You mentioned some deals close in two weeks. Think about those specifically. What did those companies look like? What was the operations manager dealing with when they found you?"
- "Your best customers are mid-size operators with 3+ warehouses. What's different about the ones with fewer warehouses — do they get less value, or do they just take longer to see it?"
- "When a deal dies at month four, what's usually the reason? Is it the champion losing interest, budget approval failing, or something else?"

**Facilitator notes:**
- The founder likely has strong intuitions about customer fit but hasn't articulated them. The Pattern Wall exercise should surface these intuitions and make them explicit.
- Watch for tension between the sales perspective (who we can close) and the CS perspective (who actually succeeds). Both are valuable. The ICP should optimize for success, not just close rate.

---

## Step 4: The Workshop Happens

*(The actual workshop is facilitated by a human. strategy-please isn't in the room.)*

The team runs the 90-minute session. Key findings:

- Fast-close customers all had 3+ warehouse locations AND were replacing a specific legacy tool (LogiTrack). They already understood the problem and were actively looking.
- Slow-death deals were typically smaller companies (under 100 employees) or companies that didn't have an existing tool — they needed to be convinced the problem was worth solving, not just that NordFlow was the right solution.
- The customer success lead revealed that the 5 highest-NPS customers all came through the same channel: logistics industry LinkedIn groups.
- The "disqualify" signals became clear: companies under 80 employees, companies without a dedicated operations manager, companies still using paper-based coordination.

---

## Step 5: Workshop Debrief (workshop-debrief)

The founder drops his session notes into strategy-please:

> "Here are my notes from the ICP workshop. Process these."

### Debrief output

```
WORKSHOP DEBRIEF

Workshop: ICP Discovery Workshop
Company: NordFlow
Date: 2026-04-15
Participants: Erik (founder/CEO), Markus (head of sales), Lena (CS lead)
Facilitated by: Self (with guide)

---

Decisions made:

- Primary ICP: Operations managers at mid-size logistics companies (80-500
  employees) with 3+ warehouse locations, currently using a legacy coordination
  tool (LogiTrack, DispatchPro, or similar)
- Disqualify: companies under 80 employees, no dedicated ops manager, paper-based
  coordination (too much education required)
- Secondary ICP: Same profile but without existing tool — viable but requires
  longer sales cycle and different messaging. Pursue only when capacity allows.
- All new inbound leads to be scored against the qualifying criteria before
  investing sales time

---

Outputs produced:

| Output | Status | Summary |
|--------|--------|---------|
| ICP definition (2-3 segments) | Complete | Primary and secondary segments defined with clear boundaries |
| Primary segment with rationale | Complete | Mid-size operators replacing legacy tools — fastest close, highest NPS |
| Qualifying/disqualifying criteria | Complete | 5 qualifying signals, 3 disqualifying signals documented |
| Customer language bank | Partial | Some language captured but needs enrichment from CS conversations |

---

Scorecard delta:

| Dimension | Before | After | What moved it |
|-----------|--------|-------|---------------|
| 3. ICP Definition and Focus | 2 | 3 | Documented ICP with qualifying criteria, up from intuitive sense |
| 2. Positioning and Messaging | 2 | 2 | No change — positioning work not done yet |
| 8. Growth Engine and Distribution | 1.5 | 1.5 | No change — but the ICP now provides a clear target for growth work |

Net movement: Dim 3 moved from 2 to 3. NordFlow now has a documented primary
ICP with qualifying criteria and a clear secondary segment. The team can
evaluate every new prospect against explicit criteria. The dimension isn't at
4 yet because the ICP hasn't been tested against real pipeline data over time.

---

Surprises and new insights:

- The LogiTrack replacement pattern was the biggest insight. Customers replacing
  a known tool close 3x faster because they already understand the problem.
  This has implications for positioning (message the switch, not the category)
  and growth (target LogiTrack users specifically).
- The LinkedIn logistics groups as a channel signal was unexpected. All 5 highest-NPS
  customers came through this channel. Worth investigating in the Growth Channel workshop.

---

Unresolved items:

- Customer language bank is partial. Lena will compile actual quotes from the
  top 10 customers over the next two weeks.
- The secondary ICP (no existing tool) wasn't fully scoped. The team decided to
  deprioritize for now and revisit after 30 days of using the primary ICP criteria.

---

Recommended next steps:

Immediate (this week):
- Markus: apply qualifying criteria to current pipeline, re-evaluate stalled deals
- Erik: update the NordFlow website to speak to the primary ICP
- Lena: begin compiling customer language bank from support conversations and NPS responses

Next workshop: Positioning Workshop (half-day). The ICP is now clear enough to
build positioning around. The LogiTrack replacement insight is a strong
positioning angle that should be tested. Recommended timing: 2-3 weeks from now,
after the customer language bank is enriched.

Follow-up check: Review the ICP criteria after 30 days of sales activity. Are
the qualifying criteria holding up? Is the primary segment producing the expected
close rates?
```

---

## What this example shows

1. **Problem → Dimensions → Workshop:** The founder said "growth feels random." The system identified ICP as the root cause, not growth channels.
2. **Tailored design:** The generic ICP Discovery exercises were adapted with NordFlow-specific questions about deal velocity and specific customers.
3. **Concrete outputs:** The workshop produced documented criteria the team can use immediately, not abstract "alignment."
4. **Scorecard movement:** Dim 3 moved from 2 to 3. Honest — a single workshop moves things, but not to perfection.
5. **Surprises feed forward:** The LogiTrack replacement insight and LinkedIn groups finding both inform the next workshops (Positioning and Growth Channel).
6. **The chain emerges:** ICP Discovery → Positioning → Growth Channel. Each workshop's outputs feed the next.
