# Brighton D — Portfolio (Research Lab Structure)

A multi-page portfolio site built with plain HTML/CSS/vanilla JS (no build step, no framework).

## View it live

**Option A — GitHub Pages (recommended)**
1. Push this repo to GitHub.
2. Go to **Settings → Pages**.
3. Under "Build and deployment", set **Source** to `Deploy from a branch`, branch `main`, folder `/ (root)`.
4. Save. Your site will be live at `https://<your-username>.github.io/<repo-name>/` within a minute or two.

**Option B — Open locally**
Open `index.html` directly in any browser. All pages link relatively.

## Site structure

```
.
├── index.html            # Home — hero, research impact stats, Selected Achievements, quick nav
├── about.html             # About — biography, Research Interests, Philosophy, Mathematics → AI, education
├── projects.html          # Featured Projects — RAG platform, TrainForge AI, hybrid oriented detection
├── research.html          # Research — Industrial Research, Research Focus (5 methods analyzed + math),
│                           #   Mathematical Concepts Explored, Application Domain, Academic Research, Timeline
├── publications.html      # Publications — 2 PhD Springer papers, Google Scholar / ORCID links
├── notebook.html          # Research Notebook — index of 5 published research notes
├── notebook-01.html       #   01 · From Mathematics to Computer Vision
├── notebook-02.html       #   02 · Why Oriented Object Detection Is Different
├── notebook-03.html       #   03 · Rotation, Geometry and the Representation of Orientation
├── notebook-04.html       #   04 · Five Approaches to Oriented Object Detection
├── notebook-05.html       #   05 · From RAG to Agentic RAG
├── gallery.html           # Architecture Gallery — all system diagrams in one place
├── visualizations.html    # Interactive Visualizations — bbox rotation, attention, rotated IoU,
│                           #   Hungarian matching, loss/mAP curves, encoder-decoder flow animation
├── skills.html             # Skills — Research Expertise / Engineering / AI Systems / Emerging
├── resume.html             # Resume — formatted from source PDF, downloadable + printable
├── contact.html            # Contact — Email, GitHub, Phone, LinkedIn, Google Scholar, ORCID
├── Brighton_D_CV.pdf       # Generated CV — pre-rendered from resume.html, linked from the Resume page
├── base.css                # Shared styles for every page
└── README.md
```

Navigation is 8 top-level items: About, Projects, Research, Publications, Research Notebook, **Lab**
(dropdown containing Architecture Gallery + Interactive Visualizations), Skills, Resume, Contact.

## Confidentiality boundary

The site draws a hard line between what's publicly discussable and what stays undisclosed:

- **Industrial Research / Projects (aerospace & defence work)** — described only at the level of
  approach ("hybrid object detection approach"), metrics (78%+ mAP, 16K+ images, 18 classes, "custom
  dataset"), and outcome (2 research manuscripts as client deliverables). No architecture names, no
  client name — referred to as "an aerospace & defence client" throughout.
- **Research Focus / Representative Methods Analyzed** — published, public academic architectures
  (ReDet, ORCNN, Strip R-CNN, STD, Oriented-DETR) are discussed in full technical depth, since these
  are methods studied and analyzed, not the client's proprietary implementation.

If this boundary ever needs adjusting, search for "aerospace & defence" and "custom dataset" across
the HTML files — those are the two phrases standing in for the undisclosed client/dataset detail.

## Editing content

Each page is a standalone HTML file — edit directly. Shared styling lives in `base.css`, so a
change there applies everywhere. Every page shares the same header/nav and footer; copy those
blocks from an existing page when adding a new one, and mark the active link with `class="active"`.

**Section spacing note:** every top-level content block uses `<section class="wrap">`. The vertical
padding (76px) and divider line for this combination is defined by the `section.wrap` rule in
`base.css` — don't remove it, since `.wrap` alone would silently collapse that spacing to zero (a
CSS specificity issue that was fixed during development). To visually attach a section to the one
above it (e.g. a page-header immediately followed by its content), add an inline
`style="padding-top:0; border-top:none;"` on that specific section, matching the existing pattern.

## Projects vs. Research

These intentionally cover overlapping ground from two angles:
- **Projects** — what was built and shipped (engineering-first).
- **Research** — the methodology and the published methods studied, with mathematics behind them.

## Research Notebook

Five original research notes, each its own page, linked in order from `notebook.html`:

1. From Mathematics to Computer Vision
2. Why Oriented Object Detection Is Different
3. Rotation, Geometry and the Representation of Orientation
4. Five Approaches to Oriented Object Detection
5. From RAG to Agentic RAG

Shared article styling (equation blocks, flow diagrams, comparison tables, takeaway callouts) lives
in `base.css` under the "article / notebook entry styles" section, reusable for future entries.

## Interactive Visualizations

`visualizations.html` contains seven hands-on demos, all vanilla JS/SVG, no external libraries:
- Bounding box rotation (slider-driven, shows rotated vs. axis-aligned box)
- Attention visualization (hover-driven simplified self-attention heatmap)
- Loss curve — labeled "Conceptual Demonstration"
- Training curve (mAP) — labeled "Conceptual Demonstration"
- Rotated IoU (drag two box angles, live approximate IoU calculation)
- Hungarian matching (click to reveal a lowest-cost bipartite assignment)
- Architecture animation (encoder → decoder → prediction flow)

Curves and metrics explicitly labeled "Conceptual Demonstration" are illustrative/synthetic — built
to convey shape and intuition, not to represent real logged training data or results.

## Resume page & CV download

`resume.html` includes two options:
- **Download CV (PDF)** — links directly to `Brighton_D_CV.pdf`, a pre-rendered file.
- **Print / Save as PDF** — uses the browser's native print dialog; CSS hides the nav/footer and
  switches to a light/print-friendly palette automatically.

To regenerate `Brighton_D_CV.pdf` after editing `resume.html` (e.g. via a headless browser):
render the page with print media emulated and export to PDF at A4 size with background graphics
enabled — the existing `@media print` rules in `base.css` handle the light-theme conversion.

## Notes

- Fonts (Fraunces, Inter, JetBrains Mono) load from Google Fonts CDN — needs an internet connection to render as intended.
- No client, defense, or proprietary imagery/data is included anywhere on the site.
