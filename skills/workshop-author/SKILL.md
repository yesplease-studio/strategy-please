---
name: workshop-author
description: >
  Creates new workshop entries for the catalog using the standard schema. Takes a description
  of the workshop concept and produces a complete workshop file following WORKSHOP-SCHEMA.md.
  Validates coverage across dimensions, maturity levels, and facilitation tiers. Trigger
  when the user says "create a workshop", "author a new workshop", "add a workshop to the
  catalog", "I want to build a workshop for X", or provides a concept for a new workshop format.
system: strategy-workshops
integrations:
  required: []
  optional: []
---

# Workshop Author Skill

You create new workshops for the strategy-please catalog. The output is a complete workshop file that follows `WORKSHOP-SCHEMA.md`, ready to add to the `workshops/` directory. You ensure the workshop covers all required sections, maps correctly to the dimension taxonomy, and fills a genuine gap in the catalog.

---

## Step 0: Load context

1. Read `WORKSHOP-SCHEMA.md` for the required format and authoring checklist.
2. Read `systems/strategy-workshops/SYSTEM.md` for the dimension taxonomy and maturity levels.
3. Scan `workshops/` to understand the existing catalog and identify coverage gaps.
4. Read 1-2 existing workshop files from `workshops/` as quality benchmarks.

---

## Step 1: Understand the concept

The user provides a workshop idea. This can range from a single sentence ("a pricing strategy workshop") to a detailed brief.

Clarify:
1. **What strategic challenge does this workshop address?** Map to specific dimensions.
2. **What maturity level is the target audience?** Companies just starting (1-2), developing (2-3), or refining (3-4)?
3. **What format?** 60-min, 90-min, or half-day? What drives the length?
4. **Who's in the room?** How many participants, what roles?
5. **What should participants walk away with?** Concrete outputs, not learning objectives.
6. **What facilitation level?** Can a team self-facilitate, or does it need a guide?

Don't ask all of these as a list. Infer what you can from the concept description and ask about what's genuinely unclear.

---

## Step 2: Validate the concept

Before authoring, check:

**Catalog fit:**
- Does this workshop fill a gap, or does it overlap significantly with an existing workshop?
- If it overlaps, is the differentiation clear? (Different maturity level, different audience, different format?)

**Dimension coverage:**
- Does this map to dimensions that are underserved in the current catalog?
- Is the dimension mapping accurate? (A "pricing workshop" is Dim 4, not Dim 2.)

**Scope:**
- Is the workshop scope achievable in the stated format? (A half-day workshop can cover 4-5 exercises. A 60-min session can cover 2-3.)
- Is the scope narrow enough to produce concrete outputs, or does it try to do too much?

If the concept has issues, raise them before writing: "This overlaps significantly with [existing workshop]. Here's how I'd differentiate it..." or "The scope is too broad for 90 minutes. I'd suggest focusing on [subset]."

---

## Step 3: Author the workshop

Write the complete workshop file following every section in `WORKSHOP-SCHEMA.md`:

### Frontmatter
- Choose a descriptive `id` slug: `ws-<descriptive-name>`
- Map `dimensions` accurately to the taxonomy
- Set `maturity_target` to the realistic range (most workshops work across 2-3 levels, not all 5)
- Set the `format` based on scope
- Set `participants` to a realistic range
- Set `facilitation` to the minimum level needed

### When to run this
- Write 4-5 concrete, recognizable situations (not abstract criteria)
- The reader should think "that's us" when the workshop fits
- Include the maturity level context

### What participants will answer
- 4-6 strategic questions that represent the real work
- These are the "so what" questions, not process steps
- Each question should make a founder pause and think

### Agenda
- Time blocks that add up to the stated format
- Each block has a clear purpose
- Include breaks for half-day workshops
- Opening and closing blocks included

### Exercises
- 3-5 exercises depending on format length
- Each exercise: what it is, why it matters, key prompts, what it produces
- Prompts should be specific enough to drive real conversation
- Outputs should be concrete artifacts, not "understanding" or "alignment"

### Expected outputs
- Specific, concrete artifacts
- Name the format: "a prioritized list of..." not "clarity on..."
- Usually 3-5 outputs

### What typically comes next
- Connect to other workshops in the catalog
- Include non-workshop follow-ups (decisions, document updates, team communication)

### Board layout
- Detailed enough for a facilitator to build from
- Frame names, sections, sticky note prompts
- Visual hierarchy and grouping

---

## Step 4: Validate the output

Run through the authoring checklist from `WORKSHOP-SCHEMA.md`:

- [ ] Frontmatter complete with all required fields
- [ ] `dimensions` accurately mapped
- [ ] `maturity_target` realistic
- [ ] "When to run this" describes recognizable situations
- [ ] "What participants will answer" contains real strategic questions
- [ ] Agenda time blocks add up to format duration
- [ ] Exercises have clear inputs, prompts, and outputs
- [ ] Expected outputs are concrete and specific
- [ ] "What typically comes next" connects to the catalog
- [ ] Board layout is detailed enough to build from

---

## Step 5: Present and save

Show the complete workshop to the user. Ask:
- Does the scope feel right?
- Are the exercises the right ones for this concept?
- Anything missing from the expected outputs?

After confirmation, save to `workshops/ws-<id>.md`.

If the new workshop affects the recommendation logic (e.g., fills a previously uncovered dimension), note that `systems/strategy-workshops/SYSTEM.md` may need updating.

---

## Self-check before delivering

1. Would a practitioner who runs workshops read this and say "I could facilitate this tomorrow"?
2. Are the exercises genuinely different from each other, or are they variations on the same activity?
3. Is the scope achievable in the stated time? (Common mistake: trying to pack too much into 90 minutes)
4. Do the expected outputs justify the time investment? Would a participant feel the session was worth it?
5. Is the facilitation level honest? If you marked it "self-serve," could a team actually run this without outside help?
6. Does this workshop add something the catalog didn't have before, or is it a reskin of an existing one?
7. Is the language practitioner-grade? No consulting jargon, no filler, no vague learning objectives.
