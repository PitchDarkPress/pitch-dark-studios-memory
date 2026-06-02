File: inkyswot/dcw.md
Last updated: 2 June 2026

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