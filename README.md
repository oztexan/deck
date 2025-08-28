# Deck Viewer (Three.js, VS Code)

This folder is a self-contained **VS Code** project for your deck concept. It uses **Three.js** via **import maps** (no bundler required).  
Open `index.html` directly or run a tiny web server for nice module support and live reload.

## Quick start

### Option A — Open file
Just open `index.html` in your browser. (Chrome/Edge/Safari usually allow local import maps; if not, use Option B.)

### Option B — Live Server (recommended)
1. Install the VS Code extension **Live Server** (Ritwick Dey).
2. Right-click `index.html` → **Open with Live Server**.

### Option C — Node static server
```bash
npm install
npm run dev
```
Then open the URL printed in your terminal.

## What’s inside

- `index.html` — the live viewer (E/W mirror baked, orbit auto-center, water, planters = 400 mm deep extruded to z=-300, rails along pond edge).
- `data/scene-config.json` — the dimensions & elements captured as data for future refactors (not yet used by `index.html`, but ready to wire up).
- `.vscode/` — editor settings and extension recommendations.
- `package.json` — `npm run dev` uses a tiny static file server.

## Controls

- Left-drag: orbit • Right-drag: pan • Mousewheel: zoom  
- Buttons: **Top‑down**, **Recenter**, **Reset view**  
- Toggles: Deck, Stairs, Rails (deck + bridge), Planters, Fireplace, House walls, Water, North arrow, Axes, Grid

## Orientation & units

- Axes: **x = east (+)**, **z = north (+)**, **y = up (+)**  
- All dimensions are **millimetres**.  
- E/W mirror is **baked in** so the model matches your plan.

## Next steps (ideas)

- **Data-driven scene:** Replace hard-coded arrays with a loader for `data/scene-config.json` so updates are one-file edits.
- **Code‑compliant rails:** Parameterize height (e.g. 1000–1200) and add intermediate rails/balusters or glass.
- **Shadows & materials:** Add soft shadows, wood grain textures, or switch to photoreal PBR.
- **Exports:** Add buttons to export **PNG** screenshots or a **GLB** model.
- **Measurements overlay:** Draw dimension lines for print-ready elevations/plan.
- **Variants:** Toggle stair counts/going, planter spans, or pond width.
- **React/Vite port:** Wrap in a React component for stateful UI if desired.

## Prompt handover (copy/paste snippets)

Use these prompts to have the assistant pick up exactly where we left off:

- “**Load `data/scene-config.json` and refactor `index.html` to build the scene from it. Keep all current visuals identical.**”
- “**Change deck guardrail height to 1000 mm and post spacing to 1000 mm, then regenerate `index.html`.**”
- “**Move the pond 300 mm further south (negative z), keep width the same, and update rails accordingly.**”
- “**Add a screenshot button that saves a 1920×1080 PNG with the current camera and layer toggles.**”
- “**Replace planters with a continuous bench (w=450, h=450) along the south edge, except across the bridge opening.**”
- “**Port this to a Vite + React project with the same features and a side panel for parameters.**”

## Known-good parameters (for reference)

These are the exact numbers reflected in `index.html` and `data/scene-config.json` (source of truth: `index.html`).

- **Deck plates:** 4280–7350×0–5700; 0–4280×0–4620; 3150–4350×−2000–0, z=0–25  
- **Stairs:** y=3420–4620, 4 risers, going=270, rise≈162.5, nosing west
- **Pond:** x=1650–5850, y=−2000–0, z=−300…−290
- **Rails:** bridge sides plus south segments at y=0 over pond
- **Planters:** all depth 400; z=−300…400 (west long; south‑west cropped to x≤1650; east along x=6450..7350)
- **Fireplace:** 1200 deep brick column; round metal flue
- **House walls:** hugging deck along north & east, h=3000


## Deploying to GitHub Pages

This repo is preconfigured with a **GitHub Actions** workflow at `.github/workflows/pages.yml`.

**Steps:**
1. Create a new GitHub repo and push this folder to it on the `main` branch.
2. On GitHub, go to **Settings → Pages → Build and deployment → Source** and choose **GitHub Actions**.
3. Push to `main` again (or wait if you just pushed) — the workflow will build and deploy automatically.
4. Your site will be live at: `https://<username>.github.io/<repo-name>/`

No build step needed — it uploads the static files directly.
