---
marp: true
author: Marco Spinello
title: Tech docs for curious cats
style: |
    .fa-twitter, .fa-x-twitter { color: #8be9fd; }
    .fa-linkedin { color: #8be9fd; }
    .fa-bandcamp { color: #8be9fd; }
    .fa-github { color: #f8f8f2; }
    @import 'https://cdnjs.cloudflare.com/ajax/libs/font-awesome/7.0.1/css/all.min.css';
    .big {
      font-size: 2em;
      font-weight: 700;
      line-height: 1.15;
    }
    .huge {
      font-size: 2.6em;
      font-weight: 800;
      line-height: 1.1;
    }
    .quiet {
      color: #6272a4;
      font-style: italic;
    }
    .accent {
      color: #ff79c6;
    }
    .section-divider,
    .section-open {
      text-align: left;
    }
    .section-divider h2,
    .section-open h2 {
      margin-top: 0.05em;
      margin-bottom: 0.25em;
      line-height: 1.05;
    }
    .section-divider p {
      max-width: 780px;
      margin-top: 0.4em;
      font-size: 1.05em;
      line-height: 1.3;
    }
    .section-kicker {
      margin-bottom: 0.35em;
      color: #8be9fd;
      font-size: 0.62em;
      font-weight: 800;
      letter-spacing: 0;
      text-transform: uppercase;
    }
    .section-open .section-kicker {
      margin-bottom: 0.55em;
    }
    .section-rule {
      width: 5.2em;
      height: 0.22em;
      margin-top: 0.8em;
      border-radius: 999px;
      background: #ff79c6;
    }
    .manifesto p {
      font-size: 1.4em;
      font-weight: 600;
      margin: 0.6em 0;
      line-height: 1.25;
    }
    .manifesto ol {
      font-size: 1.4em;
      font-weight: 600;
      margin: 0.6em 0;
      line-height: 1.25;
    }
    .manifesto li {
      margin: 0.25em 0;
    }
    .dense {
      font-size: 24px;
    }
    .dense h2 {
      margin-bottom: 0.45em;
    }
    .source-board {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 0.55em;
      margin-top: 0.8em;
    }
    .source-card {
      min-height: 4.8em;
      padding: 0.75em;
      border-left: 6px solid #8be9fd;
      border-radius: 8px;
      background: #44475a;
      color: #f8f8f2;
      font-size: 0.72em;
      line-height: 1.25;
    }
    .question-checklist table {
      font-size: 0.9em;
      line-height: 1.25;
    }
    .question-checklist table td {
      width: 50%;
      padding: 0.35em 0.6em;
    }
    .map-overview {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 0.42em;
      margin-top: 0.55em;
    }
    .map-card {
      min-height: 2.7em;
      padding: 0.42em 0.6em;
      border-left: 6px solid #8be9fd;
      border-radius: 8px;
      background: #44475a;
      color: #f8f8f2;
    }
    .map-source {
      color: #f1fa8c;
      font-size: 0.72em;
      font-weight: 800;
      line-height: 1.15;
    }
    .map-action {
      margin-top: 0.18em;
      color: #8be9fd;
      font-size: 0.9em;
      line-height: 1.18;
    }
    .map-lesson {
      margin-top: 0.35em;
      color: #f8f8f2;
      font-size: 0.76em;
      line-height: 1.2;
    }
    .map-zoom {
      margin-top: 0.65em;
      padding: 0.7em;
      border-radius: 8px;
      background: #44475a;
    }
    .map-zoom-title {
      color: #f1fa8c;
      font-size: 1.05em;
      font-weight: 800;
    }
    .map-zoom-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 0.45em;
      margin-top: 0.55em;
    }
    .map-field {
      padding: 0.45em;
      border-radius: 6px;
      background: #282a36;
      font-size: 0.78em;
      line-height: 1.15;
    }
    .map-field-name {
      color: #ff79c6;
      font-weight: 800;
    }
    .map-field-value {
      margin-top: 0.16em;
      color: #f8f8f2;
    }
    .page-excerpt {
      margin-top: 1em;
      padding: 0.9em 1em;
      border-left: 6px solid #ff5555;
      border-radius: 8px;
      background: #44475a;
      color: #f8f8f2;
      font-size: 0.86em;
      line-height: 1.36;
    }
    .page-sample {
      margin-top: 0.45em;
      padding: 0.62em 0.75em;
      border-radius: 8px;
      background: #f8f8f2;
      color: #282a36;
      font-size: 0.72em;
      line-height: 1.16;
    }
    .page-title {
      color: #282a36;
      font-size: 1.35em;
      font-weight: 800;
    }
    .page-lede {
      margin-top: 0.22em;
      color: #44475a;
      font-size: 0.8em;
      line-height: 1.18;
    }
    .page-grid {
      display: grid;
      grid-template-columns: 0.9fr 1.1fr;
      gap: 0.45em;
      margin-top: 0.55em;
    }
    .page-card {
      padding: 0.48em 0.55em;
      border-left: 5px solid #bd93f9;
      border-radius: 6px;
      background: #ffffff;
    }
    .page-heading {
      color: #bd93f9;
      font-size: 0.88em;
      font-weight: 800;
    }
    .page-line {
      margin-top: 0.15em;
      font-size: 0.78em;
      line-height: 1.18;
    }
    .page-step {
      margin-top: 0.12em;
      font-size: 0.76em;
      line-height: 1.15;
    }
    .page-zoom-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 0.7em;
      margin-top: 0.85em;
    }
    .page-zoom-card {
      min-height: 5.1em;
      padding: 0.72em;
      border-left: 6px solid #8be9fd;
      border-radius: 8px;
      background: #44475a;
      color: #f8f8f2;
      font-size: 0.78em;
      line-height: 1.2;
    }
    .page-zoom-title {
      color: #f1fa8c;
      font-size: 1.05em;
      font-weight: 800;
      line-height: 1.15;
    }
    .page-zoom-text {
      margin-top: 0.35em;
    }
---

<!-- markdownlint-disable MD026 MD033 because slides use prompts and Marp HTML layouts. -->

<!-- _class: lead -->

## Tech docs for curious cats

Marco Spinello

Senior technical writer at Booking.com

<!--
Open with the promise that this is a practical talk, not a style lecture. Set the tone around curiosity, systems thinking, and making technical information easier to trust.
-->

---

<!-- _class: lead -->

## From messy notes to useful docs

One messy onboarding story, five better questions, one usable docs system.

<!--
Frame the talk as a journey from scattered knowledge to a docs experience that helps real people move. Tie the promise to TravelCo partner onboarding so every idea has a concrete anchor.
-->

---

## What you will learn

- See docs as an information system
- Ask better questions before writing
- Structure content for trust, maintenance, and AI

<!--
Preview the learning path in plain terms. Tell the audience that useful docs come from discovery, structure, trust signals, and maintenance, not only sentence-level polish.
-->

---

## About me

![bg left:50%](../assets/img/about-me.jpg)

- Senior technical writer at Booking.com
- Guitar player in an instrumental power trio
- No CS background
- Curious by habit

<!--
Give enough personal context to explain your point of view. Connect the non-CS background to technical writing as a practice of making expert knowledge usable.
-->

---

<!-- _class: lead section-divider -->

<div class="section-kicker">1 / Messy input</div>

## TravelCo partner onboarding

A new partner needs to connect, configure, test, and go live.

<div class="section-rule"></div>

<!--
Introduce TravelCo as the running example. The partner's goal is practical: connect, configure, test, and go live without chasing answers across teams.
-->

---

## The partner has a simple question

"What do we need to do next?"

<!--
Make the question sound simple on purpose. Use it to show the gap between how readers think and how internal knowledge is often organized.
-->

---

## The answer is everywhere

<div class="source-board">
  <div class="source-card">GitLab issue: auth setup changed after partner sandbox migration.</div>
  <div class="source-card">Confluence page: onboarding guide last updated eight months ago.</div>
  <div class="source-card">Google Drive doc: spreadsheet with partner fields and unclear owners.</div>
  <div class="source-card">Slack thread: engineer explains one exception in a thread nobody will find later.</div>
  <div class="source-card">PDF: old partner checklist still linked from an internal page.</div>
  <div class="source-card">Human memory: one engineer knows which setup step is no longer required.</div>
</div>

<!--
Walk through the source board as the messy input. None of these fragments are bad by themselves, but together they create a maze for a partner who only needs the next step.
-->

---

## (Too) many docs can hide the truth.

Published pages are not the same thing as a reliable source of truth.

<!--
Separate the existence of documentation from the reliability of documentation. A page can look official while being incomplete, stale, or disconnected from the team that owns the behavior.
-->

---

## Why this hurts humans

- Readers lose time
- Support teams repeat answers
- Writers become detectives

<!--
Describe the human cost before the business cost. Unclear docs shift effort onto partners, support engineers, account managers, and writers.
-->

---

## Why this hurts companies

- Slower onboarding
- More support load
- Riskier releases

<!--
Translate the same problem into company impact. Every unclear answer becomes a conversation, escalation, or delay, and TravelCo takes longer to go live.
-->

---

<!-- _class: lead -->

## Takeaway: docs are an information system

Pages are the visible part. \
Decisions, owners, and signals make them work.

<!--
Land the first section with a clear mental model. Good docs are not only words on pages; they are the product of source management, ownership, review, and structure.
-->

---

<!-- _class: section-open question-checklist -->

<div class="section-kicker">2 / Better questions</div>

## Better questions

| Ask before drafting | Ask before publishing |
| --- | --- |
| Who is the reader? | Who can verify it? |
| What job are they trying to complete? | What changed recently? |
| What do they already know? | What happens if the doc is wrong? |
| Where does the current truth live? | What can we delete or archive? |

<!--
Transition from diagnosing the problem to a practical working method. This checklist reduces ambiguity before drafting and keeps review focused on truth, risk, and maintenance.
-->

---

## Question 1: Who is this for?

Primary reader:
- TravelCo integration lead.

<!--
Explain why "the user" is too broad to guide useful documentation. Audience decisions shape vocabulary, examples, and depth.
-->

---

## Question 2: What are they trying to do?

Task:
- Complete partner onboarding with the fewest unknowns.

<!--
Move from audience identity to audience intent. The page should support a task, not merely describe a system.
-->

---

## Question 3: Where does truth live?

Sources:
- Product behavior
- API contracts
- Owner knowledge
- Release notes

<!--
Explain that writers need to identify authoritative sources before writing. Distinguish between places where people discuss onboarding and places where truth is maintained.
-->

---

## Question 4: Who owns it?

Owner:
- The team accountable for the behavior and the promise.

<!--
Explain that ownership keeps documentation from becoming an orphaned snapshot. Writers coordinate ownership, but they cannot replace it.
-->

---

## Question 5: What changed?

Change signal:
- New behavior
- New risk
- New reader confusion
- New support trend

<!--
Explain that change is where documentation quietly breaks. Writers need signals that tell them when a requirement, API field, or onboarding policy has moved.
-->

---

<!-- _class: lead -->

## Takeaway: writing starts before writing

Discovery is documentation work.

<!--
Validate the invisible work. Asking, mapping, and confirming are not delays before writing; they are how useful writing becomes possible.
-->

---

<!-- _class: lead section-divider -->

<div class="section-kicker">3 / Better structure</div>

## Better structure

Turn scattered answers into a map readers can follow.

<div class="section-rule"></div>

<!--
Introduce structure as the next layer of usefulness. Once sources and owners are known, the writer can decide what belongs together and what belongs somewhere else.
-->

---

## From source sprawl to docs map

Inventory the fragments before choosing the page shape.

<!--
Explain the move from collecting sources to organizing them. Mapping prevents the final page from simply mirroring the internal mess.
-->

---

## The docs map

<div class="map-overview">
  <div class="map-card">
    <div class="map-source">GitLab issue</div>
    <div class="map-action">Keep as source of truth</div>
  </div>
  <div class="map-card">
    <div class="map-source">Confluence page</div>
    <div class="map-action">Merge into onboarding guide</div>
  </div>
  <div class="map-card">
    <div class="map-source">Drive sheet</div>
    <div class="map-action">Ask owner to verify</div>
  </div>
  <div class="map-card">
    <div class="map-source">Slack thread</div>
    <div class="map-action">Rewrite as task steps</div>
  </div>
  <div class="map-card">
    <div class="map-source">PDF checklist</div>
    <div class="map-action">Archive as outdated</div>
  </div>
  <div class="map-card">
    <div class="map-source">Human memory</div>
    <div class="map-action">Link as supporting reference</div>
  </div>
</div>

<div class="map-lesson">The map is not a dumping ground. Every fragment gets a decision.</div>

<!--
Walk through the map as an editorial decision tool, not a final navigation menu. The visible slide shows the key decision for each fragment so the audience can read it from the back of the room.

Full docs map:
Source | What it explains | Audience | Owner | Freshness | Action
GitLab issue | Auth setup change | Engineers | Partner Integrations | Recent | Keep as source of truth
Confluence page | Onboarding flow | Partners | Docs team | 8 months old | Merge into onboarding guide
Drive sheet | Partner fields | Ops | Unknown | Unclear | Ask owner to verify
Slack thread | Sandbox exception | Support | Engineer | Recent | Rewrite as task steps
PDF checklist | Old checklist | Partners | Unknown | Stale | Archive as outdated
Human memory | Removed step | Writers | Engineer | Current | Link as supporting reference
-->

---

## Docs map zoom: one row

<div class="map-zoom">
  <div class="map-zoom-title">GitLab issue</div>
  <div class="map-zoom-grid">
    <div class="map-field">
      <div class="map-field-name">What it explains</div>
      <div class="map-field-value">Auth setup change</div>
    </div>
    <div class="map-field">
      <div class="map-field-name">Audience</div>
      <div class="map-field-value">Engineers</div>
    </div>
    <div class="map-field">
      <div class="map-field-name">Owner</div>
      <div class="map-field-value">Partner Integrations</div>
    </div>
    <div class="map-field">
      <div class="map-field-name">Freshness</div>
      <div class="map-field-value">Recent</div>
    </div>
    <div class="map-field">
      <div class="map-field-name">Action</div>
      <div class="map-field-value">Keep as source of truth</div>
    </div>
    <div class="map-field">
      <div class="map-field-name">Decision</div>
      <div class="map-field-value">Use this to verify the new setup behavior.</div>
    </div>
  </div>
</div>

<!--
Use this zoom slide to show the columns behind the overview: Source, What it explains, Audience, Owner, Freshness, and Action. Every row answers the same questions, but the live slide does not need every row and column at once.
-->

---

## What to merge, move, rewrite, or delete

Every fragment needs a content decision.

<!--
Explain that structure requires editorial judgment. Information can be merged, moved, rewritten, or deleted; deletion is part of making docs useful.
-->

---

## From map to page

Design the page around the reader's next decision.

<!--
Explain how the docs map becomes an actual page. Each section should help the partner answer "Can I continue, or do I need something first?"
-->

---

## Bad docs page

<div class="page-excerpt">
To set up a partner account, first make sure the partner is active and that all fields are configured correctly. Some partners may need sandbox access before production access. If something does not work, check with Integrations or ask in Slack. The process changed recently, so make sure you follow the latest steps.
</div>

<!--
Describe how this page technically contains information but still fails the reader. It hides prerequisites, mixes setup with troubleshooting, names no owner, and points people toward Slack instead of a durable answer.
-->

---

## Better docs page

<div class="page-sample">
  <div class="page-title">Set up a partner sandbox account</div>
  <div class="page-lede">Use this guide when a new travel partner needs sandbox access before production onboarding.</div>
  <div class="page-grid">
    <div class="page-card">
      <div class="page-heading">Before you start</div>
      <div class="page-line">- Partner contract is approved.</div>
      <div class="page-line">- Partner ID exists in Partner Admin.</div>
      <div class="page-line">- You can access the sandbox environment.</div>
    </div>
    <div class="page-card">
      <div class="page-heading">Steps</div>
      <div class="page-step">1. Create the sandbox account in Partner Admin.</div>
      <div class="page-step">2. Add contact and billing fields.</div>
      <div class="page-step">3. Enable sandbox API access.</div>
      <div class="page-step">4. Send credentials securely.</div>
      <div class="page-step">5. Ask the partner to test booking.</div>
    </div>
    <div class="page-card">
      <div class="page-heading">Verify setup</div>
      <div class="page-line">- Partner can authenticate successfully.</div>
      <div class="page-line">- Test booking returns a sandbox confirmation ID.</div>
      <div class="page-line">- No production inventory is affected.</div>
    </div>
    <div class="page-card">
      <div class="page-heading">Owner and freshness</div>
      <div class="page-line">- Owner: Partner Integrations.</div>
      <div class="page-line">- Last reviewed: 2026-05-30.</div>
      <div class="page-line">- Source of truth: Partner onboarding runbook.</div>
    </div>
  </div>
</div>

<!--
Show what better structure looks like in the same case. This is a rendered-page mockup, not raw Markdown source. The slide compresses some line wording for live readability, while the complete model remains in these notes.

Full improved page model:
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
-->

---

## Better docs page: zoom

<div class="page-zoom-grid">
  <div class="page-zoom-card">
    <div class="page-zoom-title">Task first</div>
    <div class="page-zoom-text">The title names the exact job: set up a sandbox account.</div>
  </div>
  <div class="page-zoom-card">
    <div class="page-zoom-title">Proof of done</div>
    <div class="page-zoom-text">The verify section tells readers how to know the setup worked.</div>
  </div>
  <div class="page-zoom-card">
    <div class="page-zoom-title">Trust signals</div>
    <div class="page-zoom-text">Owner, review date, and source of truth make the page safer to use.</div>
  </div>
</div>

<!--
Use this zoom slide to make the design lesson explicit. The improved page works because it starts with the task, separates setup from verification, and ends with ownership and freshness signals.
-->

---

<!-- _class: lead -->

## Takeaway: structure is kindness

Good structure saves readers from doing your sorting work.

<!--
Close the structure section with the human reason for organizing content. Every clear heading, sequence, and boundary removes work from the reader.
-->

---

<!-- _class: lead section-divider -->

<div class="section-kicker">4 / Better trust</div>

## Better trust

Readers need signals that the page is safe to use.

<div class="section-rule"></div>

<!--
Transition from structure to trust. A well-structured page still fails if readers cannot tell whether it is current, reviewed, and owned.
-->

---

## Trust signals readers need

- Last reviewed
- Applies to
- Owner
- Known limits
- Next escalation path

<!--
Explain the practical signals that help readers judge a page before acting on it. Trust signals do not need to be fancy, but they need to be visible and true.
-->

---

## Review and ownership

A review process is a promise with names attached.

<!--
Explain how review and ownership turn documentation into a maintained artifact. Review needs the right subject-matter experts, not just a general approval.
-->

---

## Freshness and deprecation

Old content should say what it is, where to go, and when it stops applying.

<!--
Explain that stale pages are especially dangerous when they still look official. Freshness notes and deprecation paths preserve reader confidence even when content changes.
-->

---

<!-- _class: lead -->

## Takeaway: trust has maintenance costs

If no one maintains the signal, the signal becomes noise.

<!--
Name the cost honestly. Review dates, owners, and deprecation notices require maintenance, but the alternative is silent decay.
-->

---

<!-- _class: lead section-divider -->

<div class="section-kicker">5 / Better AI</div>

## Better AI

AI can use docs better when docs are already structured for people.

<div class="section-rule"></div>

<!--
Transition into AI without treating it as magic. AI does not remove the need for reliable documentation; it amplifies the value of structure, ownership, and clear source boundaries.
-->

---

## Practical Claude workflow

1. Ask Claude to summarize scattered source material.
2. Ask Claude to list conflicts, missing owners, and stale claims.
3. Ask Claude to propose a docs map.
4. Ask a human expert to verify the proposed structure and claims.
5. Use Claude to draft the first page from verified inputs.
6. Review the draft for accuracy, audience fit, and missing caveats.
7. Add metadata, source links, ownership, and freshness signals.

<!--
Describe a practical AI-assisted workflow for the onboarding case. Claude can process fragments, reveal gaps, propose structure, and draft from verified inputs, but the team still has to validate truth.
-->

---

## AI finds gaps, not truth

AI can help you move faster through the mess, but it cannot decide what is true unless the sources and humans around it make truth visible.

<!--
Set a clear boundary around AI usefulness. AI can notice that a prerequisite appears in one source but not another, but it cannot decide which source is authoritative.
-->

---

## Why chunks and metadata matter

Good retrieval depends on clean boundaries and useful labels.

<!--
Explain chunking and metadata in accessible terms. Sections like requirements, setup, and troubleshooting make better retrieval units than one long mixed page.
-->

---

## Human-readable to agent-friendly

If a human can scan it, an assistant can often retrieve it better.

<!--
Explain that agent-friendly docs start with human-friendly structure. Clear headings, explicit prerequisites, and stable terminology help both TravelCo and AI tools find the right answer.
-->

---

<!-- _class: lead -->

## Takeaway: AI rewards structured docs

Better inputs make better assistance possible.

<!--
Close the AI section by returning to fundamentals. AI raises the stakes for source quality because messy docs become messy answers at scale.
-->

---

<!-- _class: lead manifesto -->

## Five rules for useful docs

1. Name the reader
2. Follow the task
3. Map the truth
4. Show the owner
5. Maintain the signal

<!--
Summarize the talk as a short practical checklist. Make this slide the memory aid the audience can carry back to their own docs.
-->

---

## What to try next

- Pick one messy page
- Map its sources
- Add one trust signal
- Ask one better review question

<!--
Give the audience a small next action instead of a giant documentation transformation. One page is enough to start practicing the method.
-->

---

<!-- _class: lead -->

## Thank you

Questions, observations, and remarks are welcome.

Marco Spinello

LinkedIn: [marco-spinello](https://www.linkedin.com/in/marco-spinello/)

GitHub: [marcospinello](https://github.com/marcospinello)

Bandcamp: [Be-Style EP](https://spinello-band.bandcamp.com/album/be-style)

<!--
Invite questions and make space for practical discussion. Close by reinforcing that useful docs are built through curiosity, structure, and maintenance.
-->
