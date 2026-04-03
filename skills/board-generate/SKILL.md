---
name: board-generate
description: >
  Creates pre-built Miro workshop boards from the Board layout section of any workshop
  in the catalog. Generates frames, sticky note prompts, sections, and participant
  instructions via the Miro REST API. Trigger when the user says "create the board",
  "generate the Miro board", "set up the workshop board", "build the board for [workshop]",
  or is preparing for a session and needs the visual workspace ready.
system: strategy-workshops
integrations:
  required:
    - miro
  optional: []
---

# Board Generate Skill

You create pre-built Miro boards for workshops in the catalog. Each workshop's `Board layout` section defines the visual structure. This skill translates that specification into a real Miro board with frames, sections, sticky note prompts, and participant instructions, ready for the facilitator to use.

---

## Step 0: Load context

1. Read the specific workshop file from `workshops/` to get the Board layout section.
2. If a session plan was designed using `workshop-design`, read it for any company-specific adaptations to the board.
3. Verify Miro API access is available. If not, fall back to generating a detailed board specification the facilitator can build manually.

---

## Step 1: Confirm the board

Before generating:

1. **Which workshop:** Confirm the specific workshop from the catalog.
2. **Customization:** Is this a generic board (from the catalog spec) or a tailored board (adapted for a specific company via `workshop-design`)?
3. **Miro team/workspace:** Which Miro workspace should the board be created in?
4. **Participant count:** Adjust the board layout if the participant count differs from the workshop default (e.g., more rows for customer stories if 6 participants instead of 4).

---

## Step 2: Parse the board layout

Extract the board structure from the workshop's `Board layout` section:

### Frame inventory

For each frame described in the layout:
- **Frame name:** The label for the frame
- **Purpose:** What this frame is for (maps to which exercise)
- **Sections within the frame:** Columns, rows, quadrants, or other subdivisions
- **Sticky note prompts:** Pre-populated text for sticky notes that guide participants
- **Visual hierarchy:** How frames relate to each other (sequence, grouping)

### Layout decisions

- **Frame arrangement:** Left-to-right flow matching the agenda sequence
- **Frame sizing:** Larger frames for exercises with more content (Pattern Wall, Positioning Drafts), smaller for summaries
- **Color coding:** Use consistent colors for categories (e.g., green for strengths, red for gaps, yellow for questions)
- **Spacing:** Enough room between frames for the board to feel navigable, not cramped

---

## Step 3: Generate the board via Miro API

### API operations

The Miro REST API supports the following operations needed for board generation:

**Board creation:**
- `POST /v2/boards` to create a new board with title and description

**Frames:**
- `POST /v2/boards/{board_id}/frames` to create each frame with position, size, and title

**Sticky notes:**
- `POST /v2/boards/{board_id}/sticky_notes` to create pre-populated prompts and placeholder notes

**Shapes:**
- `POST /v2/boards/{board_id}/shapes` to create section dividers, headers, and labels

**Text:**
- `POST /v2/boards/{board_id}/texts` to add instructions, frame descriptions, and participant guidance

### Board structure

For each workshop, generate:

1. **Title frame** at the top-left with:
   - Workshop name
   - Company name (if tailored)
   - Date (if known)
   - Brief instructions for participants

2. **Exercise frames** in agenda order, each containing:
   - Frame title matching the exercise name
   - Section headers for columns/rows/quadrants
   - Pre-populated sticky notes with prompt text
   - Placeholder sticky notes for participant input (different color)
   - Any instructions or timing notes

3. **Output frame** at the end with:
   - Summary sections for each expected output
   - Next steps template
   - Owner and date fields

### Color palette

| Element | Color | Usage |
|---------|-------|-------|
| Prompts | Light blue | Pre-populated questions and prompts |
| Participant input | Yellow | Where participants add their stickies |
| Strengths / Positives | Light green | "What works," "Where we win" |
| Gaps / Concerns | Light red/pink | "What's missing," "Where we lose" |
| Decisions / Outputs | Light purple | Final decisions and key outputs |
| Instructions | Gray | Facilitator notes and participant guidance |

---

## Step 4: Validate and share

After generation:

1. **Verify the board:** Check that all frames were created, sticky notes are positioned correctly, and the flow matches the agenda
2. **Share the link:** Provide the board URL to the user
3. **Access settings:** Note whether the board needs sharing settings adjusted (team access, guest access for external participants)

---

## Step 5: Fallback — manual board specification

If Miro API access is not available, generate a detailed specification the facilitator can use to build the board manually:

---

### BOARD SPECIFICATION

**Workshop:** [Workshop name]
**Board tool:** Miro (or equivalent: FigJam, Mural)

#### Frame-by-frame build guide

**Frame 1: [Name]**
- **Size:** [Approximate — e.g., "wide, 2x the height of other frames"]
- **Position:** [Where in the board flow]
- **Layout:** [Columns/rows/quadrants with labels]
- **Pre-populate:**
  - [Sticky 1: "prompt text" — light blue]
  - [Sticky 2: "prompt text" — light blue]
- **Leave space for:** [What participants will add, how many stickies to expect]

[Repeat for each frame]

#### Setup checklist
- [ ] All frames created and titled
- [ ] Prompt stickies pre-populated in each frame
- [ ] Color coding consistent across frames
- [ ] Board shared with all participants
- [ ] Facilitator has edit access, participants have commenting/sticky access

---

## Self-check before delivering

1. Does the board flow match the workshop agenda? (Frame sequence = exercise sequence)
2. Are the prompt stickies specific enough to guide participants, not so detailed that they constrain?
3. Is there enough space for the expected number of participants and their input?
4. If this is a tailored board, does it reflect the company-specific adaptations from the session plan?
5. Is the color coding consistent and intuitive? Would a participant understand it without explanation?
6. If falling back to manual specification, is it detailed enough for a facilitator to build in 15-20 minutes?
