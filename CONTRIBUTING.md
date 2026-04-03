# Contributing to strategy-please

Workshops are the core unit of value in this project. Contributions that expand the catalog, improve existing workshops, or refine the recommendation logic are welcome.

---

## What makes a good workshop

Before submitting, check that your workshop:

1. **Addresses a real strategic challenge.** It should map to one or more of the eight dimensions and solve a problem that founders and teams actually face. "Thought leadership brainstorm" is too vague. "Content Strategy Workshop: building a publishing system that serves your ICP" is specific.

2. **Follows the schema.** Every workshop uses the format in [WORKSHOP-SCHEMA.md](WORKSHOP-SCHEMA.md). All sections are required. The authoring checklist at the bottom of the schema is your acceptance criteria.

3. **Produces concrete outputs.** Participants should walk away with artifacts they can use: a documented ICP, a positioning statement, a prioritized channel plan. "Better understanding of X" is not an output.

4. **Respects the time budget.** A 90-minute workshop can support 3-4 exercises with real depth. A half-day can support 5-6. If your agenda is packed tighter than that, the exercises are too shallow.

5. **Fills a catalog gap.** Check the existing catalog in `workshops/` before writing. If your concept overlaps significantly with an existing workshop, consider improving that workshop instead.

---

## How to contribute a workshop

### Option 1: Use the workshop-author skill

If you have Claude Code, open this repo and say:

> "I want to create a workshop for [concept]"

The `workshop-author` skill will guide you through the process, validate your concept against the catalog, and produce a complete workshop file.

### Option 2: Write it manually

1. Copy the structure from [WORKSHOP-SCHEMA.md](WORKSHOP-SCHEMA.md)
2. Fill in every section
3. Run through the authoring checklist before submitting
4. Submit a pull request to `workshops/`

### File naming

Workshop files follow the pattern: `ws-<descriptive-slug>.md`

Examples: `ws-icp-discovery.md`, `ws-pricing-strategy.md`, `ws-content-engine.md`

---

## Review criteria

Workshop pull requests are reviewed against:

| Criterion | What we're checking |
|-----------|-------------------|
| **Schema compliance** | All required sections present and complete |
| **Dimension accuracy** | The `dimensions` field correctly maps to the taxonomy |
| **Maturity targeting** | The `maturity_target` is realistic for the workshop's scope |
| **Exercise quality** | Prompts are specific enough to drive real conversation, not generic brainstorming |
| **Output concreteness** | Expected outputs are artifacts, not "understanding" or "alignment" |
| **Time realism** | Agenda time blocks add up correctly and each exercise has enough time to produce its output |
| **Catalog fit** | The workshop fills a genuine gap rather than duplicating existing coverage |
| **Board layout** | Detailed enough for a facilitator to build the workspace in 15-20 minutes |

---

## Improving existing workshops

Improvements to existing workshops are also welcome:

- **Exercise refinements:** Better prompts, clearer outputs, more effective sequencing
- **Board layout improvements:** More detailed specs, better visual structure
- **"When to run this" additions:** New recognizable situations that point to the workshop
- **"What typically comes next" connections:** Better links to other workshops in the catalog

For improvements, open a pull request with a clear description of what changed and why.

---

## Improving the recommendation logic

The recommendation methodology lives in `systems/strategy-workshops/SYSTEM.md`. If you've used the system and found that the challenge-to-workshop mapping missed a common pattern, submit a PR adding the pattern to the mapping table.

---

## What's out of scope

- **Operational workshops** (retros, sprint planning, design sprints) — strategy-please covers strategic workshops only
- **Detailed facilitation guides** — the catalog provides the structure and questions. How to read the room, manage dynamics, and adapt in real-time is the facilitator's expertise.
- **Workshop execution tooling** — timers, voting tools, participant management. Use existing tools for these.

---

## Code of conduct

Be direct, be specific, be helpful. The same voice that works for the workshops works for the contribution process: practitioner-grade, no filler, no ego.
