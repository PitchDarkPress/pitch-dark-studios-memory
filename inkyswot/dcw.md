File: inkyswot/dcw.md
Last updated: 1 June 2026

MOCKUP FILES
inkyswot-daw.html — the original interactive strip mockup.
Live at: https://inkyswot-app.vercel.app/inkyswot-daw.html
Built 1 June 2026 (in-session demonstrations, to be stored in CODE):
- scene-level DCW board (A Christmas Carol) — shows the three track
  types and the story told beat by beat across 37 scenes.
- fusion trial — Plot Mapper note cards sitting on the DCW board.
These are demonstrations of the fused thinking, not the build target.

WHAT THE DCW IS
The Digital Creative Workstation. InkySwot's owned term.
Equivalent to a DAW in music production. Said as three letters: D.C.W.
It is a persistent strip below the three main panels, above the footer.
Always present. Toggleable. Not a screen the writer navigates to.
When rivals copy InkySwot they will be labelled
'just another DCW ripoff.'

PLATFORM POSITION
Sits below: top menu / left sidebar / main work area / right panel.
Sits above: footer menu.
Full width across all three panels.
Toggleable — slides up to reveal, slides down to hide.
Toggle control in the top menu.
(The strip stays. Kev has ideas for it — do not change to a full
top-down screen.)

THE FUSION — DCW × PLOT MAPPER (1 June 2026)
The Plot Mapper and the DCW are ONE instrument, not two screens.
They are two states of the same board:
- FLOAT — the corkboard. Notes dragged anywhere, threads pulled
  between them, thinking before the order is fixed.
- PIN — the timeline. Drag a note onto a chapter and it snaps to a
  track, ordered. Same note, same gesture: scatter → arrange → pin.
The thing that lives on the board is the Plot Mapper NOTE CARD.
On the timeline, a card pinned to a track is what we used to call a
"block". Block and card are the same object.
The full card mechanics — note types, the type tab with its full-stop,
flip-to-back DARK THOUGHTS, drag-to-connect threads, the copy system
("n of n"), the chapter dividers, and the lift (Prologue/Backstory
below Chapter 1) — are specced under PLOT MAPPING in
locked-decisions.md and carry forward unchanged.

THREE TRACK TYPES
Tracks are called TRACKS throughout the UI. There are three families.

TYPE 1 — STRUCTURAL (block-based: what happens, who is in it)
Character — one per character. Where they are active.
Plot — the main plot arc across chapters.
Subplot — secondary story threads.
Location — where the story is set, chapter by chapter.
Event — key story events pinned to chapters.
Object — significant objects and their journey.
Theme — thematic threads across the story.
Notes — private notes pinned to chapters. Never exported.
Cards on these tracks carry the matching note type. Free Note cards
float (corkboard thinking) until pinned.

TYPE 2 — CURVE (a continuous line, not blocks)
Tension — the tension curve (three modes, below).
Emotional Maps — per-character emotion curves (below).

TYPE 3 — AMBIENT / WORLD (block-based: what the world is doing)
Atmosphere — scene mood across chapters (cold / warm / dread / joy).
Weather — what the sky is doing.
Time — story-time.
TIME IS A BLOCK, not a ruler mode. The horizontal axis is fixed
READING ORDER and only ever runs forward. Time blocks declare
STORY-TIME, which can leap anywhere — so a single chapter can hold
several Time blocks (present / past / future) to show a flashback or
intercut timeline. Separating the two clocks is the insight; it is
what no rival tool does.
(Note: Atmosphere as scene-mood sits close to the Emotional Maps and
to the Buildings "Atmosphere" database field. A DCW Atmosphere track
means scene mood across chapters — keep it distinct from both.)

CARDS ON THE TIMELINE
Each card spans one or more chapters. Colour coded to its track.
The front shows the beat; click the tab to flip to DARK THOUGHTS.
Click to select (gold outline). Hover shows a tooltip.
Gaps and clusters tell the story — where a card is absent, that
character or thread is off the page.

CARDS HOLD TEXT
A card is not just a label that points at writing kept elsewhere.
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
Plan a card loose (float) → pin it to a track and chapter →
open it and write the scene inside it.
The Write screen (Step 10) is the DCW opened all the way down to one
card, in focus. Same manuscript, two distances. Reconcile the Write
screen spec with this when it is written.

THE WRITING CARD — THE KEYSTONE (provisional)
Every other note type DESCRIBES the story. One type CONTAINS it —
the card the writer actually writes in. It is mostly body: the front
carries just enough to know it at a glance (title, a line of synopsis,
word count); open it and you are writing.
Working name: "Scene." — NOT yet locked.

TENSION CURVE — THREE MODES
Runs as an SVG curve across the full timeline. A continuous line, not
blocks. Draggable points at each chapter position.
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

CONNECTIONS
Every card connects to the world database.
Highlight text in the main work area — option to pin to the timeline.
An entity tagged in the manuscript appears on its relevant track.
(Open: with cards carrying their own front and back, whether a
separate right-hand detail panel is still needed — see OPEN.)

TOGGLE STATES
DCW hidden — full height for the three panels. Default on open.
DCW visible — strips height from the panels. Slides up from the bottom.
DCW expanded — takes more vertical space for detailed work.
Toggle control: single button in the top menu.

LAYOUT
Ruler — chapters run left to right across the top. Each chapter shows
a label and a status colour bar (Draft / Revised / Final / Planned /
None). The ruler is reading order and stays fixed.
Track headers — left column, fixed width. Each shows colour bar /
name / type / Hide and Lock buttons.
Track content — scrolls horizontally with the ruler.
Minimap — compressed overview at the bottom; viewport indicator shows
scroll position.
Zoom — + and − expand or compress the timeline (the cascade control).

ADD TRACK
Add Track button in the left sidebar of the DCW. Grouped by type:
Structural — Character / Plot / Subplot / Location / Event / Object /
  Theme / Notes.
Curve — Tension / Emotional Map.
Ambient — Atmosphere / Weather / Time.

VIEWS
Full Story — all tracks, all chapters.
By Character — character tracks only.
By Chapter — all tracks, single chapter focused.
Print View — exportable overview.

WHAT THE DCW IS NOT
Not a screen the writer navigates to — it is a strip.
Not a separate mode that replaces the workspace.
Not optional in the long term — it is the platform's defining feature
and must always be present.

OPEN — NOT YET DECIDED
Card fields: the per-type fields shown on the FRONT of each note card.
Writing card: its final name (working name "Scene.").
Right-hand panel: whether the separate entity detail panel survives
the fusion, or the card's own front/back makes it redundant.
Note range: whether a card can span a chapter range (e.g. Ch.3–Ch.9)
in addition to the copy-per-chapter system.
Build sequencing: Plot Mapping was to fold into index.html early and
the DCW at Step 13 — the fusion converges them. Reconcile in
build-list.md.

BUILD ORDER
Step 13. Needs The Treatment (Step 11) in place first.
Original mockup (inkyswot-daw.html) already built.
At Step 13: the fused strip — three track types, cards (with text and
the cascade), all three tension modes, all Emotional Map types per
character, toggleable. Full width.