# Prompt recipes

Copy one of these into the assistant to continue the work on this exact project.

1) Refactor to data-driven
> Load and validate `data/scene-config.json` in `index.html`, and rebuild the scene from that JSON (no visual changes). Add schema checks & helpful console errors for missing fields.

2) Code-compliant guardrails
> Change deck guardrail height to 1000 mm and post spacing to 1000 mm. Keep bridge rails at 600 mm. Add a toggle to show/hide balusters every 120 mm.

3) Camera & screenshots
> Add a 'Screenshot' button that saves a 1920×1080 PNG to disk. Include a 'Plan Screenshot' that automatically switches to top-down before capture.

4) Materials & lighting
> Add directional light helpers and enable contact soft shadows. Replace the wood with a PBR texture (UVs per box). Keep colors close to current look.

5) Variants & comparisons
> Add a right-side panel to save 'Variants' (A/B/C) of planter spans and guard rail specs. Buttons switch variants and animate transitions.

6) Export GLB
> Add a button that exports the deck (excluding house walls) to GLB. Maintain units in mm by scaling appropriately.
