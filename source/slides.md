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
    .map-grid {
      display: grid;
      grid-template-columns: 0.82fr 1fr 0.72fr 0.88fr 0.68fr 1.15fr;
      gap: 2px;
      margin-top: 0.7em;
      font-size: 0.54em;
      line-height: 1.12;
    }
    .map-cell {
      min-height: 2.7em;
      padding: 0.32em 0.36em;
      background: #44475a;
      color: #f8f8f2;
    }
    .map-head {
      min-height: 2em;
      color: #f1fa8c;
      font-weight: 800;
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
      padding: 0.65em 0.75em;
      border-radius: 8px;
      background: #f8f8f2;
      color: #282a36;
      font-size: 0.58em;
      line-height: 1.18;
    }
    .page-title {
      margin-bottom: 0.3em;
      color: #282a36;
      font-size: 1.35em;
      font-weight: 800;
    }
    .page-lede {
      margin-bottom: 0.45em;
    }
    .page-grid {
      display: grid;
      grid-template-columns: 0.9fr 1.2fr;
      gap: 0.35em 1em;
    }
    .page-heading {
      margin-top: 0.15em;
      color: #bd93f9;
      font-weight: 800;
    }
    .page-line {
      margin-top: 0.08em;
    }
---

<!-- markdownlint-disable MD026 MD033 because slides use prompts and Marp HTML layouts. -->

<!-- _class: lead -->

## Tech docs for curious cats

Marco Spinello

Senior technical writer at Booking.com

<!--
Open with the promise that this is a practical talk, not a style lecture. Explain that the partner onboarding case study will carry the audience from messy notes to useful docs. Set the tone around curiosity, systems thinking, and making technical information easier to trust.
-->

---

<!-- _class: lead -->

## From messy notes to useful docs

One messy onboarding story, five better questions, one usable docs system.

<!--
Frame the talk as a journey from scattered knowledge to a docs experience that helps real people move. Tie the promise to TravelCo partner onboarding so the audience knows every concept has a concrete anchor. Emphasize that usefulness comes from decisions about audience, structure, ownership, and maintenance.
-->

---

## What you will learn

- See docs as an information system
- Ask better questions before writing
- Structure content for trust, maintenance, and AI

<!--
Preview the learning path in plain terms. Tell the audience that the session is about the work around writing as much as the writing itself. Connect each learning outcome to the partner trying to complete onboarding without chasing answers across teams.
-->

---

## About me

![bg left:50%](../assets/img/about-me.jpg)

- Senior technical writer at Booking.com
- Guitar player in an instrumental power trio
- No CS background
- Curious by habit

<!--
Give the audience enough personal context to understand your point of view. Explain that coming from outside computer science made you pay close attention to how people learn systems. Connect that perspective to technical writing as a practice of making expert knowledge usable.
-->

---

## The case: TravelCo partner onboarding

A new partner needs to connect, configure, test, and go live.

<!--
Introduce TravelCo as the running example for the rest of the deck. Explain the partner's goal in practical terms: integrate with Booking.com, understand requirements, and complete onboarding without unnecessary back-and-forth. Keep the setup realistic, with enough detail to make later problems feel familiar.
-->

---

## The partner has a simple question

"What do we need to do next?"

<!--
Make the question sound simple on purpose. Explain that partners often ask direct workflow questions, while organizations answer with scattered fragments. Use this moment to show the gap between how users think and how internal knowledge is organized.
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
Walk through the source board as the messy input for the case study. Explain that none of these fragments are bad by themselves, but together they create a maze: recent behavior in GitLab, stale guidance in Confluence, unclear spreadsheet ownership, a Slack exception, an old PDF, and one person's memory. Tie the pain back to the partner who needs one next step, not a tour of internal history.
-->

---

## Docs exist. Truth is harder.

Published pages are not the same thing as a reliable source of truth.

<!--
Separate the existence of documentation from the reliability of documentation. Explain how a page can look official while being incomplete, stale, or disconnected from the teams that own the behavior. Use the case study to show why readers need confidence, not just content.
-->

---

## Why this hurts humans

- Readers lose time
- Support teams repeat answers
- Writers become detectives

<!--
Describe the human cost before the business cost. Explain how unclear docs shift effort onto partners, support engineers, account managers, and writers. Keep the focus on frustration, rework, and the feeling of not knowing which answer to trust.
-->

---

## Why this hurts companies

- Slower onboarding
- More support load
- Riskier releases

<!--
Translate the same problem into company impact. Explain that scattered truth creates operational drag because every unclear answer becomes a conversation, escalation, or delay. Tie the point to TravelCo taking longer to go live.
-->

---

<!-- _class: lead -->

## Takeaway: docs are an information system

Pages are the visible part. Decisions, owners, and signals make them work.

<!--
Land the first section with a clear mental model. Explain that good docs are not only words on pages; they are the product of source management, ownership, review, and structure. Use the TravelCo example to show that the system behind the page determines whether the page can be trusted.
-->

---

<!-- _class: dense question-checklist -->

## Better questions

| Ask before drafting | Ask before publishing |
| --- | --- |
| Who is the reader? | Who can verify it? |
| What job are they trying to complete? | What changed recently? |
| What do they already know? | What happens if the doc is wrong? |
| Where does the current truth live? | What can we delete or archive? |

<!--
Transition from diagnosing the problem to a practical working method. Explain that better docs start with better discovery questions. Tell the audience this checklist reduces ambiguity before anyone starts drafting and keeps the later review focused on truth, risk, and maintenance.
-->

---

## Question 1: Who is this for?

Primary reader: TravelCo integration lead.

<!--
Explain why "the user" is too broad to guide useful documentation. In the case study, name the primary reader and describe what they know, what they do not know, and what pressure they are under. Show that audience decisions shape vocabulary, examples, and depth.
-->

---

## Question 2: What are they trying to do?

Task: complete partner onboarding with the fewest unknowns.

<!--
Move from audience identity to audience intent. Explain that the page should support a task, not merely describe a system. Use TravelCo onboarding to show how task framing creates a clearer sequence of actions and decisions.
-->

---

## Question 3: Where does truth live?

Sources: product behavior, API contracts, owner knowledge, release notes.

<!--
Explain that writers need to identify authoritative sources before writing. In the case study, distinguish between places where people discuss onboarding and places where truth is maintained. Make the practical point that source quality determines doc quality.
-->

---

## Question 4: Who owns it?

Owner: the team accountable for the behavior and the promise.

<!--
Explain that ownership keeps documentation from becoming an orphaned snapshot. Use the TravelCo flow to show how each requirement or step needs a team that can confirm it, change it, and answer for it. Emphasize that writers coordinate ownership but cannot replace it.
-->

---

## Question 5: What changed?

Change signal: new behavior, new risk, new reader confusion, new support trend.

<!--
Explain that change is where documentation quietly breaks. In the case study, a requirement, API field, or onboarding policy can shift while the page stays still. Show why writers need signals that tell them when to revisit the docs.
-->

---

<!-- _class: lead -->

## Takeaway: writing starts before writing

Discovery is documentation work.

<!--
Wrap the questions section by validating the invisible work. Explain that asking, mapping, and confirming are not delays before writing; they are how useful writing becomes possible. Connect this back to TravelCo receiving a cleaner path because the team did the discovery first.
-->

---

<!-- _class: lead -->

## Better structure

Turn scattered answers into a map readers can follow.

<!--
Introduce structure as the next layer of usefulness. Explain that once the sources and owners are known, the writer can decide what belongs together and what belongs somewhere else. Keep the transition focused on reducing cognitive load for the partner.
-->

---

## From source sprawl to docs map

Inventory the fragments before choosing the page shape.

<!--
Explain the move from collecting sources to organizing them. In the TravelCo case, show that emails, API docs, tickets, and notes each contain different kinds of information. The speaker should make clear that mapping prevents the final page from simply mirroring internal mess.
-->

---

<!-- _class: dense docs-map -->

## The docs map

<div class="map-grid">
  <div class="map-cell map-head">Source</div>
  <div class="map-cell map-head">What it explains</div>
  <div class="map-cell map-head">Audience</div>
  <div class="map-cell map-head">Owner</div>
  <div class="map-cell map-head">Freshness</div>
  <div class="map-cell map-head">Action</div>
  <div class="map-cell">GitLab issue</div>
  <div class="map-cell">Auth setup change</div>
  <div class="map-cell">Engineers</div>
  <div class="map-cell">Partner Integrations</div>
  <div class="map-cell">Recent</div>
  <div class="map-cell">Keep as source of truth</div>
  <div class="map-cell">Confluence page</div>
  <div class="map-cell">Onboarding flow</div>
  <div class="map-cell">Partners</div>
  <div class="map-cell">Docs team</div>
  <div class="map-cell">8 months old</div>
  <div class="map-cell">Merge into onboarding guide</div>
  <div class="map-cell">Drive sheet</div>
  <div class="map-cell">Partner fields</div>
  <div class="map-cell">Ops</div>
  <div class="map-cell">Unknown</div>
  <div class="map-cell">Unclear</div>
  <div class="map-cell">Ask owner to verify</div>
  <div class="map-cell">Slack thread</div>
  <div class="map-cell">Sandbox exception</div>
  <div class="map-cell">Support</div>
  <div class="map-cell">Engineer</div>
  <div class="map-cell">Recent</div>
  <div class="map-cell">Rewrite as task steps</div>
  <div class="map-cell">PDF checklist</div>
  <div class="map-cell">Old checklist</div>
  <div class="map-cell">Partners</div>
  <div class="map-cell">Unknown</div>
  <div class="map-cell">Stale</div>
  <div class="map-cell">Archive as outdated</div>
  <div class="map-cell">Human memory</div>
  <div class="map-cell">Removed step</div>
  <div class="map-cell">Writers</div>
  <div class="map-cell">Engineer</div>
  <div class="map-cell">Current</div>
  <div class="map-cell">Link as supporting reference</div>
</div>

<!--
Walk through the map as an editorial decision tool, not a final navigation menu. Explain how each row gives a fragment a purpose, audience, owner, freshness signal, and action. Tie the decisions to TravelCo's journey from first contact to production launch.
-->

---

## What to merge, move, rewrite, or delete

Every fragment needs a content decision.

<!--
Explain that structure requires editorial judgment. Use the case study to show examples of information that should be merged into a guide, moved to API reference, rewritten for clarity, or deleted because it no longer serves the task. Emphasize that deletion is part of making docs useful.
-->

---

## From map to page

Design the page around the reader's next decision.

<!--
Explain how the docs map becomes an actual page. In the TravelCo example, each section should help the partner answer "Can I continue, or do I need something first?" Make the point that page structure should reduce hesitation.
-->

---

## Bad docs page

<div class="page-excerpt">
To set up a partner account, first make sure the partner is active and that all fields are configured correctly. Some partners may need sandbox access before production access. If something does not work, check with Integrations or ask in Slack. The process changed recently, so make sure you follow the latest steps.
</div>

<!--
Describe how this page technically contains information but still fails the reader. It hides prerequisites, mixes setup with troubleshooting, names no owner, and points people toward Slack instead of a durable answer. Keep this as a setup for the better page rather than a long critique.
-->

---

<!-- _class: dense -->

## Better docs page

<div class="page-sample">
  <div class="page-title"># Set up a partner sandbox account</div>
  <div class="page-lede">Use this guide when a new travel partner needs sandbox access before production onboarding.</div>
  <div class="page-grid">
    <div>
      <div class="page-heading">## Before you start</div>
      <div class="page-line">- Partner contract is approved.</div>
      <div class="page-line">- Partner ID exists in Partner Admin.</div>
      <div class="page-line">- You can access the sandbox environment.</div>
    </div>
    <div>
      <div class="page-heading">## Steps</div>
      <div class="page-line">1. Create the partner sandbox account in Partner Admin.</div>
      <div class="page-line">2. Add the required contact and billing fields.</div>
      <div class="page-line">3. Enable sandbox API access.</div>
      <div class="page-line">4. Send the sandbox credentials through the approved secure channel.</div>
      <div class="page-line">5. Ask the partner to complete a test booking flow.</div>
    </div>
    <div>
      <div class="page-heading">## Verify setup</div>
      <div class="page-line">- Partner can authenticate successfully.</div>
      <div class="page-line">- Test booking returns a sandbox confirmation ID.</div>
      <div class="page-line">- No production inventory is affected.</div>
    </div>
    <div>
      <div class="page-heading">## Owner and freshness</div>
      <div class="page-line">- Owner: Partner Integrations.</div>
      <div class="page-line">- Last reviewed: 2026-05-30.</div>
      <div class="page-line">- Source of truth: Partner onboarding runbook.</div>
    </div>
  </div>
</div>

<!--
Show what better structure looks like in the same case. Explain that the content is not necessarily longer; it is arranged around the partner's workflow. Point out that prerequisites, validation, ownership, freshness, and the source of truth are part of the user journey, not afterthoughts.
-->

---

<!-- _class: lead -->

## Takeaway: structure is kindness

Good structure saves readers from doing your sorting work.

<!--
Close the structure section with the human reason for organizing content. Explain that every clear heading, sequence, and boundary removes work from the reader. Use TravelCo to show that structure can make the difference between progress and another support ticket.
-->

---

<!-- _class: lead -->

## Better trust

Readers need signals that the page is safe to use.

<!--
Transition from structure to trust. Explain that a well-structured page still fails if readers cannot tell whether it is current, reviewed, and owned. In the case study, trust determines whether TravelCo follows the docs or asks for confirmation elsewhere.
-->

---

## Trust signals readers need

- Last reviewed
- Applies to
- Owner
- Known limits
- Next escalation path

<!--
Explain the practical signals that help readers judge a page. Tie each signal to a question TravelCo might ask before acting on onboarding instructions. Keep the message grounded: trust signals do not need to be fancy, but they need to be visible and true.
-->

---

## Review and ownership

A review process is a promise with names attached.

<!--
Explain how review and ownership turn documentation into a maintained artifact. Use the partner onboarding flow to show why review needs the right subject-matter experts, not just a general approval. Emphasize that ownership should survive the initial publication moment.
-->

---

## Freshness and deprecation

Old content should say what it is, where to go, and when it stops applying.

<!--
Explain that stale pages are especially dangerous when they still look official. In the TravelCo case, outdated setup steps can cause failed tests or support escalations. Show how freshness notes and deprecation paths preserve reader confidence even when content changes.
-->

---

<!-- _class: lead -->

## Takeaway: trust has maintenance costs

If no one maintains the signal, the signal becomes noise.

<!--
Close the trust section by naming the cost honestly. Explain that review dates, owners, and deprecation notices require maintenance, but the alternative is silent decay. Tie the point back to the partner who needs to know whether the page can guide real decisions.
-->

---

<!-- _class: lead -->

## Better AI

AI can use docs better when docs are already structured for people.

<!--
Transition into AI without treating it as magic. Explain that AI does not remove the need for reliable documentation; it amplifies the value of structure, ownership, and clear source boundaries. Keep TravelCo in view as the reader whose questions may now pass through an assistant.
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
Describe a practical AI-assisted workflow for the onboarding case. Explain that Claude can help process fragments, reveal gaps, propose structure, and draft from verified inputs, but the team still has to validate truth. Keep the workflow concrete enough that the audience can try it after the talk.
-->

---

## AI finds gaps, not truth

AI can help you move faster through the mess, but it cannot decide what is true unless the sources and humans around it make truth visible.

<!--
Set a clear boundary around AI usefulness. In the TravelCo example, AI can notice that a prerequisite appears in one source but not another, but it cannot decide which source is authoritative. Emphasize that verification remains a human and organizational responsibility.
-->

---

## Why chunks and metadata matter

Good retrieval depends on clean boundaries and useful labels.

<!--
Explain chunking and metadata in accessible terms. Use the onboarding docs map to show how sections like requirements, setup, and troubleshooting make better retrieval units than one long mixed page. Connect metadata to reader and agent trust: scope, owner, version, and freshness help the right answer surface.
-->

---

## Human-readable to agent-friendly

If a human can scan it, an assistant can often retrieve it better.

<!--
Explain that agent-friendly docs start with human-friendly structure. In the case study, clear headings, explicit prerequisites, and stable terminology help both TravelCo and AI tools find the right answer. Avoid promising automation; focus on disciplined content design.
-->

---

<!-- _class: lead -->

## Takeaway: AI rewards structured docs

Better inputs make better assistance possible.

<!--
Close the AI section by returning to fundamentals. Explain that AI raises the stakes for source quality because messy docs become messy answers at scale. Tie the point back to the same practices already covered: audience, task, truth, ownership, change, structure, and trust.
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
Summarize the talk as a short practical checklist. Explain each rule quickly through the TravelCo case so it feels actionable rather than abstract. Make this slide the memory aid the audience can carry back to their own docs.
-->

---

## What to try next

- Pick one messy page
- Map its sources
- Add one trust signal
- Ask one better review question

<!--
Give the audience a small next action instead of a giant documentation transformation. Explain that one page is enough to start practicing the method. Tie the action back to the partner onboarding story: choose a page where a real reader needs a real next step.
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
Invite questions and make space for practical discussion. Encourage people to bring up their own messy docs examples, especially places where truth is split across teams or tools. Close by reinforcing that useful docs are built through curiosity, structure, and maintenance.
-->
