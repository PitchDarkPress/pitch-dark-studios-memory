File: inkyswot/current-state.md
Last updated: 14 June 2026 (session — NAV ORDER settled; SITE MAP reframed
as theatrical "where you are" and PARKED for its own page; left nav rebuilt;
right column widened; four-heading map kept as the calm sidebar version)

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
"n", "next", "y", or "done" = confirmed, proceed.
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
code before any work begins. THE CODE IS THE TRUTH.
Update the files at the end of a session. Rebuild clean — never patch
on patch. The .md is the single source of truth; the code is the truth
above it. When updating a file, rewrite the WHOLE file clean.
WHEN DESIGNING A LIVE MECHANISM (motion, scroll, interaction, drag,
keyboard behaviour): build a small STATIC mockup FIRST, agree the still
picture, THEN add the movement. Designing moving behaviour in words
wastes time (learned hard on the wheel). Ask for a screenshot/sketch.
WORK FROM THE IMAGE / THE CODE — NOT FROM A GUESS (hard lesson, 9 June).
When Kev gives a screenshot, that image IS the template — match it, do
not reinterpret it. When changing a built file, work from the pasted
code, never a reconstruction of it from memory or a screenshot. SMALL
CHANGES MEAN SMALL CHANGES — change only the one thing asked, touch
nothing else.
DISPLAY FREEZE: if edits stop showing, do a CLEAN REBUILD in a fresh
artifact rather than editing on.
LONG-THREAD DRIFT: a long, winding conversation degrades reliability —
start a fresh chat (with the .md files pasted) for a new build session
rather than carrying a tired thread on. (This 14 June session ran long
across several rebuilds/reverts — banked and broken here.)

================================================================
THE MODEL — INKYSWOT *IS* THE DCW (settled 4 June 2026)
================================================================
- InkySwot IS THE DCW — the whole instrument. Every section already
  built (Characters, Locations, Events, etc.) is part of it. The
  database IS the bones of the story.
- THE TREATMENT / THE DCW is the database switched on — assembled into a
  readable, writable whole. A plotline is a VIEW of data that already
  exists, not a new thing to author.

THREE VIEWS OF ONE BODY OF DATA — THE FUNNEL (settled 9 June 2026)
*** STILL UNDER REVIEW — the BOARD / wide view's fate was NOT settled
this session. Do not build from it until Kev settles its scope. ***
- THE BOARD (was "Plot Mapping reborn") — the WIDE view. The whole book
  as an instrument: scenes down the spine, the world across the tracks.
  Whether it survives is OPEN (see PLOT MAPPING / SYNOPSIS below).
- THE WP + THE WHEEL — the CLOSE view. The same data narrowed to the one
  scene being written. (Live, built.)
- THE SITE MAP — the WHOLE-STRUCTURE view (right sidebar; see below).
It is a FUNNEL: wide and loose at the top, narrowing to the single scene
at the spine. LIVING LINK, BOTH WAYS — change data in one view, it
changes in the others. NOTHING ENTERED TWICE.
First foundation question for bringing the views together: HOW THE
DATABASE IS REORGANISED so all views read from and write to the same
records.

================================================================
PLOT MAPPING = SYNOPSIS — ONE THING; "PLOT MAPPING" NAME DROPPED
(confirmed 14 June 2026; first dropped 11 June)
================================================================
KEV'S DECISION (clarified 14 June): "Plot Mapping" and "Synopsis" are the
SAME THING. The "Plot Mapping" NAME/FRAMING is dropped; SYNOPSIS is the
name that stays, and it lives under DCW. There is NOT a separate Plot
Mapping item to add anywhere.
- The settled nav lists SYNOPSIS under DCW (see NAV — SETTLED).
- THE BOARD (the wide six-track view once logged as "Plot Mapping
  reborn") — its scope is STILL OPEN; it was not built or settled this
  session. Treat THE BOARD / THREE-VIEWS FUNNEL as UNDER REVIEW.
- code-map-plotter.html (old corkboard) and code-board-look.html (the
  board look) remain as history pending the board scope call.

THE SPINE — A TIMELINE OF EVENTS
Three tiers: CHAPTER → SCENE → EVENT. Only EVENTS sit on the line and
become prose — only events HAPPEN. Characters, Locations, Objects, etc.
do not happen; they are REACHED INTO by the events that use them.

"FILL IN THE BLANKS"
The Treatment assembles the SUBSTANCE from the database and leaves the
writer the blanks: the prose only they can write. Assembled, the
sections ARE the draft; the writing is the last layer.

================================================================
THE SIX TRACK COLOURS — SETTLED (9 June 2026)
================================================================
One decision, used wherever the entity categories appear. All six pull
clearly apart; a dyslexic reader must tell them at a glance, so no two
muddy neighbours.
  EVENTS      gold        #c9923a
  LOCATIONS   teal        #5fa898
  CHARACTERS  terracotta  #cf7f57
  OBJECTS     steel blue  #7a9bd0
  THEMES      violet      #a07d9a
  TENSION     red         #c45b48
NB: this REVISES the older locked section colours (Character #cba36a,
Event #b08a6a). Characters is now terracotta; Events takes the gold.
Locations teal unchanged. Applied to the WP scene menu (live in the
wheel file). Chapter #9a8fb0.

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
leader centre mark; hover lights node only; eased motion (rate 0.072,
TIGHT=46, GAP=64); 0.35s smoothed hand-off.

THE PAGE LANDING — ONE SHARED READING LINE (page-top bug fixed 7 June).
Page and wheel share one reading line ~28px below the header
(READ_PAD=28). Clicking a label (or opening a scene) lands the scene's
TOP on the line (rollToTop). The wheel reads "where you are" from the
same line. SMALL OPEN TWEAK: live label flips ~halfway down a tall page;
biasing it later is an easy future tweak.

WRITING MODE shows ONLY the live scene; other pages hidden. "‹ overview"
returns to the Treatment.

================================================================
THE CHAPTER (STAVE) PAGE — A SYNOPSIS PAGE OF ITS OWN (built 11 June 2026)
================================================================
THE GAP FOUND: the synopsis only existed at SCENE level. The CHAPTER had
no synopsis of its own — leaving the chapter-level + Prompt nothing to
act on.

THE FIX: a CHAPTER gets its own full page, SAME FORMAT FAMILY as a scene
page, sitting BEFORE that stave's first scene. The spine reads: Stave One
page → its scenes → Stave Two page → its scenes, etc.

THE STAVE PAGE LAYOUT (agreed against Kev's image, 11 June):
- Full US-Letter sheet, page shadow — a scene page's twin.
- Running head top-right ("A Christmas Carol by Charles Dickens"), alone.
- The stave TITLE shown large (Crimson Pro ~30px, weight 600) — this IS
  the heading; NO duplicate mono stave line above it.
- A small mono line under the title, on the rule: "STAVE ONE · 5 SCENES".
- A centred mono section label on/under the rule: "CHAPTER SYNOPSIS".
- The SYNOPSIS BLOCK — identical grammar to a scene's .event block, then
  the italic invitation "— click to write this synopsis —".
- A hidden writing surface beneath; the chapter synopsis is editable.
STILL PICTURE only (standalone artifact). NOT YET folded into the wheel
file; the wheel will also need a label for the stave page (not yet done).

================================================================
THE WP AI PROMPT — PROMPT + EXPAND ON THE PAGE (settled 11 June 2026)
================================================================
The writer-facing Ada buttons (gold "+ Prompt" / "⟳ Expand").

WHAT IT DOES — AND ITS LIMIT (assisted-not-generative guard):
- SCOPED to expand the SYNOPSIS of the scene or chapter — NOT the prose.
  Expanding the synopsis thickens the PLAN; the blank the writer fills
  stays blank. Ada makes the brief richer, never finishes the work.
- Scales with the spine: a chapter + Prompt expands the CHAPTER synopsis;
  a scene + Prompt expands THAT scene's synopsis. (Why the chapter
  synopsis had to exist first.)
- HOW "stop AI writing the whole thing" is guaranteed: (a) scoped buttons
  — no "write everything" door; (b) hidden system prompt is OURS,
  forbidding prose, server-side (Steps 5–7); (c) output lands by CHOICE.

THE LOOK — PAGE FURNITURE, NOT DARK-UI CHROME (settled 11 June):
On the cream sheet, drawn in the PAGE'S OWN palette — page ink (#221a14),
page rule (#ded6c6), page-mute grey (#8a7d68). NO gold loudness at rest.
- CHOSEN TREATMENT ("A"): an OUTLINE PAIR. Thin page-rule border, page-ink
  text, transparent inside. EXPAND carries a faint grey WASH
  (rgba(138,125,104,.14)) as the weightier of the two; PROMPT stays open
  paper. HOVER: border + text wake to GOLD.
PLACEMENT (from Kev's image): TOP-RIGHT of the page, level with the large
title, tucked under the running head.
NOT YET folded into the wheel file.

================================================================
THE WP SCENE MENU — LEFT OF THE PAGE (built 9 June 2026)
================================================================
The home for the four reach-into tracks. In the dark channel LEFT of the
WP, MIRRORING the wheel on the right — the workspace reads as one
instrument, the same gold rail-and-ring furniture both sides.
- WHAT IT IS: "what this scene reaches into" — the Characters, Objects,
  Themes and Tension of the scene in front of you. Tied to the PAGE; it
  changes scene to scene.
- LOOK: right-aligned list. Coloured group headers (Characters terracotta,
  Objects steel blue, Themes violet, Tension red), names in plain ink
  beneath. Thin vertical gold RAIL, gold RING (17px) on the rail, short
  gold LEADER pointing INWARD.
- CLICKABLE: a name opens that entity's draggable POP-UP RECORD with copy
  buttons.
- TENSION — A METER (settled 9 June; NOT YET BUILT). A SEGMENTED BAR METER
  — segments GREEN → AMBER → RED, lighting to the scene's level, the
  PERCENTAGE beneath (e.g. 55%). Can run PAST 100 into red. A light-up
  SWEEP between scenes wanted (car-dial wake) — build static-first.
  (Currently shows a plain "55%" placeholder in the wheel file.)

================================================================
THE SITE MAP — REFRAMED AS THEATRICAL "WHERE YOU ARE"; PARKED
(14 June 2026)
================================================================
*** THE BIG TURN THIS SESSION. *** Kev revealed the Site Map he actually
wants is NOT the calm tree the 11-June redesign recorded. The intended
Site Map is OUTRAGEOUSLY THEATRICAL — a delight, not a menu.

THE INTENT (Kev's words, 14 June):
- It SHOWS WHERE THE WRITER IS — nothing more functional than that. It is
  set dressing / theatre, NOT a working navigation control (the wheel and
  the nav do the real navigating).
- BLOCKS OF COLOUR (the six track colours), connected by STRANGE LINES.
- It should MAKE THE USER SMILE.
- When the writer NAVIGATES (goes somewhere on the menu), the Site Map
  goes "BOOM (ish)" — a flourish that celebrates where you've landed. The
  drama is the REACTION to the click, not ambient self-motion.

WHAT WE TRIED (14 June) — and PARKED:
- A playful CONSTELLATION in the right sidebar: scattered colour blocks,
  wandering lines, a lit "You are here" block. Then iterated: straight
  lines, more delicate, more linear. It WAS NOT WORKING — the 290px
  sidebar is too cramped for something that wants to go BOOM. PUT ON HOLD.
- The BOOM itself (the motion) was never built — static-first rule held;
  we never got past the resting still.

THE PLAN WHEN IT COMES BACK (Kev's question, agreed in principle):
- The theatrical "where you are" map likely wants ITS OWN PAGE (room to
  breathe and bang), reached from the nav — NOT the narrow sidebar.
- The RIGHT SIDEBAR can KEEP the calm four-heading map (quiet,
  always-there, tells you where you are at a glance).
- Two stills to agree first (resting + exploded), THEN wire the BOOM.

THE CALM FOUR-HEADING SITE MAP — the SIDEBAR version (built, kept):
A calm SPINE of the FOUR HEADINGS, each heading's contents POPPING UP on
hover; the four headings the only fixed things. Spine on the RIGHT, ring
nodes, plain-text contents right-aligned in their own lane (no boxes, no
glow), two lanes (headings always visible), STATIC / hover-driven. The
four headings + contents match the SETTLED nav (see NAV — SETTLED). This
is what currently sits in the wheel file's right sidebar (clean, known
state). Earlier "+" deeper-level behaviour still OPEN.

================================================================
NAV — SETTLED (14 June 2026)
================================================================
*** ORDER NOW SETTLED. *** Kev gave the full list; this supersedes the
8-June "under rework" structure. Left nav (in the wheel mockup) was
rebuilt to this list, ALL OPEN (nothing collapsed). The four-heading Site
Map already draws the same list.

THE FULL LIST:
- PROJECTS
   - New Project
   - Load Project
   - Demo
      - A Christmas Carol
      - The Wind in the Willows
- DCW
   - Synopsis
   - Chapters
   - Scenes
   - Writing Panel
- WORLD BUILDING
   - Cast
      - Characters
      - Relationships
      - Language & Dialogue
      - Factions & Organisations
   - World
      - Locations
      - Buildings
      - Objects & Artefacts
      - Rules & Lore
- NOTES
   - Library
   - Research & Reference
   - Notes & Scratchpad

NOTES ON THE SETTLED NAV:
- SYNOPSIS under DCW IS the former "Plot Mapping" (same thing; name
  dropped). No separate Plot Mapping item.
- OVERVIEW and SANDBOX are NOT in this list. (The old nav carried them.)
  Whether OVERVIEW persists as the post-login LANDING screen even though
  it is not a nav heading is a CARRIED QUESTION — Kev to confirm.
- FACTIONS & ORGANISATIONS — written in FULL. Never "Orgs".
- STRUCK FROM THE NAV earlier (hidden, not deleted as screens): Plot
  Threads, Subplots, Themes & Motifs.
- The LEFT nav and the four-heading SITE MAP must stay in step.

ENTRY (settled 8 June, standing):
- LANDING PAGE (before login): Sign In / Sign Up. Its own screen.
- After sign in/up the writer lands on the OVERVIEW page (currently titled
  "BASIS" in index.html — RENAME to OVERVIEW; pending code job).

LAUNCHPAD ICONS — SETTLED (8 June 2026)
Clean single-weight gold line art, stroke="currentColor" (recolour with
Tone; no PNGs). Three drawn: Load Project — drawer chest; New Project —
typewriter; Demos — signpost. Stored with inkyswot/home-icons.svg.md.

================================================================
MANUSCRIPT VIEW — TOGGLE (writer comfort, agreed 8 June)
================================================================
A toggle in the WP to strip the chrome and read the book as a continuous
manuscript. Display-level only; TRUE flowing pagination remains a bigger
deferred build.

================================================================
SECURITY — A NOTE FROM 8 June (resolves a WP worry)
================================================================
Full system in security.md (seven layers, locked 24 May; paid-only; API
key in Vercel env vars only; server-side prompt tracking Steps 5–7).
- Protecting on-screen TEXT from copying is NOT achievable in a browser.
  Do NOT harden the WP against text-lifting.
- THE REAL FARMING MOAT: paid-only + assisted-not-generative (InkySwot
  won't WRITE the book) + per-account rate limits.
- The WP + Prompt expands the SYNOPSIS, never prose (prose-forbidding
  prompt server-side).
- PRESS-AS-CLEAN-EXPORT is good commercial design, NOT a security feature.

OTHER STANDING SECTIONS (unchanged — abbreviated; see specialist files):
- IDENTITY & BRANDING, COLOURS, FONTS — Playfair 900 logo; Crimson Pro
  body; JetBrains Mono UI; dark palette #0f0d0a / ink #e8e0d0 / gold
  #c9923a–#e8b060. TRACK COLOURS per THE SIX TRACK COLOURS; Chapter
  #9a8fb0.
- PRICING — paid only; £9.95/mo, £99.50/yr; 14-day money back; £1
  publication fee.
- TECHNICAL — v4.7 pre-Step 1 rebuild; Autumn 2026 target; repo
  PitchDarkPress/inkyswot-app; Vercel Hobby; API claude-haiku-4-5; key in
  Vercel env vars only.
- THE PRESS (two doors), ADA (Step 12), MANUSCRIPT FORMAT / GROUPS / GENRE
  lists, LANDING + LOGIN pages — as previously logged.

================================================================
THE MEMORY DATABASE — HOUSEKEEPING (9 June 2026)
================================================================
Pitch Dark Studios Memory (pitchdarkpress.github.io/pitch-dark-studios-
memory) holds files per DIVISION. Code files carry a "code-" prefix, e.g.
  inkyswot/code-readme.md            (index of the code files)
  inkyswot/code-treatment-wheel.html.md   (the WHEEL — live design source)
  inkyswot/code-board-look.html.md   (the board STILL PICTURE)
  inkyswot/code-site-map.html.md     (the SITE MAP)
  inkyswot/code-map-plotter.html.md  (old corkboard — SUPERSEDED history)
  inkyswot/home-icons.svg.md         (launchpad line icons)
STILL TO TEST: whether the InkySwot division can hold a .png / .jpg image.

FILES — InkySwot division of the memory database
current-state.md · locked-decisions.md · dcw.md (the three core .md).
inkyswot/code-treatment-wheel.html.md — THE LIVE DESIGN SOURCE. NOW also
carries: the SETTLED LEFT NAV (rebuilt this session, all open), the RIGHT
COLUMN widened to 290px, and the calm FOUR-HEADING SITE MAP sitting in the
right sidebar. STILL NOT folded in: the chapter STAVE PAGE; the WP
Prompt/Expand buttons; the wheel's stave-page label; the Tension meter
(still a "55%" placeholder).
inkyswot/code-site-map.html.md — the SITE MAP. The standalone four-heading
spine. NB the THEATRICAL "where you are" Site Map (blocks of colour, BOOM)
is the new intent and is PARKED (likely its own page) — not in any file.
inkyswot/code-board-look.html.md — the BOARD still picture. UNDER REVIEW.
inkyswot/home-icons.svg.md — launchpad icons.
inkyswot/code-map-plotter.html.md — old Plot Mapping corkboard. SUPERSEDED.
index.html — the app workspace (Overview screen still titled "BASIS").
login.html — login / sign up gate (stubbed).

WHAT IS BUILT AND WORKING
Landing page; login page (stubbed); My Projects / Trash / New Project
modal / Overview / Characters / Relationships / Factions & Orgs /
Language & Dialogue / Locations / Buildings / Objects & Artefacts /
Rules & Lore / Plot Threads / Subplots / Themes & Motifs / Events &
Timeline / Chapters / The Treatment (placeholder shell) / AI Expand /
AI ON-OFF / Read Aloud / light-dark / voice selector. The WHEEL + WP +
LEFT SCENE MENU + SETTLED LEFT NAV + calm FOUR-HEADING SITE MAP live
together in the standalone mockup (code-treatment-wheel.html), NOT yet in
index.html. The BOARD is a standalone still picture, UNDER REVIEW.

BUILD ORDER — CONFIRMED (unchanged)
Step 1 v4.0 App Shell Rebuild (NOT STARTED) · 2 Walk · 3 Sign-off Gate ·
4 Supabase · 5 Lifetime flag · 6 F12/Security · 7 Server prompt tracking
· 8 Stripe · 9 Resend · 10 Writing surface (WP + pop-ups + wheel + scene
menu) · 11 The Treatment (the wheel) · 12 Ada · 13 DCW (= the wheel) ·
14 Export Suite · 15 The Press · 16 Admin · 17 PWA · 18 Beta · 19 Launch.
DEMO BOOKS (Carol then Willows) — after Step 1 sections are final.

CURRENT STATUS & NEXT ACTIONS
v4.7 pre-Step 1 rebuild. Autumn 2026 target.
... [history through 11 June as previously logged] ...
14 June (chat / design session): NAV ORDER SETTLED (the full four-section
  list). LEFT NAV in the wheel file rebuilt to it, all open. RIGHT COLUMN
  widened 230 → 290px. Plot Mapping = Synopsis confirmed (one thing; name
  dropped). The four-heading SITE MAP folded into the wheel file's right
  sidebar as the calm version. SITE MAP REFRAMED as theatrical "where you
  are" (blocks of colour, strange lines, BOOM on navigate) — constellation
  tried in the sidebar, didn't work (too cramped), PARKED; likely its own
  page when it returns. Several rebuilds/reverts; ended on a clean known
  state. current-state.md rewritten clean (this file).

NEXT (do in order, one at a time — START A FRESH CHAT for a build)
1. FOLD THE STAVE PAGE + WP PROMPT/EXPAND into code-treatment-wheel.html
   (work from Kev's pasted file). Then the wheel's stave-page label.
2. Build the TENSION SEGMENTED BAR METER + sweep (static-first) to replace
   the "55%" placeholder in the scene menu.
3. THE THEATRICAL SITE MAP (when off hold): agree resting + exploded
   stills, then wire the BOOM — likely as its OWN PAGE, sidebar keeping the
   calm four-heading map.
4. (Held by the scope call) THE BOARD / THREE VIEWS — revisit once Kev
   settles whether the wide view survives.
5. UPDATE locked-decisions.md and dcw.md to match this session (nav
   settled; Plot Mapping = Synopsis; Site Map reframed) — one file at a
   time.
6. Test whether the InkySwot division can hold a .png image.
7. (Carried app jobs) Rename Overview "BASIS" → "OVERVIEW"; build the nav
   into index.html (to the SETTLED order); build the home launchpad; begin
   Step 1 — v4.0 app shell rebuild.

OPEN DECISIONS — STILL TO SETTLE (one at a time)
1. THE BOARD / WIDE VIEW scope — does it survive, and under what name?
2. OVERVIEW & SANDBOX — do they return anywhere? (Not in the settled nav.
   Does Overview persist as the post-login landing screen?)
3. THE THEATRICAL SITE MAP — its own page vs sidebar; what the BOOM is.
4. THE FOUR-HEADING MAP DEEPER LEVEL — how Demo's books and Cast/World's
   "+" contents open.
5. THE DATABASE REORGANISATION for the living link.
6. SYNOPSIS → WP TRANSITION — mechanics still to build.
7. WHERE THE MOOD WORDS LIVE (Cold · Bleak · Biting). Parked.
8. EVENT ORDER WITHIN A SCENE (events lack a position).
9. EVENTS ON THE PAGE — multiple events per scene: list or collapse.
10. TAG SET — Prose vs Action; Dialogue's place; Emotion tag vs Map.
11. CARRIED FEATURES' HOME — Emotional Maps, Ambient, the lift.
12. WHEEL LIVE-LABEL FLIP POINT — small tweak.
13. THE STAVE PAGE'S WHEEL LABEL — settle when folding the stave page in.

================================================================
ROUGH — NOT SETTLED. Captured so it is not lost. Do NOT build from this.
Proper home: future.md.
================================================================
THE LAYERED / ONION-SKIN WRITING SURFACE + HOT-KEY TAGGING.
- Write the story as a LOOSE, REORDERABLE TIMELINE OF EVENTS.
- As you write, people/places/things are caught and FILED to the side
  menu as entities. The database fills ITSELF.
- A known entity carries a quiet MARK in the prose (NOT colour alone; calm
  for a dyslexic reader).
THE TAGGING MECHANISM:
- Write freely. Hit a HOT KEY — grabs the LAST WORD. BACK-ARROW extends
  word-by-word for multi-word names. [build static-first.]
- A menu offers the TYPE; pick one → existing records + "New: …".
- A record is a THING, not a string: one CANONICAL name + ALIASES.
- DIAL: "err toward asking" over "guessing". Suggest, never decide.
- Forgiving for a dyslexic writer — never make spelling the price.

================================================================
SUPERSEDED / DROPPED — KEPT AS HISTORY (do NOT build from any of this)
================================================================
- THE CALM FOUR-HEADING SITE MAP AS THE INTENDED MAP — superseded 14 June
  as the *whole* intent: it is now only the calm SIDEBAR version. The
  intended Site Map is THEATRICAL ("where you are", blocks of colour,
  BOOM). The four-heading map is kept, not killed.
- THE 14-JUNE SIDEBAR CONSTELLATION TRIES — scattered blocks + wandering
  curved lines; then straight lines; then more delicate; then more linear.
  All PARKED — the 290px sidebar is too cramped for the BOOM; the
  theatrical map wants its own page.
- "PLOT MAPPING" as a name/item — dropped; it IS Synopsis.
- THE FIRST SITE MAP (11 June) — full branching TREE with self-running
  walk + blooms. Superseded by the four-heading spine.
- THE "ROAD MAP" NAME — renamed to SITE MAP, 11 June.
- THE OLD GOLD CHARACTERS / BROWN EVENTS section colours — revised 9 June
  to the six-colour set.
- TENSION as a VU NEEDLE / FLAT LINE-WITH-POINTER / plain "55%" text — all
  tried 9 June; superseded by the segmented bar meter.
- MERGING the left scene menu INTO the wheel — rejected 9 June.
- SITE MAP BUTTON TREATMENTS B / C / D (WP Prompt/Expand) — "A" chosen.
- MAPS & GEOGRAPHY / "SimCity" stamp composer / tile sets — DROPPED 8 June.
- POP-UP RESTYLE to the "C / ticket" note — abandoned 8 June.
- Per-user NAV reordering — dropped 8 June.
- [Earlier superseded items — the shutter, the old vertical board, the
  fusion, the card model, the one-screen X-ray, the horizontal strip,
  rollToCentre, the single reused pop-up, etc. — as in dcw.md /
  locked-decisions.md history. Unchanged.]
RETAINED FROM HISTORY (still live): the QUIET NOTE grammar; Dark Thoughts
(private, never exported); the SECTION ? help pill; the SIX TRACK COLOURS;
carried features (Emotional Maps, Ambient, the lift) awaiting placement.