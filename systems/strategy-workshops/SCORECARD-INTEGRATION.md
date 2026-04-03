# Scorecard Integration

Direct pipeline from strategic maturity assessment results into the workshop recommendation engine. A scorecard result becomes a workshop program recommendation without manual re-entry.

---

## How it works

The strategy-please recommendation engine accepts scorecard results as a first-class input. When a user provides dimension scores (from a self-assessment, a facilitated assessment, or an existing assessment document), the system maps those scores directly to workshop recommendations.

This eliminates the intermediate step of describing challenges in words. The scores are the diagnostic; the workshops are the prescription.

---

## Input formats

### Format 1: Raw scores

The user provides scores directly:

```
1. Strategic Clarity: 2
2. Positioning and Messaging: 1.5
3. ICP Definition and Focus: 2
4. Revenue Model and Pricing: 3
5. Content and Thought Leadership: 1
6. Sales Process and Conversion: 2.5
7. Competitive Awareness: 1.5
8. Growth Engine and Distribution: 1
```

### Format 2: Assessment document

The user provides or references an assessment file (e.g., `assessment.md` from a company profile). The system reads the scorecard table and extracts dimension scores, evidence, and key gaps.

### Format 3: Partial scores

Not all dimensions need to be scored. The system works with whatever scores are available and notes which dimensions lack data.

### Format 4: Conversational

The user describes their assessment informally: "We're pretty good on strategy and pricing, but our ICP is vague, positioning is weak, and we have no growth engine." The system maps this to approximate scores and confirms before proceeding.

---

## Processing logic

### Step 1: Parse and validate scores

- Extract scores for each dimension (1-5 scale, half-points allowed)
- Flag any scores that seem inconsistent (e.g., high positioning with low ICP, since ICP is upstream)
- If evidence is available, note it for use in the recommendation rationale

### Step 2: Identify the pattern

Apply the pattern recognition from the scorecard methodology:

| Pattern | What it means | Recommendation approach |
|---------|--------------|----------------------|
| **Flat low scores** (most dims 1-2) | Everything needs work | Single highest-leverage workshop, not a massive program |
| **One dimension far below others** | Clear bottleneck | Workshop targeting that dimension |
| **High strategy, low execution** (Dims 1-3 high, 5-8 low) | Thinking without doing | Execution-oriented workshop (Growth Channel) or non-workshop intervention |
| **High execution, low strategy** (Dims 5-8 high, 1-4 low) | Activity without direction | Strategic Clarity first |
| **Strong outlier** (one dim at 4-5, rest at 2-3) | One strength, many gaps | Use the strength as leverage; workshop the adjacent dimension |
| **Multiple mid-range** (most dims at 2.5-3.5) | Foundations exist, nothing sharp | Targeted workshop on the dimension most connected to their current priority |

### Step 3: Map to workshops

For each dimension scoring below 3.5, check if a workshop exists:

| Dimension | Workshop | Available |
|-----------|----------|-----------|
| 1. Strategic Clarity | Strategic Clarity Workshop | Yes |
| 2. Positioning and Messaging | Positioning Workshop | Yes |
| 3. ICP Definition and Focus | ICP Discovery Workshop | Yes |
| 4. Revenue Model and Pricing | Pricing Strategy Workshop | Yes |
| 5. Content and Thought Leadership | Content Strategy Workshop | Yes |
| 6. Sales Process and Conversion | Sales Process Workshop | Yes |
| 7. Competitive Awareness | Competitive Landscape Workshop | Yes |
| 8. Growth Engine and Distribution | Growth Channel Workshop | Yes |

Cross-cutting workshops (Stakeholder Alignment, Assumption Mapping) are recommended based on pattern, not dimension score:
- **Stakeholder Alignment:** When multiple dimensions show inconsistent scores or the assessment notes internal disagreement
- **Assumption Mapping:** When the company is about to make a significant investment based on the current assessment, or when confidence in the scores is low

### Step 4: Apply sequencing

If multiple workshops are needed, use the `workshop-chain` skill logic:
1. Respect dimension dependencies (Dim 1 before others, Dim 3 before Dim 2, etc.)
2. Start with the bottleneck (highest-leverage single workshop)
3. Don't recommend more than 3 workshops without the user explicitly asking for a full program

### Step 5: Route to the right skill

Based on the scorecard input:

| Result | Route to |
|--------|----------|
| 1 clear gap | `workshop-recommend` with the dimension pre-identified |
| 2-3 gaps with clear priority | `workshop-recommend` for the top gap, mention the chain opportunity |
| 4+ gaps or request for full program | `workshop-chain` for a sequenced program |
| All dimensions above 3.5 | Honest message: workshops may not be the right intervention |

---

## Integration with external assessments

### From the Yes Please vault

When scorecard results come from the Yes Please strategy system (`systems/strategy/SCORECARD.md`), the dimension taxonomy is identical. Scores map 1:1 with no translation needed.

The assessment file (`companies/<company>/assessment.md`) contains:
- Dimension scores with evidence
- Bottleneck identification
- Recommended engagement type

The scorecard integration uses the scores and evidence but generates its own workshop-specific recommendation. The vault assessment recommends engagement types (Workshop, Fractional, Advisory). The scorecard integration recommends specific workshops within the Workshop engagement type.

### From self-assessments

When users self-assess (e.g., during onboarding via `SETUP.md`), scores may be less calibrated. The system should:
- Note that self-assessment scores tend to be slightly inflated
- Pay attention to the relative pattern (which dimensions are lowest) more than absolute scores
- Suggest validating low-confidence scores through the workshop itself

---

## Output

The scorecard integration produces the same output as `workshop-recommend` or `workshop-chain`, depending on the routing decision. The difference is the input path: scores in, recommendation out, with no intermediate challenge-description step.

The recommendation should reference the specific scores that drove the decision:

> "Your ICP score of 1.5 tells me you have an intuitive sense of who your customer is but nothing documented or tested. That's exactly where ICP Discovery adds the most value. Your positioning score of 1.5 is connected, but ICP comes first because the positioning work needs a defined customer to speak to."
