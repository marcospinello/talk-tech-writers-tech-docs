# Tech Docs for Curious Cats Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Build the approved Marp deck, including local Pixabay-sourced images, a complete slide structure, practical case-study artifacts, speaker notes, and verified HTML/PDF/PPTX exports.

**Architecture:** Keep `source/slides.md` as the single source of truth. Use local images in `assets/img/`, track image provenance in `assets/img/ATTRIBUTION.md`, and build the deck in passes: assets, skeleton, case-study content, polish, and exports.

**Tech Stack:** Marp CLI, Markdown, local CSS in Marp front matter, Pixabay image assets, npm scripts from `package.json`, `markdownlint`.

---

## File Structure

- Modify: `source/slides.md`
  - Full Marp slide deck source, front matter, slide content, and speaker notes.
- Create: `assets/img/ATTRIBUTION.md`
  - Image source, author, URL, license note, and deck usage for each downloaded asset.
- Add: `assets/img/*.jpg` or `assets/img/*.png`
  - Local images used by the deck. Prefer Pixabay AI-generated results by searching with `content_type=ai`.
- Modify: `README.md`
  - Add a short asset provenance note after images are selected.
- Keep: `.marprc.yml`
  - Existing Marp configuration remains the export source of truth.

---

### Task 1: Capture Baseline and Asset Rules

**Files:**

- Read: `docs/superpowers/specs/2026-05-30-tech-docs-for-curious-cats-design.md`
- Read: `source/slides.md`
- Read: `package.json`
- Read: `.marprc.yml`

- [ ] **Step 1: Confirm the working tree is clean**

Run:

```bash
git status --short
```

Expected: no output.

- [ ] **Step 2: Confirm current image inventory**

Run:

```bash
find assets/img -maxdepth 1 -type f -not -name '.DS_Store' -print | sort
```

Expected: includes `assets/img/about-me.jpg`.

- [ ] **Step 3: Confirm Marp scripts**

Run:

```bash
npm run lint
npm run marp:html
```

Expected: both commands exit with code 0. Existing npm `email` config warnings are acceptable if the command exits with code 0.

- [ ] **Step 4: Commit the baseline check result only if files changed**

No commit is needed when this task only reads files and runs commands.

---

### Task 2: Acquire and Track Pixabay Images

**Files:**

- Create: `assets/img/ATTRIBUTION.md`
- Add: `assets/img/title-curious-cat.jpg`
- Add: `assets/img/travel-platform.jpg`
- Add: `assets/img/docs-sprawl.jpg`
- Add: `assets/img/partner-onboarding.jpg`
- Add: `assets/img/question-checklist.jpg`
- Add: `assets/img/docs-map.jpg`
- Add: `assets/img/before-after-docs.jpg`
- Add: `assets/img/trust-signals.jpg`
- Add: `assets/img/ai-docs-workflow.jpg`
- Add: `assets/img/thank-you.jpg`

- [ ] **Step 1: Search Pixabay with AI precedence**

Use Pixabay search pages with `content_type=ai` first. Use these target searches:

```text
https://pixabay.com/images/search/curious%20cat%20laptop/?content_type=ai
https://pixabay.com/images/search/travel%20technology%20platform/?content_type=ai
https://pixabay.com/images/search/messy%20documents%20computer/?content_type=ai
https://pixabay.com/images/search/online%20onboarding%20travel/?content_type=ai
https://pixabay.com/images/search/checklist%20questions%20desk/?content_type=ai
https://pixabay.com/images/search/knowledge%20map%20documents/?content_type=ai
https://pixabay.com/images/search/document%20before%20after/?content_type=ai
https://pixabay.com/images/search/trust%20documentation%20checkmark/?content_type=ai
https://pixabay.com/images/search/artificial%20intelligence%20documents/?content_type=ai
https://pixabay.com/images/search/curious%20cat%20thank%20you/?content_type=ai
```

If an AI-generated result is weak, use the same search without `content_type=ai` and choose a meaningful, export-safe image.

- [ ] **Step 2: Download selected images locally**

Download the chosen images into the exact filenames listed above. Use JPEG for photographic images and PNG only when the source image is graphic or has transparency.

Expected after download:

```bash
ls assets/img
```

Includes:

```text
ATTRIBUTION.md
about-me.jpg
ai-docs-workflow.jpg
before-after-docs.jpg
docs-map.jpg
docs-sprawl.jpg
partner-onboarding.jpg
question-checklist.jpg
thank-you.jpg
title-curious-cat.jpg
travel-platform.jpg
trust-signals.jpg
```

- [ ] **Step 3: Write image attribution manifest**

Create `assets/img/ATTRIBUTION.md` with this structure:

```markdown
# Image Attribution

Images in this folder are used as local assets for the Marp deck.

Pixabay images are used under the Pixabay Content License. Attribution is not required by Pixabay, but this file tracks provenance for maintainability and review.

| File | Usage | Source URL | Creator | Notes |
| --- | --- | --- | --- | --- |
| `about-me.jpg` | About me slide | Local speaker photo | Marco Spinello | Existing repo asset. |
```

For each downloaded Pixabay file, add one row with the exact image page URL and creator name from the selected Pixabay page before committing. Each Notes value should state either `AI-generated result` or `Non-AI result chosen because the AI-generated results were not relevant`.

- [ ] **Step 4: Verify image files are usable by Marp**

Run:

```bash
file assets/img/*.jpg assets/img/*.png
```

Expected: each downloaded image is reported as JPEG or PNG image data.

- [ ] **Step 5: Commit image assets**

Run:

```bash
git add assets/img
git commit -m "docs: add deck image assets"
```

Expected: commit succeeds and includes only image files plus `assets/img/ATTRIBUTION.md`.

---

### Task 3: Build the Full Slide Skeleton

**Files:**

- Modify: `source/slides.md`

- [ ] **Step 1: Replace the boilerplate with the approved slide map**

Keep the existing Marp front matter and CSS helpers, then create slides in this order:

```text
01 Title: Tech docs for curious cats
02 Promise: From messy notes to useful docs
03 What you will learn
04 About me
05 The case: TravelCo partner onboarding
06 The partner has a simple question
07 The answer is everywhere
08 Docs exist. Truth is harder.
09 Why this hurts humans
10 Why this hurts companies
11 Takeaway: docs are an information system
12 Better questions
13 Question 1: Who is this for?
14 Question 2: What are they trying to do?
15 Question 3: Where does truth live?
16 Question 4: Who owns it?
17 Question 5: What changed?
18 Takeaway: writing starts before writing
19 Better structure
20 From source sprawl to docs map
21 The docs map
22 What to merge, move, rewrite, or delete
23 From map to page
24 Bad docs page
25 Better docs page
26 Takeaway: structure is kindness
27 Better trust
28 Trust signals readers need
29 Review and ownership
30 Freshness and deprecation
31 Takeaway: trust has maintenance costs
32 Better AI
33 Practical Claude workflow
34 AI finds gaps, not truth
35 Why chunks and metadata matter
36 Human-readable to agent-friendly
37 Takeaway: AI rewards structured docs
38 Five rules for useful docs
39 What to try next
40 Thank you
```

- [ ] **Step 2: Add speaker-note intent under each slide**

Each slide must have an HTML comment with 2-5 sentences describing what the speaker should say. Use this pattern:

```markdown
<!--
Explain the real work behind this slide. Keep the spoken point practical and tied to the partner onboarding case study.
-->
```

Expected: every slide has a speaker-note block.

- [ ] **Step 3: Run slide-source linting**

Run:

```bash
npx markdownlint source/slides.md
```

Expected: command exits with code 0.

- [ ] **Step 4: Render HTML**

Run:

```bash
npm run marp:html
```

Expected: `output/slides.html` is created and the command exits with code 0.

- [ ] **Step 5: Commit the slide skeleton**

Run:

```bash
git add source/slides.md output/slides.html
git commit -m "docs: add deck slide skeleton"
```

Expected: commit succeeds and includes the slide source plus generated HTML.

---

### Task 4: Fill Case-Study Artifacts and Examples

**Files:**

- Modify: `source/slides.md`

- [ ] **Step 1: Add the messy source board content**

In the Messy Input section, include a visual artifact showing these source fragments:

```text
GitLab issue: auth setup changed after partner sandbox migration.
Confluence page: onboarding guide last updated eight months ago.
Google Drive doc: spreadsheet with partner fields and unclear owners.
Slack thread: engineer explains one exception in a thread nobody will find later.
PDF: old partner checklist still linked from an internal page.
Human memory: one engineer knows which setup step is no longer required.
```

- [ ] **Step 2: Add the question checklist content**

In the Better Questions section, include this checklist:

```text
Who is the reader?
What job are they trying to complete?
What do they already know?
Where does the current truth live?
Who can verify it?
What changed recently?
What happens if the doc is wrong?
What can we delete or archive?
```

- [ ] **Step 3: Add the docs map content**

In the Better Structure section, include a docs map with these columns:

```text
Source
What it explains
Audience
Owner
Freshness
Action
```

Use these actions:

```text
Keep as source of truth
Merge into onboarding guide
Rewrite as task steps
Archive as outdated
Link as supporting reference
Ask owner to verify
```

- [ ] **Step 4: Add before/after page content**

Use this bad page example:

```text
To set up a partner account, first make sure the partner is active and that all fields are configured correctly. Some partners may need sandbox access before production access. If something does not work, check with Integrations or ask in Slack. The process changed recently, so make sure you follow the latest steps.
```

Use this improved page model:

```text
# Set up a partner sandbox account

Use this guide when a new travel partner needs sandbox access before production onboarding.

## Before you start
- Partner contract is approved.
- Partner ID exists in Partner Admin.
- You can access the sandbox environment.

## Steps
1. Create the partner sandbox account in Partner Admin.
2. Add the required contact and billing fields.
3. Enable sandbox API access.
4. Send the sandbox credentials through the approved secure channel.
5. Ask the partner to complete a test booking flow.

## Verify setup
- Partner can authenticate successfully.
- Test booking returns a sandbox confirmation ID.
- No production inventory is affected.

## Owner and freshness
- Owner: Partner Integrations.
- Last reviewed: 2026-05-30.
- Source of truth: Partner onboarding runbook.
```

- [ ] **Step 5: Add AI workflow content**

In the Better AI section, show this practical workflow:

```text
1. Ask Claude to summarize scattered source material.
2. Ask Claude to list conflicts, missing owners, and stale claims.
3. Ask Claude to propose a docs map.
4. Ask a human expert to verify the proposed structure and claims.
5. Use Claude to draft the first page from verified inputs.
6. Review the draft for accuracy, audience fit, and missing caveats.
7. Add metadata, source links, ownership, and freshness signals.
```

Add this caution:

```text
AI can help you move faster through the mess, but it cannot decide what is true unless the sources and humans around it make truth visible.
```

- [ ] **Step 6: Render and commit case-study content**

Run:

```bash
npx markdownlint source/slides.md
npm run marp:html
git add source/slides.md output/slides.html
git commit -m "docs: fill deck case study content"
```

Expected: lint and render commands exit with code 0, then commit succeeds.

---

### Task 5: Polish Visual Rhythm and Slide Notes

**Files:**

- Modify: `source/slides.md`

- [ ] **Step 1: Add local image references**

Use these image assignments:

```text
title-curious-cat.jpg -> title slide
travel-platform.jpg -> case-study intro
docs-sprawl.jpg -> messy input
partner-onboarding.jpg -> partner onboarding scenario
question-checklist.jpg -> better questions
docs-map.jpg -> better structure
before-after-docs.jpg -> before/after page
trust-signals.jpg -> better trust
ai-docs-workflow.jpg -> better AI
about-me.jpg -> about me
thank-you.jpg -> thank you
```

Use Marp background directives such as:

```markdown
![bg right:45%](../assets/img/docs-sprawl.jpg)
```

- [ ] **Step 2: Add section divider rhythm**

Use section divider slides for:

```text
Messy input
Better questions
Better structure
Better trust
Better AI
```

Each divider should use a short headline and one sentence of speaker notes.

- [ ] **Step 3: Check speaker notes**

Run:

```bash
rg --color never -n "^<!--$|^-->$" source/slides.md
```

Expected: comment blocks are present throughout the deck.

- [ ] **Step 4: Render and commit visual polish**

Run:

```bash
npx markdownlint source/slides.md
npm run marp:html
git add source/slides.md output/slides.html
git commit -m "docs: polish deck visuals and notes"
```

Expected: lint and render commands exit with code 0, then commit succeeds.

---

### Task 6: Update README Asset Notes

**Files:**

- Modify: `README.md`

- [ ] **Step 1: Add asset provenance section**

Add this section after the Repo Layout section:

```markdown
## Image Assets

Slide images live in `assets/img/`.

Most deck images are sourced from [Pixabay](https://pixabay.com/), with preference given to AI-generated images when relevant search results are available. Image provenance is tracked in `assets/img/ATTRIBUTION.md`.
```

- [ ] **Step 2: Run root Markdown linting**

Run:

```bash
npm run lint
```

Expected: command exits with code 0.

- [ ] **Step 3: Commit README update**

Run:

```bash
git add README.md
git commit -m "docs: document image asset provenance"
```

Expected: commit succeeds and includes only `README.md`.

---

### Task 7: Final Export Verification

**Files:**

- Generate: `output/slides.html`
- Generate: `output/slides.pdf`
- Generate: `output/slides.pptx`

- [ ] **Step 1: Render all output formats**

Run:

```bash
npm run marp:html
npm run marp:pdf
npm run marp:pptx
```

Expected:

```text
output/slides.html
output/slides.pdf
output/slides.pptx
```

exist and all commands exit with code 0.

- [ ] **Step 2: Verify output files exist**

Run:

```bash
ls -lh output/slides.html output/slides.pdf output/slides.pptx
```

Expected: each file exists and has a non-zero size.

- [ ] **Step 3: Search for broken local image references**

Run:

```bash
rg --color never -n "\.\./assets/img/[^) ]+" source/slides.md
```

Expected: every referenced filename exists in `assets/img/`.

- [ ] **Step 4: Commit final outputs**

Run:

```bash
git add output/slides.html output/slides.pdf output/slides.pptx
git commit -m "docs: export deck outputs"
```

Expected: commit succeeds and includes generated output files only.

---

## Self-Review Checklist

- The implementation tasks cover the approved title, subtitle, audience, case study, section architecture, recurring artifacts, AI payoff, Marp implementation, and export validation.
- The plan gives exact filenames for local images and the attribution manifest.
- The plan keeps AI as the payoff section rather than the main topic.
- The plan includes no exercises.
- The plan uses local image paths for export reliability.
- The plan verifies HTML, PDF, and PPTX output.
