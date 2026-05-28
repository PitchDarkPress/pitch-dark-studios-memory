File: inkyswot/dcw.md

InkySwot — DCW Specification
Last updated: 28 May 2026

MOCKUP FILE
inkyswot-daw.html — fully working interactive mockup.
Live at: https://inkyswot-app.vercel.app/inkyswot-daw.html
Built and ready to integrate at Step 13.

WHAT THE DCW IS
The Digital Creative Workstation. InkySwot's owned term.
Equivalent to DAW in music production.
Said as three letters: D.C.W.
The DCW is not a screen the writer navigates to.
It is a persistent strip below the three main panels,
above the footer. Always present. Toggleable.
When rivals copy InkySwot they will be labelled
'just another DCW ripoff.'

PLATFORM POSITION
Sits below: top menu / left sidebar / main work area / right panel.
Sits above: footer menu.
Full width across all three panels.
Toggleable — slides up to reveal, slides down to hide.
Toggle control in the top menu.

LAYOUT
Ruler — chapters run left to right across the top.
Each chapter shows: label / status colour bar.
Chapter statuses: Draft / Revised / Final / Planned / None.
Track headers — left column, fixed width.
Each track shows: colour bar / name / type / Hide and Lock buttons.
Track content — scrollable horizontally with the ruler.
Minimap — compressed overview at the bottom of the DCW.
Shows all tracks and blocks at a glance.
Viewport indicator shows current scroll position.
Zoom controls — + and − to expand or compress the timeline.

TRACK TYPES
Character Track — one per character. Blocks show
scenes and moments where character is active.
Plot Track — main plot arc across chapters.
Subplot Track — secondary story threads.
Location Track — where the story is set chapter by chapter.
Event Track — key story events pinned to chapters.
Object Track — significant objects and their journey.
Theme Track — thematic threads across the story.
Tension Track — the tension curve (see below). Not blocks.
Notes Track — private notes pinned to chapters. Never exported.

BLOCKS
Each block spans one or more chapters.
Colour coded to its track.
Label shows scene or moment name.
Click to select. Selected block shows gold outline.
Click to open detail in right panel.
Hover shows tooltip with block label.

TENSION CURVE — THREE MODES
The tension curve is the standout feature.
Runs as an SVG curve across the full timeline.
Not blocks — a continuous line showing tension level.
Draggable points at each chapter position.

Mode 1 — Manual
Writer drags the curve themselves.
Full creative control. Their instinct, their shape.
The plan for where tension should be.

Mode 2 — AI-Guided
Writer draws where they want tension to go.
Ada compares the target curve to the actual text.
Ada advises specifically how to achieve the target tension
at each point — scene suggestions, pacing notes, structural advice.
Based entirely on the writer's own text and world.

Mode 3 — Analysis
Ada reads the written text and plots the curve automatically.
Shows the story's actual tension shape as it currently stands.
Writer sees the real shape of their story, not the imagined one.
Reveals flat sections, missing peaks, unearned climaxes.

All three modes can be used together.
Manual sets the target. Analysis shows the reality.
AI-Guided bridges the gap.

EMOTIONAL MAPS
The Emotional Maps are the DCW's second defining feature.
Developed 28 May 2026.

What they are:
Each Map is a continuous curve — like the tension curve —
that tracks the rise and fall of a single emotion belonging
to a single character, across the chapters of the story.

The word Map is deliberate.
It names the line now.
It leaves the door open for a full cartographic
emotional view of a character in a later version.

How they work:
Each character can have multiple Maps assigned to them.
Each Map tracks one emotion — Love, Hate, Despair,
Breaking Point, Fear, Trust, or any emotion the writer names.
Maps are colour coded. Each emotion has its own colour.
Multiple Maps run simultaneously across the timeline —
like instruments in a score, playing at once.
The writer toggles individual Maps on and off.
Maps can be viewed per character or overlaid across
multiple characters simultaneously.
In practice a writer will typically have two or three
Maps active at any one time — the ones relevant to
the scene or chapter they are working on.
The toggle system is designed for this. All Maps are
available. None are forced on. The writer composes
their own view.

Why they matter:
Eleanor's Love Map running against Margaret's Hate Map
shows exactly where they intersect, diverge, peak and collapse.
The writer sees the emotional score of the entire story —
not just what happens, but how it feels, chapter by chapter.
Flat sections, missing emotional beats, unearned resolutions
all become visible in the shape of the lines.

Named examples:
Eleanor's Love Map
Margaret's Hate Map
Henry's Despair Map
Eleanor's Breaking Point Map

The system:
Add Map button in the character's track header.
Select emotion from a list or type a custom emotion.
Draggable points at each chapter position — same as tension curve.
Ada can analyse the written text and plot a Map automatically
(Analysis mode — same three modes as the tension curve).
Maps are saved per character per project.

The music analogy:
The DCW is a DAW for story.
The Emotional Maps are the instruments.
Each character is a voice in the score.
The writer is the composer.

FUTURE — EMOTIONAL MAP AS LITERAL MAP
The word Map was chosen with intention.
In a future version, an Emotional Map may expand
into a full cartographic view — a visual landscape
of a character's emotional journey through the story.
High ground for intensity. Low ground for numbness.
Rivers for flow. Storms for crisis.
This is not on the current build list.
It is the destination the word points toward.

CONNECTIONS
Every block connects to the world database.
Click a character block — character detail opens in right panel.
Click a location block — location detail opens in right panel.
Highlight text in main work area — option to pin to timeline.
Entity tagged in manuscript — automatically appears on relevant track.

TOGGLE STATES
DCW hidden — full height for three panels. Default on open.
DCW visible — strips height from panels. Slides up from bottom.
DCW expanded — takes more vertical space for detailed work.
Toggle control: single button in top menu.

ADD TRACK
Add Track button in left sidebar of DCW.
Dropdown: Character / Plot / Subplot / Location /
Event / Object / Theme / Tension / Notes.

VIEWS
Full Story — all tracks, all chapters.
By Character — character tracks only.
By Chapter — all tracks, single chapter focused.
Print View — exportable overview.

WHAT THE DCW IS NOT
Not a screen the writer navigates to.
Not a separate mode that replaces the workspace.
Not optional in the long term — it is the platform's
defining feature and must always be present.

BUILD ORDER
Step 13. Needs The Treatment (Step 11) in place first.
Mockup (inkyswot-daw.html) already built — integrate at Step 13.
Tension curve full build at Step 13.
Emotional Maps full build at Step 13.
Full width. All track types. All three tension modes.
All Emotional Map types. Per character. Toggleable.