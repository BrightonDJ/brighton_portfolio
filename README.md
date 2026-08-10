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
├── publications.html      # Publications — 2 PhD Springer papers
├── notebook.html          # Research Notebook (renamed from Blog) — placeholder, topics planned
├── gallery.html           # Architecture Gallery — all system diagrams in one place
├── visualizations.html    # Interactive Visualizations — bbox rotation, attention, rotated IoU,
│                           #   Hungarian matching, loss/mAP curves, encoder-decoder flow animation
├── skills.html             # Skills — Technical Skills / Research Expertise / Emerging Areas
├── resume.html             # Resume — formatted from source PDF, printable to PDF
├── contact.html            # Contact
├── base.css                # Shared styles for every page
└── README.md
```

Navigation is 8 top-level items: About, Projects, Research, Publications, Notebook, **Lab** (dropdown
containing Architecture Gallery + Interactive Visualizations), Skills, Resume, Contact.

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

## Projects vs. Research

These intentionally cover overlapping ground from two angles:
- **Projects** — what was built and shipped (engineering-first).
- **Research** — the methodology and the published methods studied, with mathematics behind them.

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

## Resume page

`resume.html` includes a **Print / Save as PDF** button using the browser's native print dialog;
CSS hides the nav/footer automatically when printing.

## Notes

- Fonts (Fraunces, Inter, JetBrains Mono) load from Google Fonts CDN — needs an internet connection to render as intended.
- No client, defense, or proprietary imagery/data is included anywhere on the site.
