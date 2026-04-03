# Workshop Effectiveness Tracking

A lightweight system for recording which workshops moved which dimensions, building evidence over time for recommendation quality.

---

## Purpose

Every workshop recommendation is a hypothesis: "this workshop will move this dimension for a company at this maturity level." Effectiveness tracking turns those hypotheses into evidence. Over time, the data improves the recommendation engine's accuracy.

---

## How it works

After every workshop debrief (via the `workshop-debrief` skill), the scorecard delta is recorded in the tracking log. Each entry captures what was run, for whom, and what moved.

### Tracking log

File: `tracking/effectiveness-log.md`

Each entry follows this format:

```markdown
## [Date] — [Workshop Name] — [Company (anonymized)]

- **Workshop:** ws-[id]
- **Company stage:** [Early traction / Growing / Established]
- **Participant count:** [N]
- **Facilitation:** [Self-serve / Guided / Expert]
- **Dimensions targeted:** [Dim X, Dim Y]
- **Maturity before:** [Dim X: score, Dim Y: score]
- **Maturity after:** [Dim X: score, Dim Y: score]
- **Delta:** [Dim X: +N, Dim Y: +N]
- **Secondary movements:** [Any dimensions that moved as side effects]
- **Key insight:** [One sentence — the most important thing learned about this workshop's effectiveness]
- **Would recommend again for this profile:** [Yes / Yes with adjustments / No]
- **Adjustments noted:** [If applicable — what would make this workshop more effective for this company profile]
```

### Anonymization

Company names are replaced with descriptive labels: "12-person logistics SaaS (post-seed)" rather than "NordFlow." The tracking log may be reviewed by contributors or used in public discussions about recommendation quality.

---

## What gets tracked

| Data point | Why it matters |
|-----------|---------------|
| Workshop ID | Which workshop was run |
| Company stage | Whether the workshop works differently at different stages |
| Maturity before/after | The actual dimension movement |
| Facilitation level | Whether facilitation quality affects outcomes |
| Participant count | Whether group size affects outcomes |
| Secondary movements | Which workshops produce spillover benefits |
| Would recommend again | The practitioner's subjective assessment |

---

## Analysis patterns

As the log accumulates entries, look for:

### Per-workshop patterns
- Average dimension movement per workshop
- Which maturity levels see the most movement (does ICP Discovery work better at level 1 or level 2?)
- Facilitation effect: do guided workshops produce more movement than self-serve?

### Cross-workshop patterns
- Which workshop sequences produce the most cumulative movement?
- Are there workshops that consistently produce secondary dimension movements?
- Are there company profiles where a workshop consistently underperforms?

### Recommendation quality
- When the system recommended Workshop A, how often was that the right call?
- Are there challenge patterns where the recommendation logic misses?

---

## Feeding back into the system

When patterns emerge from the tracking data:

1. **Update maturity targets.** If a workshop consistently works better at level 2 than level 1, adjust `maturity_target` in the frontmatter.

2. **Update the recommendation logic.** If certain challenge patterns reliably map to workshops the system doesn't currently suggest, add them to the mapping table in `systems/strategy-workshops/SYSTEM.md`.

3. **Adjust facilitation levels.** If a self-serve workshop consistently produces less movement than when facilitated, consider upgrading the facilitation recommendation.

4. **Note effective sequences.** If a specific workshop chain consistently outperforms ad-hoc ordering, codify it in `workflows/`.

---

## Getting started

Create the tracking directory and log:

```
tracking/
  effectiveness-log.md
  README.md (this file)
```

The first entries come from the `workshop-debrief` skill. After generating a debrief, Claude should offer: "Want me to log this to the effectiveness tracker?" and append the entry to the log.

Over time, as entries accumulate, periodic analysis sessions can identify patterns and feed improvements back into the system.
