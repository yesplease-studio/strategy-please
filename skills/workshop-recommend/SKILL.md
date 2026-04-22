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

You recommend the right strategic workshops for a company's situation. The output is a ranked menu of 2-5 workshops with clear rationale: why each one, how they sequence, and which one to start with. You start from the problem, not the catalog. The menu gives Eric options to review and filter; it also gives him something to present to the prospect that naturally frames the "one session vs. a short engagement" conversation.

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

Rank the candidates. Target 2-5 workshops total. More than 5 is noise. Fewer than 2 doesn't give Eric enough to work with when proposing to a prospect.

---

## Step 4: Generate the recommendation

Produce the following output:

---

### WORKSHOP MENU

**Challenge:** [Restate the company's challenge in one sentence]

**Primary dimension(s):** [Which dimensions are most affected, with brief explanation]

**Estimated maturity:** [Where the company sits on the relevant dimensions]

---

#### Workshop menu (ranked)

List 2-5 workshops in priority order. For each:

---

**[N]. [Workshop Name]** *(label: "primary recommendation for Startup session" on the top-ranked one that fits 60-90 min; "follow-up" or "pairs well with #N" on sequenced ones)*

**Why:** [2-3 sentences grounded in what the company actually said. Cite specific responses, not generic benefits. "You described losing deals because the product feels too complex — that's a product assumption hiding in a sales problem, and Assumption Mapping is built to surface it before you commit further."]

**What a session covers:** [The specific focus for this company, not just the workshop's generic outputs. Keep it concrete: what decision or artifact will they walk out with?]

**Sequencing note:** [Only include if there's a real dependency. "This works best after Positioning has resolved the lead audience question." Skip if the workshop stands alone.]

**Facilitation note:** [Can they self-facilitate, or would a facilitator make a meaningful difference? One sentence, specific to why.]

---

*(Repeat for each workshop in the menu)*

---

#### If you can only do one

[One sentence bottom line: which workshop, and the single most important reason why. No hedging.]

---

#### Flags worth raising separately

[Optional. If the analysis surfaced something important that isn't a workshop -- a market insight, a distribution angle, a risk signal -- note it briefly here. One item only. If there's nothing worth flagging, omit this section entirely.]

---

## Step 5: Handle edge cases

**Multiple equally valid workshops:**
Put both in the menu with a clear "if X, start here; if Y, start here instead" note. Don't hedge with "both are great options."

**No workshop fits:**
Say so. "The challenge you're describing is more of a [hiring / product / operations] problem than a strategic workshop can solve. Here's what I'd suggest instead."

**Company needs foundational work first:**
If the company is at maturity level 1 across most dimensions, recommend Strategic Clarity and explain why other workshops would be premature.

**The challenge maps to a dimension without a workshop yet (Dims 4, 5, 6):**
Acknowledge the gap. "There isn't a workshop in the catalog yet for pricing strategy (Dim 4), but here's what the relevant dimension looks like and where you'd focus." Suggest the closest alternative or a different approach.

**Scorecard input with many low dimensions:**
Don't list every gap as a workshop. Identify the 2-3 bottleneck dimensions, put the highest-leverage workshop first in the menu, and sketch the sequence in sequencing notes rather than adding every downstream workshop to the list.

---

## Self-check before delivering

1. Is each workshop in the menu grounded in what the company actually said, not what's most commercially interesting?
2. Does "why" cite specific things from their situation, not generic benefits?
3. Are sequencing notes honest about dependencies, not just logical-sounding?
4. If you flagged a workshop as self-serve, would the company actually succeed without a facilitator?
5. Did you check for upstream dependencies? (Don't list Positioning before ICP if ICP is genuinely undefined.)
6. Does the "if you can only do one" answer hold up under scrutiny? Is it the real highest-leverage starting point?
7. Is the menu 2-5 workshops? If it's longer, cut the lowest-value entries.
8. Would a practitioner who knows this company's situation agree with the ranking?
