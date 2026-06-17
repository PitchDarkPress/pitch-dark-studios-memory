File: inkyswot/current-state.md
Last updated: 17 June 2026 (chat / BUILD session — THE QUICK-NOTE (pinned
post-it) BUILT as a standalone component and signed off: amber scrap, a
two-state thumbtack pin (gold OUTLINE when loose → the SAME shape filled
with colour when pinned), a colour popup using the six track colours,
pin-drag moves the note, pinned scraps anchor to the scene and scroll with
it; saved to the DB as inkyswot-code-quick-note.html.md. STILL TO DO: make
notes PERSIST + a "SEE ALL" button + the across-all-screens wiring. Images
DROPPED from notes — they live in Research. Admin-panel gotcha found and
fixed: a file saved at the repo ROOT saves fine but does NOT show in the
menu — give it the division folder.)

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
KEEP IT SIMPLE — when Kev says he doesn't understand, STOP, drop the
jargon and the long lists, and say it in plain words, one thing at a
time. Do not dump a big banked list on him; hold it yourself.
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

================================================================
*** THE BIG TURN — THE DCW IS ONE BODY OF DATA / A MIXDOWN ***
(settled 16 June 2026 — supersedes "three views" framing)
================================================================
KEV'S INSIGHT, stated plainly: "It is just one thing." The DCW is NOT
three separate screens you move between. It is ONE body of material seen
through OVERLAYS — and it behaves like a MIXDOWN in music.

THE FUNNEL, END TO END (both ends now seen on real screens):
- SANDBOX — the raw, no-order end. Brainstorming. You drop ideas in
  (places, characters, events, objects) and toss them about until they
  coalesce into a semblance of a story. WIDE end of the funnel.
- SYNOPSIS — the SAME material with an overlay that fixes it into an
  ORDERED timeline; then a SECOND overlay drops CHAPTERS and SCENES onto
  it.
- THE MANUSCRIPT (renamed from "Writing Panel", 16 June) — the SAME
  material again, with the writing surface revealed, where the writer
  completes the book. CLOSE end of the funnel (one scene).

WHY BACK-AND-FORTH IS FREE — THE MIXDOWN:
- Like multitrack music: the tracks underneath never go away; a mixdown
  RENDERS them together but does not destroy them. Going back is free
  because nothing was ever converted — it was the same data wearing a
  different coat all along.
- Things drop into FIXED PLACES (a home/slot) but can STILL be moved
  from place to place. Loose AND structured at once.
- When you MIX DOWN, only certain things stay VISIBLE in the centre (the
  spine / the EVENTS — the through-line), and the rest (Characters,
  Locations, Objects, Themes, Tension — the "reach-into" tracks) drop to
  a LIST DOWN THE SIDE. They don't vanish; they move to the margin. That
  side-list IS the WP SCENE MENU already built into the wheel file.
- THE BOARD (code-board-look.html) is the WIDE end — all six tracks as
  columns, everything visible. THE WHEEL + PAGE is the CLOSE end — spine
  as the page, reach-into tracks as the side list. SAME DATA, two coats.

THE HARD KERNEL — THE KEYSTONE (NOT yet solved; the next real build):
- The whole thing only works if each overlay's structure — the ordering,
  the timeline position, the chapter/scene home — is STORED ON THE
  SHARED DATA itself, not held inside a view. In music terms: the
  structure lives in the MIX INSTRUCTIONS that sit alongside the tracks,
  not in the tracks.
- THE QUESTION TO ANSWER (still-picture first, fresh chat): how does ONE
  record carry its board position, its timeline order, AND its
  chapter/scene home all at once, so the overlays just read and write the
  same thing? This is the SAME beast as the long-standing DATABASE
  REORGANISATION question.
- OPEN within this: is each level's ordering a SEPARATE set of mix
  instructions (Sandbox can stay jumbled while Synopsis holds the tidy
  order), or does ordering in one level flow down and change the others?

THE SPINE — A TIMELINE OF EVENTS
Three tiers: CHAPTER → SCENE → EVENT. Only EVENTS sit on the line and
become prose — only events HAPPEN. Characters, Locations, Objects, etc.
do not happen; they are REACHED INTO by the events that use them.

"FILL IN THE BLANKS"
The Treatment assembles the SUBSTANCE from the database and leaves the
writer the blanks: the prose only they can write. Assembled, the
sections ARE the draft; the writing is the last layer.

================================================================
THE QUICK-NOTE — PINNED POST-IT, BUILT (component, 17 June 2026)
================================================================
The PINNED POST-IT idea (raised 16 June) is now a WORKING, APPROVED
standalone component, signed off by Kev. Saved to the DB as
inkyswot/inkyswot-code-quick-note.html.md. NOT yet wired into the
platform — it is a finished part waiting to be dropped in.

WHAT IT IS (settled this session):
- A small AMBER PAPER SCRAP — warm amber on the dark workspace, so it
  reads instantly as a SCRAP (a thought, NOT filed story data). Built as
  the scruffy cousin of the entity POP-UP idiom: drag by its top strip,
  ✕ to delete (top-right), cascades when there is more than one, click a
  scrap to raise it to the front.
- Square-ish and upright. AUTO-GROWS as you type — the paper deepens, so
  there is never a scrollbar. The folded bottom-right corner is a real
  RESIZE handle (drag it).
- IT IS NOT STORY DATA: never a character / event / scene, never becomes
  prose, never mixes down. The writer talking to themselves ("fix this",
  "Marley too early?", "check the date").

THE LIFE OF A SCRAP — three exits:
- SUMMON from anywhere → jot → then one of:
  · KEEP (Enter) — files it away. In the platform this hands the text to
    the Notes pad via an optional hook (window.QuickNoteOnKeep).
  · BIN (esc, or the ✕) — gone.
  · PIN — sticks it down; it stays until deleted.

THE PIN — a two-state thumbtack (much-iterated; Kev happy):
- LOOSE: a small GOLD OUTLINE thumbtack, centred on the top of the note.
- PINNED: the SAME thumbtack SHAPE, FILLED with a colour, in the SAME
  spot — clicking swaps outline → filled IN PLACE (no jump). The note
  also gains a faint gold ring, so "pinned" reads at a glance.
- A CLEAN CLICK on the pin toggles pinned/loose. A PRESS-AND-DRAG on the
  very same pin MOVES the note — so a pinned scrap is still freely
  movable (grab the pin, or the top strip).
- PINNED = ANCHORED TO THE SCENE: a pinned scrap drops into the scrolling
  page and SCROLLS WITH IT (content-anchored, not floating on the glass).
  Loose scraps float over the view.

THE PIN-HEAD COLOUR — assignable, per note (new this session):
- When you pin, a small COLOUR POPUP opens just below the pin. Pick a
  colour and it applies and the popup closes (clicking away also closes
  it). Each scrap remembers its own head colour.
- The palette is THE SIX TRACK COLOURS (Events gold, Locations teal,
  Characters terracotta, Objects steel blue, Themes violet, Tension red),
  default Tension red — so a pin's colour can MEAN something later rather
  than being random decoration.
- To recolour later you re-pin (the popup is tied to the pinning action).
  A "recolour without unpinning" gesture is a possible future tweak — not
  built.

HOW THE COMPONENT IS WIRED (for the integration step):
- HOST = a layer fixed in the viewport — loose scraps float here.
- STAGE = the scrolling scene/page — pinned scraps anchor here.
- window.QuickNoteOnKeep(text) = optional hook; in the platform it files
  a kept scrap into the Notes pad.
- summonNote() = call it from the summon key / a button / the ELSRA keypad.
- The file ships with a DEMO HARNESS (dark backdrop + ＋ button + N key),
  clearly marked to DELETE on integration; the STYLES and SCRIPT blocks
  are marked to lift whole.

STILL TO DO (also noted as a comment in the code):
1. PERSIST — scraps must STAY where dropped and survive a refresh. In the
   standalone file that means browser memory; in the platform they should
   save into the InkySwot DATABASE like everything else. NOT built.
2. SEE ALL — one button that shows EVERY scrap at once, wherever each is
   pinned. UNDECIDED: a panel that LISTS them, or GATHER the actual notes
   onto the screen. NOT built. (Persistence comes first — you cannot
   gather what was never saved.)
3. ACROSS ALL SCREENS — the founding requirement. This is the integration
   job: HOST becomes one app-level overlay above EVERY screen; the summon
   moves to app level (the keypad). Needs the live platform shell pasted.

STILL OPEN (carried from 16 June): does a PINNED note travel BETWEEN views
(pinned to the THING — e.g. a scene — so it rides the funnel) or live only
in the view it was stuck in (pinned to the VIEW)? The component anchors a
pinned scrap to the scene/page and scrolls with it; whether it CROSSES the
funnel is still undecided.

DROPPED this session: notes do NOT hold images. Images live in the
RESEARCH section.

LINEAGE: the grown-up form of the old "Stickies" toy / Map Plotter
corkboard. Stickies remains NOT a menu destination; its DNA lives here and
in the board.

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
wheel file), and now ALSO to the QUICK-NOTE pin-head palette (17 June).
Chapter #9a8fb0.

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
THE RIGHT-HAND ROADMAP — TO BE REMOVED; THE WHEEL STAYS (16 June 2026)
================================================================
The current live wheel file (see FILES — the real file is now
wheel-with-roadmap (7).html) carries a scrolling ROADMAP down the RIGHT
side — a list of every scene (Stave One Scene One, Fred's Visit, …).
- DECISION: the right-hand ROADMAP GOES. It duplicates the WHEEL — both
  tell you "where you are" and move you between scenes. One mover, not two.
- THE WHEEL STAYS, on the right, in its place.
- RESTING SHAPE of the close view: LEFT reach-into list (Characters,
  Objects, Themes, Tension) · the PAGE in the centre · the WHEEL on the
  right.
- This is a SMALL SURGICAL build for a fresh chat: remove the roadmap
  from the pasted wheel file, wheel untouched, small-change-means-small.

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
- THIS IS THE MIXED-DOWN SIDE LIST (see THE MIXDOWN): the reach-into
  tracks that collapse out of the board's columns into the margin.
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
THE MENU SPINE — GROWN (16 June 2026)
================================================================
Kev grew the menu beyond the bare nav to a full spine: a Landing page,
then a Home page, then the project nav. NOTE: this is a SPINE, not the
finished map — Kev flagged there is still "loads missing". Wording on a
few items is LEANING, not locked (see OPEN DECISIONS).

THE LANDING PAGE (before login)
- Sign in
- Sign up

THE HOME PAGE (after login — the launchpad)
- New Project
- Load Project
- Demos
   - A Christmas Carol
   - The Wind in the Willows
- The Press

THE PROJECT NAV (the in-app left menu)
- PROJECTS
   - New Project
   - Load Project
   - Demo
      - A Christmas Carol
      - The Wind in the Willows
- DCW
   - Sandbox        (moved here — head of the funnel)
   - Synopsis
   - Chapters
   - Scenes
   - Manuscript     (was "Writing Panel")
   - The Press       (its second home; sub-items TBD — "other stuff")
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
   - Snippets        (was "Library" — Snippets = bits of script/text YOU
                      wrote and saved for later; replaces the vague
                      "Library" wrapper)
   - Research        (was "Research & Reference" — material brought in
                      from OUTSIDE the story; ALSO now the home for any
                      IMAGES — they are NOT held on notes, 17 June)
- HELP
   - Tutorials
   - Manual
   - FAQs
   - What's New
- Trash
   - View Trash
   - Empty Trash

NOTES ON THE MENU SPINE:
- SANDBOX now lives at the HEAD of DCW (not under NOTES). It is the loose
  entry point that feeds the DCW; head of DCW = where the funnel begins.
- THE PRESS lives in TWO homes: on the HOME page, and nested under DCW.
  Its DCW sub-items are not yet defined ("other stuff" placeholders).
- NOTES = Snippets + Research. "Library" dropped (too vague — Snippets
  names the actual contents, so a writer never hesitates "mine vs found").
- STICKIES (Notes & Scratchpad) — DELIBERATELY DROPPED from the menu (16
  June). It is NOT a menu destination; it is the PINNED-NOTE layer, now
  BUILT as the QUICK-NOTE component (see that section).
- SYNOPSIS under DCW IS the former "Plot Mapping" (same thing; name
  dropped, confirmed 14 June).
- FACTIONS & ORGANISATIONS — written in FULL. Never "Orgs".
- STRUCK FROM THE NAV earlier (hidden, not deleted as screens): Plot
  Threads, Subplots, Themes & Motifs.

ENTRY (settled 8 June, standing):
- LANDING PAGE (before login): Sign In / Sign Up. Its own screen.
- After sign in/up the writer lands on the HOME page (launchpad).
- OVERVIEW: currently titled "BASIS" in index.html. Whether OVERVIEW
  persists as a screen at all is now in doubt — the new spine routes
  login → HOME, not login → Overview. CARRIED QUESTION.

LAUNCHPAD ICONS — SETTLED (8 June 2026)
Clean single-weight gold line art, stroke="currentColor" (recolour with
Tone; no PNGs). Three drawn: Load Project — drawer chest; New Project —
typewriter; Demos — signpost. Stored with inkyswot/home-icons.svg.md.

================================================================
THE SITE MAP — TWO DIFFERENT THINGS; DON'T CONFUSE THEM
================================================================
1. THE STRUCTURAL SITE MAP (a PLAN, not a feature) — the complete tree of
   what InkySwot contains, the skeleton on paper, built to settle where
   everything lives. Kev asked for this 16 June ("we have to build a
   complete site map… so we stop messing"). NOT yet built — wants its own
   fresh chat with the core files. The MENU SPINE above is the start of it.
2. THE THEATRICAL SITE MAP (a FEATURE in the app) — the "where you are"
   delight: blocks of colour (the six track colours), strange lines, a
   "BOOM (ish)" flourish on navigate, meant to make the writer smile.
   PARKED (14 June) — likely wants its OWN PAGE; the 290px sidebar was too
   cramped. The calm FOUR-HEADING SIDEBAR map is the quiet stand-in.

THE CALM FOUR-HEADING SITE MAP — the SIDEBAR version (built, kept):
A calm SPINE of the FOUR HEADINGS, contents popping up on hover; spine on
the RIGHT, ring nodes, plain-text contents right-aligned, two lanes,
STATIC / hover-driven. NB the four headings should be kept in step with
the SETTLED nav — which has now GROWN (see THE MENU SPINE), so the
sidebar map will need updating when next touched.

================================================================
MANUSCRIPT VIEW — TOGGLE (writer comfort, agreed 8 June)
================================================================
A toggle in the WP to strip the chrome and read the book as a continuous
manuscript. Display-level only; TRUE flowing pagination remains a bigger
deferred build. (NB: "the Manuscript" is now also the NAME of the close /
writing view — see THE MIXDOWN. This toggle is a comfort view within it.)

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
THE MEMORY DATABASE — HOUSEKEEPING (9 June; updated 17 June 2026)
================================================================
Pitch Dark Studios Memory (pitchdarkpress.github.io/pitch-dark-studios-
memory) holds files per DIVISION. Code files carry a "code-" prefix, e.g.
  inkyswot/code-readme.md            (index of the code files)
  inkyswot/code-treatment-wheel.html.md   (the WHEEL — live design source)
  inkyswot/code-board-look.html.md   (the board STILL PICTURE)
  inkyswot/code-site-map.html.md     (the SITE MAP)
  inkyswot/code-map-plotter.html.md  (old corkboard — SUPERSEDED history)
  inkyswot/home-icons.svg.md         (launchpad line icons)
  inkyswot/inkyswot-code-quick-note.html.md  (NEW 17 June — the QUICK-NOTE
                                     component; note this one carries the
                                     division at the FRONT of the name,
                                     fuller than the older "code-" prefix)

*** ADMIN-PANEL GOTCHA — FOUND & FIXED (17 June) ***
A file saved at the repo ROOT (a bare filename, no division folder in
front) SAVES fine but does NOT appear in the admin menu. The menu builder
(renderTree) buckets files by their top-level folder and deliberately
drops anything not inside one. THE FIX: always put the division folder in
front, e.g. "inkyswot/inkyswot-code-quick-note.html.md" — not just the
bare filename. (Any root copy made by mistake is hidden, not lost.)

STILL TO TEST: whether the InkySwot division can hold a .png / .jpg image
(now mainly for RESEARCH, since images are NOT held on notes).

FILES — InkySwot division of the memory database
current-state.md · locked-decisions.md · dcw.md (the three core .md).
*** FILE-OF-TRUTH NOTE (16 June): the LIVE wheel file is now
"wheel-with-roadmap (7).html" — it carries the SETTLED four-section nav,
the LEFT reach-into list, and the RIGHT-HAND ROADMAP (which is to be
REMOVED, wheel kept). An OLDER copy with a stub left-nav and an EMPTY
right sidebar was pasted earlier and is NOT the truth. Always ask Kev for
the current file at the start of a build. ***
inkyswot/code-treatment-wheel.html.md — earlier live design source (the
older lineage; superseded by wheel-with-roadmap (7).html as the working
file). STILL NOT folded in anywhere: the chapter STAVE PAGE; the WP
Prompt/Expand buttons; the wheel's stave-page label; the Tension meter
(still a "55%" placeholder).
inkyswot/inkyswot-code-quick-note.html.md — the QUICK-NOTE component
(BUILT 17 June, signed off). Standalone; STYLES + SCRIPT blocks marked to
lift, plus a DEMO HARNESS marked to delete on integration. NOT yet wired
into index.html or the wheel.
inkyswot/code-site-map.html.md — the SITE MAP. The standalone four-heading
spine. NB the THEATRICAL "where you are" Site Map (blocks of colour, BOOM)
is the new intent and is PARKED (likely its own page) — not in any file.
inkyswot/code-board-look.html.md — the BOARD still picture = the WIDE end
of the funnel (all six tracks as columns). Now CONFIRMED as part of the
mixdown, not "under review".
inkyswot/home-icons.svg.md — launchpad icons.
inkyswot/code-map-plotter.html.md — old Plot Mapping corkboard (grew from
the original "Stickies" toy). SUPERSEDED as a screen; its DNA feeds the
QUICK-NOTE and the Sandbox.
index.html — the app workspace (Overview screen still titled "BASIS").
login.html — login / sign up gate (stubbed).

WHAT IS BUILT AND WORKING
Landing page; login page (stubbed); My Projects / Trash / New Project
modal / Overview / Characters / Relationships / Factions & Orgs /
Language & Dialogue / Locations / Buildings / Objects & Artefacts /
Rules & Lore / Plot Threads / Subplots / Themes & Motifs / Events &
Timeline / Chapters / The Treatment (placeholder shell) / AI Expand /
AI ON-OFF / Read Aloud / light-dark / voice selector. The WHEEL + WP +
LEFT SCENE MENU + SETTLED LEFT NAV + RIGHT-HAND ROADMAP live together in
the standalone mockup (wheel-with-roadmap (7).html), NOT yet in
index.html. The BOARD is a standalone still picture (the wide end). The
QUICK-NOTE component is built and signed off as a STANDALONE file — NOT
yet wired into the platform.

BUILD ORDER — CONFIRMED (unchanged)
Step 1 v4.0 App Shell Rebuild (NOT STARTED) · 2 Walk · 3 Sign-off Gate ·
4 Supabase · 5 Lifetime flag · 6 F12/Security · 7 Server prompt tracking
· 8 Stripe · 9 Resend · 10 Writing surface (WP + pop-ups + wheel + scene
menu) · 11 The Treatment (the wheel) · 12 Ada · 13 DCW (= the wheel) ·
14 Export Suite · 15 The Press · 16 Admin · 17 PWA · 18 Beta · 19 Launch.
DEMO BOOKS (Carol then Willows) — after Step 1 sections are final.

CURRENT STATUS & NEXT ACTIONS
v4.7 pre-Step 1 rebuild. Autumn 2026 target.
... [history through 14 June as previously logged] ...
16 June (chat / design session — NO CODE CHANGED): settled the DCW as ONE
  BODY OF DATA / a MIXDOWN (Sandbox → Synopsis (timeline + Chapters/Scenes
  overlays) → THE MANUSCRIPT, renamed from Writing Panel). Saw the funnel
  end-to-end on real screens: the BOARD is the wide end, the WHEEL+PAGE
  the close end, the left scene menu IS the mixed-down side list. Decided
  the RIGHT-HAND ROADMAP goes and the WHEEL stays. New idea: PINNED
  POST-IT NOTES — a layer above the data, content-anchored, never mixed
  down. Grew the MENU SPINE (Landing / Home / four-section nav; Sandbox to
  head of DCW; NOTES = Snippets + Research; Stickies parked; Press in two
  homes; Trash opens to View/Empty). Identified the real wheel file as
  wheel-with-roadmap (7).html (older pasted copy was stale).
17 June (chat / BUILD session — CODE BUILT): built THE QUICK-NOTE
  component (the pinned post-it) end to end and Kev signed it off. An
  amber scrap built as the pop-up's scruffy cousin (drag, ✕, cascade,
  raise-to-front); auto-grows with the text; folded-corner resize; summon
  → jot → keep / bin / pin. The PIN is a two-state thumbtack — gold
  OUTLINE when loose, the SAME shape FILLED with colour when pinned, swap
  in place, with a faint gold ring when pinned; a clean click toggles, a
  drag on the pin MOVES the note; a pinned scrap anchors to the scene and
  scrolls with it. The pin-HEAD colour is assignable via a small POPUP (the
  six track colours, default Tension red). Saved to the DB as
  inkyswot/inkyswot-code-quick-note.html.md. Images on notes DROPPED (they
  live in Research). Found & fixed an admin-panel gotcha: root-level files
  save but do not show in the menu — give the division folder. STILL TO
  DO: persistence + a "see all" button + the across-all-screens wiring.
  current-state.md rewritten clean (this file).

NEXT (do in order, one at a time — START A FRESH CHAT for a build)
1. SMALL SURGICAL BUILD: remove the RIGHT-HAND ROADMAP from the live wheel
   file (wheel-with-roadmap (7).html), WHEEL UNTOUCHED. Work from Kev's
   pasted file.
2. THE KEYSTONE: design the FUNNEL DATA MODEL (still-picture first) — how
   ONE record carries its board position + timeline order + chapter/scene
   home at once so the overlays/mixdown read and write the same thing.
   This is the spine of the whole platform.
3. FOLD THE STAVE PAGE + WP PROMPT/EXPAND into the live wheel file. Then
   the wheel's stave-page label.
4. Build the TENSION SEGMENTED BAR METER + sweep (static-first) to replace
   the "55%" placeholder in the scene menu.
5. THE QUICK-NOTE — finish it: (a) PERSIST the scraps (browser memory in
   the standalone, the DATABASE in the platform); (b) the SEE-ALL button
   (decide first: a panel that lists them, or gather the notes onto the
   screen); (c) settle whether a pinned note CROSSES between views; then
   (d) WIRE IT ACROSS ALL SCREENS (HOST as an app-level overlay; summon on
   the keypad) — needs the live platform shell pasted.
6. THE THEATRICAL SITE MAP (when off hold): agree resting + exploded
   stills, then wire the BOOM — likely its OWN PAGE.
7. UPDATE locked-decisions.md and dcw.md to match (DCW = mixdown; Writing
   Panel = Manuscript; menu spine; roadmap out; the QUICK-NOTE settled
   spec) — one file at a time.
8. Test whether the InkySwot division can hold a .png image (for Research).
9. (Carried app jobs) settle Overview's fate; build the nav into
   index.html (to the new spine); build the home launchpad; begin Step 1.

OPEN DECISIONS — STILL TO SETTLE (one at a time)
1. THE KEYSTONE — the FUNNEL DATA MODEL (how one record holds all three
   structures at once). The big one; everything hangs on it.
2. PINNED NOTES — does a note cross BETWEEN views (pinned to the thing) or
   live in one view (pinned to the view)? (Component anchors to the scene
   and scrolls with it; crossing the funnel is still undecided.)
2b. QUICK-NOTE "SEE ALL" — does the button open a PANEL that LISTS every
   scrap, or GATHER the actual notes onto the screen? Undecided.
2c. QUICK-NOTE PERSISTENCE — browser memory (quick, standalone) vs the
   InkySwot DATABASE (proper, everywhere). The DB is the real home; the
   storage swaps over at integration.
3. MENU WORDING — final confirm "Snippets" replaces "Library"; "Research"
   vs "Research & Reference"; THE PRESS's DCW sub-items.
4. THE PRESS — what its two homes each hold; its DCW sub-items.
5. OVERVIEW — does it survive at all now that login routes to HOME?
6. THE BOARD's exact role in the mixdown (it is the wide end — but does
   the writer build IN it, or is it a read view?).
7. STICKIES / NOTES & SCRATCHPAD — now answered by the QUICK-NOTE; any
   remaining "scratchpad" need to revisit.
8. THE THEATRICAL SITE MAP — its own page; what the BOOM is.
9. EVENT ORDER WITHIN A SCENE; multiple events per scene (list or collapse).
10. WHERE THE MOOD WORDS LIVE (Cold · Bleak · Biting). Parked.
11. TAG SET — Prose vs Action; Dialogue's place; Emotion tag vs Map.
12. CARRIED FEATURES' HOME — Emotional Maps, Ambient, the lift.
13. WHEEL LIVE-LABEL FLIP POINT — small tweak.
14. THE STAVE PAGE'S WHEEL LABEL — settle when folding the stave page in.

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
- "THREE VIEWS OF ONE BODY OF DATA" as the framing — superseded 16 June by
  THE MIXDOWN (one body, overlays). The funnel idea survives; "three
  separate views" does not.
- "WRITING PANEL" as the name — renamed THE MANUSCRIPT, 16 June.
- THE RIGHT-HAND ROADMAP — to be removed (duplicates the wheel), 16 June.
- "LIBRARY" as a NOTES item — replaced by "Snippets", 16 June.
- IMAGES ON NOTES — dropped 17 June. A quick-note holds text only; images
  live in the RESEARCH section.
- THE ROUND GLOSSY RED PUSHPIN for the pinned note — superseded 17 June by
  the FILLED THUMBTACK that matches the gold outline shape (same shape,
  one outline, one filled).
- THE CALM FOUR-HEADING SITE MAP AS THE INTENDED MAP — superseded 14 June
  as the *whole* intent: now only the calm SIDEBAR version. The intended
  Site Map is THEATRICAL. The four-heading map is kept, not killed.
- THE 14-JUNE SIDEBAR CONSTELLATION TRIES — all PARKED; the theatrical map
  wants its own page.
- "PLOT MAPPING" as a name/item — dropped; it IS Synopsis.
- THE FIRST SITE MAP (11 June) — full branching TREE; superseded by the
  four-heading spine.
- THE "ROAD MAP" NAME — renamed to SITE MAP, 11 June.
- THE OLD GOLD CHARACTERS / BROWN EVENTS section colours — revised 9 June.
- TENSION as a VU NEEDLE / FLAT LINE-WITH-POINTER / plain "55%" text — all
  superseded by the segmented bar meter.
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