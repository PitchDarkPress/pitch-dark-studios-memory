# SESSION NOTE — THE ROOM — 2026-05-20

## SUMMARY
GLB asset pipeline established for The Room. Assets can now be stored, credited, viewed and handed to ChatGPT in one workflow.

---

## WHAT WAS BUILT

### GLB Asset Storage
- Folder: the-room/assets/glb/
- Credits file: the-room/assets/credits.md
- Repo is PUBLIC — raw URLs work for ChatGPT direct access

### Asset Viewer
- Google model-viewer, 320px popup modal
- Drag to rotate, auto-rotate
- Eight metadata fields: Asset Path, Raw File URL, Title, Artist, Platform, Licence, Creator Credit, Locked Reference
- Sketchfab credit line parser — paste and auto-fill
- Save writes to credits.md and caches locally

### ChatGPT Handover Workflow
1. Upload GLB to DB
2. Open viewer, fill credits, save
3. Tick required fields, Copy All
4. Paste into ChatGPT — includes public repo notice and raw URL
5. ChatGPT fetches file directly

---

## ASSETS CURRENTLY IN THE-ROOM/ASSETS/GLB
- terminal.glb
- chair.glb
- notebook_material.glb
- office_desk_18mb.glb (renamed)
- animated_fire.glb
- desk_lamp.glb
- 70s_retro_computer.glb (renamed)

---

## CC BY 4.0 OBLIGATIONS CONFIRMED
- Credit artist, link to original, note licence
- Terminal screen scroll confirmed as the correct place for credits in The Room

---

## LOCKED DECISIONS
- Credits scroll on terminal screen — under Shakespeare quotes
- All assets must be credited before being locked
- Locked Reference field in viewer tracks confirmed assets

---

## WHAT STILL NEEDS DOING
- Fill in credits for all current assets
- Terminal screen credits scroll (ChatGPT session)
- Stage, scale and darken assets in The Room (ChatGPT session)