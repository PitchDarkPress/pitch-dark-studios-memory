File: inkyswot/dcw.md
Last updated: 3 June 2026

================================================================
READ FIRST — 3 JUNE 2026: THIS SPEC IS SUPERSEDED (kept as history)
The shutter / fused vertical-board model below is RETIRED. The DCW is
now ONE SCREEN — a linear, screenplay-meets-spreadsheet document with
an on/off X-ray. See the long dated note at the FOOT of this file
("3 JUNE 2026 — THE TURN") and the top of current-state.md. The text
between here and that note is preserved only as the record of how we
got here. Do NOT build from it.
================================================================

MOCKUP / BUILD FILES
inkyswot-daw.html — the ORIGINAL horizontal strip mockup. SUPERSEDED
by the vertical DCW (2 June 2026). Kept only as history.
Live at: https://inkyswot-app.vercel.app/inkyswot-daw.html
CODE/dcw-vertical.html — the CURRENT build target (in progress,
2 June 2026): the vertical DCW board inside the shutter frame, with a
placeholder Writing Panel on the right. Shutter frame signed off;
vertical board in; WP side still placeholder.
In-session demonstrations built 1–2 June (vertical board on
A Christmas Carol — 37 scenes, 16 tracks, three track types, note-card
face on the structural tracks) informed the build target.

WHAT THE DCW IS
The Digital Creative Workstation. InkySwot's owned term.
Equivalent to a DAW in music production. Said as three letters: D.C.W.
It is the platform's defining feature. When rivals copy InkySwot they
will be labelled "just another DCW ripoff."

THE BIG SHAPE — A VERTICAL BOARD (2 June 2026)
The DCW is a VERTICAL board. The horizontal STRIP is RETIRED.
- Scenes / chapters run TOP-TO-BOTTOM down the left spine.
- Tracks are COLUMNS across the top.
- Reading order runs DOWN the spine and only ever runs forward.
WHY VERTICAL: the manuscript page runs down; the old DCW ran across.
Two axes cannot be one thing. Turned vertical, the board and the page
run the same way, side by side, aligned row-by-row — the funnel made
visible. (On 1 June the strip was thought retained and a top-down
screen rejected; on 2 June, to fuse the DCW with the Writing Panel,
the board was turned vertical. The strip is gone.)
No fit-to-screen-by-default — the board opens at natural size and
scrolls. Reading text is large (Crimson Pro); columns are wide.
Magnify/zoom still to be wired (the + / − in the footer — the cascade
altitude control).

THE SHUTTER — DCW AND WRITING PANEL ARE ONE INSTRUMENT (2 June 2026)
The DCW and the Writing Panel are ONE manuscript seen at two distances,
not two tools joined by a bridge. They are divided by a SHUTTER.
- The shutter is a CURTAIN, not a stretcher. It COVERS and REVEALS;
  it does NOT resize either side. Both sides stay full-size underneath;
  only the curtain moves.
- The WP is ALWAYS ON TOP (it is a writing platform). The DCW sits on
  the LEFT; the WP is revealed from the RIGHT.
- TWO EXTREMES: shutter fully to the page side = pure Writing Panel
  (this IS Full Screen — not a separate mode); shutter fully to the
  DCW side = the full board. Everything between is a chosen balance.
- A grab-handle on the shutter keeps it findable at the extremes.
THE FUNNEL (Kev's image): raw cards = fleece; the storyline = the
funnel; the manuscript = spun yarn. Cards are spun into prose as you
move down the storyline; yarn is still wool — you can unspin (move
cards) and re-spin. So the DCW never goes obsolete: it is a permanent
ALTITUDE, not a starter tool, and it shows prose FOLDED so it never
overcrowds — most useful when the book is LONGEST.

THE FUSION — DCW × PLOT MAPPER
The Plot Mapper and the DCW are ONE instrument, not two screens.
They are two states of the same board:
- FLOAT — the corkboard. Notes dragged anywhere, threads pulled
  between them, thinking before the order is fixed.
- PIN — the timeline. Drag a note onto a chapter/scene and it snaps to
  a track, ordered. Same note, same gesture: scatter → arrange → pin.
The thing that lives on the board is the Plot Mapper NOTE CARD.
Pinned to a track, a card is what we used to call a "block". Block and
card are the same object.
The full card mechanics — note types, the type tab with its full-stop,
flip-to-back DARK THOUGHTS, drag-to-connect threads, the copy system
("n of n"), the chapter dividers, and the lift (Prologue/Backstory
below Chapter 1) — are specced under PLOT MAPPING in
locked-decisions.md and carry forward unchanged into the fused tool.

THREE TRACK TYPES
Tracks are called TRACKS throughout the UI. There are three families.

TYPE 1 — STRUCTURAL (note cards: what happens, who is in it)
Character — one per character. Where they are active.
Plot — the main plot arc.
Subplot — secondary story threads.
Location — where the story is set, scene by scene.
Event — key story events.
Object — significant objects and their journey.
Theme — thematic threads.
Notes — private notes. Never exported.
Cards on these tracks carry the Plot Mapper note-card face: a coloured
type TAB across the top (the type label + a full-stop), a KNOT circle,
and a bordered body holding the beat. The full-stop goes RED when the
card has Dark Thoughts. CLICK A CARD TO EXPAND it into a centred
overlay. Free Note cards float (corkboard) until pinned.

TYPE 2 — CURVE (a continuous line, not cards)
Tension — the tension curve (three modes, below).
Emotional Maps — per-character emotion curves (below).
On the vertical board the curves run DOWN their own column (each curve
likely its own narrow column; bulge one way = high, the other = low).

TYPE 3 — AMBIENT / WORLD (what the world is doing)
Atmosphere — scene mood (cold / warm / dread / joy).
Weather — what the sky is doing.
Time — story-time.
Ambient tracks wear CARD FURNITURE (a type tab and a body, tinted with
the track's wash) but NO knot and NO full-stop — the calmer,
non-openable cousin to the structural cards.
TIME IS A BLOCK, not a ruler mode. Vertical reading order is fixed and
only runs forward. Time blocks declare STORY-TIME, which can leap
anywhere — so a single chapter can hold several Time blocks (present /
past / future) for a flashback or intercut timeline. Separating the two
clocks is the insight; it is what no rival tool does.
(Note: keep DCW Atmosphere — scene mood across chapters — distinct from
the Emotional Maps and from the Buildings "Atmosphere" database field.)

THE SPINE, DIVIDERS, HEADERS (vertical board furniture)
SPINE (left column): each scene/chapter cell shows its number and title
in large reading type. Sticky — stays put as the board scrolls sideways.
STAVE / CHAPTER DIVIDERS: full-width separator ROWS across every column,
a line above and below the label — a real divider between sections.
Cards finish cleanly above a divider; the divider sits on top of any
card edge so nothing bleeds through.
TRACK HEADERS (across the top): horizontal, centred over their column,
auto-wrapping (long words hyphenate), each with a downward CHEVRON in
the track colour pointing at its column. (45° angled headers were tried
and rejected once the columns were widened — 2 June.)

CARDS HOLD TEXT
A card is not just a label pointing at writing kept elsewhere.
A card OPENS to hold the writing itself. Closed on the board it is a
beat in context; opened it is a writing surface.

THE CASCADE
Zoom is the main control of the instrument, not a convenience.
Book → chapters → scenes → words.
Zoom out and detail folds up into headline cards.
Zoom in and a card unfolds into its scenes, and a scene into its prose.
It cascades both ways: write at the bottom and it rolls up — the card
fills, the summary updates, the curves redraw. Nothing entered twice.

THE CARD IS THE BRIDGE TO WRITING
Plan a card loose (float) → pin it to a track and scene →
open it and write the scene inside it.
The Write screen (Step 10) is the DCW opened all the way down — the
shutter pushed fully to the page side. Same manuscript, two distances.
Reconcile the Write screen spec and the existing locked Index Card
system with this when the Write spec is written.

THE WRITING CARD — THE KEYSTONE (provisional)
Every other note type DESCRIBES the story. One type CONTAINS it —
the card the writer actually writes in. It is mostly body: the front
carries just enough to know it at a glance (title, a line of synopsis,
word count); open it and you are writing.
Working name: "Scene." — NOT yet locked.
UNRECONCILED (handover, 2 June): script grammar may need TWO writing
note types rather than one —
  DIALOGUE — spoken lines, indented under a character cue.
  DESCRIPTIVE — action / description, set as prose blocks.
The page would lay these in SCRIPT FORM (location = slug line,
description = action block, character = cue, speech = dialogue) as the
COMPOSE view; the format-aware engine then sets them to the final
manuscript style (novel / play / verse) as the OUTPUT. Confirm whether
"Scene." survives as a wrapper or whether Dialogue + Descriptive
replace it outright.

FILLING IN THE BLANKS — THE WRITER TAKING OVER (the seam — unresolved)
The seam where arranging cards becomes WRITING prose must feel like a
GRADIENT, not a mode-wall. Three approaches discussed (likely all
layered, none yet chosen):
(a) NO MODE-WALL — a card is ALREADY editable text; you grow it into
    prose (the cascade opening to its words), not "fill a blank".
(b) GHOST-PROMPTS — an arranged-but-unwritten card shows a faint italic
    shorthand (e.g. [the castle — bleak, cold]); writing it turns it
    solid. The gaps guide, never intimidate. With AI off, the
    ghost-prompts remain the writer's own notes.
(c) ADA PRIMES A LINE — where a card has detail but no prose, Ada lays
    a provisional draft line; writer accepts / rewrites / ignores.
    A primer, not generation — assisted, never instant, writer-led
    (Ada = Step 12).

THE (*) MARKER (handover, 2 June — design intent)
(*) is ALWAYS the thing you click to open a card — one rule, every type.
LOUD / QUIET toggle: loud shows every (*); quiet hides them for clean
reading prose, but entity names stay gently live (gold) underneath.
Open: the way back into a card in quiet mode when (*) is hidden — hover
the name, a keystroke, or click the word. There must be a door even
when the handle is hidden.

TENSION CURVE — THREE MODES
A continuous line, not cards. Draggable points at each scene position.
Runs DOWN its column on the vertical board.
Manual — the writer drags the curve. Their instinct, their shape.
AI-Guided — the writer draws a target; Ada compares it to the actual
text and advises how to reach it (scene, pacing, structure), based
entirely on the writer's own work.
Analysis — Ada reads the text and plots the real curve automatically,
revealing flat sections, missing peaks, unearned climaxes.
Used together: Manual sets the target, Analysis shows the reality,
AI-Guided bridges the gap.

EMOTIONAL MAPS
The DCW's second defining feature (28 May 2026). Each Map is a
continuous curve — like the tension curve — tracking the rise and
fall of a single emotion belonging to a single character across the
chapters. The word Map is deliberate: it names the line now and
future-proofs a full cartographic view later.
How they work:
- Multiple Maps per character. Each tracks one emotion — Love, Hate,
  Despair, Breaking Point, Fear, Trust, or any emotion the writer names.
- Colour coded, one colour per emotion. Multiple Maps run at once,
  like instruments in a score. The writer toggles each on and off.
- Viewable per character or overlaid across several characters.
  Typically two or three active at a time. None forced on.
The system:
- Add Map button in the character's track header.
- Pick an emotion from a list or type a custom one.
- Draggable points per chapter; Ada can plot a Map by Analysis
  (same three modes as the tension curve).
- Saved per character per project.
Why they matter: Eleanor's Love Map against Margaret's Hate Map shows
where they intersect, diverge, peak and collapse — the emotional score
of the whole story, not just what happens but how it feels.
The music analogy: the DCW is a DAW for story; the Emotional Maps are
the instruments; each character is a voice; the writer is the composer.

FUTURE — EMOTIONAL MAP AS LITERAL MAP
The word Map was chosen with intention. In a future version a Map may
expand into a full cartographic view — a landscape of a character's
emotional journey. High ground for intensity, low ground for numbness,
rivers for flow, storms for crisis. Not on the current build list; it
is the destination the word points toward.

CONNECTIONS & THE ENTITY PANEL
Every card connects to the world database.
Highlight text in the writing surface — option to pin to a track.
An entity tagged in the manuscript appears on its relevant track.
THE ENTITY PANEL SURVIVES the fusion (RESOLVED, 2 June): a right-hand
panel shows the selected entity — name, type, arc, relationships,
appears-in, and the AI tools (Auto-fill / Image prompt / Check &
improve). The card's own front/back does NOT make it redundant.
The MINIMAP RAIL is REMOVED.

LAYOUT — VERTICAL BOARD FURNITURE (where the old strip furniture went)
Chapter/scene ruler → down the LEFT spine (sticky).
Track headers → across the TOP (horizontal, centred, chevron beneath).
Entity panel → the right-hand side.
Zoom → unchanged in purpose (the cascade control), now expanding /
compressing the vertical run.
Scrollbars → slim, dark, gold on hover (12px). No Windows defaults.

ADD TRACK
Add Track grouped by type:
Structural — Character / Plot / Subplot / Location / Event / Object /
  Theme / Notes.
Curve — Tension / Emotional Map.
Ambient — Atmosphere / Weather / Time.

TRACK CONTROLS (handover wishlist — not yet built)
Reorder tracks (drag headers) for personal preference (open: keep the
3 types grouped, or allow free interleave).
Widen / narrow tracks (drag column edges), Mixcraft-style — this also
lets narrow tracks compress and working tracks open up.
Possible SOLO control (show only this track) — the DCW has Hide/Lock
but no solo; consider adding.
Pack it Mixcraft-tight — use every pixel.
UNDOCKING — pop the board out into a floating, resizable window without
making it a permanent full screen.
EDIT ENTITIES from within the DCW (the card back or the entity panel),
no need to open the nav.

VIEWS
Full Story — all tracks, all chapters.
By Character — character tracks only.
By Chapter — all tracks, single chapter focused.
Print View — exportable overview.

OPEN — NOT YET DECIDED
Card fields: the per-type fields shown on the FRONT of each note card.
Writing card: its final name (working "Scene.") and whether it becomes
TWO types (Dialogue + Descriptive) — see THE WRITING CARD above.
The planning-to-writing seam: ghost-prompts / Ada primer / no
mode-wall — likely all three layered (see FILLING IN THE BLANKS).
Square the fused model with the existing locked Index Card system and
the Write screen (Step 10).
Magnify/zoom — wire the + / − (the cascade altitude control).
Quiet/loud (*) markers, and the way back into a card when (*) hidden.
Track reorder grouping; solo control; undocking.
Note range: whether a card can span a chapter/scene range (e.g.
Ch.3–Ch.9) in addition to the copy-per-chapter system.
NB (handover): Kev felt a further refinement forming about how cards
transform as you move along the storyline — the funnel + vertical turn
may have captured it; watch for more, an idea may still be uncaught.

BUILD ORDER
Step 13. Needs The Treatment (Step 11) in place first.
The fusion converges the old Plot Mapping fold-in with the DCW step
(reconcile in build-list.md).
At Step 13: the fused vertical DCW + shutter — three track types, cards
(with text and the cascade), all three tension modes, all Emotional Map
types per character, the WP behind the shutter, entity panel, magnify.
Current standalone build: CODE/dcw-vertical.html.


================================================================
3 JUNE 2026 — THE TURN. THE ONE-SCREEN DCW.
(Everything ABOVE this line is now history. This note is the live
direction. Nothing here is LOCKED yet — it is detailed thinking from
the 3 June session, to be confirmed and then folded into a clean
rewrite of this file once the two open decisions are made.)
================================================================

WHY WE TURNED
We spent days trying to make the DCW and the Writing Panel into two
things that MATCH — the shutter, the fused board, the prose-band
reported onto the board. Every version broke, because they were never
two things. The whole knot was self-inflicted: there is nothing to
match if there is only one object. Kev's words: "I am trying to make
them both the same and that can never work." Then, later: "There is
only ONE screen."

THE ONE-SCREEN MODEL — THE X-RAY
There is ONE screen: the DCW. There is no separate Writing Panel, no
shutter, no curtain.
- Think of an X-RAY MACHINE. Switch it ON and you see the BONES — the
  DCW, the structure, the tagged note lines. Switch it OFF and you see
  the FLESH — the prose, read straight down as plain text.
- The switch does NOT produce a second rendering and does NOT call AI.
  OFF simply HIDES the tags and scaffolding; what remains is the text
  already written in the cells. Same one document, lights up or down.
- TWO WAYS to throw the switch: a plain SWITCH, and a WIPE. The wipe is
  pure THEATRE — not load-bearing, only there for the drama of the
  thing. Keep it, but nothing depends on it.

THE DCW GOES LINEAR (the screenplay idea, finally placed right)
The DCW is now a LINEAR, top-to-bottom document — NOT a board of
columns/tracks. It reads like a screenplay: a column of typed note
lines, each line tagged by what it is.
Each line is a CELL the writer fills, in two parts: a TAG + CONTENT.
Worked example (DCW ON — the bones):
  Location    A television studio in New York (*)
  Character   STEVE (*)
  Direction   into headset (*)
  Dialogue    Cut to commercial! NOW! (*)
  Activity    The ON AIR light goes dark. (*)
  Character   JUNIOR REPORTER JESSICA (*)
  Direction   looks at her cell phone, eyes wide. (*)
  Character   JESSICA (*)
  Dialogue    Oh my God. (*)
Throw the switch (or wipe) and all of this becomes PROSE — the same
information, the X-ray off.

★★★ THE KEY INSIGHT — DCW = SCREENPLAY × SPREADSHEET ★★★
(REMINDER TO KEV: expand on this — it is the most important realisation
of the session. It is not just a description, it is the BUILD METHOD.)
The DCW is a cross between a SCREENPLAY and a SPREADSHEET.
- A spreadsheet is rows of CELLS — each cell typed, addressable, easy
  to read, write, hide, move.
- A screenplay is TAGGED LINES — each line knows what it is (slug /
  cue / dialogue / action).
- Put them together: the DCW is a column of ROWS, each row =
  [ TAG | CONTENT | (*)handle ]. A spreadsheet that reads like a script.
WHY THIS MAKES EVERYTHING EASY:
- Building the DCW becomes building a structured list of cells — not a
  bespoke canvas. Ordinary, well-understood, robust.
- The ON/OFF X-ray is just "show the TAG column, or hide it." Trivial.
- The BACK-AND-FORTH (bones↔flesh) becomes a DODDLE:
    bones → flesh = read the cells in order and lay them out.
    flesh → bones = drop the text back into the right cell.
  No clever parser holding the platform up, no AI dependency — it is
  DATA IN CELLS, and cells are the easiest thing in the world to move
  between two views.
This is the thing that makes the whole platform buildable. Expand it.

EACH CELL IS A LIVE HANDLE — THE (*)
The (*) on a line ties it to the world database via the NAV menu.
Click "STEVE" and the Character entry pops up — amend it / add to it —
and it updates everywhere. "A television studio in New York" is a
handle into Locations. A line is not dead text; it is a handle into the
world. A screenplay that KNOWS what everything in it is.
(NB: this likely REPLACES, or absorbs, the old locked Index Card
system and the old "(*) opens a card" marker. To be reconciled.)

WRITE WITH IT OFF, SWITCH ON, IT ASKS
You can write with the DCW OFF — just plain text, no tags, pure flow
(the discovery writer's door). When you switch back ON, the DCW ASKS
what each new piece is, and files it into the right box (Dialogue /
Action / Character / etc).
- AI OFF: it asks cold, line by line — the writer tells it.
- AI ON: Ada makes the asking smarter (suggests "this looks like
  Dialogue"), but is never required.
So both temperaments are served by one instrument: plot-first writers
work with it ON in cells; flow-first writers work with it OFF then sort
on switch-back. No markup to learn.

AI IS A QUALITY SETTING, NOT A REQUIREMENT (and the cost answer)
The flesh must exist WITHOUT AI — switching AI off must never break the
wipe or hide the writer's own book. Therefore:
- The writer writes the flesh; the bones are how it is tagged.
- Rendering cells → laid-out prose works with AI OFF (plain/templated,
  fixed rules). AI ON only makes the prose flow better.
- RENDER ONCE, then STORE the result. The switch/wipe shows stored
  text — it never calls AI, so toggling costs nothing. AI only touches
  a line when that line CHANGES, and only that line.
Two-way editing (edit the flesh → the bone updates; edit the bone →
the flesh updates) is the GOAL. bones→flesh is easy (assembly).
flesh→bones is the known HARD problem (prose is loose; a dumb parser
catches simple edits, only Ada catches a full rephrase). The
spreadsheet-of-cells model is what keeps even this tractable — see the
KEY INSIGHT above.

THE QUIET NOTE — THE VISUAL GRAMMAR OF A NOTE (settled 3 June)
The old CARD (tab, knot, full-stop, bordered body) is DEAD. Replaced by
the QUIET NOTE, then by the linear tagged line — but the quiet-note
grammar is the look that carries through:
- NO box, NO tab, NO knot, NO side-stem.
- The TRACK/TAG decides the type — no separate type label on the note.
- A SUB-TITLE in the track colour.
- A DESCRIPTION beneath it in NEUTRAL ink (so the eye reads sense, not
  colour; the flow of the story stays legible across all notes).
- A SOLID end-line in the track colour closes the note.
- (Interim steps tried and dropped: a dotted side-stem; a dotted
  divider between sub-title and description. Both removed — the solid
  end-line is all the closure needed.)
- CLICK a note to EXPAND it into a writing surface — the note opens up
  and you write the prose INSIDE it. The note becomes the page. (This
  is the live mechanism: "the notes expand to be written in.")
- DARK THOUGHTS live on the BACK — flip to a private panel, never
  exported, never sent to InkySwot.
- DARK-THOUGHTS MARKER: a small GREY-VIOLET dot by the sub-title.
  Red can NOT be reused for this — red now means FREEFORM (see below).

NAMING, ORDER, FREEFORM (settled 3 June)
- ENTITY tracks (Character / Location / Emotional Map): the WriterDuet
  model — FIRST use ASKS for the name; AFTER that a DROPDOWN of names
  already used PLUS a field to type a new one. The dropdown is the
  running record; naming a track is what adds it to the list.
- BUILT-IN single tracks (Plot / Tension / Atmosphere / Weather /
  Time): the type IS the name. Fixed. No renaming.
- MAKE-YOUR-OWN track: the writer names it and can RENAME it later, but
  the COLOUR is fixed BRIGHT RED. There is ONE make-your-own-track
  tool; an "Ideas column" is simply its most obvious use.
- IDEA = the free, type-less, GO-ANYWHERE note. Drops into any column.
  Can be gathered into a make-your-own column if the writer wants.
- RED = FREEFORM (Ideas + make-your-own tracks). "This one's yours, off
  the grid." NB: bright red sits close to the locked Danger red
  (#c43a2a) — consider a distinct shade so red ≠ warning.
- "SNAP TO DEFAULT" — the tidy control. (Named by Kev; "drag-to-
  reorder" rejected as ugly mechanic-speak; "Tidy"/"Reset"/"Realign"
  also considered.) Default track order was Structural · Curve ·
  Ambient, left to right, with free reordering after. NB: this whole
  reorder/Snap-to-Default idea was settled while the DCW was still a
  GRID OF COLUMNS. Under the new LINEAR model it must be RE-TESTED — it
  may not survive in the same form. See OPEN DECISIONS.

THE NOTE GRAMMAR — THE TAG SET (working list, nothing pruned yet)
Built from Kev's screenplay-element list merged with the scene-grammar
list. The two lists barely overlapped (only Character and Note were
shared) — proof they are the two ENDS of the bridge: Kev's list is
mostly CONTENT (what you write); the grammar list is mostly STRUCTURE +
SCENE (what you plot); the SCENE band is the plank that joins them.
Four levels:
  STRUCTURE — New Act · End Act · Sequence · Outline · Beat
  SCENE     — Scene · Where (Location) · When (Time) ·
              Who (Character / POV) · What (the beat) · Mood
              (Atmosphere) · Want · Plot · Theme · Seed
  CONTENT   — Action · Dialogue · Parens · Transition · Shot ·
              Voice Over / Narrator · Intercut · Montage · Super ·
              SFX · Text · Lyrics · Image
  MARGIN    — Note
Each SCENE/STRUCTURE tag corresponds to what used to be a "track".
"KEEP EVERYTHING" for now — edit/prune only when using it shows what is
dead weight. These tags ARE the structural shorthand the writer plots
in (DCW on) and that render to prose (DCW off).

WHAT THE TURN KILLS (history — do NOT build from the spec above)
- The horizontal STRIP and the VERTICAL board (tracks as columns).
- The SHUTTER (curtain covering/revealing DCW vs WP).
- The fused "one manuscript seen at two distances" model + the
  prose-band reported onto the board.
- Full Screen defined as "shutter pushed to the page side" (redefine
  under the one-screen model — e.g. DCW off + chrome hidden).
- The note CARD (type tab, knot, full-stop, flip-from-tab).
- CODE/dcw-vertical.html and CODE/map-plotter.html as BUILD TARGETS
  (kept only as history).
SURVIVES, to be re-fitted to the linear model:
- Tension curve (three modes), Emotional Maps, Ambient (Atmosphere /
  Weather / Time, Time as a block), the lift (Prologue/Backstory below
  Ch.1), the (*) database handle, the SECTION ? help pill, Dark
  Thoughts, the funnel idea (raw → spun → can unspin). HOW these live
  in a linear, on/off document is exactly what needs working out.

STUDY MOCKUPS BUILT 3 JUNE (studies of the new thinking, not agreed
builds; store + index in the CODE locker when confirmed):
- quiet-note thumbnail (the final note grammar).
- quiet-note board (Plot / Dialogue / Character, colour at the margin).
- "DCW — as agreed" board: quiet notes, default family order, drag to
  reorder, Snap to Default, Ideas + freeform red, curves, ambient,
  stave dividers, expand-to-write overlay, Dark Thoughts back.
  (NB: built as a column-board — predates the final linear turn.)
- expand-to-write study: a note opening into a writing surface, the
  plan striking through as prose fills, the written face on the board.

OPEN DECISIONS — DO THESE FIRST, NEXT SESSION (one at a time)
1. Does the one-screen DCW REPLACE the Write screen entirely (Step 10 /
   the locked Index Card system) — since "writing" is just the DCW
   switched off — OR do both survive as separate things? UNDECIDED.
2. Lights-OFF result: CLEAN PROSE (cells written as real sentences,
   tags hidden = flowing text) or a STRIPPED SCRIPT (cell content
   stacked, just unlabelled)? This decides how cells want to be
   written. UNDECIDED.
3. Re-test tracks / curves / ambient / Snap-to-Default against the
   LINEAR model — do columns survive at all, or does everything become
   tagged lines?
4. Confirm two-way flesh↔bone scope; flesh→bone is the hard part.
5. Reconcile the (*) live-handle with the old locked Index Card system.
6. Expand the SCREENPLAY × SPREADSHEET insight (the build method).

PROCESS NOTE
locked-decisions.md was deliberately LEFT UNTOUCHED on 3 June — the
turn is an hour old and two big calls are parked; we do not unlock
hard-won decisions or re-lock fresh thinking until the decisions are
actually made. current-state.md was rewritten (turn captured at top,
shutter dumped). This file (dcw.md) keeps its old spec as history with
this note appended; it gets a clean rewrite once decisions 1 and 2 are
settled.