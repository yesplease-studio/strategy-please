---
name: workshop-debrief
description: >
  Post-workshop processing. Takes session notes, outcomes, and decisions from a completed
  workshop and produces: an updated company profile reflecting what changed, a scorecard
  delta showing which dimensions moved, and a recommended next workshop or follow-up actions.
  Trigger when the user says "debrief the workshop", "process session notes", "what changed
  after the workshop", "update the profile", or provides notes/outcomes from a completed session.
system: strategy-workshops
integrations:
  required: []
  optional: []
---

# Workshop Debrief Skill

You process the results of a completed workshop. The output closes the loop: what was decided, what changed in the company's strategic picture, which dimensions moved, and what should happen next. The debrief turns a session into durable progress.

---

## Step 0: Load context

1. Read `systems/strategy-workshops/SYSTEM.md` for the dimension taxonomy and maturity levels.
2. Read `config/profile.md` for the current company profile.
3. Read the specific workshop file from `workshops/` that was run.
4. If a session plan was designed using `workshop-design`, read it for the tailored objectives and expected outputs.

---

## Step 1: Gather session input

The debrief can be triggered with:

**Session notes:**
Raw notes taken during the workshop. Can be structured (following the agenda) or unstructured (a brain dump after the session).

**A voice memo or transcript:**
The facilitator (or a participant) recorded their observations. Extract decisions, outputs, and observations.

**Photos of the board:**
Screenshots or photos of the Miro board, whiteboard, or sticky notes. Extract the content and map it to the workshop's expected outputs.

**Completed outputs:**
The artifacts the workshop was supposed to produce (ICP definition, positioning statement, etc.) provided directly.

**A verbal summary:**
The user describes what happened conversationally. Ask follow-up questions to fill gaps.

### What to extract

For every debrief, identify:

1. **Decisions made:** What was agreed on? What was resolved?
2. **Outputs produced:** Which of the workshop's expected outputs were actually created? What do they contain?
3. **Surprises:** What came up that wasn't expected? New insights, disagreements surfaced, pivots in thinking.
4. **Unresolved items:** What was supposed to be decided but wasn't? What needs follow-up?
5. **Energy and dynamics:** Where did the conversation catch fire? Where did it stall? (This informs the next recommendation.)

---

## Step 2: Assess the scorecard delta

For each dimension the workshop targeted, assess whether it moved:

**Before score:** Use the estimate from the recommendation or the existing assessment. If no prior score exists, estimate based on what was known before the workshop.

**After score:** Based on the outputs and decisions from the session, where does the dimension sit now?

**What moved it:** The specific output or decision that shifted the score.

**What's still missing:** If the dimension didn't reach the next full level, what gap remains?

### Scoring rules

- A single workshop rarely moves a dimension by more than 1 point. If you're scoring a 2-point jump, double-check.
- The dimension moves when the *output exists and is usable*, not when the conversation happened. "We discussed ICP" is not the same as "we have a documented ICP with qualifying criteria."
- Adjacent dimensions may shift as side effects. An ICP Discovery workshop may slightly improve Positioning (Dim 2) because the team now has customer language. Note these secondary movements.
- If the workshop didn't produce its expected outputs, the dimension may not have moved. Be honest about this.

---

## Step 3: Update the company profile

Based on the workshop outputs, identify what should change in `config/profile.md`:

**Direct updates:**
- New ICP definition from an ICP Discovery workshop
- Updated strategic context from a Strategic Clarity workshop
- New competitive intelligence from a Competitive Landscape workshop
- Revised maturity scores in the scorecard section

**Indirect updates:**
- Customer language that should be added to the profile
- New insights about what's working or what's stuck
- Updated 12-month vision if direction shifted

### Present updates before applying

Show the user:
1. What will change in the profile
2. The old value vs. the new value
3. Why (which workshop output drives the change)

Apply only after confirmation.

---

## Step 4: Generate the debrief

Produce the following output:

---

### WORKSHOP DEBRIEF

**Workshop:** [Workshop name]
**Company:** [Company name]
**Date:** [Session date]
**Participants:** [Who was in the room]
**Facilitated by:** [Self / Facilitator name]

---

#### What was decided

[Bulleted list of concrete decisions made during the session. Each item is a specific, actionable decision, not a topic discussed.]

---

#### Outputs produced

For each expected output from the workshop:

| Output | Status | Summary |
|--------|--------|---------|
| [Expected output 1] | Complete / Partial / Not reached | [1-2 sentence summary of what was produced] |
| [Expected output 2] | ... | ... |

---

#### Scorecard delta

| Dimension | Before | After | What moved it |
|-----------|--------|-------|---------------|
| [Dim name] | [score] | [score] | [1 sentence] |
| ... | ... | ... | ... |

**Net movement:** [Summary: "Dim 3 (ICP) moved from 1.5 to 2.5. The team now has a documented primary ICP with qualifying criteria, up from an intuitive sense of who the customer is."]

---

#### Surprises and new insights

[Anything that came up during the session that wasn't expected. New strategic context, alignment gaps surfaced, pivots in thinking, strong reactions to specific topics. These are often the most valuable outputs of a workshop.]

---

#### Unresolved items

[What was supposed to be decided but wasn't. What needs follow-up. Include why it wasn't resolved if known.]

---

#### Recommended next steps

**Immediate (this week):**
- [Action items from the session with owners]

**Next workshop:** [If the debrief reveals a clear next workshop, recommend it with brief rationale. Reference `workshop-recommend` logic.]

**Follow-up check:** [When to revisit the workshop outputs. "Review the ICP definition after 30 days of sales conversations to see if it holds up."]

---

#### Profile updates

[Summary of what will change in `config/profile.md`, pending user confirmation.]

---

## Step 5: Offer follow-up

After generating the debrief, offer:

- "Want me to update the company profile with these results?" (apply the profile changes)
- "Should I recommend the next workshop based on what we learned?" (run `workshop-recommend`)
- "Want me to design the next session?" (run `workshop-design` for the recommended workshop)

---

## Self-check before delivering

1. Are the decisions listed specific and actionable, or vague summaries of topics discussed?
2. Is the scorecard delta honest? Did the dimension actually move, or did the team just talk about it?
3. Are the profile updates grounded in workshop outputs, not assumptions about what the team will do next?
4. Do the unresolved items include context about why they weren't resolved? (This informs the next session.)
5. Is the next workshop recommendation connected to what happened in this session, not just the next item in a generic sequence?
6. Would the participants read this debrief and say "yes, that captures what happened"?
7. Are the surprises and new insights captured? These are often the most valuable part of the debrief.
