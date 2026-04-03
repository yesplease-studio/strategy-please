---
name: workshop-chain
description: >
  Sequences multiple workshops into a coherent program. Takes scorecard results, a broad
  challenge description, or multiple identified gaps, and produces an ordered workshop
  sequence with rationale, dependencies, and total time estimate. Trigger when the user
  says "build a workshop program", "what's the full sequence?", "we have multiple gaps",
  "design a workshop series", or has scorecard results showing gaps across multiple dimensions.
system: strategy-workshops
integrations:
  required: []
  optional: []
---

# Workshop Chain Skill

You sequence multiple workshops into a coherent program. The output is an ordered workshop series with clear rationale for the sequence, dependencies between sessions, spacing recommendations, and total time and investment estimate. A company with multiple gaps gets a structured roadmap, not a pile of suggestions.

---

## Step 0: Load context

1. Read `systems/strategy-workshops/SYSTEM.md` for the sequencing principles and dimension dependencies.
2. Read `config/profile.md` if it exists (company context).
3. Scan `workshops/` to know the full catalog.
4. Read `WORKSHOP-SCHEMA.md` for reference.

Do NOT read every workshop file upfront. Read specific ones as needed during sequencing.

---

## Step 1: Understand the gaps

The chain can be triggered by:

**Scorecard results:**
Dimension scores showing gaps across multiple dimensions. This is the cleanest input because the maturity levels are explicit.

**A broad challenge description:**
"We need to get our strategic foundations right." This requires mapping to specific dimensions before sequencing.

**Multiple specific challenges:**
"We don't know our customer AND our positioning doesn't work AND growth is random." Each maps to a dimension.

**Post-recommendation expansion:**
The user received a single workshop recommendation and wants to know "what's the full program?"

### Mapping to dimensions

For each identified gap, determine:
- Which dimension(s) it affects
- The estimated maturity level
- How critical the gap is (blocking other progress, or an isolated weakness?)

---

## Step 2: Apply sequencing principles

Use the sequencing rules from `systems/strategy-workshops/SYSTEM.md`:

1. **Strategic Clarity first** if purpose or direction is unclear (Dim 1 scores low)
2. **ICP before Positioning** (Dim 3 before Dim 2)
3. **Positioning before Competitive Landscape** (Dim 2 before Dim 7)
4. **Foundation dimensions (1-3) before execution dimensions (7-8)**
5. **Stakeholder Alignment early** when visible misalignment exists
6. **Assumption Mapping** fits anywhere, especially useful early (de-risk) or late (validate)

### Dependency checks

For each workshop in the draft sequence, verify:
- Are its upstream dependencies satisfied by earlier workshops in the chain?
- Does it produce outputs that later workshops need?
- Is the maturity level appropriate given what the preceding workshops will have built?

### Pruning

Not every gap needs a workshop. Check:
- Can some gaps be addressed by the outputs of other workshops? (e.g., the Positioning Workshop includes competitive differentiation work, which may partially address Dim 7)
- Are some gaps better addressed through direct work rather than a workshop? (e.g., a company at Dim 5 level 1 may just need to start publishing, not run a workshop about it)
- Is the total program realistic given the company's capacity and timeline?

---

## Step 3: Design the program

Read the workshop files for each selected workshop in the sequence.

For each workshop in the chain, determine:
- **Position in sequence:** Why it goes here, not earlier or later
- **Dependencies:** What it needs from preceding workshops
- **Outputs that feed forward:** What it produces that later workshops will use
- **Spacing:** How much time between this workshop and the next (for implementation, reflection, or pre-work)

---

## Step 4: Generate the program

Produce the following output:

---

### WORKSHOP PROGRAM

**Company:** [Company name, if profile exists]
**Challenge:** [Summary of the overall situation in 1-2 sentences]
**Program duration:** [Total elapsed time, including spacing between workshops]
**Total session time:** [Sum of workshop durations]
**Number of workshops:** [Count]

---

#### Program overview

| # | Workshop | Dimension(s) | Format | Gap it addresses |
|---|----------|-------------|--------|-----------------|
| 1 | [Name] | [Dims] | [Duration] | [1 sentence] |
| 2 | [Name] | [Dims] | [Duration] | [1 sentence] |
| ... | ... | ... | ... | ... |

---

#### Sequence rationale

[2-3 paragraphs explaining why this order. Reference specific dependencies: "ICP Discovery comes before Positioning because the positioning work needs a defined customer to speak to. Without ICP clarity, the positioning exercise produces generic output." This should read as strategic advice, not a process description.]

---

#### Workshop details

For each workshop in the sequence:

**Workshop [#]: [Name]**

- **Why now:** [Why this workshop at this point in the sequence]
- **Depends on:** [Which preceding workshops provide necessary input, or "None, starting point"]
- **Feeds into:** [Which later workshops use this workshop's output]
- **Key focus for this company:** [1-2 sentences adapting the generic workshop to the company's situation]
- **Spacing after:** [Recommended time before the next workshop and why. "2 weeks to implement the ICP definition before building positioning on top of it."]

---

#### What's NOT included (and why)

[For each gap or dimension that was identified but NOT assigned a workshop, explain why. "Dim 5 (Content) scores low, but a workshop isn't the right intervention. Once positioning is clear (Workshop 3), the team should start publishing against the new positioning. We can revisit content strategy as a workshop if progress stalls after 3 months."]

---

#### Entry point option

[If the first workshop in the sequence works as a standalone 60-90 min session, note it. "Workshop 1 (Stakeholder Alignment) works as a standalone entry-point session. Run it first, evaluate the results, and decide whether to commit to the full program. Low risk, immediate value." This creates the escalation path.]

---

#### Total investment

[If facilitator-led, estimate the total time and investment. If self-facilitated, estimate the total time commitment. Frame both options if relevant.]

---

## Step 5: Handle edge cases

**Too many gaps (5+ dimensions low):**
Don't build a 5-workshop program. Identify the 2-3 highest-leverage workshops, present them as Phase 1, and note that Phase 2 can be designed after Phase 1 results are in.

**Only 2 workshops needed:**
A chain of 2 is still a chain if the sequencing matters. Present it simply. Don't inflate to justify the skill.

**Gaps in dimensions without workshops (Dims 4, 5, 6):**
Acknowledge the gap. Suggest non-workshop interventions (direct work, hiring, consulting engagement) and note that workshops for these dimensions are in development.

**Company can't commit to a multi-workshop program:**
Recommend the single highest-leverage workshop (use `workshop-recommend` logic) and note what they'd gain from the full sequence.

---

## Self-check before delivering

1. Does the sequence respect all dependency rules? (No positioning before ICP, no growth before clarity)
2. Is every workshop genuinely necessary, or could some gaps be addressed by outputs of other workshops?
3. Are the spacing recommendations realistic? (Too short: no time to implement. Too long: momentum lost.)
4. Is the total program achievable given the company's capacity and timeline?
5. Did you explain what's NOT included and why? (Shows the recommendation is thoughtful, not exhaustive)
6. Is the entry point option genuinely low-risk and high-value? Would you recommend it with confidence?
7. Does the rationale read as strategic advice, not a process description?
