# placement-dashboard

Static dashboard for a placement pipeline. Two branches, on purpose:

- **`main`** — the static site (HTML/CSS/JS, no build step). Changes rarely. Served by GitHub Pages.
- **`status`** — machine-written JSON data under `data/`, pushed by `pp publish`. **Not** a Pages branch, so pushes to it trigger no Pages build (GitHub Pages has a soft limit of 10 builds/hour).

The site reads `data/` from the `status` branch via the GitHub contents API, falling back to `raw.githubusercontent.com` on rate-limit.

## What is published here

Stage states, keyword *terms* with their JD line numbers and match state, and interview question checklists.

## What is never published here

Profile facts, contact details, resume `.tex` sources, the master resume, original job descriptions, pre-placement-talk material, and the raw page cache. A PII scan runs before every push and aborts it on any hit.

Site content lands here in Phase 6 of the build.
