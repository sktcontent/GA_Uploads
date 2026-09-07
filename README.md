# Course Content Gap Analysis

A single-file, client-side web app that compares two OLX course exports (e.g. an edX course and its SkillUp/myclass equivalent) and shows a module-by-module gap analysis: which topics match, which have asset differences, which are missing, and which are extra.

No backend, no build step, no dependencies — everything (tar/gzip decompression, XML parsing, comparison logic, dashboard rendering) runs in the visitor's browser.

## Usage

1. Open `index.html` (or the GitHub Pages URL for this repo) in Chrome, Edge, or Firefox.
2. Export each course from its Studio/authoring tool as an OLX `course.tar.gz` file (Studio → **Export Course**).
3. Upload Course A and Course B into the two drop zones.
4. Click **Run gap analysis**.

You'll get:
- Summary stats (total topics, matches, asset differences, missing, extra)
- Filterable, searchable, module-by-module breakdown
- Color-coded status per topic: Match / Asset diff / Missing in B / Extra in B

## Requirements

- A modern browser with support for the native `DecompressionStream` API (current Chrome, Edge, Firefox).
- Course exports must be in **OLX format** (the standard Open edX course export structure: `course/course.xml`, `course/chapter/*.xml`, `course/sequential/*.xml`, `course/vertical/*.xml`).

## Hosting on GitHub Pages

1. Upload `index.html` to the repo root.
2. Repo Settings → Pages → Source: Deploy from a branch → `main` / `(root)` → Save.
3. Your app will be live at `https://<username>.github.io/<repo-name>/`.

## Privacy

Nothing is uploaded to a server. All file processing happens locally in the browser tab.
