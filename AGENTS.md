# AGENTS.md

This file guides Codex and other coding agents when working in this repository.

## Web Search

Do not use the built-in WebSearch tool. It does not work at Booking.com.
Use the websearch MCP tools (`mcp__websearch__*`) for all web searches instead.

## Repository Purpose

This repository is a single [Marp](https://marp.app/) presentation deck for a
talk about technical writing and technical documentation. There is no
application code. The source of truth is Markdown, rendered by Marp CLI into
HTML, PDF, and PPTX.

## Project Layout

- `source/slides.md` is the deck source. Marp front matter, slide content, and
  speaker notes live here.
- `.marprc.yml` is the central Marp CLI configuration. It sets `inputDir:
  ./source`, `output: ./output`, `themeSet: ./assets/themes`, `theme: dracula`,
  `template: bespoke`, `allowLocalFiles: true`, and the HTML allowlist.
- `assets/img/` contains images used by slides. Image paths in `source/slides.md`
  are relative to that file, usually `../assets/img/<filename>`.
- `assets/themes/` contains Marp theme CSS. Change the active theme in
  `.marprc.yml` unless the user explicitly asks for a per-slide override.
- `output/` is generated output. Rebuild it with Marp instead of hand-editing
  HTML, PDF, or PPTX files.
- `plans/` and `playground/` are working areas, not deck source.
- `.vale.ini` and `vale-styles/` are for optional prose linting.

## Common Commands

Use npm scripts first so `.marprc.yml` stays the single source of Marp settings:

```bash
npm install          # install dependencies
npm run marp:serve   # live preview server on port 9999
npm run marp:html    # build output/slides.html
npm run marp:pdf     # build output/slides.pdf
npm run marp:pptx    # build output/slides.pptx
npm run lint         # markdownlint *.md in the repo root
npm run format       # markdownlint --fix *.md in the repo root
```

For slide-specific linting, run:

```bash
npx markdownlint source/slides.md
```

For prose linting, if Vale is installed:

```bash
vale sync
vale source/slides.md
```

## Marp Authoring Guidance

- Preserve the top YAML front matter and keep `marp: true`.
- Use `---` on its own line to separate slides.
- Keep speaker notes in HTML comments below the slide they belong to.
- Do not reflow the entire deck for small edits. Treat each slide as a small,
  independent unit.
- Prefer concise slide text and put delivery detail in speaker notes.
- Keep image references local and relative to `source/slides.md`.
- Before adding or changing background images, verify the file exists in
  `assets/img/`.
- Use Marp background directives such as `![bg left:50%](../assets/img/foo.jpg)`
  and `![bg contain](../assets/img/bar.png)` instead of custom layout hacks.
- Keep the active theme in `.marprc.yml` so HTML, PDF, and PPTX exports match.
- If adding raw HTML, make sure it is compatible with `.marprc.yml` and all
  target exports.

## Agent Workflow

- For content edits, inspect the slide map first:

  ```bash
  rg --color never -n "^---$|^#{1,3} " source/slides.md
  ```

- For structural changes, update one slide or section at a time, then render:

  ```bash
  npm run marp:html
  ```

- For visual changes, render HTML and inspect the result in a browser. Check for
  broken images, clipped text, unreadable contrast, and slides that rely on
  assets that are not committed.
- For export changes, run the exact target command (`npm run marp:pdf` or
  `npm run marp:pptx`). PDF and PPTX exports require a Chromium-class browser.
- Keep `AGENTS.md` and `CLAUDE.md` aligned except for agent-specific wording.
