# Erick James Sibayan — Portfolio

A dark, interactive personal portfolio built with plain HTML/CSS/JS and Three.js — featuring a rotating 3D chrome monogram, a magnetic interactive line field, and a projects/experience page with hover-driven animations.

Design direction inspired by [TRIONN](https://trionn.com)'s 404 page: near-black backgrounds, bold monospace/grotesk type, glowing chrome extrusions, and draggable background lines.

## Live pages

| File | What it is |
|---|---|
| `index.html` | Landing page — rotating 3D "EJS" monogram, name, role, and a "Get in Touch" contact modal |
| `projects.html` | Projects grid + experience timeline, with 3D tilt cards, magnetic buttons, and scroll-reveal animations |
| `resume.pdf` | **Not included yet** — add your resume PDF here so the "Resume" buttons work |

## Features

- **3D rotating monogram** (`index.html`) — real WebGL text extrusion via Three.js, auto-rotating with a traveling glow light and cursor-based parallax tilt
- **Interactive line field** — faint background lines bend magnetically toward your cursor on both pages; click-and-hold on the home page triggers a spark "blast"
- **Contact modal** — opens from "Get in Touch" on either page (Name / Email / Message), styled to match the dark theme; front-end only, no backend wired up
- **Projects grid** — each card tilts in 3D and shows a cursor-following spotlight on hover, with links out to GitHub repos
- **Experience timeline** — hover-highlighted entries covering internships, freelance work, and education
- **Scroll-reveal animations** — cards, timeline entries, and section labels fade/slide in as you scroll
- **Magnetic buttons** — nav pills and CTA buttons nudge toward your cursor on hover

## Tech stack

- Vanilla HTML/CSS/JavaScript (no build step, no framework)
- [Three.js r128](https://threejs.org/) (loaded via CDN) for the 3D monogram
- Google Fonts: [Space Grotesk](https://fonts.google.com/specimen/Space+Grotesk) (display) + [JetBrains Mono](https://fonts.google.com/specimen/JetBrains+Mono) (UI/body)
- Canvas 2D for the interactive line field and spark particles

## Running locally

No build tools needed — just open the file in a browser:

```bash
# from the project folder
open index.html        # macOS
start index.html        # Windows
```

Or serve it locally (recommended, since some browsers restrict certain features on `file://`):

```bash
python -m http.server 8000
# then visit http://localhost:8000
```

> Both pages load Three.js and Google Fonts from a CDN, so you'll need an internet connection for the 3D effect and fonts to render correctly.

## Deploying (GitHub Pages)

1. Push this folder to a GitHub repo
2. Go to **Settings → Pages**
3. Set the source branch to `main` (or wherever these files live) and the folder to `/root`
4. Your site will be live at `https://<username>.github.io/<repo>/`

## Still needs your input

- [ ] **Add `resume.pdf`** to this folder — the "Resume" / "Download Resume" buttons link to it but it doesn't exist yet
- [ ] **Fill in remaining GitHub repo links** — a few project cards on `projects.html` still point to your GitHub profile instead of their specific repo:
  - AiNomally
  - TrabaguioHanap
  - Senti-BPO
  - 100 Degree Café
- [ ] **Verify project descriptions** — descriptions for Ice Cream Man, Church Analysis, Customer Churn Prediction, Civil Portfolio, and Erick were written from repo names alone since I don't have details on what each one does; swap in real descriptions when you can

## Customizing

- **Colors**: edit the CSS custom properties at the top of each file's `<style>` block (`--bg`, `--ink`, `--glow-1`, `--glow-2`, etc.)
- **Monogram text**: change the `'EJS'` string passed to `TextGeometry` in `index.html`'s script
- **Rotation/glow speed**: adjust the `t += 0.012` increment and the `Math.sin(t*0.6)` terms in the `renderThree()` function
- **Line field density**: change the `NUM` constant in either file's script

## Credits

- Visual direction inspired by [TRIONN](https://trionn.com)
- Built collaboratively with Claude
