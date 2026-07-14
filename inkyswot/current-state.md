File: inkyswot/current-state.md

================================================================
*** CONCEPTS — THE IDEAS SYSTEM · BUILT & WORKING (14 July 2026) ***
Paste this block into the TOP of current-state.md (just under the Overview
section). It REPLACES the old "Ideas Database / Ideas Box" design block from
13 July — see the SUPERSEDED note at the foot. This session took the idea
from a filing-box concept to a finished, working, clickable prototype.
The working file this session: concepts-canvas.html (the full journey).
================================================================

WHAT IT IS
CONCEPTS — a writer's private store for FUTURE-story ideas, separate from any
one project. It lives ON THE MY PROJECTS SCREEN, not in its own pocket: the
screen splits, My Projects on the left (unchanged), the Ideas/Concepts area
on the right. A concept is a pre-project — a seed that may one day become one
of the books on the shelf. (The name CONCEPTS is held LIGHTLY — settled for
now, change later if a better one turns up. "Ideas" is the working heading on
screen in the prototype.)

THE STRUCTURE — THREE STAGES (locked, matches Kev's map)
GENRE FOLDER -> STORY TITLE -> MAIN STORY CARD (a canvas). No more levels.
- GENRE FOLDER: a narrow bar. Named from the real GENRE LIST (the same list
  as the Overview screen's custom dropdown — all ~50, twelve greyed "coming
  soon"). Made via a + FOLDER button, bottom-right of the Ideas area
  (mirrors + NEW PROJECT bottom-left). + FOLDER makes an EMPTY genre folder
  and nothing more.
- Click a genre folder: its STORY SUB-FOLDERS (story titles) open OUT TO THE
  SIDE (to the right), joined by a dotted connector line. Narrow genre bars
  stack tight; the opened stories float beside without adding row height.
  Stories are added by the folder's OWN + (and a "+ New story" line).
  Story titles are PLAIN BARS (just the title), not header-band cards.
- Click a STORY TITLE: its MAIN STORY CARD opens as an almost-full-screen
  POP-UP on a dimmed backdrop (modal). Title sits IN THE TOP BAR, with the
  close x. No category band in the head (that was removed — it belonged to
  earlier idea-card thinking).

THE MAIN STORY CARD = A RESIZABLE CANVAS (the heart of it)
- The story card is NOT a title-and-body page. It is a CANVAS that holds
  small header-band idea cards — a mini-board, the board idiom scaled down
  and living inside a story.
- ADD IDEA button (top bar) opens a GROUPED DROPDOWN = the platform's real
  side-menu list:
    Cast:  Characters, Relationships, Factions & Orgs, Language & Dialogue
    World: Locations, Buildings, Objects & Artefacts, Rules & Lore
    Plot:  Plot Threads, Subplots, Themes & Motifs, Events & Timeline
  Pick a category -> a HEADER-BAND CARD drops onto the canvas, named and
  COLOURED BY FAMILY (Cast = terracotta, World = teal, Plot = violet — deep
  muted tints from the platform palette). A glance tells you the kind by
  colour. Each card has a "Write your idea..." body that auto-grows, and a
  small x to remove.
- WHY IT MATTERS (the integration thread): because these are the platform's
  REAL side-menu categories, a card jotted in a Concept LATER INTEGRATES
  into the main platform when the idea grows into a project (a Location
  jotted here can carry through to the project's Locations).
- Cards DRAG FREELY around the canvas (grab the card, not the text).
- The WHOLE POP-UP is RESIZABLE (head + canvas + foot grow together — not
  the canvas alone). It opens LARGE by default (~94vw x 90vh) since it's a
  pop-up and has the room; drag the bottom-right corner to adjust.
- PROMPT and EXPAND buttons float up the right edge of the pop-up, gold,
  matching the Overview screen's Ada-assist buttons. Placeholders for now —
  to wire to the corridor's aiAutofill / aiExpand helpers when built for real.

GENRE FOLDER COLOUR (locked)
- Default = a REPEATING PALETTE of the SIX TRACK COLOURS (deep muted body
  tints, so folders sit calm in the dark, light text on deep bar). New folder
  takes the next colour; loops after six.
- The writer CAN CHANGE any folder's colour: a small colour dot on each bar
  opens a six-swatch picker (same six, same idiom as the note palette).

THE EMPTY-CARD IDIOM (settled, kept)
- An empty/unfiled card is a DASHED OUTLINE only (no fill) — tab band and
  body both just a soft pencil-grey stroke on the black. It earns its colour
  by being filled/filed. (Chosen over a grey fill — an empty idea is honestly
  empty.)

BUILT FROM THE TRUTH
- The header-band card was lifted from code-board-rotated.html (the take-6
  cards: .note-tab band + .note-card body + "Write your idea..." + Details).
- The genre list was read from project-overview.html (the real dropdown).
- The side-menu category list (Cast/World/Plot, 12 items) came from Kev.

STILL TO DO (next session)
- The "+ New story" and folder "+" are demo placeholders — build the actual
  story-naming step.
- Wire Prompt / Expand to the real Ada helpers (aiAutofill / aiExpand).
- PERSIST — folders, stories, cards, and card positions must save into the
  InkySwot database (and integrate the cards into the main platform entities
  when a concept becomes a project).
- Decide if a card, once dropped, needs anything beyond its body (kept
  deliberately just body for now — the seed end must not be forced).
- A gold-rendering niggle on Prompt/Expand on Kev's screen was NOT resolved
  (the icons were flat system glyphs; swapped to gold SVGs; Kev still saw no
  gold — likely browser/cache, left for later).

BANKED FOR future.md (from the dropped face-generator idea, still valid)
- (a) richer CHARACTER fields; (b) ADA AS CONTINUITY-GUARD ("written with
  long hair, but his record says short"). Banked, not started.

----------------------------------------------------------------
*** SUPERSEDED — the 13 July "Ideas Box / filing-box" design ***
The filing-box metaphor (face-on drawer, genre divider TABS across the top,
an Unfiled tab, cream front card, brass pull, four richness levels) was
ABANDONED this session. Reason: it chased theatre over usability. It was
replaced by the simple Concepts system above (folders on the My Projects
screen). The header-band CARD idiom and the DASHED-empty state survived from
that thinking; everything else about the box (drawer, tabs-as-furniture,
folding cards, the peeking-blank-card, richness levels) is dropped. Do not
rebuild the box.
----------------------------------------------------------------