# Setup Guide

This guide walks you through creating a company profile so strategy-please can give you tailored workshop recommendations. Claude follows this flow during your first conversation.

The whole process takes 5-10 minutes.

---

## How onboarding works

### Step 1: Check for existing context

Ask the user:

> "Do you have any existing documents or context you can share? A website, strategy doc, pitch deck, or company profile you've used with Claude before."

If they provide something:
- Read and extract what you can: what the company does, who it's for, stage, team size, strategic context
- Note what's covered and what's still missing
- Move to Step 2 to fill gaps

If they don't have anything, move straight to Step 2.

### Step 2: Fill gaps conversationally

Based on what's missing from Step 1, ask about:

**What the company does and who it's for**
- What does the company do, in plain language?
- Who are the customers? (Be specific: job title, company type, the problem they have)
- What stage is the company at? (Pre-revenue, early traction, growing, established)
- Roughly how many people are on the team?

**What's working and what feels stuck**
- What's going well right now?
- What feels unclear or broken?
- What decisions are coming up that need strategic clarity?

**Strategic context**
- What does winning look like in 12 months?
- What's been tried before? What worked, what didn't?

Don't ask all of these as a list. Have a conversation. Skip questions where the answer is already clear from Step 1. Follow up on interesting answers.

### Step 3: Write the profile

Once you have enough context, generate `config/profile.md` using the template from `config/_template.md`.

Before saving:
1. Show the user the complete profile
2. Ask if anything needs adjusting
3. Save only after confirmation

### Step 4: First recommendation

After the profile is saved, offer to run a workshop recommendation:

> "Your profile is set up. Want me to suggest which workshop would be most useful based on what you've told me?"

If yes, run the `workshop-recommend` skill.

---

## Notes for Claude

- The goal is a useful profile, not a complete one. Missing fields are fine. Mark them as "Unknown" or "Not discussed" rather than guessing.
- If the user provides a website, read it and extract what you can, but don't treat the website copy as ground truth for strategic clarity. Many companies' websites don't reflect their actual positioning.
- Keep the conversation natural. This is a getting-to-know-you session, not a form to fill out.
- If the user clearly knows what workshop they want and doesn't need a profile, skip onboarding and go straight to the catalog.
