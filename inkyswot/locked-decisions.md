File: inkyswot/locked-decisions.md
Last updated: 15 August 2026 — rewritten WHOLE. Two months of platform
work (the corridor-plus-pockets architecture, the rebuilt sidebar, the
Plot Mapper) had never reached this file, and several June locks now
conflict with what is live. Nothing has been deleted: everything
overtaken has moved to SUPERSEDED LOCKS with its date and the reason.

NOTE ON THIS FILE
Normally add-only. Rewritten whole when a model shift supersedes a block
of locks (4, 7, 9, 11, 17 June; now 15 August). Superseded locks are NOT
deleted — they move to the foot, dated.

WHAT CHANGED ON 15 AUGUST, IN ONE LINE EACH
- The SYNOPSIS SCREEN IS THE PLOT MAPPER, and it is the only one. This
  reverses the 11 June "Plot Mapping dropped" and retires the board.
- SINGLE FILE ARCHITECTURE is gone — the platform is CORRIDOR + POCKETS.
- The SECTION ? pill now opens a MOVABLE WINDOW, not a slide-in panel.
- New house rules on controls that change size.

================================================================
LIVE LOCKED DECISIONS
================================================================

PLATFORM IDENTITY
InkySwot is a writing platform. Not a content generation engine.
Assisted creation. Not instant generation. Non-negotiable.
Tagline: Publish and be damned. Always.
"Publish and be prepared" must never be used.

PROAUTHORISM
Declared human-AI collaboration. The writer's voice is ALWAYS primary.
Ada proposes and assists; she never writes the prose. Every word stays
the writer's to change.

INKYSWOT IS THE DCW
The DCW is not a screen, strip, board or panel. It is the WHOLE
platform. Every section already built is part of the instrument. The
database is the bones of the story. Locked: 4 June 2026.

CORRIDOR PLUS POCKETS — THE ARCHITECTURE — LOCKED (August 2026)
(SUPERSEDES SINGLE FILE ARCHITECTURE — see SUPERSEDED LOCKS.)
- corridor.html is the shared shell: header, sidebar, all shared CSS and
  JavaScript. Pockets drop into it at <!-- POCKET:id --> slots.
- pockets/ holds one HTML file per screen. HTML only, though a pocket may
  carry its own scoped <style> and <script> (the Overview pocket does).
- THE ENCLOSURE, at core/enclosure.html in the memory database: STITCH
  assembles corridor + pockets into index.html; PUBLISH TO LIVE pushes it
  to PitchDarkPress/inkyswot-app; Vercel deploys to app.inkyswot.com.
Private repo: PitchDarkPress/inkyswot-rebuild.

THE PUBLISHING RULE — LOCKED, LEARNED TWICE
WAIT A FULL MINUTE between Stitch and Publish. Publishing twenty seconds
after Stitch reads the PREVIOUS index.html and silently deploys stale
code. Stitch's character count and Publish's character count MUST MATCH
before a hard refresh is trusted. NEVER press Split unless deliberately
re-splitting a whole index.html. NEVER press "ADD SPELL CHECK TO
CORRIDOR" — it pushes an older corridor back over the fix.

THE PLOT MAPPER — THE SYNOPSIS SCREEN IS THE PLOT MAPPER — LOCKED
(15 August 2026)
(SUPERSEDES "PLOT MAPPING — DROPPED" of 11 June and "THE BOARD IS PLOT
MAPPING REBORN" of 9 June — see SUPERSEDED LOCKS.)
Not a screen that feeds a mapper. It IS the mapper. The writer writes the
story down in one continuous piece, breaks it into chapters and scenes,
and names the people, places and things inside it. That is plot mapping.
AND IT IS THE ONLY ONE. Kev: "This is the only one we will be putting
live." The corkboard, the rotated board, the vertical DCW and the
horizontal work area are all out. If a board is ever revived it needs a
DIFFERENT NAME.
Working file: code-plot-mapper-10.html. Not yet a pocket.

F2 IS THE ONE KEY — LOCKED (15 August 2026)
It reads the situation. Bare cursor: Chapter break (1) or Scene break
(2). A phrase highlighted: the SIXTEEN sections of the sidebar. Nothing
appears from highlighting alone — selecting a word to correct it must
never summon a menu.

THE SECTION MENU IS THE SIDEBAR — LOCKED (15 August 2026)
All sixteen sections, in the sidebar's own order, under its four group
headings, in the four family colours, four columns so none is hidden.
The screen you are on is left out of its own list.

CATCHING PART OF A WORD IS ENOUGH — LOCKED (15 August 2026)
Selections grow out to whole words. Precision is NEVER required of the
writer. Kev: "a tired writer would get pissed off damn quick."

A MARK IS A DASHED LINE BENEATH, NEVER A TINTED WORD — LOCKED
(15 August 2026)
The writing stays the writer's; the colour is an annotation on it, the
way a pencil marks a page. Colour is by FAMILY, not by section — four
colours read at a glance, sixteen do not.

THE BREAK — KEV'S DIVIDER — LOCKED (15 August 2026)
A dashed gold hairline through the writing, the "Ch. 1" pill out in a
left gutter, a gold dot at the far end. Scene breaks are the same mark in
pale stone. The same divider is used wherever chapters and scenes are
shown, so the writer learns one mark. A break never falls mid-word.

ADA SITS BESIDE WHAT SHE WORKS ON — LOCKED (15 August 2026)
Prompt and Expand belong ON the chapter or scene line, right-hand end,
and on a card. NEVER floating at the foot of a page with no subject.
AND HER BUTTONS READ THEIR CONTENT: nothing to expand means Expand goes
quiet and says why. A button that cannot work says so rather than
failing when pressed.

ALSO CALLED — ONE CARD, SEVERAL NAMES — LOCKED (15 August 2026)
Mr. Toad is also Toad. The first name is the proper one; the rest are
ways of referring to it. The platform PROPOSES the obvious ones as faint
dashed pills; nothing is ever added behind the writer's back.
A REJECTED SUGGESTION GOES QUIET, NOT AWAY — it stops being offered and
gathers behind a "2 set aside" line. Kev: "being offered something you
have rejected every time you open a card will get very dull very quickly
BUT we need to keep that ability to add a something that you have
rejected." Rejection belongs to that card only.

THE SIDEBAR — LOCKED (11 August 2026, amended 15 August)
(SUPERSEDES THE MENU SPINE's project-nav shape — see SUPERSEDED LOCKS.)
BASICS, then:
  STORY    Plot Threads · Subplots · Themes & Motifs · Events & Timeline
  PEOPLE   Characters · Relationships · Factions & Orgs · Language & Dialogue
  WORLD    Locations · Buildings · Objects & Artefacts · Rules & Lore
  LIBRARY  Research & Reference · Notes · Images · Sandbox
  DCW      Plot Mapper · Manuscript · Publish
Synopsis has gone from Story (15 August) — it was the Plot Mapper under
another name. "Library" has RETURNED as a group heading, having been
dropped in June as too vague.
OPEN: "Basics" vs "Overview" vs "Front Matter". Sandbox should move from
Library to DCW. Group headings should become live rooms — five to build.

THE SECTION ? GUIDE — PLATFORM-WIDE — LOCKED (15 August 2026)
(SUPERSEDES the 30 May slide-in form — see SUPERSEDED LOCKS.)
- EVERY SCREEN carries a SECTION ? pill at the TOP RIGHT of its header,
  gold-bordered, same corner everywhere. A screen with no guide written
  yet still gets the pill and an honest short panel — a pill present on
  some screens and absent on others cannot be trusted.
- IT OPENS A MOVABLE, RESIZABLE WINDOW. Drag by the head, resize by a
  corner grip, close with x or Escape. NO SCRIM — the page stays live so
  the guide can be read while working.
- DO NOT USE CSS resize:both on the window: it makes the panel its own
  layer and the text renders soft. Use a grip, and round every position
  and size to whole pixels.
- ONE LINE PER THING: a gold label, one plain sentence. Kev: "You are not
  writing a 3 act play explaining what everything does. I know how it all
  works and stopped reading it."

CONTROLS DO NOT CHANGE SIZE — LOCKED (15 August 2026)
- A CONTROL THAT CHANGES ITS WORDING MUST NOT CHANGE ITS SIZE. Fixed
  width sized to its longest state, text centred. AI ON/OFF, Light/Dark,
  Budget on/off, More/Less, Indent, Details — and every switch built from
  here. TO BE SWEPT ACROSS THE CORRIDOR when it is next in hand.
- A CONTROL'S SIZE MUST NOT DEPEND ON WHAT IS BESIDE IT.
- OPENING SOMETHING MUST NOT PUSH WHAT IS ABOVE IT.

NEVER NAME A VARIABLE history, name, location, status, top, self or
parent — LOCKED (15 August 2026)
The window already owns them and a top-level var will not override it.
"var history = []" silently killed every action that changed the Plot
Mapper for two days.

WHEN A FAULT SURVIVES ONE FIX, MAKE THE SCREEN SAY WHAT IT DID — LOCKED
(15 August 2026)
Build a version that prints each step to a line on the page rather than
guessing a third time. That is how the history clash was found.

THE DCW IS ONE BODY OF DATA — THE MIXDOWN — LOCKED (16 June 2026)
The DCW is NOT separate screens you move between. It is ONE body of
material seen through OVERLAYS, like a mixdown in music — the tracks
beneath never go away; an overlay RENDERS them together without
destroying them, so going back is free.
THE FUNNEL: SANDBOX (wide, loose) → THE PLOT MAPPER (the same material
divided into chapters and scenes) → THE MANUSCRIPT (one scene, the close
end).
LIVING LINK, BOTH WAYS; NOTHING ENTERED TWICE.
THE KEYSTONE, still open and still the question the platform hangs on:
each overlay's structure must be STORED ON THE SHARED DATA itself, not
inside a view. How one record carries its position, its order and its
chapter/scene home at once. THIS IS STEP TWO OF THE PLOT MAPPER GOING
LIVE — the cards writing into the same store Characters and Locations
read from.

THE TREATMENT IS THE DCW SWITCHED ON
Everything in the database ASSEMBLES into a readable, writable whole. A
plotline is a VIEW of data that already exists, not a new thing to
author. Locked: 4 June 2026.

THE SPINE IS A TIMELINE OF EVENTS
Tiers: CHAPTER → SCENE → EVENT. Only EVENTS sit on the line and become
prose — because only events happen. Characters, Locations, Objects and
the rest do not happen; they are reached into. Locked: 4 June 2026.

THE CUT — WHAT TRANSFERS TO THE MANUSCRIPT — LOCKED (9 June 2026)
- EVENTS + LOCATIONS form the SYNOPSIS content of every chapter and
  scene — the "what happens and where" that becomes prose-bound.
- CHARACTERS · OBJECTS · THEMES · TENSION are related to the scene but do
  NOT pour into prose; they are REACHED INTO, and their home is the SCENE
  MENU on the left of the page.

TEST FOR ANY PLOT MAPPER — LOCKED
Can it produce chapter, scene number, title and summary? If not it is not
a Plot Mapper, whatever else it does well. The Wheel needs all four.

THE MANUSCRIPT — THE CLOSE / WRITING VIEW — LOCKED (16 June 2026)
The close end of the funnel, where the writer completes the book. Earlier
locks saying "WP" or "Writing Panel" refer to THE MANUSCRIPT — the name
changed, the spec did not. The "Manuscript View" comfort toggle lives
within it.

THE SIX TRACK COLOURS — LOCKED (9 June 2026)
  EVENTS gold #c9923a · LOCATIONS teal #5fa898 · CHARACTERS terracotta
  #cf7f57 · OBJECTS steel blue #7a9bd0 · THEMES violet #a07d9a ·
  TENSION red #c45b48
Used for the scene menu, board tracks and the quick-note pin heads.
NB (August): the SIDEBAR groups carry FOUR FAMILY COLOURS — Story
#c9923a, People #cf7f57, World #5fa898, Library #9a8f72 — and these
govern the Plot Mapper's marks and menus. The two sets agree where they
overlap.

SCENES ARE LABELLED, TITLE OPTIONAL
"Scene 1", "Scene 2"… with an optional title. Events live under their
scene. Locked: 4 June 2026.

THE CHAPTER HAS A SYNOPSIS OF ITS OWN — LOCKED (11 June 2026)
The synopsis exists at CHAPTER level as well as scene level. In the Plot
Mapper this is the prose falling between a chapter break and the next
break. On its own page in the Manuscript it is a full sheet in the
scene-page family, sitting before that chapter's first scene.

THE AI PROMPT — PROMPT + EXPAND, SCOPED TO THE SYNOPSIS — LOCKED
(11 June 2026)
- THE SCOPE: the button expands the SYNOPSIS of the scene or chapter —
  NOT the prose. Expanding the synopsis thickens the PLAN; the blank the
  writer fills stays blank.
- IT SCALES WITH THE SPINE: a chapter's Prompt expands the chapter
  synopsis; a scene's expands that scene's.
- "STOP AI WRITING THE WHOLE THING" IS BUILT INTO THE SHAPE: scoped
  buttons, a server-side system prompt that forbids prose, and output
  that lands by CHOICE, never automatically.

ONE SCENE PER FULL PAGE — LOCKED (6 June 2026)
Read and written one scene per page, each on its own full US-Letter sheet
(816 × 1056px). Pages are ALWAYS full height — a short scene leaves white
space; pages are never shrunk to hug content.

THE CLICK-TO-WRITE IS THE WHEEL
The page sits shifted right; in the dark channel to its right, a vertical
belt of labels on a hairline gold RAIL with a fixed gold CENTRE.
Scrolling the page turns the wheel; whatever sits at the centre is where
you are. Locked: 4 June 2026.

THE WHEEL LABELS ARE TWO LINES — LOCKED (7 June 2026)
A small gold mono caps KICKER ("STAVE ONE — SCENE ONE") and the SCENE
TITLE beneath in Crimson Pro. No separate stave marker labels.

THE WHEEL — WINDOWED, EASED, STRAIGHT — LOCKED (7 June 2026)
Window of NINE labels each side of centre, fading at the edges with a
brightness floor. Motion eased and slow (rate 0.072), never 1:1. Row
spacing TIGHT=46, centre gap GAP=64. The belt is STRAIGHT (BOW=0). The
live hand-off carries a 0.35s transition.

THE WHEEL CENTRE MARK — LOCKED (6 June 2026)
A gold RING (17px, 2px border) with a filled dot and a short gold LEADER
toward the centre label, whose title lights gold.

THE WHEEL HOVER — LOCKED (6 June 2026)
Hovering lights ONLY its node gold; the label text does not change.

ONE SHARED READING LINE — LOCKED (7 June 2026)
Page and wheel share one line, READ_PAD = 28px below the header. Opening
a scene lands its TOP on that line. The wheel reads "where you are" from
the same line, so page and wheel cannot disagree.

WRITING MODE SHOWS ONLY THE LIVE SCENE — LOCKED (7 June 2026)

TWO STATES — OVERVIEW AND WRITING MODE — LOCKED (4 June 2026)
Overview: the assembled Treatment, one scene per page, wheel turning with
the scroll. Writing Mode: the page opens clean for that one scene, the
wheel stays lit, and travel between scenes happens BY THE WHEEL without
leaving. The writing position and the map position are the same thing.

PAGE CENTRE, SCENE MENU LEFT, WHEEL RIGHT — LOCKED (9 June 2026)

THE SCENE MENU — LOCKED (9 June 2026)
The home of the four reached-into tracks, in the channel left of the
page, mirroring the wheel's furniture. Right-aligned list, coloured group
headers, names in plain ink. Clicking a name opens that entity's pop-up.
Tied to the PAGE, not the book.

TENSION IS A SEGMENTED BAR METER — LOCKED (9 June 2026)
In the scene menu, a row of segments green → amber → red lighting to the
scene's level, percentage beneath, able to run past 100 into the red.

THE ENTITY POP-UP — LOCKED (4 June 2026)
Reach the database without leaving the page. Click to open, ✕ to close;
does not vanish on click-away; does not close when text is selected
inside it. Draggable by its header.

POP-UPS ARE MULTIPLE AND INDEPENDENT — LOCKED (7 June 2026)
Each click opens its OWN pop-up at the home position with a small cascade
offset. Clicking one raises it to the front.

THE QUICK-NOTE — PINNED POST-IT — LOCKED, BUILT (17 June 2026)
The writer's OWN scrap — NEVER story data, never prose, never mixed down.
A small amber paper note on the dark workspace, the scruffy cousin of the
entity pop-up: drag by its top strip, ✕ to delete, cascades, raises on
click. Auto-grows so there is never a scrollbar; the folded corner is a
real resize handle.
Summon → jot → KEEP (Enter) / BIN (esc) / PIN.
THE PIN is a two-state THUMBTACK: gold outline when loose, the same shape
FILLED when pinned, swapped in place. A clean click toggles; a
press-and-drag moves it. Pinned = anchored to the scene and scrolls with
it; loose scraps float over the view.
PIN-HEAD COLOUR is assignable per note from the six track colours,
default Tension red. NO IMAGES on notes — images live in Research.
Saved as inkyswot/inkyswot-code-quick-note.html.md. Not yet wired in.

THE EMPTY-CARD IDIOM — LOCKED
An empty or unfiled card is a DASHED OUTLINE only — no fill. It earns its
colour by being filled. An empty idea is honestly empty. The Plot
Mapper's Also-called suggestions use the same idiom.

COPY AND PASTE IS HOW INFO REACHES THE MANUSCRIPT — LOCKED (4 June 2026)
Each pop-up field has a COPY button. Copy takes TEXT ONLY: coloured in
the pop-up, it lands PLAIN, taking the page's own ink.

SPELL CHECK — THE MUTATIONOBSERVER PATTERN — LOCKED (11 August 2026)
enableSpellCheck must catch fields created LATER, not only those present
at load. It watches for input[type="text"] and textarea appearing and
marks each data-spellReady="1". NB: it does NOT cover contenteditable —
the Plot Mapper sets its own. Widen the selector if another screen needs
it.
THE GRAMMARLY TRAP: if a spell-check fault is reported, CHECK FOR
GRAMMARLY FIRST. It masks the browser's own underlines with its own, and
must be REMOVED AND THE PC RESTARTED — closing the tab is not enough. It
also turns Chrome's own spell-check off on install and does not turn it
back on. Chrome must be set to BASIC (not Enhanced, which sends typed
text to Google) with English (United Kingdom) ticked.

RANGES, NEVER A SINGLE TARGET — LOCKED (12 August 2026)
The Overview gives word and chapter counts as RANGES, and everything
downstream must agree. The Plot Mapper divides the book's range across
its chapters to give each its own. Warnings inform; they never block.

DESIGN-A-MECHANISM RULE — LOCKED (4 June 2026)
Build a small STATIC mockup first, agree the still picture, THEN add
movement. A sketch from Kev beats ten descriptions — ask for one.

WORK FROM THE IMAGE / THE CODE — LOCKED (9 June 2026)
A screenshot from Kev IS the template — match it, do not reinterpret it.
When changing a built file, work from the pasted code, never a
reconstruction. SMALL CHANGES MEAN SMALL CHANGES.

CLEAN-REBUILD RULE — LOCKED (6 June 2026)
If edits stop showing on screen, do NOT keep editing — clean rebuild in a
fresh file.

FILE DISCIPLINE — LOCKED (2 June 2026)
When updating any .md file, rewrite the WHOLE file clean and hand it back
complete. Never a list of patches. The .md is the single source of truth;
the code is the truth above it.

MEMORY DATABASE — LOCKED (9 June 2026)
Everything InkySwot — notes AND code — lives in the InkySwot division of
the Pitch Dark Studios Memory system. Code files carry a "code-" prefix.
A file must be saved INSIDE its division folder; a root-level file saves
but does not appear in the admin menu.

ADA
Female, named after Ada Lovelace. Voice fixed as Google UK English
Female. Sara Martin will NOT voice Ada. A contextual creative
collaborator — not a search engine, not a writing generator.
AI is never REQUIRED: assembling the database, the wheel, copy-paste, the
scene menu and the Plot Mapper's breaks are plain mechanics. The AI
switch turns Ada off entirely and the platform still works.

DEMO BOOKS — DECIDED (7 June 2026)
Two ship with the platform: "A Christmas Carol" (1843) and "The Wind in
the Willows" (1908), both out of copyright. Carol first. A demo is a
NORMAL project, fully populated, with the scene-writing left blank.
FULLY EDITABLE. RESET TO PRISTINE returns it. SAVE = SAVE AS A COPY.

PRICING
Paid only. No free tier. No exceptions. Monthly £9.95, annual £99.50 (two
months free). 14-day money back, no questions asked. One tier, no feature
gates. Locked: 24 May 2026.

PUBLICATION FEE
£1 GBP per publication, base currency GBP, Stripe handles conversion.
Paid users get one free publication per week, £1 after that. Anti-scam
friction, not a revenue stream. Locked: 24 May 2026.

SECURITY SYSTEM — LOCKED LAYERS
Invisible: device fingerprinting, IP tracking, behaviour patterns,
disposable email detection, Stripe fraud detection. Visible but
acceptable: email verification, paid upfront, money-back guarantee,
support ticket for a new device. Locked: 24 May 2026.

MARKETING POSITIONING — NEVER USE
Never: "Write books instantly" / "Passive income publishing" / "Make 100
books a week" / "AI author riches". InkySwot markets to writers,
creators, worldbuilders, playwrights, serious independents, disabled
writers, dyslexic writers. Locked: 24 May 2026.

FORMAT LIST — LOCKED (26 May 2026)
Academic Essay / Thesis · Audio Drama · Audiobook · Autobiography ·
Biography · Children's Book · Comic Script · Cookbook · Essay Collection ·
Flash Fiction · Game Script · Graphic Novel · Literary Journal · Memoir ·
Non-Fiction · Novel · Novella · Personal Essay · Creative Non-Fiction ·
Picture Book · Poetry Collection · Radio Drama · Screenplay · Short
Story · Stage Play · Teleplay · Travel Writing · Other.

FORMAT GROUPS — LOCKED (26 May 2026)
Prose · Script · Verse · Hybrid, as previously listed.

FORMAT-AWARE FORMATTING TOOLBAR — LOCKED (26 May 2026)
The toolbar adapts to the document format. One codebase, conditional
display.

MANUSCRIPT FORMAT CHOSEN FIRST — LOCKED (26 May 2026)
Format is the first decision in project setup. It drives the toolbar, the
workspace layout and the AI context.

GENRE — LOCKED (27 May 2026, extended 12 August)
One primary genre, two sub-genres. All three feed AI context.
EVERY GENRE CARRIES its industry word-count range, its words per chapter,
and ITS OWN SENTENCE WORDING, so the steer is never grammatically wrong.
PAGES ARE NOT USED — "there are so many page sizes."

DCW TENSION CURVE — THREE MODES — LOCKED (26 May 2026)
Manual, AI-guided, Analysis.

DCW EMOTIONAL MAPS — LOCKED (28 May 2026)
Curves tracking one emotion for one character across chapters. Multiple
per character, colour coded, toggleable. Carried, not yet placed.

HOME PAGE — MY PROJECTS — LOCKED (31 May 2026)
The screen a writer lands on at login and returns to. A hub, not a path.
The only unavoidable sequence is the one-time new-project setup.
CONCEPTS lives here too — the writer's store for future-story ideas,
splitting the screen with My Projects.

USER JOURNEY — TWO SHAPES — LOCKED (31 May 2026)
Before login a fixed path; after login an open hub.

THE PRESS — TWO DOORS — LOCKED (31 May 2026)
One tool, two entry points: inside for members, outside at
press.inkyswot.com for pay-per-book non-subscribers. The public Press
must be CLONED, not re-skinned — it needs a different payment gateway.

THE PRESS — LOCKED (29 May 2026)
Cover Creator (Fixed Spine System); Book Layout Tool; Platform
Requirements Database, live and maintained; Front and Back Matter
Assembly. Paperback / Hardback / Ebook, audiobook later. Full spec in
press.md.

SIGNUP / AUTHENTICATION
Email + password → verification → access. No SSO, no third-party auth.
Locked: 25 May 2026.

DATA
InkySwot never sells user data. Ever. GDPR compliant. Deletion within
30 days.

SCROLLBARS
Slim, dark, gold-on-hover, everywhere. No Windows defaults.

HOUSE STYLE
#0a0806 near-black · #0f0d0a background · #c9923a gold · #e8b060 bright
gold. Crimson Pro (body) · JetBrains Mono (labels and interface) ·
Playfair Display (wordmark and titles). Muted danger red #c43a2a for
overruns and warnings — THEY INFORM, THEY NEVER BLOCK THE WRITER.
Light/dark toggle platform-wide.
GOLD MARKS ANYTHING ALIVE AND RESPONDING. NEVER DECORATIVE.

================================================================
OPEN — NOT YET DECIDED
================================================================
STEP TWO OF THE PLOT MAPPER — the cards writing into the same store
Characters, Locations and the rest read from. This is the keystone above,
and the continuity library depends on it. THE VANISHING TINTS MUST BE
SOLVED AS PART OF IT, not after: a mark held as a character offset cannot
survive the text being edited, and both need the platform to follow a
phrase as it moves.
"BASICS" vs "OVERVIEW" vs "FRONT MATTER".
SANDBOX moving from Library to DCW.
THE FIVE ROOMS — the sidebar's group headings as live screens.
THE LIBRARY's shape. The insight worth keeping is Kev's own: "Damn we
already have it" — every screen is already list-left, detail-right.
WHAT "MORE" SHOULD SHOW on the Plot Mapper, and whether STATUS should be
editable there rather than only in Basics.
THE QUICK-NOTE — persistence; a "see all"; whether a pinned note crosses
between views; wiring it across all screens.
THE SITE MAP — built in June against the old nav; needs checking against
the rebuilt sidebar before it is trusted.
THE STAVE PAGE'S WHEEL LABEL.
EVENT ORDER WITHIN A SCENE; multiple events per scene on the page.
TAG SET: Prose vs Action; Dialogue's place; Emotion as a per-beat tag or
the seed of an Emotional Map.
AMBIENT (Atmosphere / Weather / Time): carried, placement open.
CONCEPTS still uses the OLD Cast / World / Plot grouping — bring it into
line with the sixteen sections when next touched.
MEMORY DIVISION IMAGES: whether the division can hold .png/.jpg.

================================================================
SUPERSEDED LOCKS — HISTORY, DO NOT BUILD
(Kept as the record of how we got here.)
================================================================

SINGLE FILE ARCHITECTURE (locked 26 May, SUPERSEDED August 2026) — "the
app is a single HTML file". Replaced by CORRIDOR PLUS POCKETS, with the
Enclosure stitching and publishing. The single file survives only as the
stitched index.html output.

PLOT MAPPING — DROPPED (locked 11 June, SUPERSEDED 15 August 2026) —
Plot Mapping was removed from the platform. REVERSED: the Plot Mapper
exists, it is the screen that was the Synopsis, and it is the only
mapper. What survived the drop and still survives: the quiet-note
grammar, Dark Thoughts, and THE CUT.

THE BOARD IS PLOT MAPPING REBORN — THE WIDE END (locked 9 June,
confirmed 16 June, SUPERSEDED 15 August 2026) — scenes down a sticky left
spine with six tracks across the top. The rotated board reached a working
state (code-board-rotated-5.html) with a compass rose, an arrival state
reading chapterRange from localStorage "is-projects", header-band cards,
drag-to-reorder tracks and snap-to-grid. It is OUT as the Plot Mapper.
Its parts are worth robbing; its name is taken.
NB: code-board-rotated-6 to -11 were a failed rescue on 15 August. Do not
build on them.

PLOT MAPPING TIMELINE — "THE LIFT" (locked 30 May, SUPERSEDED 15 August
2026) — the backstory as the basement of the same map, descending below
chapter one into the Prologue and the Backstories. Tied to the board and
retired with it. THE IDEA IS GOOD and could return in the Plot Mapper:
breaks going the other way, before the beginning.

SECTION HELP PILL AS A SLIDE-IN (locked 30 May, SUPERSEDED 15 August
2026) — the pill and its top-right corner SURVIVE and are now
platform-wide law. The slide-in panel does not: it is a movable,
resizable window with no scrim.

THE MENU SPINE'S PROJECT NAV (recorded 16 June, SUPERSEDED 11 August
2026) — PROJECTS / DCW / WORLD BUILDING / NOTES, with Cast and World as
sub-groups and Notes as Snippets + Research. Replaced by the rebuilt
sidebar: BASICS, then STORY / PEOPLE / WORLD / LIBRARY / DCW. "Library"
has returned as a heading, having been dropped in June as too vague.
The LANDING PAGE and HOME LAUNCHPAD parts of that lock still stand.

THREE VIEWS OF ONE BODY OF DATA (locked 9 June, SUPERSEDED 16 June) —
replaced by THE MIXDOWN. The funnel and the living link survive.

"WRITING PANEL" / "WP" AS THE NAME (from 4 June, SUPERSEDED 16 June) —
now THE MANUSCRIPT.

THE RIGHT-HAND ROADMAP (SUPERSEDED 16 June) — duplicated the wheel.

"LIBRARY" AS A NOTES ITEM (SUPERSEDED 16 June, PARTLY REVERSED August) —
dropped as too vague in favour of Snippets; Library has since returned as
a sidebar group holding Research & Reference, Notes, Images and Sandbox.

THE FIRST SITE MAP — A BRANCHING TREE (SUPERSEDED 11 June later) —
replaced by the four-heading spine with pop-up contents.

SITE MAP STYLING TRIES (11 June) — journey-spine, coloured track-chips,
boxes round the contents, glow on the ring, the ring as a separate
marker. All dropped.

THE "ROAD MAP" NAME (9 June, REVISED 11 June) — renamed the Site Map.

THE QUICK-NOTE ROUND RED PUSHPIN (17 June) — replaced by the filled
thumbtack.

PROMPT / EXPAND BUTTON TREATMENTS B / C / D (11 June) — replaced by
treatment "A": an outline pair in the page's own palette, waking to gold
on hover. NB (15 August): on the Plot Mapper the pair sits on the
chapter or scene line in gold outline — the page-palette treatment
belongs to the cream sheet of the Manuscript.

SECTION COLOURS Character #cba36a / Event #b08a6a (4 June, REVISED
9 June) — replaced by the six track colours.

TENSION AS A VU NEEDLE / FLAT LINE / PLAIN "55%" (9 June) — replaced by
the segmented bar meter.

MERGE THE SCENE MENU INTO THE WHEEL (9 June, REJECTED) — the wheel is the
BOOK; the scene menu is THIS SCENE.

PAGE RIGHT, POP-UP LEFT (4 June, REVISED 9 June) — two balanced channels.

DEMO BOOKS "ideally read-only" (SUPERSEDED 7 June) — fully editable, with
Reset and Save-as-copy.

rollToCentre (SUPERSEDED 7 June) — clipped page tops; replaced by
rollToTop.

SINGLE REUSED POP-UP (SUPERSEDED 7 June) — replaced by multiple
independent pop-ups.

THE 4 JUNE WHEEL DETAIL (SUPERSEDED 6–7 June) — split bunches, window of
~3, single-line labels. Replaced by one scene per page, two-line kicker
labels, window of nine, straight belt.

SEPARATE STAVE MARKER LABELS / BLANK STAVE PAGE (7 June) — replaced by
the kicker on every scene label. A stave page returned 11 June as a
SYNOPSIS page, not a blank marker.

THE WHEEL BLOOM + CHEVRON (REMOVED 6 June). THE WHEEL BOW (REMOVED
6 June) — ran the two-line labels together.

THE SHUTTER (2 June, SUPERSEDED 4 June). THE DCW AS A VERTICAL BOARD
(2 June). DCW × PLOT MAPPER FUSION AS BUILT (1–2 June). DCW TERMINOLOGY
TRACKS / THREADS (29 May). THE NOTE CARD FACE (30 May). WRITE SCREEN /
FULL SCREEN / INDEX CARD (28 May & 2 June). INDENTATION RULE (4 June).
THE WRITING CARD (SUPERSEDED 4 June). "SNAP TO DEFAULT" / DRAG-TO-REORDER
TRACKS / BRIGHT-RED FREEFORM / IDEAS COLUMNS / MAKE-YOUR-OWN TRACKS
(3 June). THE ONE-SCREEN DCW / X-RAY / LINEAR TAGGED CELLS (3 June). THE
FIRST 4 JUNE CLICK-TO-WRITE, an inline gap growing under the event —
replaced by the WHEEL.

THE IDEAS BOX / FILING-BOX (13 July, SUPERSEDED) — the filing-box
metaphor chased theatre over usability. Replaced by CONCEPTS. The
header-band card idiom and the dashed-empty state survived. Do not
rebuild the box.

THE SYNOPSIS AS BOXES (code-synopsis-boxes.html, SUPERSEDED 12 August) —
a Whole Story box, then chapter boxes opening into scene boxes. Wrong
because it asked the writer to know their chapter breaks before they knew
their story. Replaced by the one continuous document that became the Plot
Mapper.