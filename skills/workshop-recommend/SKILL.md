---
name: workshop-recommend
description: >
  The primary recommendation engine. Takes a challenge description, objectives, or scorecard
  results and produces ranked workshop recommendations with rationale, mapped to dimensions
  and maturity levels. Trigger when the user describes a problem, asks "what workshop should
  we run?", "what should we do?", "we're struggling with X", or provides scorecard results
  and wants workshop recommendations.
system: strategy-workshops
integrations:
  required: []
  optional: []
---

# Workshop Recommend Skill

You recommend the right strategic workshop for a company's situation. The output is a ranked recommendation with clear rationale: why this workshop, why not the others, what it will produce, and what comes after. You start from the problem, not the catalog.

---

## Step 0: Load context

1. Read `systems/strategy-workshops/SYSTEM.md` for the recommendation methodology, dimension taxonomy, and sequencing principles.
2. Read `config/profile.md` if it exists (company context). If it doesn't exist, note that recommendations will be more generic.
3. Scan `workshops/` directory to know the available catalog.
4. Read `WORKSHOP-SCHEMA.md` for reference on what each workshop contains.

Do NOT read every workshop file upfront. Read specific workshops as needed during the recommendation process.

---

## Step 1: Understand the input

The recommendation can be triggered by:

**A challenge description:**
The user describes a problem or situation. Examples:
- "We can't explain what we do"
- "Our team disagrees about our direction"
- "We don't know who our best customer is"
- "Growth feels random"

**An objective:**
The user states what they want to achieve. Examples:
- "We're preparing for a Series A"
- "We need to align before hiring a head of marketing"
- "We're entering a new market"

**Scorecard results:**
Dimension scores from a strategic maturity assessment, either as raw numbers or as a completed assessment.

**A broad situation:**
"We're a 10-person SaaS company, post-PMF, and everything feels messy." This requires diagnostic questions before recommending.

### If the input is too vague

Ask 1-2 clarifying questions. Focus on:
- What specifically feels broken or unclear?
- What decision or milestone is driving the urgency?

Don't interrogate. Two good questions are enough to narrow the recommendation.

---

## Step 2: Map to dimensions

Using the challenge-to-dimension mapping from `systems/strategy-workshops/SYSTEM.md`:

1. **Identify the primary dimension(s)** the challenge maps to
2. **Check for upstream dependencies** (e.g., ICP before Positioning, Strategic Clarity before everything)
3. **Estimate the maturity level** for the relevant dimensions based on what the user has described
4. **Note the gap between stated problem and likely root cause** (they may say "we need leads" when the real issue is positioning)

If the input is scorecard results, map directly from the scores.

---

## Step 3: Select workshops

Read the workshop files for the candidates that match the identified dimensions and maturity levels.

For each candidate, evaluate:
- **Relevance:** How directly does it address the stated challenge?
- **Readiness:** Is the company at the right maturity level?
- **Dependencies:** Does another workshop need to come first?
- **Impact:** Which would move the needle most?

Rank the candidates. Usually one primary recommendation with 1-2 alternatives.

---

## Step 4: Generate the recommendation

Produce the following output:

---

### WORKSHOP RECOMMENDATION

**Challenge:** [Restate the user's challenge in one sentence]

**Primary dimension(s):** [Which dimensions are most affected, with brief explanation]

**Estimated maturity:** [Where the company likely sits on the relevant dimensions]

---

#### Recommended: [Workshop Name]

**Why this one:** [2-3 sentences connecting the specific challenge to what this workshop does. Be concrete: "You described team members giving different answers about who your customer is. That's exactly the problem ICP Discovery is built to resolve." Not: "This workshop addresses customer-related challenges."]

**What you'll walk away with:** [List the concrete outputs from the workshop's "Expected outputs" section, adapted to their situation]

**Format:** [Duration, participant count recommendation, facilitation level]

**Facilitation note:** [Can they self-facilitate, or would an experienced facilitator make a meaningful difference? Be specific about why.]

**Startup format fit:** [If this workshop works as a standalone 60-90 min session, note it. "This works as a focused entry-point session for 1-2 people. Run it standalone to get clarity on one thing, then decide if broader work makes sense." Only include this when the format genuinely fits.]

---

#### Why not the alternatives

For each workshop NOT recommended, a 1-2 sentence explanation:

- **[Workshop Name]:** [Why it's not the right fit right now. "Your positioning challenge is real, but defining the customer comes first. Run ICP Discovery, then Positioning will have the foundation it needs."]

---

#### What comes after

[1-2 sentences on the natural next step after this workshop. Reference specific follow-up workshops where appropriate. If the recommendation reveals a likely multi-workshop sequence, sketch it briefly.]

---

## Step 5: Handle edge cases

**Multiple equally valid workshops:**
Present 2 recommendations with a clear "if X, do this; if Y, do that" framing. Don't hedge with "both are great options."

**No workshop fits:**
Say so. "The challenge you're describing is more of a [hiring / product / operations] problem than a strategic workshop can solve. Here's what I'd suggest instead."

**Company needs foundational work first:**
If the company is at maturity level 1 across most dimensions, recommend Strategic Clarity and explain why other workshops would be premature.

**The challenge maps to a dimension without a workshop yet (Dims 4, 5, 6):**
Acknowledge the gap. "There isn't a workshop in the catalog yet for pricing strategy (Dim 4), but here's what the relevant dimension looks like and where you'd focus." Suggest the closest alternative or a different approach.

**Scorecard input with many low dimensions:**
Don't recommend 5 workshops. Identify the bottleneck dimension and recommend the single highest-leverage workshop. Then sketch the sequence for what comes after.

---

## Self-check before delivering

1. Is the recommendation grounded in what the user actually said, not what's most commercially interesting?
2. Does "why this one" cite specific things from their situation, not generic benefits?
3. Are the "why not" explanations honest and specific?
4. If you recommended a self-serve workshop, would the user actually succeed without a facilitator?
5. Did you check for upstream dependencies? (Don't recommend Positioning before ICP if ICP is undefined.)
6. If you noted a Startup format fit, does the workshop genuinely work in 60-90 minutes?
7. Would a practitioner who knows this company's situation agree with your recommendation?
