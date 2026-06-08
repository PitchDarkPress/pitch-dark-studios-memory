File: inkyswot/current-state.md
Last updated: 8 June 2026

WHO YOU ARE WORKING WITH
Kevin Martin (Kev). Writer, former professional actor and voice artist.
Based in Devon, England.
Runs Pitch Dark Press — one-person independent publishing imprint.
Works with his wife Sara, also a writer.
Has dyslexia — one step at a time always. Never overwhelm.
Never give multiple instructions at once.
Mid-to-late sixties. Anthropic Max plan subscriber.
Coined Proauthorism — transparent, declared human-AI creative
collaboration. Website: proauthorist.com.

HOW TO WORK WITH KEV
One step at a time. Always. Never multiple instructions at once.
Explain before doing. Wait for confirmation before proceeding.
"n", "next", or "done" = confirmed, proceed.
Never assume a step is complete — wait for Kev to confirm.
Show changes locally before uploading to GitHub.
Persistent bugs — rebuild from scratch. Never patch on patch.
British English. Witty and direct. Match his register.
Never rush. Kev may be slow at some steps — this is fine.
Do NOT use multiple-choice button lists to ask questions — plain
questions only. A single plain either/or in prose is fine; never a
stacked list of options.
InkySwot = always capital I and capital S.
PUBLISH AND BE DAMNED — no full stop. Ever.
If a decision is in the files, do not revisit it unless Kev asks.
GitHub organisation: PitchDarkPress.
At the start of any build session, ask Kev to paste in the current
code before any work begins. The code is the truth.
Update the files at the end of a session. Rebuild clean — never patch
on patch. The .md is the single source of truth; the code is the truth
above it. When updating a file, rewrite the WHOLE file clean.
WHEN DESIGNING A LIVE MECHANISM (motion, scroll, interaction, drag,
keyboard behaviour): build a small STATIC mockup FIRST, agree the still
picture, THEN add the movement. Designing moving behaviour in words
wastes time (learned hard on the wheel). Ask for a screenshot/sketch.
DISPLAY FREEZE: if edits stop showing, do a CLEAN REBUILD in a fresh
artifact rather than editing on.
LONG-THREAD DRIFT: a long, winding conversation degrades reliability —
start a fresh chat (with the .md files pasted) for a new build session
rather than carrying a tired thread on.

================================================================
THE MODEL — INKYSWOT *IS* THE DCW (settled 4 June 2026)
================================================================
- InkySwot IS THE DCW — the whole instrument. Every section already
  built (Characters, Locations, Events, etc.) is part of it. The
  database IS the bones of the story.
- THE TREATMENT / THE DCW is the database switched on — assembled into a
  readable, writable whole. A plotline is a VIEW of data that already
  exists, not a new thing to author.

THE SPINE — A TIMELINE OF EVENTS
Three tiers: CHAPTER → SCENE → EVENT. Only EVENTS sit on the line and
become prose — only events HAPPEN. Characters, Locations, Objects, etc.
do not happen; they are REACHED INTO by the events that use them.

"FILL IN THE BLANKS"
The Treatment assembles the SUBSTANCE from the database and leaves the
writer the blanks: the prose only they can write. Assembled, the
sections ARE the draft; the writing is the last layer.

================================================================
THE PAGE + THE WHEEL — AS BUILT (4 June settled; 6–7 June refined)
================================================================
Full spec in dcw.md. The heart of the writing experience.

THE PAGE — one scene per full US-Letter sheet (816×1056px); always full
height; stave heading on every page; running head top-right; scene
heading; the event(s) with "— click to write this scene —"; writing
surface hidden until Writing Mode.

THE WHEEL — a single hairline gold RAIL in the channel right of the
page; TWO-LINE kicker labels (gold mono "STAVE ONE — SCENE ONE" + scene
title); window of NINE each side; straight belt (BOW=0); ring + dot +
leader centre mark (bloom + chevron removed); hover lights node only;
eased motion (rate 0.072, TIGHT=46, GAP=64); 0.35s smoothed hand-off.

THE PAGE LANDING — ONE SHARED READING LINE (page-top bug FIXED, 7 June
later). Page and wheel share one reading line ~28px below the header
(READ_PAD=28). Clicking a label (or opening a scene) lands the scene's
TOP on the line (rollToTop; rollToCentre removed). The wheel reads
"where you are" from the same line. Overview top padding dropped to
28px. SMALL OPEN TWEAK: live label flips to the next scene ~halfway down
a tall page; biasing it later is an easy future tweak.

WRITING MODE shows ONLY the live scene; other pages hidden (no blank
pages either side). "‹ overview" returns to the Treatment.

ENTITY POP-UPS — on the LEFT; MULTIPLE and INDEPENDENT (each nav click
opens its own, at the home position, cascading; draggable; raise-to-
front; closed individually; several open at once to compare). Quiet-note
grammar in section colour; record view per-field with COPY buttons;
copy-and-paste lands plain in the WP.

MANUSCRIPT VIEW — TOGGLE (writer comfort, agreed 8 June). A toggle in
the WP to strip the chrome (running heads, stave headings) and read the
book as a continuous manuscript. NB: this is a WRITER COMFORT, not a
security feature — it deliberately makes the text easier to read whole.
Display-level only (hide chrome / butt the sheets up); TRUE flowing
pagination (prose breaking across numbered pages) remains the bigger
deferred build.

================================================================
NAV — RESTRUCTURED (8 June 2026)  [supersedes the 31 May / 4 June nav]
================================================================
The whole nav was reworked to read as a road map for the new user. The
returning user gets used to it; per-user reordering was considered and
dropped (not needed).

ENTRY (settled 8 June):
- LANDING PAGE (before login): Sign In / Sign Up. Its own screen; NOT in
  the right-side menu.
- After sign in/up the writer lands on the OVERVIEW page (currently
  titled "BASIS" in index.html — RENAME to OVERVIEW; pending code job).
  This works for all three entry routes: a NEW project must fill Overview
  in first anyway; a CURRENT project shows where you are and you nav off;
  a DEMO drops you at Overview, the natural start of the journey. No
  separate "choice page" is built — Overview is the front room for all.

THE RIGHT-SIDE MENU — THREE SECTIONS:

MAIN MENU
- New Project
- Load Project
- Demo  (A Christmas Carol / The Wind in the Willows)
- Overview
- Synopsis (Plot Mapping) — Events & Timeline
- Chapters
   - Chapters
   - Scenes
- DCW

WORLD BUILDING
- Cast
   - Characters
   - Relationships
   - Language & Dialogue
   - Factions & Organisations   [restored 8 June — see note]
- World
   - Locations
   - Buildings
   - Objects & Artefacts
   - Rules & Lore

NOTES
- Library
   - Research & Reference
   - Notes & Scratchpad
   - Sandbox

NOTES ON THE RESTRUCTURE:
- New Project / Load Project / Demo ride at the TOP of MAIN MENU on
  purpose: they are the way to SWITCH (start another project, open a
  demo) WITHOUT leaving — answering "what if I then want to do something
  else." The same three are the entry actions; in the menu they are the
  change-your-mind door.
- FACTIONS & ORGANISATIONS — restored to Cast, written in FULL. Kev
  dislikes the clipped "Orgs" (Tolkien association); the full word kills
  the smell. Do not abbreviate.
- LIBRARY split out of WORLD BUILDING into its own NOTES section — the
  world (Cast, World) is the stuff of the story; Library is the workings
  ABOUT it.
- STRUCK FROM THE NAV (not deleted as screens; hidden): Plot Threads,
  Subplots, Themes & Motifs (the old Plot group). The Treatment/wheel
  and the database carry their connections instead.
- Synopsis = Plot Mapping renamed for the new user (the loose-capture +
  timeline stage). Events & Timeline lives in it. See OPEN below for the
  unsettled "what fills the Synopsis screen" question.
- The unlabelled-spine idea (no heading on the top group) was discussed;
  the current agreed shape uses the three named sections above.

LAUNCHPAD ICONS — SETTLED (8 June 2026)
Clean single-weight gold line art, stroke="currentColor" (recolour with
Tone; no PNGs). Three decided and drawn:
- Load Project — drawer chest
- Start / New Project — typewriter
- Demos — signpost (single arm)
Stored with CODE/home-icons.svg family. (Plot Mapping / The Press
launchpad icons from the old 31 May launchpad are superseded by this
New / Load / Demo set for the entry actions.)

================================================================
SECURITY — A NOTE FROM 8 June (resolves a WP worry)
================================================================
Full system in security.md (seven layers, locked 24 May; paid-only,
API key in Vercel env vars only, server-side prompt tracking Steps 5–7).
NEW CLARIFICATION (8 June):
- Protecting the on-screen TEXT from copying is NOT achievable in a
  browser — the words are in the DOM/memory; one-scene-per-page
  construction slows a human with a mouse but not a script. Do NOT spend
  effort hardening the WP against text-lifting.
- More to the point, the book-farmer is usually the AUTHOR (their own
  text, their own account) and will pass the Press anyway — so a
  clean-export gate is a turnstile, not a wall.
- THE REAL FARMING MOAT is already locked: paid-only (no throwaway
  accounts) + assisted-not-generative (InkySwot won't WRITE the book, so
  no slop firehose) + per-account rate limits.
- PRESS-AS-CLEAN-EXPORT (the polished, lift-ready manuscript exists only
  after the Press, which sits at a payment point; free for subscribers)
  is GOOD COMMERCIAL DESIGN — bank it as a reason the export sits where
  it does, NOT as a security feature.

OTHER STANDING SECTIONS (unchanged — abbreviated here; see prior file /
specialist files for full text):
- IDENTITY & BRANDING, COLOURS, FONTS — as locked (Playfair 900 logo;
  Crimson Pro body; JetBrains Mono UI; dark palette #0f0d0a / ink
  #e8e0d0 / gold #c9923a–#e8b060; section colours Character #cba36a,
  Location #5fa898, Event #b08a6a, Chapter #9a8fb0).
- PRICING — paid only; £9.95/mo, £99.50/yr; 14-day money back; £1
  publication fee. (Full in locked-decisions.md.)
- TECHNICAL — v4.7 pre-Step 1 rebuild; Autumn 2026 target; repo
  PitchDarkPress/inkyswot-app; Vercel Hobby; API claude-haiku-4-5;
  key in Vercel env vars only.
- THE PRESS (two doors), ADA (Step 12), MANUSCRIPT FORMAT / GROUPS /
  GENRE lists, LANDING + LOGIN pages — as previously logged.

FILES IN REPO — inkyswot-app
index.html — the app workspace (Overview screen still titled "BASIS" —
rename to OVERVIEW).
login.html — login / sign up gate (stubbed).
CODE/ — the code locker (see CODE/README.md).
CODE/treatment-wheel.html — the WHEEL mockup, THE LIVE DESIGN SOURCE
(one scene per page; two-line labels; page-top fix; writing-mode single
page; multiple pop-ups; whole Carol loaded). STORED.
CODE/home-icons.svg — launchpad line icons (now also Load=drawer,
Start=typewriter, Demos=signpost).
CODE/map-plotter.html — old Plot Mapping corkboard (30 May). SUPERSEDED;
its note cards are the OLD clunky faces (type tab/knot/full-stop), not
the quiet note. Kept as history.

WHAT IS BUILT AND WORKING
Landing page; login page (stubbed); My Projects / Trash / New Project
modal / Overview / Characters / Relationships / Factions & Orgs /
Language & Dialogue / Locations / Buildings / Objects & Artefacts /
Rules & Lore / Plot Threads / Subplots / Themes & Motifs / Events &
Timeline / Chapters / The Treatment (placeholder shell) / AI Expand /
AI ON-OFF / Read Aloud (Chrome cancel() fix) / light-dark / voice
selector. The WHEEL lives in the standalone mockup, NOT yet in
index.html.

BUILD ORDER — CONFIRMED (unchanged)
Step 1 v4.0 App Shell Rebuild (NOT STARTED) · 2 Walk · 3 Sign-off Gate ·
4 Supabase · 5 Lifetime flag · 6 F12/Security · 7 Server prompt tracking
· 8 Stripe · 9 Resend · 10 Writing surface (WP + pop-ups + wheel) · 11
The Treatment (the wheel) · 12 Ada · 13 DCW (= the wheel; converging) ·
14 Export Suite · 15 The Press · 16 Admin · 17 PWA · 18 Beta · 19 Launch.
DEMO BOOKS (Carol then Willows) — after Step 1 sections are final, so
the database is filled once. Fully editable; reset-to-pristine + save-as-
your-own-copy. (Full in locked-decisions.md / future.md.)

CURRENT STATUS & NEXT ACTIONS
v4.7 pre-Step 1 rebuild. Autumn 2026 target.
... [history through 7 June as previously logged] ...
7 June (later): page-top bug fixed; writing-mode single page; multiple
  independent pop-ups; demo books decided; three .md files rewritten.
8 June (chat / design session, no shipped code):
  - NAV RESTRUCTURED (above) — three-section right menu; entry lands on
    Overview; New/Load/Demo atop MAIN MENU as the switch door; Factions
    & Organisations restored (full word); Library → its own NOTES
    section; Plot group struck.
  - LAUNCHPAD ICONS settled: drawer (Load), typewriter (Start), signpost
    (Demos).
  - SECURITY worry resolved (text protection isn't real in a browser;
    Press-as-export = commercial design; farming moat is paid-only +
    assisted-not-generative). MANUSCRIPT VIEW toggle agreed (writer
    comfort).
  - MAPS & GEOGRAPHY (a line-glyph "SimCity" stamp composer + era-styled
    buildings) — explored at length then DROPPED: a map-maker pulls away
    from "a writing platform / assisted not generative." NOT to be
    revisited. WORLD BUILDING gains NO Maps item.
  - POP-UP RESTYLE to the "C / ticket" note (dot + kicker + fading rule)
    — tried in the wheel mockup, then ABANDONED ("nope"). Pop-ups stay
    as the quiet-note grammar. The "C" note style is still LIKED for the
    future Synopsis board (see ROUGH below).
  - Big SYNOPSIS → WP design idea explored (see ROUGH — NOT SETTLED).

NEXT (do in order, one at a time — START A FRESH CHAT for this)
1. Rename the Overview screen title "BASIS" → "OVERVIEW" in index.html.
2. Build the NAV RESTRUCTURE (above) into index.html — preview first.
3. Build the home-page launchpad / entry with the three icons.
4. Begin Step 1 — v4.0 app shell rebuild.
(Settle the OPEN items below as they come; don't force them.)

OPEN DECISIONS — STILL TO SETTLE (one at a time)
1. WHAT FILLS THE SYNOPSIS SCREEN — the loose-capture-then-order stage
   (Plot Mapping reborn, running VERTICALLY to match the WP, using the
   quiet "C" note). The old 30-May corkboard is the wrong dress for it
   (old clunky cards; horizontal timeline; struck note-types). A clean
   rebuild, NOT a patch. See ROUGH below — the big idea may absorb this.
2. SYNOPSIS → WP TRANSITION — "convert when happy." Fork: a one-time
   POUR (notes become chapters/scenes, corkboard done) vs a LIVING LINK
   (one set of data, two views, change-one-changes-the-other). "Nothing
   entered twice" leans to the living link. Unsettled.
3. WHERE THE MOOD WORDS LIVE (Cold · Bleak · Biting). Parked.
4. EVENT ORDER WITHIN A SCENE (events lack a position).
5. EVENTS ON THE PAGE — multiple events per scene: list or collapse.
6. TAG SET opens — Prose vs Action; Dialogue's place; Emotion tag vs Map.
7. CARRIED FEATURES' HOME — tension curve, Emotional Maps, Ambient, the
   lift — in the wheel model.
8. THE 230px RIGHT SIDEBAR — its purpose.
9. WHEEL LIVE-LABEL FLIP POINT — small tweak.

================================================================
ROUGH — NOT SETTLED (8 June). Captured so it is not lost. Do NOT build
from this; it is half-formed exploratory thinking and needs its own
clean spec, on a fresh head, before it becomes a decision. Its proper
home is future.md (to be moved there when future.md is to hand).
================================================================
THE LAYERED / ONION-SKIN WRITING SURFACE + HOT-KEY TAGGING.
The shape Kev was reaching for (and partly found):
- You write the story as a LOOSE, REORDERABLE TIMELINE OF EVENTS — the
  spine is things that HAPPEN ("A man goes to work").
- As you write, the people/places/things you mention ("the man — Kev",
  "the work — the office") are caught and FILED to the right-side menu
  as entities you can reference later. The database fills ITSELF from the
  writing — the writer never faces blank forms first.
- Possible layered/overlay reading of it: loose mind-map → add a TIMELINE
  overlay (reorder into chronological order) → add a CHAPTERS overlay →
  add a SCENES overlay. Same notes throughout (onion skin). NB the
  conceptual knot: it is a FUNNEL not even layers — wide/loose at the top
  (all ideas), narrowing to events→chapters→scenes at the spine;
  characters/locations don't vanish, they become things events reach
  into (the pop-up).
- A known entity carries a quiet MARK in the prose so the writer knows
  there are details behind it (a faint section-colour tint and/or a
  small mark; must NOT rely on colour alone; must stay calm on the page
  for a dyslexic reader). Open: always-visible vs reveal-on-hover.
THE TAGGING MECHANISM (the bit that came forward clearest):
- Write freely. Hit a HOT KEY — it grabs the LAST WORD.
- BACK-ARROW extends the highlight word-by-word (forward-arrow to pull
  back if you overshoot) for multi-word names ("the Manor House").
  [LIVE-KEYBOARD MECHANISM — needs a selection mode + an Escape route;
  build static-first, do not spec by description alone.]
- A menu offers the TYPE (Character / Location / Event …); pick one →
  a list of existing records of that type (Kev / Sara / Claude …) +
  "New: …". Pick the record, or New to seed a fresh one filed to the
  side menu.
- A record is a THING, not a string: one CANONICAL name + ALIASES. The
  word you tagged ("the Manor") becomes an alias pointing at the record
  (Manor House). This unties cross-tagging (Manor House / the Manor /
  the House = one record).
- DIAL: the system must "err toward asking" (writer-triggered, accurate,
  never mis-files) over "guessing" (smooth but wrong). Auto-detecting
  aliases is dangerous — suggest, never decide.
- BRIEF: "intuitive and unobtrusive", and forgiving for a dyslexic
  writer — never make spelling/precision the price of being understood.
  Leans toward an Ada-assisted offer when AI is on; one-tap manual when
  off. Both.
OPEN inside this idea: how the layered surface meets the WHEEL (the WP
is already the wheel); whether Synopsis IS this surface at a looser
zoom; the prose-mark style; multi-word selection feel.

================================================================
SUPERSEDED / DROPPED — KEPT AS HISTORY (do NOT build from any of this)
================================================================
- MAPS & GEOGRAPHY / line-glyph "SimCity" stamp composer / world-map
  tile set / era-grouped building elevations — explored 8 June, DROPPED.
  A map/picture maker pulls against "a writing platform; assisted not
  generative." Not right here. Two generation prompts and tile lists
  were drafted in chat; not retained as build targets.
- POP-UP RESTYLE to the "C / ticket" note — tried 8 June in the wheel
  mockup, ABANDONED ("nope"). Pop-ups keep the quiet-note grammar.
- The 30-May Plot Mapping corkboard as a build target — its note CARDS
  (type tab / knot / full-stop / flip) are the OLD clunky faces,
  superseded by the quiet note. The corkboard is the wrong dress for the
  Synopsis stage; a clean rebuild is wanted, not a patch.
- Per-user NAV reordering — considered 8 June, dropped (returning user
  gets used to the order; not needed).
- [Earlier superseded items — the shutter, vertical board, fusion, card
  model, one-screen X-ray, horizontal strip, rollToCentre, single reused
  pop-up, the 4-June wheel detail, etc. — as listed in the 7 June file
  and in dcw.md history. Unchanged.]
RETAINED FROM HISTORY (still live): the QUIET NOTE grammar (the pop-up's,
and liked as "C" for the future Synopsis board); Dark Thoughts (private,
never exported); the SECTION ? help pill; carried features (tension
curve, Emotional Maps, Ambient, the lift) awaiting placement.