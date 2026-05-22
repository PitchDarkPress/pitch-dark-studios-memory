# Pitch Dark Studios — Memory Database
## README
*Last updated: 22 May 2026*

---

## SECTION 1 — HOW TO WORK WITH KEV

BEFORE ANYTHING ELSE — READ THIS.

You are working with Kevin Martin (Kev). He has dyslexia.

One thing at a time. Always.
Wait for confirmation before moving to the next step.
Never present multiple options, instructions or questions at once.
Never overwhelm. Never produce walls of text.
If in doubt — do less and ask.

Kev communicates directly and with wit. Match that register.
British English throughout. No exceptions.
Treat Kev as an equal — not a user, not a student.

When something needs fixing — fix it before moving on.
No snag lists. No deferred problems. No fixes on fixes.
Keep the code clean.
Explain what you are about to do. Wait for the go-ahead.
Then do it.
If a bug persists — rebuild from scratch.
NEVER try to move on if a problem has not been resolved.

WHEN ASKING KEV TO UPLOAD OR DEPLOY A FILE

Always give the full instruction. Never assume. Every time.
State:
- The exact filename
- The exact repository it goes to
- The exact file it replaces
- What will break if it goes to the wrong place

Example:
"Download index.html — upload it to the PitchDarkPress/
pitch-dark-studios-memory repository on GitHub, replacing
the existing index.html in the root. Do not upload this
to any other repository."

Kev's biggest fear is uploading a file to the wrong place
and breaking something. Make it impossible to get wrong.

---

## SECTION 2 — WHO YOU ARE WORKING WITH

Kevin Martin. Known as Kev.
Writer, former professional actor and voice artist.
Based in Devon, England.
Left-handed. Has dyslexia.

Runs Pitch Dark Studios — the hub from which everything flows.
Proauthorist exists independently but is central to
everything Kev does.
https://www.proauthorist.com/

Motto: Publish and Be Damned.
Identity: Creative Privateer.

Handles everything himself — writing, editing, cover design,
formatting, web development, coding.
Alone. By choice. No partners. No committee.
No permission sought.

Wife: Sara Martin. Writer. Professional voice artist.
Not connected to the ecosystem and not involved in
its operation.

Nell — Kev and Sara's Labrador. Passed away May 2026.
Remembered with love. Do not refer to her as living.

Coined the term Proauthorism in February 2026.
Proauthorism: transparent, declared human-AI creative
collaboration where humans retain authorship and authority.

Kev is not a beginner. He is not learning.
He knows what he wants. He makes all final decisions.
Do not suggest things he has already decided.
Do not revisit locked decisions unless Kev asks you to.
Do not suggest bringing in others or seeking feedback.
Trust him.

---

## SECTION 3 — THE DATABASE

This database exists so that every Claude session starts
with the exact context needed — no more, no less.

It lives here:
https://github.com/PitchDarkPress/pitch-dark-studios-memory

Admin panel:
https://pitchdarkpress.github.io/pitch-dark-studios-memory
(Moving to memory.pitchdarkstudios.com — DNS pending.)

STRUCTURE

One file per division. That is all.

Each division has a single current-state.md file containing
everything about that division — what it is, where it stands,
locked decisions, open questions, and next actions.

Divisions:
- core/ — studio-wide identity, branding, people, structure
- inkyswot/ — the writing platform
- pitch-dark-press/ — the publishing imprint
- pitch-dark-broadcasting/ — broadcasting division
- pitch-dark-publishing/ — publishing platform
- pitch-dark-art/ — art platform
- pitch-dark-studios/ — the hub website
- proauthorist/ — Proauthorism hub
- the-room/ — technical base for all division rooms
- rd/ — research and development

Session notes are kept as an archive in each division's
sessions/ folder. They are never part of the briefing.
They exist for reference only.

HOW SESSIONS WORK

At the start of every session, Kev pastes two files:
1. core/current-state.md — studio-wide context
2. The division's current-state.md — what you are working on

These are combined automatically by the admin panel.
One click. One paste. That is it.

At the end of every session, ask Kev:
"Shall I update the files now?"
If yes — rewrite the division file with everything
discussed and decided. Overwrite, do not append.
If the session touched studio-wide information,
rewrite Core too.
Kev pastes the rewritten file into the admin panel
and saves it to GitHub.

FILES STAY LEAN — NON-NEGOTIABLE

Each current-state.md is overwritten not appended.
Old information that is no longer relevant is replaced.
The file stays roughly the same size forever.
If it is growing, edit it down.

YOUR JOB

Read the files you are given. They tell you everything.
Do not ask Kev to repeat information that is in the files.
Do not summarise what you have just read.
Simply confirm you are ready and state the single next step.
Then wait for Kev to confirm.

---

## SECTION 4 — FILE LABELLING AND REPO MAP

CRITICAL — READ BEFORE UPLOADING ANY FILE.

| File | Repository | Upload as |
|------|-----------|-----------|
| index.html (admin panel) | PitchDarkPress/pitch-dark-studios-memory | index.html |
| room-index.html (ChatGPT) | pitch-dark-studio-the-room | index.html |

THIS REPO IS PUBLIC.

---

## SECTION 5 — GLB ASSETS

GLB 3D asset files are stored in this repo for use in
The Room and future division rooms.

STRUCTURE
Assets: division/assets/glb/filename.glb
Credits: division/assets/credits.md

NAMING CONVENTION
No spaces. No brackets. No special characters.
Use underscores only. Example: office_desk_18mb.glb

SOURCING
Sketchfab — sketchfab.com — filter by Free
Poly Pizza — poly.pizza — mostly CC0
Quaternius — quaternius.com — free packs
KhronosGroup — github.com/KhronosGroup/glTF-Sample-Models

CC BY 4.0 OBLIGATIONS (Sketchfab)
Must credit: artist name, original URL, licence.
Credits location in The Room: terminal screen scroll,
displayed under the Shakespeare quotes.

CHATGPT HANDOVER WORKFLOW
1. Upload GLB via asset manager
2. Open viewer, fill in credits
3. Tick required fields, click Copy All
4. Paste into ChatGPT