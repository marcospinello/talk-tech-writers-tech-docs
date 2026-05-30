# talk-tech-writers-tech-docs

A Marp-based slide deck for a talk introducing technical writing and technical
documentation to non-expert audiences.

The deck is authored in Markdown at `source/slides.md` and rendered with
[Marp CLI](https://github.com/marp-team/marp-cli) into HTML, PDF, and PPTX.

## Repo Layout

| Path | Purpose |
| --- | --- |
| `source/slides.md` | The source file for the slide deck. Edit this while authoring. |
| `.marprc.yml` | Marp CLI configuration for input/output folders, theme, template, and HTML handling. |
| `assets/themes/` | Local Marp themes. The active theme is configured in `.marprc.yml`. |
| `assets/img/` | Local images referenced from slides as `../assets/img/<filename>`. |
| `output/` | Generated HTML, PDF, and PPTX files. Rebuild these; do not edit them by hand. |
| `package.json` | npm dependencies and project commands. |

## Prerequisites

- Node.js 18 or later, with npm.
- A Chromium-class browser, such as Chrome, Edge, Brave, or Chromium, for PDF
  and PPTX export. HTML output and the live preview server do not need it.

## Install Dependencies

For a clean install that follows `package-lock.json`, run:

```bash
npm ci
```

For day-to-day dependency installation or when intentionally updating the lock
file, run:

```bash
npm install
```

## Get Started

Start the live preview server:

```bash
npm run marp:serve
```

Open `http://localhost:9999/source/slides.md` in a browser and edit
`source/slides.md`. The server watches the project and refreshes as you work.

## Build Outputs

The recommended commands use the npm scripts in `package.json`, which in turn
use `.marprc.yml`.

| Output | Command | Result |
| --- | --- | --- |
| HTML | `npm run marp:html` | `output/slides.html` |
| PDF | `npm run marp:pdf` | `output/slides.pdf` |
| PPTX | `npm run marp:pptx` | `output/slides.pptx` |

The direct Marp CLI equivalents are:

```bash
npx marp --config-file .marprc.yml --html --allow-local-files source/slides.md -o output/slides.html
npx marp --config-file .marprc.yml --pdf --allow-local-files source/slides.md -o output/slides.pdf
npx marp --config-file .marprc.yml --pptx --allow-local-files source/slides.md -o output/slides.pptx
```

## Authoring Notes

- Keep all slide content in `source/slides.md`.
- Separate slides with `---` on its own line.
- Speaker notes live in HTML comments under the slide they support.
- Keep images in `assets/img/` and reference them from `source/slides.md` with
  paths like `../assets/img/example.jpg`.
- Change deck-wide Marp settings in `.marprc.yml`, not in generated output.
- If an export shows broken backgrounds, check that every referenced image file
  exists in `assets/img/`.

## Linting

Run Markdown linting for root-level Markdown files:

```bash
npm run lint
```

Run Markdown linting for the slide source:

```bash
npx markdownlint source/slides.md
```

If Vale is installed and the styles are available, run prose linting with:

```bash
vale sync
vale source/slides.md
```
