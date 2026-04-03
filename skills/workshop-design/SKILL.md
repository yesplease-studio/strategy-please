---
name: workshop-design
description: >
  Takes a recommended workshop and the company profile, produces a tailored session plan.
  Adapts the generic workshop to the specific company: customized questions, participant
  brief, pre-work checklist, and expected outputs. Trigger when the user says "design the
  session", "prepare the workshop", "tailor this for us", "build the session plan", or
  has received a recommendation and wants to prepare for the actual session.
system: strategy-workshops
integrations:
  required: []
  optional: []
---

# Workshop Design Skill

You take a workshop from the catalog and adapt it for a specific company. The output is a ready-to-run session plan: tailored agenda, company-specific questions, participant brief, pre-work checklist, and expected outputs. The generic workshop becomes a specific engagement.

---

## Step 0: Load context

1. Read `systems/strategy-workshops/SYSTEM.md` for methodology context.
2. Read `config/profile.md` for the company profile. **This skill requires a company profile.** If none exists, ask the user to set one up first (see `SETUP.md`), or gather minimum context: what the company does, who the customers are, and what the workshop should focus on.
3. Read the specific workshop file from `workshops/` that's being designed.
4. Read `WORKSHOP-SCHEMA.md` for reference.

---

## Step 1: Confirm the workshop and objectives

Before designing, confirm:

1. **Which workshop:** Confirm the specific workshop from the catalog. If the user hasn't been through `workshop-recommend`, briefly validate that this workshop fits their situation.
2. **Session objectives:** What does the company specifically want to walk away with? The generic workshop has standard outputs. The tailored version may need to emphasize or de-emphasize certain areas.
3. **Participants:** Who will be in the room? Names, roles, and what perspective each person brings. This affects which exercises to emphasize and how to frame the questions.
4. **Format constraints:** Any changes to the standard format? Shorter time, remote vs. in-person, larger group?

---

## Step 2: Tailor the session

For each section of the workshop, adapt to the company's context:

### Agenda adaptation

- Adjust time allocations based on what's most relevant for this company
- If certain exercises are less relevant given the company's maturity, note what to shorten or skip
- If the company has strong existing context (e.g., they already have customer data for ICP Discovery), adjust the flow to build on what exists rather than starting from scratch
- Add or modify transitions based on the participant group

### Question customization

- Take the generic "key prompts" from each exercise and rewrite them using the company's actual context
- Reference specific products, customers, competitors, or situations from the company profile
- Add follow-up probes based on known gaps or tensions from the profile
- Example: Generic: "Who is your best customer?" Tailored: "You mentioned [Company X] as your strongest account. What makes them different from [Company Y] where the relationship has been harder?"

### Participant dynamics

- Note which participants are likely to have strong opinions on which topics
- Flag potential alignment issues (e.g., "The founder and CTO may have different views on ICP. The Pattern Wall exercise should surface this constructively.")
- Suggest who should lead which exercise (if self-facilitating)

---

## Step 3: Generate the session plan

Produce the following output:

---

### SESSION PLAN

**Workshop:** [Workshop name]
**Company:** [Company name]
**Date:** [If known]
**Duration:** [Adjusted duration]
**Participants:** [Names and roles]
**Facilitation:** [Who's facilitating]
**Location:** [In-person / Remote / Hybrid]

---

#### Objectives

[2-3 bullet points: what the company specifically needs to walk away with. Concrete, not generic.]

---

#### Pre-work checklist

What participants should do or bring before the session:

- [ ] [Specific pre-work item, e.g., "Review the current homepage and note one thing you'd change"]
- [ ] [e.g., "Think of your single best and single worst customer. Be ready to tell the story."]
- [ ] [e.g., "Bring any existing customer data: NPS results, churn analysis, win/loss notes"]
- [ ] [Any documents to read in advance]

Keep pre-work to 15-30 minutes maximum. More than that and people won't do it.

---

#### Tailored agenda

| Time | Block | Purpose | Notes |
|------|-------|---------|-------|
| [time] | [block] | [purpose] | [Company-specific facilitation notes] |
| ... | ... | ... | ... |

---

#### Company-specific questions

For each exercise, the tailored prompts that reference the company's actual context:

**Exercise: [Name]**
- [Tailored question 1, referencing company specifics]
- [Tailored question 2]
- [Follow-up probe based on known gaps]

---

#### Participant brief

A one-page summary to share with participants before the session:

**What this is:** [1 sentence explaining the workshop in plain language]
**Why we're doing this:** [1-2 sentences connecting to the company's specific situation]
**What to expect:** [Format, duration, what they'll do]
**What we'll produce:** [Specific outputs in concrete terms]
**How to prepare:** [Summary of pre-work]

---

#### Expected outputs (tailored)

[Adapted from the workshop's generic outputs, made specific to the company. "A prioritized ICP with qualifying criteria" becomes "A clear primary ICP definition that resolves the current tension between targeting [segment A] vs. [segment B], with criteria the sales team can apply to every new lead."]

---

#### Facilitator notes

[If facilitation is guided or expert: specific notes for the facilitator about this company's dynamics, where to push, where to hold back, potential sensitive topics, and how to handle likely disagreements.]

---

## Step 4: Offer follow-up

After generating the session plan, offer:

- "Want me to draft the participant brief as a standalone document you can share?"
- "Should I prepare a follow-up template for capturing decisions during the session?"
- "Want me to outline the board layout tailored to your company?" (references the Board layout section)

---

## Self-check before delivering

1. Does every tailored question reference something specific from the company profile?
2. Is the pre-work realistic? (Under 30 minutes, specific, actionable)
3. Does the participant brief explain the value in terms the participants would care about, not consulting language?
4. Are the facilitator notes honest about potential dynamics? (Alignment gaps, strong personalities, sensitive topics)
5. Do the expected outputs connect to the company's stated objectives, not just the generic workshop outputs?
6. Is the time allocation realistic for the adjusted agenda?
7. If this is a remote session, have you addressed the facilitation differences? (Shorter exercises, more structure, different board tools)
