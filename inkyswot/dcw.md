File: inkyswot/dcw.md
Last updated: 9 June 2026

================================================================
READ FIRST — THIS IS THE LIVE SPEC.
InkySwot IS the DCW. The Treatment is the DCW switched on — a TIMELINE
OF EVENTS assembled from the database, written by filling in the blanks.
There are THREE VIEWS of one body of data: THE BOARD (Plot Mapping
reborn — wide), THE WP + WHEEL (close, one scene), THE ROAD MAP (the
journey). A FUNNEL, living link both ways, nothing entered twice.
Everything from the LIVE SPEC heading down to "================ HISTORY"
is current and buildable. Everything below "HISTORY" is SUPERSEDED —
kept only as the record of how we got here. Do NOT build from history.

9 JUNE 2026 UPDATE: the BOARD came back as Plot Mapping reborn (six
tracks). The CUT was settled (Events+Locations feed the synopsis; the
other four are reached-into). The WP gained a LEFT SCENE MENU mirroring
the wheel. The SIX TRACK COLOURS were settled. TENSION got a segmented
bar METER. The right sidebar got its purpose: the ROAD MAP. The code is
the truth; this file follows it.
================================================================

================================================================
THE LIVE SPEC — INKYSWOT IS THE DCW / THE TREATMENT / THE WHEEL
================================================================

WHAT THE DCW IS
The Digital Creative Workstation. InkySwot's owned term. Said as three
letters: D.C.W. Equivalent to a DAW in music production. It is the
platform's defining feature. When rivals copy InkySwot they will be
labelled "just another DCW ripoff."
BUT — the 4 June realisation — the DCW is NOT a screen, a strip, a
board, or a panel. It is the WHOLE PLATFORM. Every section already
built (Characters, Locations, Events, Plot Threads, etc.) is part of
the instrument. The database is the BONES of the story.

THREE VIEWS OF ONE BODY OF DATA — THE FUNNEL (settled 9 June 2026)
The whole instrument is seen at three distances, and the writer moves
freely between them:
- THE BOARD (Plot Mapping reborn) — the WIDE view. The whole book as an
  instrument: scenes down the spine, the world across the tracks.
- THE WP + THE WHEEL — the CLOSE view. The same data narrowed to the
  one scene being written.
- THE ROAD MAP — the JOURNEY view (right sidebar).
A FUNNEL: wide and loose at the top (the board), narrowing to the single
scene at the spine (the WP). LIVING LINK, BOTH WAYS — change data in one
view, it changes in the others. NOTHING ENTERED TWICE. The three stages
are to be BROUGHT TOGETHER as the next build; the foundation question
(Kev's first for that build) is HOW THE DATABASE IS REORGANISED so all
three read/write the same records.

THE TREATMENT IS THE DCW SWITCHED ON
The Treatment is where everything in the database ASSEMBLES into a
readable, writable whole. A plotline is not a new thing to author — it
is a VIEW of data that already exists. The writer fills in the
sections; The Treatment gathers them, in order, onto the page.

THE SPINE — A TIMELINE OF EVENTS
The Treatment is a TIMELINE OF EVENTS. Three tiers:
  CHAPTER  →  SCENE  →  EVENT
- Only EVENTS sit on the line and become prose — because only events
  HAPPEN. Characters, Locations, Objects, etc. do not happen; they are
  REACHED INTO by the events that use them (via the pop-up / scene menu).
- This answers the old "what is a row?" knot: the line is made of
  events, not of everything.
- Chapters and Scenes are the dividers. A SCENE is labelled "Scene 1",
  "Scene 2"… with an optional title. Events live under their scene.

FILL IN THE BLANKS — THE DESIGN PRINCIPLE
The Treatment assembles itself from everything in the database — not
just names, the SUBSTANCE — and leaves the writer the blanks: the prose
and dialogue no database can hold. The writer faces a page three-
quarters built, with holes shaped exactly like the writing only they
can do. Assembled, the sections ARE the draft; the writing is the last
layer, not the first.

----------------------------------------------------------------
THE BOARD — PLOT MAPPING REBORN (settled 9 June 2026)
----------------------------------------------------------------
The old DCW vertical board was killed on 4 June for the "what is a row"
knot. On 9 June it came BACK — the look that "made Kev laugh" — now in
the current visual language, and carrying the timeline-of-events truth.
The lesson: the board was never the mistake; killing the beauty to solve
a logic problem was. The board can hold the truth AND be beautiful.

THE BOARD IS PLOT MAPPING — not a tool beside it, it IS Plot Mapping
reborn. The old corkboard (code-map-plotter.html) is superseded by it.

SHAPE:
- Scenes down a sticky left SPINE (Stave / Scene, with a count + page).
- SIX TRACKS across the top, left to right:
    EVENTS · LOCATIONS · CHARACTERS · OBJECTS · THEMES · TENSION
- Each cell holds QUIET NOTES in the track colour (sub-title in the
  colour, neutral-ink description, solid colour end-line).
- TENSION is a drawn CURVE down its column (the board form; the WP form
  is the meter — see the scene menu).
- Stave divider rows break the spine into staves.

THE CUT — WHAT TRANSFERS TO THE WP (settled 9 June):
- EVENTS + LOCATIONS form the SYNOPSIS of every chapter and scene — the
  "what happens and where" that becomes the prose-bound substance on the
  WP page (the .event line).
- CHARACTERS · OBJECTS · THEMES · TENSION are reached-into; their WP home
  is the LEFT SCENE MENU.

CURRENT STATE: code-board-look.html is a STILL PICTURE only (a "look",
not wired, no drag, no real data) and still carries the OLD colours.
Applying the six colours and building it for real are jobs to come.

----------------------------------------------------------------
THE PAGE — ONE SCENE PER FULL PAGE (settled 6 June 2026)
----------------------------------------------------------------
- ONE SCENE PER FULL PAGE. Each scene sits on its OWN full US-Letter
  sheet (816 × 1056px). The old multi-event long-scrolling page is GONE.
- PAGES ARE ALWAYS FULL HEIGHT. A short scene leaves white space below —
  the rest of the sheet, like a real document page. Never shrunk to hug.
- STAVE HEADING ON EVERY PAGE (.ch-h) at the top, for navigation.
- ON A PAGE: running head top-right ("A Christmas Carol by Charles
  Dickens"), then the stave heading (mono caps, ruled under), then the
  scene heading ("Scene 1 — The Counting-House"), then the event(s)
  with a "— click to write this scene —" line beneath each.
- WHY: a page that holds ONE thing reads like a manuscript, not a
  dashboard. The calm of the page and the calm of the wheel are one.

----------------------------------------------------------------
THE WHEEL — HOW THE WRITER NAVIGATES AND WRITES
(settled 4 June; refined 6–7 June — this is AS BUILT)
----------------------------------------------------------------
The heart of the writing experience.

THE LAYOUT
- The WP / Treatment page sits in the workspace framed by two dark
  channels. The WHEEL is in the channel to the RIGHT of the page (the
  book / where you are). The SCENE MENU is in the channel to the LEFT
  (this scene's reached-into world — see below). The two channels are
  BALANCED and share the same rail/ring/leader furniture. Grid is
  ~230px 1fr 230px.
- Out in the right channel is THE WHEEL: a single hairline gold RAIL
  with small nodes, two-line labels to the right of the rail, and a
  fixed gold CENTRE.

THE LABELS — TWO LINES EACH (settled 7 June 2026)
Every wheel label is TWO LINES:
- A KICKER in gold JetBrains Mono caps ("STAVE ONE — SCENE ONE").
- The SCENE TITLE beneath in Crimson Pro ("The Counting-House").
Every label carries its full stave+scene position. NO separate stave
marker labels, NO blank stave pages — the stave is named on every scene
via the kicker. Stave/scene numbers are computed in JS from a
data-stave-open="1" attribute on each stave's FIRST page.

THE MECHANISM (as built)
- Scrolling the PAGE turns the wheel (page-scroll driven, NOT wheel-
  scroll). Whatever label sits on the fixed centre is WHERE YOU ARE.
- THE CENTRE MARK: a gold RING (17px, 2px border) with a filled gold
  dot, plus a short gold LEADER from the ring toward the centre label.
  The centre label's TITLE lights gold. The centre node is hidden.
  (REMOVED 6 June: the radial BLOOM glow and the » CHEVRON.)
- THE WINDOW: nine labels each side of centre (WINDOW=9) — a real MAP
  of the book using the full page height. Labels fade in/out at the
  edges so the wheel stays calm however long the book is.
- THE FADE: an even, gentle fade with a brightness FLOOR; centre + the
  two either side at full brightness, the rest dimmed to ~71%. Label
  text colour uniform; dimming is opacity only.
- HOVER: lights ONLY the NODE gold; the TEXT does NOT change. Clicking
  navigates.
- THE MOTION: eased and slow — glides toward target, not 1:1 to scroll.
  Ease rate 0.072. Row spacing TIGHT=46, centre gap GAP=64.
- THE LIVE HAND-OFF IS SMOOTHED: 0.35s CSS transition on the label text
  so the gold eases in/out as labels pass centre.
- THE BELT IS STRAIGHT (BOW=0). A slight outward bow was tried and liked
  but REMOVED (ran the two-line labels together). Any future bow must
  not cost two-line legibility.
- positionWheel() centres the wheel block live in the channel at any
  width; labels wrap to ~half the channel width.

THE PAGE LANDS ON ONE SHARED READING LINE (page-top bug FIXED, 7 June)
The page and the wheel share ONE reading line, READ_PAD = 28px below the
header. Clicking a label (or opening any scene) lands that scene's TOP
on the line (rollToTop), so the page reads downward from the top. The
wheel reads "where you are" from the SAME line, so page and wheel cannot
disagree. (rollToCentre, which clipped the top of a full-height page, is
gone.) OPEN SMALL TWEAK: the live-label flip point ~halfway down a tall
page; biasing it later is easy.

TWO STATES — OVERVIEW AND WRITING MODE
- OVERVIEW: the assembled Treatment shows (one scene per page); the
  wheel turns with the scroll; centre = where you are. Click a wheel
  label to go there. Click the CENTRE label (or "— click to write this
  scene —") to enter Writing Mode.
- WRITING MODE: the page opens CLEAN for that one scene; the whole page
  given to a full-height writing area. ONLY the live scene shows; every
  other page is hidden (cured the stack-of-blank-pages). The wheel stays
  lit, locked with that scene at centre. Click any wheel label to open
  THAT scene to write — travel scene-to-scene BY THE WHEEL without
  leaving Writing Mode. Each scene's text is remembered (drafts{} keyed
  by index). A "‹ overview" control (top-right, Writing Mode only)
  returns to the assembled Treatment.

THE PRINCIPLE
The writing position and the map position are the SAME thing. The writer
writes at the centre; the wheel shows what has been passed (above),
where you are (centre), and what is coming (below). The writer never
leaves the writing to move about the book.

----------------------------------------------------------------
THE WP LEFT SCENE MENU — THE REACHED-INTO TRACKS (built 9 June 2026)
----------------------------------------------------------------
The home found for Characters · Objects · Themes · Tension. In the dark
channel to the LEFT of the WP, MIRRORING the wheel — the workspace reads
as one instrument, the same furniture on both sides.
- WHAT IT IS: "what this scene reaches into" — tied to the PAGE, not the
  book; it changes scene to scene. (The wheel is the BOOK; the scene
  menu is THIS SCENE. Different jobs, opposite sides. NOT merged — that
  was considered 9 June and rejected.)
- LOOK: a RIGHT-ALIGNED list. Coloured group headers (Characters
  terracotta, Objects steel blue, Themes violet, Tension red) with names
  in plain ink beneath. MATCHING FURNITURE to the wheel: a thin vertical
  gold RAIL; a gold RING (17px, 2px, centred dot) on the rail; a short
  gold LEADER off the ring pointing INWARD toward the list (mirror of
  the wheel's outward leader, with the gold fading toward the list).
  Equal breathing room from the page as the wheel has on the right.
- CLICKABLE: clicking a name opens that entity's POP-UP RECORD — the
  same draggable pop-up the nav opens, with copy buttons. (Wired for the
  Character records; placeholder Objects/Themes items wire the same way
  once those tracks have real records.)
- TENSION IS A METER (settled 9 June): a SEGMENTED BAR METER — a row of
  segments GREEN → AMBER → RED lighting up to the scene's level, with the
  PERCENTAGE beneath (e.g. 55%). A straight percentage that can run PAST
  100 into the red. "For the theatre of it." A light-up SWEEP between
  scenes is wanted (car-dial wake: drop to zero, run up, settle) — build
  static-first. (SUPERSEDES, all tried 9 June: a VU needle gauge, a flat
  line-with-pointer, a plain "55%" text.)

----------------------------------------------------------------
THE ROAD MAP — THE RIGHT SIDEBAR'S PURPOSE (idea, 9 June 2026)
----------------------------------------------------------------
The 230px right sidebar (long blank — the open "what is it for" question)
becomes a USER ROAD MAP.
- WHAT: stages of the journey down the sidebar, with a LIT DOT/RING for
  WHERE YOU ARE. Mirrors the wheel/scene-menu rail furniture — so all
  THREE verticals (scene menu left, wheel centre-right, road map far
  right) share the look.
- REACTIVE THEATRE: actions elsewhere make the map RESPOND — e.g. open
  the Characters box and add/modify a record, and a small section-colour
  box opens on the road map off the relevant node. A living instrument,
  not a static menu.
- CLICKABLE: stages can be clicked to jump there (also navigation).
STILL TO SETTLE (next build, not yet built): WHAT STAGES live on it (the
platform journey, the story spine, or the project's progress); the
clickable behaviour and how it relates to the left NAV without doubling
up; the exact reactive-box behaviour. Build static-first.

----------------------------------------------------------------
HOW THE WORLD IS REACHED — THE ENTITY POP-UP (settled 4 June)
----------------------------------------------------------------
The writer reaches the database WITHOUT leaving the page, via a stable,
draggable pop-up panel. Opened from the NAV (two steps: section → list →
record) OR from the LEFT SCENE MENU (one click on a name → straight to
its record). Present in the wheel mockup and working.
- MULTIPLE & INDEPENDENT: each open opens its OWN pop-up at the home
  position (small cascade offset); several open at once; each dragged,
  navigated and closed on its own ✕; clicking one raises it to front.
- STABLE: click to open, click (✕) to close. Does NOT vanish on
  click-away; does NOT close when you select text inside it.
- QUIET-NOTE GRAMMAR throughout: a SUB-TITLE in the SECTION's colour, a
  DESCRIPTION in neutral ink beneath, a SOLID end-line in the colour.
  Colour = wayfinding (per THE SIX TRACK COLOURS).
- RECORD VIEW: per-field rows, each with a small COPY button (turns
  "copied" briefly), section-colour dividers, a section-colour end-line.
- COPY AND PASTE is how database substance reaches the WP. Copy takes
  TEXT ONLY: coloured in the pop-up, it lands in the WP PLAIN, taking
  the page's own ink. Colour for FINDING; neutral ink for READING.

----------------------------------------------------------------
THE WP — A REAL DOCUMENT PAGE (settled 4 June; refined 6 June)
----------------------------------------------------------------
A proper document page (US Letter, 816 × 1056px, generous margins), on
the dark workspace with a page shadow — not a thin panel. Framed by the
scene-menu channel left and the wheel channel right. ONE SCENE PER PAGE.
- Running head: small Crimson Pro line top-right, muted grey.
- Stave heading: JetBrains Mono 13px uppercase, weight 500, ruled under.
- Scene heading: JetBrains Mono 11px uppercase mute + optional italic
  Crimson Pro title, or "+ add a title".
- Writing area (.ws-area): Crimson Pro 18px, line-height 1.5.
- MAGNIFY (zoom): − / 100% / + scales the whole document (70%–200%) —
  ZOOM, not page-width; the page shape never changes. (Specced.)
- PAGE NUMBERS centred at the foot; optional UNNUMBERED TITLE PAGE with
  toggle; title + author pull from Overview. (Specced.)
- MANUSCRIPT VIEW toggle (8 June): strip the chrome to read the book as
  a continuous manuscript — writer comfort, display-level only.
- SCROLLBARS: slim, dark, gold-on-hover.
- NOTE: pages are fixed-height sheets in the mockup. REAL pagination
  (prose flowing onto new numbered pages) is a bigger build, for when
  the writing surface is real.

----------------------------------------------------------------
THE TAG SET (working list — carried, nothing pruned)
----------------------------------------------------------------
From Kev's working list: Action · Chapter · Character · Emotion ·
Event · Location · Note · Prose · Scene · Time.
Sorted by job:
  SPINE (the timeline)        — Chapter · Scene · Event
  FLESH (the writing)         — Prose · Action · (Dialogue — see NB)
  REFERENCE (reached-into)    — Character · Location · Time ·
                                Emotion · Note · Object · Theme
OPEN on the tag set:
- Is PROSE the same as ACTION, or distinct? (Working split: Action =
  what they do; Prose = description / narration.) UNDECIDED.
- DIALOGUE is not on Kev's list but a scene can't be written without
  spoken lines — confirm Dialogue's place.
- Is EMOTION a per-beat TAG, or the seed of an Emotional Map? UNDECIDED.

----------------------------------------------------------------
CARRIED FEATURES — STILL LIVE, NOT YET FULLY PLACED
----------------------------------------------------------------
TENSION CURVE — THREE MODES (locked 26 May; HOME FOUND 9 June)
A continuous line tracking tension across the story.
- MANUAL — the writer drags the curve.
- AI-GUIDED — the writer draws a target; Ada advises how to reach it.
- ANALYSIS — Ada reads the text and plots the real curve automatically.
HOME (9 June): Tension is now the sixth TRACK on the board (a CURVE down
its column) AND a per-scene SEGMENTED BAR METER in the WP scene menu.
The three modes still describe how the curve/level is set.

EMOTIONAL MAPS (locked 28 May) — the DCW's second defining feature
Each Map is a continuous curve tracking a single emotion of a single
character across chapters. Multiple per character; colour coded;
toggleable; viewable per character or overlaid. Add Map button; draggable
points per chapter; Ada can plot by Analysis. FUTURE: a Map may expand
into a literal cartographic view. NB: not yet placed in the board/wheel
model.

AMBIENT (Atmosphere / Weather / Time)
- ATMOSPHERE — scene mood (cold / warm / dread / joy). Distinct from the
  Emotional Maps and the Buildings "Atmosphere" field.
- WEATHER — what the sky is doing.
- TIME — story-time. TIME IS A BLOCK, not a ruler: reading order runs
  forward, but Time blocks declare STORY-TIME, which can leap anywhere —
  a chapter can hold several Time blocks (present / past / future).
  Separating the two clocks is the insight no rival tool has. Not placed.

DARK THOUGHTS — private notes, never exported, never sent to InkySwot.
Marker: a small grey-violet dot. Carried.

THE LIFT (Prologue / Backstory below Chapter 1) — locked 30 May. The
timeline has a "downstairs": above the line the chapters climb; below it
you descend into the Prologue, then the Backstories. Carried; re-fit to
the board / timeline-of-events model when event-ordering is settled.

THE SECTION ? HELP PILL — every screen, top-right, gold border;
slide-in guide. Template pattern, locked 30 May. Not yet built.

----------------------------------------------------------------
OPEN DECISIONS — STILL TO SETTLE (one at a time)
----------------------------------------------------------------
0. THE DATABASE REORGANISATION for the living link — the next build's
   foundation question (Kev's first for joining the three stages): how
   the board, the WP/wheel and the road map read/write the SAME records.
1. ROAD MAP DETAIL — what stages live on it; clickable vs the nav; the
   reactive-box theatre.
2. WHERE THE MOOD WORDS LIVE (Cold · Bleak · Biting). Parked.
3. EVENT ORDER WITHIN A SCENE — events group by chapter but have no
   sequence within a scene. The spine needs "this before that." (Events
   store characters[] and location; they lack a POSITION.)
4. EVENTS ON THE PAGE — with one-scene-per-page, confirm whether
   multiple events per scene stay listed on the page or collapse.
5. TAG SET opens (Prose vs Action; Dialogue's place; Emotion tag vs Map).
6. WHERE THE OTHER CARRIED FEATURES LIVE — Emotional Maps, Ambient, the
   lift — in the board/wheel model. (Tension now HAS a home.)
7. WHEEL LIVE-LABEL FLIP POINT — small tweak.

----------------------------------------------------------------
BUILD ORDER
----------------------------------------------------------------
The writing surface (Step 10), The Treatment (Step 11) and the DCW
(Step 13) are CONVERGING into the WHEEL + BOARD + SCENE MENU + ROAD MAP
— one instrument, the funnel. The next build BRINGS THE THREE STAGES
TOGETHER (board / WP+wheel / road map), starting with the database
reorganisation. The wheel mockup (code-treatment-wheel.html) and the
board still (code-board-look.html) are the current standalone build /
live design sources. Reconcile the step list once the join is built.

THE LIVE DESIGN SOURCES
- code-treatment-wheel.html — the WHEEL + WP + LEFT SCENE MENU. Built on
  "A Christmas Carol", whole book loaded (5 staves, 25 scenes). METHOD:
  static-first then animated; designing motion by description alone
  failed repeatedly (a working rule now). If edits stop showing, do a
  CLEAN REBUILD in a fresh artifact.
- code-board-look.html — the BOARD still picture (a look; old colours;
  not wired).

================================================================
HISTORY — SUPERSEDED. DO NOT BUILD FROM ANY OF THIS.
Kept as the record of how we reached here. (Full detail retained in the
7 June file; abbreviated here to the headlines, plus the 9 June items.)
================================================================

9 JUNE — TENSION TRIES (SUPERSEDED same day): a VU NEEDLE GAUGE, a FLAT
LINE-WITH-POINTER, and a plain "55%" TEXT — all tried in the scene menu,
replaced by the SEGMENTED BAR METER. And: MERGING the scene menu INTO
the wheel — considered, rejected (different jobs).

OLD SECTION COLOURS (Character #cba36a / Event #b08a6a) — revised 9 June
to THE SIX TRACK COLOURS (Characters terracotta, Events gold, Objects
steel blue, Tension red; Locations teal and Themes violet carried).

3 JUNE — THE ONE-SCREEN DCW / X-RAY (SUPERSEDED 4 June): one screen,
X-ray ON = bones / OFF = flesh; the DCW as a LINEAR column of tagged
CELLS (TAG + CONTENT + (*) handle) — "screenplay × spreadsheet"; write-
off-then-switch-on-and-it-asks; AI as a quality setting (render once,
store). Gone: the database is the bones; The Treatment assembles them;
no separate cell-grid. The (*) handle survives as the pop-up + copy. The
QUIET NOTE was settled here and SURVIVES (now the board's and pop-up's
grammar). The 3 June four-level tag list and the column-board study
mockups are history.

1–2 JUNE — VERTICAL BOARD / SHUTTER / FUSION (SUPERSEDED 4 June): the
DCW as a vertical board (scenes down a left spine, TRACKS as columns,
stave dividers, chevron headers); THE SHUTTER (DCW + WP as one manuscript
divided by a curtain; "Full Screen"); THE FUSION (Float/Pin; the note
CARD as the board object; three track types — Structural cards / Curve /
Ambient; the cascade; the card as the bridge to writing). The PRINCIPLE
that planning and writing are one instrument SURVIVES — now realised as
the FUNNEL (board / WP+wheel / road map). NB 9 June: the board-as-a-look
RETURNS as Plot Mapping reborn — but as the timeline-of-events truth
(six entity tracks, Events feed prose), NOT the old DCW column-board.

MOCKUP / BUILD FILES (history): inkyswot-daw.html (original horizontal
STRIP, superseded 2 June); CODE/dcw-vertical.html (vertical board in the
shutter, superseded); code-map-plotter.html (Plot Mapping corkboard,
30 May — superseded as a build target by the reborn board; kept as
history).

WHAT THE TURNS KILLED (so it is never rebuilt): the horizontal strip;
the old vertical board (tracks as columns / the DCW); the shutter/
curtain; the fused "one manuscript at two distances"; "Full Screen =
shutter to the page side"; the note CARD (tab/knot/full-stop/flip); the
one-screen cell-grid to type into; "Snap to Default" / drag-reorder
tracks / bright-red freeform / Ideas columns / make-your-own tracks; the
writing card "Scene." / Dialogue+Descriptive; the first 4 June inline-gap
click-to-write; the multi-event long-scrolling Treatment page; the
wheel's bloom glow and chevron; separate stave marker labels / blank
stave pages. ALSO (9 June): the Tension needle gauge / flat-line /
plain-text tries.

WHAT SURVIVED (re-fitted to the live model): the QUIET NOTE grammar (the
board's and the pop-up's); the database handle (the pop-up + copy); Dark
Thoughts; the SECTION ? help pill; the FUNNEL idea (now the three views
of one body of data); and the CARRIED features (Tension — now homed as
board curve + WP meter; Emotional Maps; Ambient with Time-as-a-block; the
lift) awaiting full placement.