# Tech Docs for Curious Cats Deck Design

## Summary

Build a 45-60 minute Marp slide deck titled **Tech docs for curious cats** with
the subtitle **From messy notes to useful docs**.

The talk is for high-school, college, and early university students from mixed
technical and non-technical backgrounds. It should be engaging, practical,
snappy, and useful. The deck should explain what technical writing looks like in
real large software companies by following a relatable case study from messy
input to useful documentation.

## Audience

The audience is mostly young students who want practical knowledge, not abstract
theory. They may be curious about software engineering, technical writing,
communication, AI tools, or technology careers.

The deck should help them understand:

- What technical writing is and why it matters in real tech teams.
- How engineers and non-technical roles can communicate complex ideas clearly.
- Why scattered, stale, or unstructured docs create real costs.
- How tech writers turn messy information into findable, trustworthy docs.
- How good human-readable docs also become better input for LLMs and agents.

## Core Promise

The audience should leave with this idea:

Technical writing is not just making words nicer. It is making complex
information findable, usable, trustworthy, and reusable.

## Approved Approach

Use a **case-study documentary** approach.

The main story follows a fictional travel-tech company where a partner needs to
onboard to the platform, but the information is scattered across GitLab,
Confluence, Google Drive, Slack, old PDFs, spreadsheets, and people in the
organization.

The talk follows what a technical writer does with that mess:

1. Make the messy input visible.
2. Ask better questions.
3. Create better structure.
4. Rebuild trust.
5. Make the docs better input for AI tools.

This approach should feel close to real daily technical writing work while
remaining accessible to students.

## Case Study Scope

The main case study is **partner onboarding docs** for a fictional travel-tech
platform.

The deck can include detours into:

- **Internal engineering docs**, because the truth often lives in APIs, repos,
  tickets, architecture notes, and engineer memory.
- **AI-ready documentation**, because existing human docs need structure,
  ownership, metadata, and clean chunks before LLMs and agents can use them
  reliably.

Customer support docs are optional. Use them only if they help the narrative
show the business cost of bad docs.

## Talk Architecture

The deck should use this high-level flow:

1. **Opening**
   - Title, promise, about the speaker, and why docs matter in real teams.
   - Rough timing: 5-7 minutes.
2. **Messy Input**
   - The partner onboarding docs exist, but they are scattered, stale, and hard
     to trust.
   - Show fragmentation across tools and the cost of people asking for help
     instead of finding reliable information.
   - Rough timing: 8-10 minutes.
3. **Better Questions**
   - The technical writer's first move is not writing. It is asking better
     questions.
   - Focus on audience, task, source, owner, freshness, risk, and missing
     information.
   - Rough timing: 10-12 minutes.
4. **Better Structure**
   - Turn scattered sources into a docs map.
   - Then turn the map into usable pages, examples, labels, navigation, and
     source-of-truth signals.
   - Rough timing: 12-15 minutes.
5. **Better Trust**
   - Explain how ownership, review, freshness, maintenance, and deprecation make
     docs trustworthy.
   - Rough timing: 8-10 minutes.
6. **Better AI**
   - Show how Claude, Claude Code, or similar tools can summarize sources,
     identify gaps, draft structure, and review output.
   - Add a light explanation of chunking, metadata, retrieval, source links,
     context, and agent-friendly docs.
   - Rough timing: 10-12 minutes.
7. **Close**
   - Leave students with practical rules they can reuse.
   - Rough timing: 3-5 minutes.

## Recurring Teaching Artifacts

Use a small set of recurring artifacts throughout the deck:

- **Mess board**
  - Slack thread, GitLab issue, Confluence page, Drive doc, PDF, spreadsheet,
    and "ask that engineer" knowledge.
- **Question checklist**
  - Audience, task, source, owner, freshness, risk, missing information.
- **Docs map**
  - What exists, where it lives, who owns it, what it supports, what to merge,
    and what to retire.
- **Before/after page**
  - A messy paragraph or scattered notes transformed into a clear docs page.
- **AI-readiness pass**
  - Headings, metadata, chunks, examples, source links, ownership, freshness,
    caveats, and context.

The main transformation is:

```text
scattered sources -> docs map -> AI-ready docs
```

Use smaller bad-page to good-page examples as zoom-ins when the audience needs
to see what changes in the writing itself.

## Slide Experience

The slides should be light, visual, and practical. They should feel friendly to
students, not corporate.

Use three recurring slide types:

- **Story beat slides**
  - One strong sentence that moves the case study forward.
- **Artifact slides**
  - A docs map, checklist, messy source set, before/after page, or AI-readiness
    pass.
- **Takeaway slides**
  - A short rule students can apply immediately.

Speaker notes should carry the deeper story, real-work anecdotes, and delivery
details. Slide text should stay short.

## Rough Slide Map

Target roughly **34-40 slides**.

Use more short slides rather than fewer crowded slides.

- **Opening**: 4-5 slides.
- **Messy input**: 5-6 slides.
- **Better questions**: 5-6 slides.
- **Better structure**: 7-8 slides.
- **Better trust**: 5-6 slides.
- **Better AI**: 6-7 slides.
- **Close**: 3-4 slides.

## Marp Implementation

Keep `source/slides.md` as the single source of truth.

Use repeatable Marp patterns:

- Lead slide.
- Split image/text slide.
- Artifact board slide.
- Before/after slide.
- Checklist slide.
- Takeaway slide.

Use local images from `assets/img/` so HTML, PDF, and PPTX exports work
reliably. Avoid remote-only visuals when possible.

Build in passes:

1. Create the full slide skeleton with titles and speaker-note intent.
2. Fill in the case-study examples and teaching artifacts.
3. Polish visual rhythm and slide density.
4. Render HTML while iterating.
5. Export PDF and PPTX once content stabilizes.

## Validation

During implementation, verify:

- The deck renders with `npm run marp:html`.
- The final deck exports with `npm run marp:pdf` and `npm run marp:pptx`.
- Image paths resolve from `source/slides.md`.
- Slide text is not crowded.
- Speaker notes explain what the slide does and what the speaker should say.
- The AI section remains practical and grounded in documentation quality.

## Non-Goals

- Do not turn the deck into a full technical writing textbook.
- Do not make the talk primarily about career advice.
- Do not make the talk primarily about customer support docs.
- Do not make the AI section the main topic of the talk.
- Do not add exercises, because there is no room for them in this session.
