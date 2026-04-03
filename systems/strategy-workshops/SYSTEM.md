# Strategy Workshops System

The methodology that powers strategy-please. This document defines how challenges map to workshops, how the recommendation engine works, and the strategic maturity taxonomy that underpins everything.

---

## Core principle

Start from the problem, not the format. A company says "we don't know who our best customer is." That's a signal, not a workshop request. The system's job is to map that signal to the right intervention: which dimensions are affected, what maturity level the company is at, and which workshop will move them forward.

---

## The eight dimensions

Every company's strategic maturity can be assessed across eight dimensions. Each dimension represents a capability area that matters for growth. Workshops in the catalog target specific dimensions at specific maturity levels.

| # | Dimension | Core question |
|---|-----------|--------------|
| 1 | Strategic Clarity | Why do we exist, who do we serve, where are we going? |
| 2 | Positioning and Messaging | Can we explain what we do in customer terms? |
| 3 | ICP Definition and Focus | Do we know who our best customers are? |
| 4 | Revenue Model and Pricing | Do we have a defensible way of making money? |
| 5 | Content and Thought Leadership | Do we systematically demonstrate expertise? |
| 6 | Sales Process and Conversion | Do we have a repeatable way of turning interest into revenue? |
| 7 | Competitive Awareness | Do we know where we win and lose? |
| 8 | Growth Engine and Distribution | Do we have a scalable way of reaching our ICP? |

### Maturity levels

Each dimension is scored on a 1-5 scale:

| Level | Label | Meaning |
|-------|-------|---------|
| 1 | Not started | No meaningful work in this area |
| 2 | Aware | Recognizes it matters, no structured work yet |
| 3 | Developing | Initial frameworks exist, incomplete or untested |
| 4 | Established | Clear, documented, actively used |
| 5 | Leading | A genuine strength, producing measurable results |

### Dimension relationships

Dimensions are not independent. Common dependencies:

- **Dim 1 (Strategic Clarity) is upstream of everything.** Without clarity on purpose, audience, and direction, positioning (Dim 2), ICP (Dim 3), and growth (Dim 8) can't be properly addressed.
- **Dim 3 (ICP) feeds Dim 2 (Positioning).** You can't position effectively without knowing who you're positioning for.
- **Dim 2 (Positioning) feeds Dim 7 (Competitive Awareness).** Competitive positioning requires your own positioning to be clear first.
- **Dims 1-3 together form the strategic foundation.** Most companies need these before Dims 4-8 become productive.

This matters for sequencing. If a company needs both ICP Discovery and Growth Channel work, ICP comes first because the growth strategy depends on knowing who to reach.

---

## Recommendation logic

### Step 1: Identify the challenge

The user describes a problem, objective, or situation. This can be:
- A direct statement: "We don't know who our best customer is"
- A symptom: "Our sales cycle is too long"
- An objective: "We need to prepare for a Series A"
- A scorecard result: dimension scores from an assessment

### Step 2: Map to dimensions

Each challenge maps to one or more dimensions. The mapping isn't always obvious:

| Challenge (what they say) | Real dimension(s) | Why |
|--------------------------|-------------------|-----|
| "We need more leads" | Dim 3 (ICP), Dim 8 (Growth) | Lead volume is usually a targeting problem, not a channel problem |
| "Our sales cycle is too long" | Dim 2 (Positioning), Dim 3 (ICP) | Long cycles often mean prospects don't understand the value or aren't the right fit |
| "We can't explain what we do" | Dim 2 (Positioning) | Direct mapping |
| "The team isn't aligned" | Dim 1 (Strategic Clarity) | Misalignment is almost always a clarity problem |
| "We don't know our competition" | Dim 7 (Competitive Awareness) | Direct mapping |
| "We're growing but it feels random" | Dim 8 (Growth), Dim 1 (Strategic Clarity) | Random growth = no engine + unclear direction |
| "We need to figure out pricing" | Dim 4 (Revenue Model) | Direct mapping (no workshop yet, note this) |
| "We're launching something new" | Dim 1 (Strategic Clarity), Dim 3 (ICP) | New initiatives need foundational clarity |

### Step 3: Assess maturity level

Based on the conversation or scorecard results, estimate where the company sits on each relevant dimension. This determines which workshop variant is appropriate:

- **Levels 1-2:** Foundational workshops. Start from scratch, build the basics.
- **Levels 2-3:** Structuring workshops. They have intuition, the workshop gives it form.
- **Levels 3-4:** Refinement workshops. Foundations exist, sharpen and pressure-test.

### Step 4: Select and rank workshops

Match the dimension + maturity level to the workshop catalog. Rank by:

1. **Relevance:** How directly does this workshop address the stated challenge?
2. **Readiness:** Is the company at the right maturity level for this workshop?
3. **Dependencies:** Does this workshop need another one first?
4. **Impact:** Which workshop would move the needle most given the company's situation?

### Step 5: Present the recommendation

A recommendation includes:
- **Primary workshop:** The single best workshop for this situation
- **Why this one:** The specific connection between their challenge and this workshop
- **What it will produce:** Concrete outputs they'll walk away with
- **Facilitation level:** Can they run it themselves, or would a facilitator help?
- **Format fit:** If it works as a standalone 60-90 min session, note that
- **What's not recommended and why:** Brief explanation of why other workshops aren't the right fit right now
- **What comes after:** The natural next workshop or action after this one

---

## Challenge-to-workshop mapping

Quick reference for the most common challenge patterns:

| Challenge pattern | Primary workshop | Secondary |
|------------------|-----------------|-----------|
| "We can't explain what we do" | Positioning | Strategic Clarity (if purpose is also unclear) |
| "We don't know our customer" | ICP Discovery | - |
| "The team disagrees on direction" | Stakeholder Alignment | Strategic Clarity |
| "We don't know our competition" | Competitive Landscape | Positioning (to sharpen against competitors) |
| "Growth feels random" | Growth Channel | ICP Discovery (if targeting is unclear) |
| "We're making assumptions we haven't tested" | Assumption Mapping | - |
| "We need strategic clarity" | Strategic Clarity | - |
| "We're launching something new" | Strategic Clarity or ICP Discovery | Assumption Mapping |
| "We're preparing for fundraising" | Strategic Clarity | Positioning, ICP Discovery |
| "Multiple things feel broken" | Stakeholder Alignment (first) | Then targeted workshops per gap |

---

## Workshop sequencing principles

When recommending multiple workshops:

1. **Strategic Clarity first** if the company's purpose or direction is unclear. Everything else depends on it.
2. **ICP before Positioning.** You need to know who you're talking to before you can craft the message.
3. **Positioning before Competitive Landscape.** You need your own positioning clear before you can position against others.
4. **Foundation dimensions (1-3) before execution dimensions (7-8).** Growth strategy without strategic clarity produces busy work.
5. **Stakeholder Alignment early** when there's visible misalignment. Other workshops won't stick if the team isn't on the same page.
6. **Assumption Mapping** fits anywhere in the sequence. It's especially useful early (to de-risk) or late (to validate).

---

## Facilitation levels

Each workshop has a facilitation level that indicates who can run it effectively:

| Level | Who runs it | What it means |
|-------|------------|---------------|
| **Self-serve** | The team, using the workshop guide | The guide provides enough structure for the team to run through it independently. Claude can help with preparation and follow-up. |
| **Guided** | A facilitator with strategic context | Benefits from someone who can read the room, push back on assumptions, and adjust the flow. The guide provides the structure; the facilitator provides the judgment. |
| **Expert** | An experienced strategic facilitator | The workshop involves complex dynamics, sensitive topics, or decisions that need an outside perspective to be made honestly. |

Facilitation level is a recommendation, not a requirement. A strong team can self-facilitate a "guided" workshop. But the output quality will generally be higher with the recommended facilitation level.

---

## Connecting to the Startup format

Some workshops in the catalog naturally fit a focused 60-90 minute format. These map directly to a standalone entry-point session for founders or teams who want to get one thing right before committing to a larger engagement.

When a recommendation fits this format, note it:
- The workshop can be run as a single focused session
- It's a low-commitment way to test the framework
- If the session reveals broader gaps, those can be addressed in subsequent workshops or a more comprehensive engagement

The escalation path: one focused session proves the value, then a broader engagement addresses the full set of gaps.
