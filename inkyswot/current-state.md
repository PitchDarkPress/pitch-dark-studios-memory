File: inkyswot/current-state.md
Last updated: 9 June 2026

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
nothing else. (9 June drifted badly by rebuilding from guesses; the fix
was to go back to Kev's file and his image.)
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

THREE VIEWS OF ONE BODY OF DATA — THE FUNNEL (settled 9 June 2026)
The big realisation of 9 June: there are THREE views of the same single
body of data, and the writer moves freely between them.
- THE BOARD (Plot Mapping reborn) — the WIDE view. The whole book as an
  instrument: scenes down the spine, the world across the tracks.
- THE WP + THE WHEEL — the CLOSE view. The same data narrowed to the one
  scene being written.
- THE ROAD MAP — the JOURNEY view (right sidebar; see below).
It is a FUNNEL: wide and loose at the top (the board), narrowing to the
single scene at the spine (the WP). LIVING LINK, BOTH WAYS — change data
in one view, it changes in the others. NOTHING ENTERED TWICE.
The three stages (board / WP+wheel / road map) are to be BROUGHT
TOGETHER as the next build (see NEXT). First foundation question Kev
flagged for that build: HOW THE DATABASE IS REORGANISED so all three
views read from and write to the same records.

THE SPINE — A TIMELINE OF EVENTS
Three tiers: CHAPTER → SCENE → EVENT. Only EVENTS sit on the line and
become prose — only events HAPPEN. Characters, Locations, Objects, etc.
do not happen; they are REACHED INTO by the events that use them.

"FILL IN THE BLANKS"
The Treatment assembles the SUBSTANCE from the database and leaves the
writer the blanks: the prose only they can write. Assembled, the
sections ARE the draft; the writing is the last layer.

================================================================
THE BOARD — PLOT MAPPING REBORN (settled 9 June 2026)
================================================================
The old DCW vertical board (killed 4 June for the "what is a row" knot)
came BACK on 9 June — the look that "made Kev laugh", now wearing the
current visual language (dark, gold, Crimson Pro / JetBrains Mono, the
quiet-note grammar). The lesson learned: the board was never the
mistake — killing the beauty to solve a logic problem was. The board can
hold the timeline-of-events truth AND be beautiful.

THE BOARD IS PLOT MAPPING. Not a separate tool beside Plot Mapping — it
IS Plot Mapping, reborn. The old CODE/map-plotter.html corkboard is
properly superseded by it.

THE BOARD SHAPE: scenes down a sticky left SPINE (Stave / Scene); SIX
TRACKS across the top, in this order, left to right:
  EVENTS · LOCATIONS · CHARACTERS · OBJECTS · THEMES · TENSION
Each cell holds the quiet notes in the track's colour. Tension is a
drawn CURVE down its column (see the meter note below for the WP form).

THE CUT — WHAT TRANSFERS TO THE WP (settled 9 June):
- EVENTS + LOCATIONS form the SYNOPSIS content of every chapter and
  scene — the "what happens and where" that becomes the prose-bound
  substance on the WP page.
- CHARACTERS · OBJECTS · THEMES · TENSION are related to the scene but
  do NOT pour into prose. They are REACHED INTO. Their home is the
  SCENE MENU on the left of the WP (see below).
This maps onto the locked principle: only events HAPPEN and become
prose; everything else is reached into.

CURRENT BOARD ARTIFACT: a STILL PICTURE only (a "look", not a working
tool — not wired, no drag, no real data). Stored as
inkyswot/code-board-look.html.md. It still carries the OLD colours —
the new six (below) are NOT yet applied to it. Applying the six colours
to the board is the agreed follow-on job.

================================================================
THE SIX TRACK COLOURS — SETTLED (9 June 2026)
================================================================
One decision, used in BOTH places (the board AND the WP scene menu).
All six pull clearly apart; a dyslexic reader must tell them at a
glance, so no two muddy neighbours.
  EVENTS      gold        #c9923a
  LOCATIONS   teal        #5fa898
  CHARACTERS  terracotta  #cf7f57   (moved OFF gold so it clears Events)
  OBJECTS     steel blue  #7a9bd0   (the cool colour the warm palette
                                     was missing — breaks the brown/gold
                                     cluster)
  THEMES      violet      #a07d9a
  TENSION     red         #c45b48   (deepened/warmed so it sits with the
                                     palette, not buzzing; clears the
                                     Characters gold)
NB: this REVISES the older locked section colours (Character #cba36a,
Event #b08a6a). Characters is now terracotta, not gold; Events takes the
gold. Locations teal unchanged. Applied to the WP scene menu (live in
the wheel file); STILL TO APPLY to the board.

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

================================================================
THE WP SCENE MENU — LEFT OF THE PAGE (built 9 June 2026)
================================================================
The home found for the four reach-into tracks. Sits in the dark channel
to the LEFT of the WP, MIRRORING the wheel on the right — the workspace
now reads as one instrument, the same gold rail-and-ring furniture on
both sides.
- WHAT IT IS: "what this scene reaches into" — the Characters, Objects,
  Themes and Tension belonging to the scene currently in front of you.
  Tied to the PAGE, not the book; it changes as you move scene to scene.
  (The wheel is about the BOOK / where you are; the scene menu is about
  THIS SCENE. Different jobs, opposite sides. They are NOT merged — that
  was considered 9 June and rejected.)
- LOOK: a right-aligned list. Coloured group headers (Characters
  terracotta, Objects steel blue, Themes violet, Tension red) with the
  names in plain ink beneath. Matching FURNITURE to the wheel: a thin
  vertical gold RAIL, a gold RING (17px, 2px, centred dot) sitting on
  the rail, and a short gold LEADER coming off the ring pointing INWARD
  toward the list (the mirror of the wheel's leader, which points out to
  its labels). Equal breathing room from the page on both sides.
- CLICKABLE: clicking a name opens that entity's POP-UP RECORD — the
  same draggable pop-up the nav opens, with its copy buttons. (Wired for
  the real Character records; the placeholder Objects/Themes items wire
  the same way once those tracks have real records.)
- TENSION — A METER (settled 9 June). Tension is not a record; it is a
  READING for this scene. Shown as a SEGMENTED BAR METER — a row of
  segments, GREEN → AMBER → RED, lighting up to the scene's level, with
  the PERCENTAGE beneath (e.g. 55%). A straight percentage that can run
  PAST 100 into the red (a scene running hot). "For the theatre of it" —
  the DAW heritage made real. A light-up SWEEP between scenes is wanted
  (car-dial wake: drop to zero, run up to the level, settle) — to be
  built static-first. (SUPERSEDES the tries it replaced: a VU needle
  gauge, a flat line-with-pointer, and a plain "55%" text — all tried
  and dropped 9 June before the segmented bar landed.)

================================================================
THE ROAD MAP — THE RIGHT SIDEBAR'S PURPOSE (idea, 9 June 2026)
================================================================
The 230px right sidebar (long blank) finds its purpose: a USER ROAD MAP.
This answers the open "what is the right sidebar for" question.
- WHAT: the stages of the journey laid out down the sidebar, with a LIT
  DOT/RING showing WHERE YOU ARE. Mirrors the wheel/scene-menu rail
  furniture (gold rail, lit ring) — so all THREE verticals (scene menu
  left, wheel centre-right, road map far right) share the look.
- REACTIVE THEATRE: actions elsewhere make the map RESPOND — e.g. open
  the Characters box and add/modify a record, and a little (section-
  colour) box opens on the road map off the relevant node. The platform
  acknowledges the work; a living instrument, not a static menu.
- CLICKABLE: stages on the road map can be clicked to jump there — so it
  is also navigation. (NB to think about: how the road map's navigation
  sits beside the left NAV without doubling up / confusing the writer.)
STILL TO SETTLE (next build): (a) WHAT STAGES live on the road map — the
platform journey, the story spine (Overview → Synopsis → Chapters →
Scenes → Treatment), or the project's own progress; (b) the clickable
behaviour and how it relates to the nav; (c) the exact reactive-box
behaviour. Build static-first as always.

================================================================
MANUSCRIPT VIEW — TOGGLE (writer comfort, agreed 8 June)
================================================================
A toggle in the WP to strip the chrome (running heads, stave headings)
and read the book as a continuous manuscript. NB: this is a WRITER
COMFORT, not a security feature — it deliberately makes the text easier
to read whole. Display-level only (hide chrome / butt the sheets up);
TRUE flowing pagination (prose breaking across numbered pages) remains
the bigger deferred build.

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
  timeline stage). Events & Timeline lives in it. NB (9 June): the
  reborn BOARD is the dress for this Synopsis / Plot Mapping stage.
- The unlabelled-spine idea (no heading on the top group) was discussed;
  the current agreed shape uses the three named sections above.

LAUNCHPAD ICONS — SETTLED (8 June 2026)
Clean single-weight gold line art, stroke="currentColor" (recolour with
Tone; no PNGs). Three decided and drawn:
- Load Project — drawer chest
- Start / New Project — typewriter
- Demos — signpost (single arm)
Stored with inkyswot/home-icons.svg.md. (Plot Mapping / The Press
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
- IDENTITY & BRANDING, COLOURS, FONTS — Playfair 900 logo; Crimson Pro
  body; JetBrains Mono UI; dark palette #0f0d0a / ink #e8e0d0 / gold
  #c9923a–#e8b060. SECTION/TRACK COLOURS now per THE SIX TRACK COLOURS
  (above, 9 June) — Events gold, Locations teal, Characters terracotta,
  Objects steel blue, Themes violet, Tension red; Chapter #9a8fb0.
- PRICING — paid only; £9.95/mo, £99.50/yr; 14-day money back; £1
  publication fee. (Full in locked-decisions.md.)
- TECHNICAL — v4.7 pre-Step 1 rebuild; Autumn 2026 target; repo
  PitchDarkPress/inkyswot-app; Vercel Hobby; API claude-haiku-4-5;
  key in Vercel env vars only.
- THE PRESS (two doors), ADA (Step 12), MANUSCRIPT FORMAT / GROUPS /
  GENRE lists, LANDING + LOGIN pages — as previously logged.

================================================================
THE MEMORY DATABASE — HOUSEKEEPING (9 June 2026)
================================================================
The Pitch Dark Studios Memory system
(pitchdarkpress.github.io/pitch-dark-studios-memory) holds files per
DIVISION (Core, The Room, Proauthorist, Pitch Dark Press, InkySwot,
Publishing, Broadcasting, Art, Studios, R&D, Test) and already handles
GLB assets.
DONE 9 June: InkySwot's CODE LOCKER files were pulled INTO the InkySwot
division so everything InkySwot — notes AND code — sits together. The
old separate CODE/ locker copies were deleted. No app surgery was
needed — files were simply created in the division and the old ones
removed. Naming convention: code files carry a "code-" prefix so they
cluster in the file list, e.g.
  inkyswot/code-readme.md            (index of the code files)
  inkyswot/code-treatment-wheel.html.md   (the WHEEL — live design source)
  inkyswot/code-board-look.html.md   (the board STILL PICTURE / a look)
  inkyswot/code-map-plotter.html.md  (old corkboard — SUPERSEDED history)
  inkyswot/home-icons.svg.md         (launchpad line icons)
STILL TO TEST (next): whether the InkySwot division can hold a .png /
.jpg image (the system's asset handling is geared to GLB). Try adding a
single image and see if it sticks before relying on it.

FILES — InkySwot division of the memory database
current-state.md · locked-decisions.md · dcw.md (the three core .md).
inkyswot/code-treatment-wheel.html.md — the WHEEL + WP mockup, THE LIVE
DESIGN SOURCE (one scene per page; two-line labels; page-top fix;
writing-mode single page; multiple pop-ups; whole Carol loaded; the LEFT
SCENE MENU now added — four colour-coded reach-into tracks, mirrored
rail/ring/leader furniture, clickable names, Tension meter as %). STORED
9 June.
inkyswot/code-board-look.html.md — the BOARD still picture (a look, old
colours, not wired). STORED 9 June.
inkyswot/code-home-icons.svg.md / home-icons.svg.md — launchpad line
icons (Load=drawer, Start=typewriter, Demos=signpost).
inkyswot/code-map-plotter.html.md — old Plot Mapping corkboard (30 May).
SUPERSEDED by the reborn board; kept as history.
index.html — the app workspace (Overview screen still titled "BASIS" —
rename to OVERVIEW). login.html — login / sign up gate (stubbed).

WHAT IS BUILT AND WORKING
Landing page; login page (stubbed); My Projects / Trash / New Project
modal / Overview / Characters / Relationships / Factions & Orgs /
Language & Dialogue / Locations / Buildings / Objects & Artefacts /
Rules & Lore / Plot Threads / Subplots / Themes & Motifs / Events &
Timeline / Chapters / The Treatment (placeholder shell) / AI Expand /
AI ON-OFF / Read Aloud (Chrome cancel() fix) / light-dark / voice
selector. The WHEEL + WP + LEFT SCENE MENU live in the standalone mockup
(code-treatment-wheel.html), NOT yet in index.html. The BOARD is a
standalone still picture (code-board-look.html), NOT wired.

BUILD ORDER — CONFIRMED (unchanged)
Step 1 v4.0 App Shell Rebuild (NOT STARTED) · 2 Walk · 3 Sign-off Gate ·
4 Supabase · 5 Lifetime flag · 6 F12/Security · 7 Server prompt tracking
· 8 Stripe · 9 Resend · 10 Writing surface (WP + pop-ups + wheel + scene
menu) · 11 The Treatment (the wheel) · 12 Ada · 13 DCW (= the wheel;
converging) · 14 Export Suite · 15 The Press · 16 Admin · 17 PWA · 18
Beta · 19 Launch.
DEMO BOOKS (Carol then Willows) — after Step 1 sections are final, so
the database is filled once. Fully editable; reset-to-pristine + save-as-
your-own-copy. (Full in locked-decisions.md / future.md.)

CURRENT STATUS & NEXT ACTIONS
v4.7 pre-Step 1 rebuild. Autumn 2026 target.
... [history through 7 June as previously logged] ...
8 June (chat / design session, no shipped code): NAV restructured;
  launchpad icons settled; security worry resolved; Manuscript View
  toggle agreed; Maps & Geography explored then DROPPED; pop-up "C/
  ticket" restyle abandoned; big Synopsis→WP idea explored (now largely
  ANSWERED by 9 June's board/funnel work).
9 June (big design session — board reborn + WP scene menu built):
  - THE BOARD came back as PLOT MAPPING REBORN (six tracks: Events ·
    Locations · Characters · Objects · Themes · Tension). The look that
    made Kev laugh, in the current visual language. Still a "look" only.
  - THE FUNNEL settled: three views of one body of data (board / WP+
    wheel / road map), living link both ways, nothing entered twice.
  - THE CUT: Events + Locations = the scene SYNOPSIS (prose-bound on the
    WP); Characters/Objects/Themes/Tension = reached-into (the WP scene
    menu).
  - THE WP SCENE MENU built into code-treatment-wheel.html — left of the
    page, mirroring the wheel (rail/ring/leader), colour-coded, names
    clickable to open pop-up records, Tension shown as a percentage
    (segmented bar METER agreed as the form, sweep to follow).
  - THE SIX TRACK COLOURS settled (Events gold, Locations teal,
    Characters terracotta, Objects steel blue, Themes violet, Tension
    red) — applied to the WP scene menu; STILL TO APPLY to the board.
  - THE ROAD MAP idea for the right sidebar (lit dot, reactive boxes,
    clickable; stages TBD).
  - MEMORY DATABASE housekeeping: InkySwot code files moved into the
    InkySwot division (code- prefix); old CODE/ locker deleted.
  - These three .md files rewritten clean at session end.

NEXT (do in order, one at a time — START A FRESH CHAT for the build)
1. BRING THE THREE STAGES TOGETHER (board / WP+wheel / road map). FIRST
   QUESTION KEV WANTS ASKED: how do we reorganise the DATABASE so all
   three views read/write the same records (the living link)?
2. Apply THE SIX TRACK COLOURS to the board (code-board-look.html).
3. Build the Tension SEGMENTED BAR METER + sweep (static-first).
4. Settle the ROAD MAP: stages on it; clickable behaviour vs the nav;
   reactive-box theatre.
5. Test whether the InkySwot division can hold a .png image.
6. (Carried app jobs) Rename Overview "BASIS" → "OVERVIEW" in index.html;
   build the NAV RESTRUCTURE into index.html; build the home launchpad;
   begin Step 1 — v4.0 app shell rebuild.
(Settle the OPEN items below as they come; don't force them.)

OPEN DECISIONS — STILL TO SETTLE (one at a time)
1. THE DATABASE REORGANISATION for the living link (the next build's
   foundation question — Kev's first question for the join-up).
2. ROAD MAP — what stages; clickable vs nav; reactive-box behaviour.
3. SYNOPSIS → WP TRANSITION — answered in principle as a LIVING LINK
   (one set of data, two views, change-one-changes-the-other); the
   one-time POUR alternative is dropped. Mechanics still to build.
4. WHERE THE MOOD WORDS LIVE (Cold · Bleak · Biting). Parked.
5. EVENT ORDER WITHIN A SCENE (events lack a position).
6. EVENTS ON THE PAGE — multiple events per scene: list or collapse.
7. TAG SET opens — Prose vs Action; Dialogue's place; Emotion tag vs Map.
8. CARRIED FEATURES' HOME — Emotional Maps, Ambient, the lift — in the
   wheel/board model. (Tension now HAS a home: the board curve + the WP
   meter.)
9. WHEEL LIVE-LABEL FLIP POINT — small tweak.

================================================================
ROUGH — NOT SETTLED. Captured so it is not lost. Do NOT build from this;
it is half-formed exploratory thinking and needs its own clean spec, on
a fresh head, before it becomes a decision. Proper home: future.md.
================================================================
THE LAYERED / ONION-SKIN WRITING SURFACE + HOT-KEY TAGGING.
(Much of this is now ANSWERED by the 9 June board/funnel work — the
funnel, the wide-to-narrow zoom, the database filling from the spine —
but the TAGGING mechanism below is still rough and unbuilt.)
- You write the story as a LOOSE, REORDERABLE TIMELINE OF EVENTS — the
  spine is things that HAPPEN ("A man goes to work").
- As you write, the people/places/things you mention are caught and
  FILED to the side menu as entities. The database fills ITSELF from the
  writing — the writer never faces blank forms first.
- A known entity carries a quiet MARK in the prose (a faint section-
  colour tint and/or a small mark; must NOT rely on colour alone; must
  stay calm for a dyslexic reader). Open: always-visible vs on-hover.
THE TAGGING MECHANISM (clearest part):
- Write freely. Hit a HOT KEY — it grabs the LAST WORD. BACK-ARROW
  extends word-by-word (forward-arrow to pull back) for multi-word names.
  [LIVE-KEYBOARD MECHANISM — needs a selection mode + Escape route;
  build static-first, do not spec by description alone.]
- A menu offers the TYPE (Character / Location / Event …); pick one →
  a list of existing records + "New: …". Pick the record, or seed a new
  one filed to the side menu.
- A record is a THING, not a string: one CANONICAL name + ALIASES. The
  word you tagged ("the Manor") becomes an alias pointing at the record
  (Manor House).
- DIAL: "err toward asking" (writer-triggered, accurate) over "guessing"
  (smooth but wrong). Suggest, never decide.
- Forgiving for a dyslexic writer — never make spelling the price of
  being understood. Ada-assisted when AI is on; one-tap manual when off.

================================================================
SUPERSEDED / DROPPED — KEPT AS HISTORY (do NOT build from any of this)
================================================================
- THE OLD GOLD CHARACTERS / BROWN EVENTS section colours — revised
  9 June to the six-colour set (Characters terracotta, Events gold).
- TENSION as a VU NEEDLE gauge, and as a FLAT LINE-WITH-POINTER, and as
  a plain "55%" text — all tried 9 June; SUPERSEDED by the segmented bar
  meter (green→amber→red + %).
- MERGING the left scene menu INTO the wheel — considered 9 June,
  rejected (wheel = the book; scene menu = this scene; different jobs).
- MAPS & GEOGRAPHY / "SimCity" stamp composer / tile sets — explored
  8 June, DROPPED (pulls against "a writing platform; assisted not
  generative"). Not to be revisited.
- POP-UP RESTYLE to the "C / ticket" note — abandoned 8 June. Pop-ups
  keep the quiet-note grammar.
- The 30-May Plot Mapping corkboard as a build target — superseded by
  the reborn board (code-board-look). Kept as history (code-map-plotter).
- Per-user NAV reordering — dropped 8 June.
- [Earlier superseded items — the shutter, the old vertical board, the
  fusion, the card model, the one-screen X-ray, the horizontal strip,
  rollToCentre, the single reused pop-up, the 4-June wheel detail, etc.
  — as listed in dcw.md / locked-decisions.md history. Unchanged.]
NB: the reborn board is NOT the old vertical board returning unchanged —
it is the timeline-of-events truth (six tracks, Events feed prose) shown
as a board, in the current visual language.
RETAINED FROM HISTORY (still live): the QUIET NOTE grammar; Dark
Thoughts (private, never exported); the SECTION ? help pill; carried
features (Emotional Maps, Ambient, the lift) awaiting placement.