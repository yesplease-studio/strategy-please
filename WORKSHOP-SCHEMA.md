# Workshop Schema

Every workshop in the catalog follows this structure. Use this as the reference when authoring new workshops or reviewing existing ones.

---

## Frontmatter

```yaml
---
id: ws-<descriptive-slug>
name: Workshop Name
dimensions: [1, 3]           # Which scorecard dimensions this addresses
maturity_target: [1, 2, 3]   # What maturity levels benefit most (1-5 scale)
format: half-day | 90-min | 60-min
participants: 3-8
facilitation: self-serve | guided | expert
---
```

**Field reference:**

| Field | Required | Description |
|-------|----------|-------------|
| `id` | Yes | Unique workshop identifier. Use descriptive slugs: `ws-icp-discovery`, `ws-positioning` |
| `name` | Yes | Human-readable workshop name |
| `dimensions` | Yes | Array of dimension numbers (1-8) this workshop addresses |
| `maturity_target` | Yes | Array of maturity levels (1-5) where this workshop is most effective |
| `format` | Yes | Session length: `half-day`, `90-min`, or `60-min` |
| `participants` | Yes | Recommended participant count or range |
| `facilitation` | Yes | Minimum facilitation level: `self-serve`, `guided`, or `expert` |

---

## Sections

### When to run this

Challenge patterns and signals that point to this workshop. Written as recognizable situations, not abstract criteria. The reader should think "that's us" when the workshop fits.

Include:
- 3-5 concrete situations or symptoms
- What the company typically says or feels when this workshop is needed
- What stage or maturity level this is most relevant for

### What participants will answer

The core questions the workshop drives toward. These are the strategic questions that matter, not facilitation mechanics. Usually 3-6 questions that represent the real work of the session.

### Agenda

High-level session structure with time blocks and the purpose of each block. Enough to understand the flow, not enough to replace a facilitator.

Format:
```
| Time | Block | Purpose |
|------|-------|---------|
| 0:00 - 0:15 | Opening | Set context, align on objectives |
| ... | ... | ... |
```

### Exercises

For each exercise in the workshop:
- **What it is** and **why it matters** (one sentence each)
- **Key questions or prompts** that drive the exercise
- **What it produces** (the concrete output)

### Expected outputs

Concrete artifacts and decisions the workshop should produce. Be specific: "a prioritized list of 3 ICP segments with qualifying criteria" not "ICP clarity."

### What typically comes next

Follow-up workshops, decisions to make, or work to do after the session. Connect to other workshops in the catalog where relevant.

### Board layout

Description of the visual workspace layout for running this session: frames, sections, sticky note prompts. Used by facilitators to build the board manually. In a future release, this section feeds automated board generation.

Include:
- Frame names and arrangement
- What goes in each section
- Sticky note prompt text
- Any visual hierarchy or grouping

---

## Authoring checklist

When creating a new workshop, verify:

- [ ] Frontmatter is complete with all required fields
- [ ] `dimensions` accurately reflects which dimensions the workshop addresses
- [ ] `maturity_target` is realistic (most workshops don't work at all 5 levels)
- [ ] "When to run this" describes recognizable situations, not abstract criteria
- [ ] "What participants will answer" contains real strategic questions, not process steps
- [ ] Agenda time blocks add up to the stated format duration
- [ ] Exercises have clear inputs, prompts, and outputs
- [ ] Expected outputs are concrete and specific
- [ ] "What typically comes next" connects to the broader catalog
- [ ] Board layout is detailed enough for a facilitator to build from
