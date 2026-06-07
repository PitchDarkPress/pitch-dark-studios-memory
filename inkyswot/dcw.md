File: inkyswot/dcw.md
Last updated: 7 June 2026

================================================================
READ FIRST — THIS IS THE LIVE SPEC.
InkySwot IS the DCW. The Treatment is the DCW switched on — a TIMELINE
OF EVENTS assembled from the database, written by filling in the blanks.
The writer navigates AND writes by THE WHEEL. Everything from the LIVE
SPEC heading down to "================ HISTORY" is current and buildable.
Everything below "HISTORY" (the one-screen X-ray, the vertical board,
the shutter, the fusion, the card model) is SUPERSEDED — kept only as
the record of how we got here. Do NOT build from the history.

7 JUNE 2026 UPDATE: the wheel was heavily refined across 6–7 June. The
WHEEL section below now describes the wheel AS BUILT in the current
mockup, which differs in several ways from the original 4 June spec
(noted inline). The code is the truth; this file follows it.
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
  REACHED INTO by the events that use them (via the pop-up).
- This answers the old "what is a row?" knot: the line is made of
  events, not of everything.
- Chapters and Scenes are the dividers. A SCENE is labelled "Scene 1",
  "Scene 2"… with an optional title ("Scene 1 — The Counting-House").
  Events live under their scene.

FILL IN THE BLANKS — THE DESIGN PRINCIPLE
The Treatment assembles itself from everything in the database — not
just names, the SUBSTANCE — and leaves the writer the blanks: the prose
and dialogue no database can hold. The writer is never facing a blank
page; they face a page three-quarters built, with holes shaped exactly
like the writing only they can do. The sections are not reference
material off to one side — assembled, they ARE the draft; the writing
is the last layer, not the first.

----------------------------------------------------------------
THE PAGE — ONE SCENE PER FULL PAGE (settled 6 June 2026)
----------------------------------------------------------------
This is the big structural change of 6 June. The Treatment is no longer
one long scrolling document of stacked staves/scenes/events. Instead:

- ONE SCENE PER FULL PAGE. Each scene sits on its OWN full US-Letter
  sheet (816 × 1056px). The old multi-event page (several scenes and
  many events stacked on one long page) is GONE — it felt "too busy"
  and made the wheel track too many close points.
- PAGES ARE ALWAYS FULL HEIGHT. A short scene leaves white space below
  it — that white space is simply the rest of the sheet, exactly like a
  real document page. Pages are NEVER shrunk to hug their content.
  (Kev: the small mockup that hugged a scene was just a sketch; the
  real thing is always a full page.)
- STAVE HEADING ON EVERY PAGE. The stave/chapter heading (.ch-h) shows
  at the TOP of every scene page, for navigation — so the writer always
  knows which stave they are in. It is not limited to the page where
  the stave opens.
- ON A PAGE: running head top-right ("A Christmas Carol by Charles
  Dickens"), then the stave heading (mono caps, ruled under), then the
  scene heading ("Scene 1 — The Counting-House"), then the event(s)
  with a "— click to write this scene —" line beneath each.
- WHY: a page that holds ONE thing reads like a manuscript, not a
  dashboard. The calm of the page and the calm of the wheel are the
  same calm — fewer points for the wheel to track, so it moves at an
  unhurried pace.

----------------------------------------------------------------
THE WHEEL — HOW THE WRITER NAVIGATES AND WRITES
(settled 4 June; heavily refined 6–7 June — this is AS BUILT)
----------------------------------------------------------------
The old "click-to-write" decision (inline-grow vs focused surface) is
RESOLVED — the answer is a WHEEL. This is the heart of the writing
experience.

THE LAYOUT
- The WP / Treatment page sits SHIFTED TO THE RIGHT of the dark
  workspace.
- The LEFT of the workspace is RESERVED for the entity POP-UP note
  (draggable, stable; spec below). Not yet built into the wheel mockup.
- A 230px right sidebar sits at the far right (purpose TBD). The wheel
  lives in the dark CHANNEL between the WP's right edge and that right
  sidebar. Grid is 230px 1fr 230px.
- Out in that channel is THE WHEEL: a single hairline gold RAIL with
  small nodes, and section labels to the right of the rail. A fixed
  gold CENTRE marks where you are.

THE LABELS — TWO LINES EACH (settled 7 June 2026)
This REPLACES the original single-line uniform labels. Every wheel
label is now TWO LINES:
- A small KICKER line in gold JetBrains Mono caps, e.g.
  "STAVE ONE — SCENE ONE" — telling you the exact position.
- The SCENE TITLE beneath it in Crimson Pro, e.g. "The Counting-House".
So every label carries its full stave+scene position. There are NO
separate stave marker labels and NO blank stave pages — the stave is
NAMED ON EVERY SCENE via the kicker. (We tried separate stave rail-
points and rejected them: they forced a blank stave page and didn't
read right. The two-line label is the resolution.)
The stave/scene numbers are computed in JS from a data-stave-open="1"
attribute on each stave's FIRST page; a counter increments the stave and
resets the scene number at each stave open.

THE MECHANISM (as built)
- Scrolling the PAGE turns the wheel (page-scroll driven, NOT wheel-
  scroll). Whatever label sits on the fixed centre is WHERE YOU ARE.
- THE CENTRE MARK: a gold RING (17px, 2px border) with a filled gold
  dot, plus a short gold LEADER line running from the ring toward the
  centre label. The centre label's TITLE lights gold. The centre node
  itself is hidden (the ring replaces it).
  REMOVED 6 June: the radial BLOOM glow and the » CHEVRON — "how many
  times do we want to point at something." The ring + dot + leader is
  the whole centre furniture now.
- THE WINDOW: nine labels each side of centre are shown (WINDOW=9), so
  the wheel is a real MAP of the book using the full page height — not
  the original ~3. Labels fade in/out at the edges so the wheel stays
  calm however long the book is.
- THE FADE: an even, gentle fade across the window with a brightness
  FLOOR so outer labels stay readable; the centre and the two labels
  either side of it are at full brightness, the rest dimmed to ~71%.
  Label text colour is uniform white/ink (an earlier per-distance dim
  on the text was dropped in favour of opacity only).
- HOVER: hovering a label lights ONLY its NODE gold. The TEXT does NOT
  change on hover. (Important to Kev — no text highlight on hover at
  all.) Clicking a label navigates to it.
- THE MOTION: eased and slow — glides toward target, does not snap 1:1
  to scroll. Glide/ease rate 0.072. Row spacing TIGHT=46, centre gap
  GAP=64.
- THE LIVE HAND-OFF IS SMOOTHED: a 0.35s CSS transition on the label
  text (colour/weight/opacity) so as one label reaches centre and
  another leaves, the gold eases in and out rather than snapping.
- THE BOW: a very slight outward curve of the belt (centre furthest
  right, labels stepping back toward the rail) was tried and LIKED as a
  "felt not seen" wheel cue — then REMOVED (BOW=0) because the two-line
  labels ran together on the curve. The belt is now STRAIGHT. (If the
  bow is ever wanted again, it cannot be at the expense of two-line
  legibility.)
- positionWheel() centres the wheel block live in the channel at any
  screen width; labels wrap to roughly half the channel width.

TWO STATES — OVERVIEW AND WRITING MODE
- OVERVIEW: the assembled Treatment shows (one scene per page); the
  wheel turns with the scroll; centre = where you are. Click a wheel
  label to go to that scene. Click the CENTRE label (or a
  "— click to write this scene —" on the page) to enter Writing Mode.
- WRITING MODE: the page opens CLEAN for that one scene — scene line +
  event title near the top, then the whole page given to a full-height
  writing area. The wheel stays lit beside you, locked with that scene
  at centre. Click any wheel label to open THAT scene to write — the
  writer travels scene-to-scene BY THE WHEEL without leaving Writing
  Mode. Each scene's text is remembered (drafts{} keyed by index).
- A "‹ overview" control (top-right, shown only in Writing Mode)
  returns to the assembled Treatment.

THE PRINCIPLE
The writing position and the map position are the SAME thing. The
writer writes at the centre; the wheel always shows what has been
passed (above), where you are (centre), and what is coming (below).
The writer never leaves the writing to move about the book.

>>> OPEN BUG — FIRST THING TO FIX NEXT SESSION (7 June) <<<
Clicking a scene label on the wheel (and opening a scene generally)
leaves the TOP OF THE PAGE CUT OFF above the fold — the page is sitting
too high, so the running head / stave heading / scene line are clipped.
Kev showed a screenshot of the CORRECT look: the page top sitting just
below the header bar, reading from the top down.
WHAT WE TRIED (not yet working): a rollToTop(target) function that
lands the sheet's top a small offset below the header (offset tried at
−28, −16; behavior:'auto'); pointed both the wheel-label click and the
writing-open at it instead of the old rollToCentre (which centres the
page's MIDPOINT on screen and therefore clips the top of a full-height
page). For writing-open we wait two requestAnimationFrames before
scrolling because applying body.writing changes .stage padding
(40vh → 34px) and hides page content, throwing off the measurement.
STILL CUTTING OFF. This is the FIRST thing to look at next session.
Likely needs: measure AFTER layout settles, or compute the offset from
the actual sheet top rather than a fixed number, and make sure no
competing smooth-scroll is running. Get a fresh screenshot from Kev of
exactly what's clipped.

THE WHEEL MOCKUP (the LIVE DESIGN SOURCE)
Built on "A Christmas Carol", whole book loaded: 5 staves, 25 scenes,
25 full pages. This is the live design source for the wheel + page.
STORE + INDEX the latest in the CODE locker, superseding earlier wheel
mockups. METHOD NOTE: built static-first then animated; designing motion
by description alone failed repeatedly (now a working rule). LESSON
(re-confirmed 6 June): if edits stop showing on screen, do a CLEAN
REBUILD in a fresh artifact — the display freezes on old versions. This
bit us twice across these sessions.

CARRIED / STILL OPEN ON THE WHEEL (small)
- The entity POP-UP note on the LEFT is not yet built into the mockup;
  the space is reserved.
- Tier styling beyond the kicker: currently the kicker line does the
  job of distinguishing position; no further per-tier styling.
- The 230px right sidebar still has no defined purpose.

----------------------------------------------------------------
HOW THE WORLD IS REACHED — THE ENTITY POP-UP (settled 4 June)
----------------------------------------------------------------
The writer reaches the database WITHOUT leaving the page, via a stable,
draggable pop-up panel. It LIVES ON THE LEFT (the page having moved
right to make room). Present in the wheel mockup and working.
- TWO STEPS from the NAV. Each nav section shows a live COUNT
  (Characters · 5, Locations · 3, Factions · 0; zero greyed). Click a
  section → a LIST of names pops up → click a name → that record opens.
  A "‹ back to list" link steps back. (A search box on the list is a
  natural future touch — not yet built.)
- STABLE: click to open, click (✕) to close. Does NOT vanish on
  click-away; does NOT close when you select text inside it — so
  copy-and-paste is easy. DRAGGABLE: grab the header, move it clear of
  the prose; it stays where put.
- QUIET-NOTE GRAMMAR throughout (list, entries, kicker, back link):
  each entry is a SUB-TITLE in the SECTION's colour, a DESCRIPTION in
  neutral ink beneath, closed by a SOLID end-line in the section
  colour. Characters read gold; Locations read teal; each section its
  own colour. Colour = wayfinding.
- RECORD VIEW: per-field rows, each with a small COPY button (turns
  "copied" briefly), section-colour dividers between fields, a section-
  colour end-line.
- COPY AND PASTE is how database substance reaches the WP (Kev's call —
  honest, learnable, unbreakable; the writer stays in charge). Copy
  takes TEXT ONLY: coloured in the pop-up, it lands in the WP PLAIN,
  taking the page's own ink. Colour for FINDING in the panel; neutral
  ink for READING on the page.
NB: the QUIET NOTE grammar and the database "handle" both survive from
the old card/(*) model — they now live here, in the pop-up.

----------------------------------------------------------------
THE WP — A REAL DOCUMENT PAGE (settled 4 June; refined 6 June)
----------------------------------------------------------------
The main work area / The Treatment is a proper document page (US Letter,
816 × 1056px, generous margins), on the dark workspace with a page
shadow — not a thin panel. Shifted RIGHT (pop-up left, wheel right).
Now ONE SCENE PER PAGE (see THE PAGE above).
- Running head: small Crimson Pro line top-right ("A Christmas Carol by
  Charles Dickens"), muted grey. (The big centred Playfair title block
  was removed 6 June.)
- Stave heading: JetBrains Mono 13px uppercase, weight 500, ruled under
  — matter-of-fact, "information not a style effect."
- Scene heading: JetBrains Mono 11px uppercase mute + optional italic
  Crimson Pro title, or "+ add a title".
- Writing area (.ws-area): Crimson Pro 18px, line-height 1.5.
- MAGNIFY (zoom): a − / 100% / + control scales the whole document
  (70%–200%). It is ZOOM, not page-width — the page shape never changes.
  (Specced; not the focus of the wheel mockup.)
- PAGE NUMBERS centred at the foot; optional UNNUMBERED TITLE PAGE with
  toggle; title + author pull from Overview. (Specced.)
- SCROLLBARS: slim, dark, gold-on-hover. No Windows defaults.
- NOTE: pages are fixed-height sheets in the mockup. REAL pagination
  (prose flowing and breaking onto new numbered pages as you write) is
  a bigger build, for when the writing surface is real. Kev understands.

----------------------------------------------------------------
THE TAG SET (working list — carried, nothing pruned)
----------------------------------------------------------------
From Kev's working list: Action · Chapter · Character · Emotion ·
Event · Location · Note · Prose · Scene · Time.
Sorted by job:
  SPINE (the timeline)        — Chapter · Scene · Event
  FLESH (the writing)         — Prose · Action · (Dialogue — see NB)
  REFERENCE (via the pop-up)  — Character · Location · Time ·
                                Emotion · Note
OPEN on the tag set:
- Is PROSE the same as ACTION, or distinct? (Working split: Action =
  what they do; Prose = description / narration.) UNDECIDED.
- DIALOGUE is not on Kev's list but a scene can't be written without
  spoken lines — confirm Dialogue's place.
- Is EMOTION a per-beat TAG, or the seed of an Emotional Map (a curve
  over time)? UNDECIDED.

----------------------------------------------------------------
CARRIED FEATURES — STILL LIVE, NOT YET PLACED IN THE WHEEL MODEL
----------------------------------------------------------------
These survive from earlier DCW thinking and are still wanted; HOW they
sit in the timeline-of-events / wheel Treatment is the open work.

TENSION CURVE — THREE MODES (locked 26 May)
A continuous line tracking tension across the story.
- MANUAL — the writer drags the curve; their instinct, their shape.
- AI-GUIDED — the writer draws a target; Ada compares it to the actual
  text and advises how to reach it (scene, pacing, structure), based
  entirely on the writer's own work.
- ANALYSIS — Ada reads the text and plots the real curve automatically,
  revealing flat sections, missing peaks, unearned climaxes.
Used together: Manual sets the target, Analysis shows the reality,
AI-Guided bridges the gap. NB: not yet placed in the wheel model.

EMOTIONAL MAPS (locked 28 May) — the DCW's second defining feature
Each Map is a continuous curve tracking the rise and fall of a single
emotion belonging to a single character across the chapters. The word
Map is deliberate — names the line now, future-proofs a full
cartographic view later.
- Multiple Maps per character (Love, Hate, Despair, Breaking Point,
  Fear, Trust, or any named emotion).
- Colour coded, one colour per emotion; multiple run at once like
  instruments in a score; the writer toggles each on/off.
- Viewable per character or overlaid across several characters.
- Add Map button; pick from a list or type a custom emotion; draggable
  points per chapter; Ada can plot by Analysis (same three modes as
  tension). Saved per character per project.
Why they matter: Eleanor's Love Map against Margaret's Hate Map shows
where they intersect, diverge, peak and collapse — the emotional score
of the whole story. The music analogy: the DCW is a DAW for story; the
Emotional Maps are the instruments; each character is a voice; the
writer is the composer.
FUTURE — EMOTIONAL MAP AS LITERAL MAP: a Map may expand into a full
cartographic view — high ground for intensity, low ground for numbness,
rivers for flow, storms for crisis. Not on the current build list; the
destination the word points toward.

AMBIENT (Atmosphere / Weather / Time)
- ATMOSPHERE — scene mood (cold / warm / dread / joy). Keep distinct
  from the Emotional Maps and from the Buildings "Atmosphere" database
  field.
- WEATHER — what the sky is doing.
- TIME — story-time. TIME IS A BLOCK, not a ruler: reading order runs
  forward, but Time blocks declare STORY-TIME, which can leap anywhere
  — a single chapter can hold several Time blocks (present / past /
  future) for a flashback or intercut timeline. Separating the two
  clocks is the insight no rival tool has. NB: not yet placed.

DARK THOUGHTS — private notes, never exported, never sent to InkySwot.
Marker: a small grey-violet dot (the old red is not reused). Carried.

THE LIFT (Prologue / Backstory below Chapter 1) — locked 30 May under
Plot Mapping. The timeline has a "downstairs": above the line the
chapters climb; below it you descend into the Prologue, then the
Backstories. Carried; re-fit when event-ordering is settled.

THE SECTION ? HELP PILL — carries (every screen, top-right, gold
border; slide-in guide). Template pattern, locked 30 May.

----------------------------------------------------------------
OPEN DECISIONS — STILL TO SETTLE (one at a time)
----------------------------------------------------------------
0. >>> THE PAGE-TOP BUG (see THE WHEEL) — FIRST THING NEXT SESSION. <<<
1. WHERE THE MOOD WORDS LIVE. Chapter/scene mood words (e.g. Cold ·
   Bleak · Biting) were pulled OFF the page; Kev wants them but doesn't
   yet know where they belong. Parked.
2. EVENT ORDER WITHIN A SCENE. Events group by chapter but have no
   sequence within a scene. The spine needs "this before that." (Events
   already store characters[] and location; they lack a POSITION.)
3. TAG SET opens (Prose vs Action; Dialogue's place; Emotion tag vs
   Map) — see THE TAG SET above.
4. WHERE THE CARRIED FEATURES LIVE — tension curve, Emotional Maps,
   Ambient, the lift — in the wheel model.
5. THE 230px RIGHT SIDEBAR — its purpose.
6. PLOT MAPPING beside The Treatment — both are views of one database;
   how the corkboard relates to the Treatment now is open.
7. EVENTS ON THE PAGE — the page now shows the scene's event(s) with a
   "click to write" line. With one-scene-per-page, confirm whether
   multiple events per scene stay listed on the page or collapse.

----------------------------------------------------------------
BUILD ORDER
----------------------------------------------------------------
The writing surface (Step 10), The Treatment (Step 11) and the DCW
(Step 13) are CONVERGING into the WHEEL — likely ONE build. Reconcile
the step list once the wheel is built for real. The wheel mockup is the
current standalone build / live design source.

================================================================
HISTORY — SUPERSEDED. DO NOT BUILD FROM ANY OF THIS.
Kept as the record of how we reached the wheel. In rough reverse order:
the 3 June one-screen X-ray, then (older) the vertical board / shutter /
fusion / card model.
================================================================

--- 3 JUNE 2026 — THE ONE-SCREEN DCW / X-RAY (SUPERSEDED 4 June) ---
Superseded because it was still inventing a NEW authoring surface (a
cell-grid to type into) and towing the old screens behind it. Under the
4 June model the database itself is the bones and The Treatment
assembles them — no separate cell-grid. The (*) handle survives as the
pop-up + copy. Preserved detail:

THE ONE-SCREEN MODEL — THE X-RAY: one screen, the DCW; no separate
Writing Panel, no shutter. X-ray ON = the BONES (structure, tagged note
lines); OFF = the FLESH (prose read straight down). The switch HIDES
tags/scaffolding; it does not call AI. Two ways to throw it: a plain
switch and a WIPE (pure theatre, not load-bearing).

THE DCW GOES LINEAR: a linear top-to-bottom document like a screenplay
— a column of tagged note lines, each a CELL of TAG + CONTENT. Worked
example (DCW ON): Location / Character / Direction / Dialogue / Activity
… each line ending (*). Throw the switch and it becomes prose.

THE KEY INSIGHT — DCW = SCREENPLAY × SPREADSHEET: a spreadsheet is rows
of cells (typed, addressable, easy to read/write/hide/move); a
screenplay is tagged lines (each knows what it is). Together: a column
of rows, each [ TAG | CONTENT | (*)handle ] — a spreadsheet that reads
like a script. Made the ON/OFF trivial (show or hide the tag column)
and bones↔flesh a "doddle" (assemble cells one way; drop text back the
other). Was felt to be the build method.

EACH CELL IS A LIVE HANDLE — THE (*): clicking an entity in a line
opens its database record; a line is a handle into the world. (Survives
as the pop-up + copy.)

WRITE WITH IT OFF, SWITCH ON, IT ASKS: write plain with the DCW off
(discovery writer's door); switch on and it asks what each new piece is
and files it (AI off = asks cold; AI on = Ada suggests). No markup to
learn.

AI IS A QUALITY SETTING, NOT A REQUIREMENT: the flesh exists without
AI; rendering cells → prose works AI-off (templated). RENDER ONCE then
STORE; the switch shows stored text, never calls AI. Two-way editing
(flesh↔bone) the goal; flesh→bone the hard problem.

THE QUIET NOTE (settled 3 June, SURVIVES into the pop-up): no box, no
tab, no knot, no side-stem. A SUB-TITLE in the section/tag colour; a
DESCRIPTION beneath in NEUTRAL ink; a SOLID end-line in the colour
closes it. (Dropped interim steps: dotted side-stem; dotted divider.)
Originally "click a note to expand into a writing surface"; Dark
Thoughts on the back; grey-violet marker.

NAMING / ORDER / FREEFORM (3 June, SUPERSEDED — column-board thinking):
WriterDuet naming model for entity tracks; built-in single tracks whose
type is their name; a MAKE-YOUR-OWN track fixed BRIGHT RED; IDEA = a
free go-anywhere note; RED = FREEFORM; "SNAP TO DEFAULT" the tidy
control. All belonged to the grid-of-columns; not part of the current
model unless re-introduced.

THE NOTE GRAMMAR — THE TAG SET (3 June four-level working list, kept
for reference): STRUCTURE (New Act · End Act · Sequence · Outline ·
Beat); SCENE (Scene · Where · When · Who · What · Mood · Want · Plot ·
Theme · Seed); CONTENT (Action · Dialogue · Parens · Transition · Shot ·
VO/Narrator · Intercut · Montage · Super · SFX · Text · Lyrics · Image);
MARGIN (Note). "Keep everything" then; the current working tag set
(above) is the trimmed live version.

3 JUNE STUDY MOCKUPS (history): quiet-note thumbnail; quiet-note board;
"DCW — as agreed" column-board; expand-to-write study. Built as column
boards — predate the linear turn and the wheel.

--- 1–2 JUNE 2026 — VERTICAL BOARD / SHUTTER / FUSION (SUPERSEDED) ---
The DCW as a VERTICAL board: scenes/chapters down a left sticky spine,
TRACKS as columns across the top, stave dividers, chevron headers,
reading order down and forward. "Why vertical": the page runs down, so
board and page run the same way. No fit-to-screen; opens at natural
size and scrolls.

THE SHUTTER: DCW and Writing Panel as ONE manuscript at two distances,
divided by a CURTAIN that covers/reveals without resizing; WP always on
top; DCW left, WP right; two extremes (pure WP = "Full Screen"; full
board); grab-handle. THE FUNNEL (Kev's image): raw cards = fleece, the
storyline = the funnel, the manuscript = spun yarn; you can unspin and
re-spin; the DCW is a permanent ALTITUDE, not a starter tool.

THE FUSION — DCW × PLOT MAPPER: one instrument in two states — FLOAT
(corkboard, notes dragged anywhere, threads pulled) and PIN (drag a
note onto a chapter/scene, it snaps to a track, ordered). The board
object was the Plot Mapper NOTE CARD; pinned, a card = a "block".

THREE TRACK TYPES (column model):
- STRUCTURAL (note cards): Character / Plot / Subplot / Location /
  Event / Object / Theme / Notes. Card face: coloured type TAB (label +
  full-stop), KNOT circle, bordered body; full-stop RED with Dark
  Thoughts; click to expand into a centred overlay; free notes float.
- CURVE (continuous lines): Tension / Emotional Maps, down their own
  columns.
- AMBIENT / WORLD: Atmosphere / Weather / Time; card furniture but no
  knot/full-stop; Time as a block.

OTHER VERTICAL-BOARD DETAIL (history): the spine (sticky), stave/chapter
divider rows, horizontal chevron track headers; CARDS HOLD TEXT (a card
opens to hold the writing); THE CASCADE (book → chapters → scenes →
words; zoom folds/unfolds both ways; nothing entered twice); THE CARD
IS THE BRIDGE TO WRITING (plan loose → pin → open and write inside);
THE WRITING CARD "Scene." keystone (provisional; possibly split into
DIALOGUE + DESCRIPTIVE for script grammar); FILLING IN THE BLANKS as a
gradient not a mode-wall (no-mode-wall / ghost-prompts / Ada-primes-a-
line — likely layered); THE (*) MARKER with LOUD/QUIET toggle; the
ENTITY PANEL on the right (survived the fusion at the time; the minimap
rail removed); ADD TRACK grouped by type; TRACK CONTROLS wishlist
(reorder, widen/narrow Mixcraft-style, solo, pack tight, undocking,
edit entities in place); VIEWS (Full Story / By Character / By Chapter /
Print View).

MOCKUP / BUILD FILES (history):
- inkyswot-daw.html — the ORIGINAL horizontal STRIP mockup. Superseded
  by the vertical board (2 June). Live at
  https://inkyswot-app.vercel.app/inkyswot-daw.html
- CODE/dcw-vertical.html — the vertical board inside the shutter frame
  (in progress 2 June). Superseded.
- CODE/map-plotter.html — Plot Mapping standalone (30 May). Superseded
  as a build target; kept as history.
In-session demos 1–2 June (vertical board on A Christmas Carol — 37
scenes, 16 tracks, three track types, note-card face) informed the
then-build-target. All superseded by the wheel.

WHAT THE TURNS KILLED (so it is never rebuilt): the horizontal strip;
the vertical board (tracks as columns); the shutter/curtain; the fused
"one manuscript at two distances"; "Full Screen = shutter to the page
side"; the note CARD (tab/knot/full-stop/flip); the one-screen cell-
grid to type into; "Snap to Default"/drag-reorder tracks/bright-red
freeform/Ideas columns/make-your-own tracks; the writing card "Scene."
/ Dialogue+Descriptive; the first 4 June inline-gap click-to-write.
ALSO KILLED (6 June): the multi-event long-scrolling Treatment page
(replaced by one scene per full page); the wheel's bloom glow and
chevron; separate stave marker labels / blank stave pages (replaced by
the two-line kicker label).

WHAT SURVIVED (re-fitted to the live model): the QUIET NOTE grammar
(now the pop-up's); the database handle (now the pop-up + copy); Dark
Thoughts; the SECTION ? help pill; the funnel idea; and the CARRIED
features above (tension curve three modes, Emotional Maps, Ambient with
Time-as-a-block, the lift) — all awaiting placement in the wheel model.