File: inkyswot/build-list.md
Last updated: 4 June 2026
Build order locked 14 May 2026.
Principle: get every user-facing element right in the single HTML
file first. Walk it. Sign it off. Then go deep with infrastructure.
Wire things up once, to something confirmed correct.

NOTE (4 June 2026): the DCW model changed. InkySwot IS the DCW — the
whole platform. The Treatment is the DCW switched on: a timeline of
events (Chapter → Scene → Event), assembled from the database already
built, written by "filling in the blanks." The old vertical-board +
shutter DCW is SUPERSEDED (see current-state.md / locked-decisions.md).
This file is rewritten to match. The writing surface, The Treatment,
and the DCW are now converging toward ONE build — see Steps 10/11/13.

CURRENT POSITION — Step 1 not yet started.
Progress / mockups since last update:
Subplots / Themes & Motifs / Events & Timeline screens built — 28 May.
Chapters screen built and wired — 29 May.
The Treatment SHELL built and wired (empty placeholder) — 29 May.
Genre list rebuilt — 48 entries, flat alphabetical — 28 May.
Plot Mapping standalone mockup — CODE/map-plotter.html — 30 May.
  (Superseded as a build target; kept as history.)
Section help pill (SECTION ?) pattern built on Plot Mapping — 30 May.
DCW × Plot Mapper fusion → vertical board + shutter — 1–2 June.
  (CODE/dcw-vertical.html. SUPERSEDED 3–4 June; kept as history.)
THE TURN (3 June) → one-screen X-ray / linear tagged cells.
  (SUPERSEDED 4 June; kept as history.)
THE SECOND TURN (4 June) → InkySwot IS the DCW / The Treatment is the
  timeline of events. WP / Treatment mockup built for "A Christmas
  Carol" — the live design source. Not yet in the app file.
Step 1 rebuild has not yet begun.

THE CONVERGENCE — A NOTE ON BUILD SEQUENCING (4 June 2026)
Under "InkySwot IS the DCW", three things that used to be separate
builds are now one thing:
- the writing surface (was "Write screen", Step 10),
- The Treatment (Step 11),
- the DCW (Step 13).
They are all the same object: the WP — a real document page showing the
timeline of events (Chapter → Scene → Event), into which the writer
writes the prose ("fills in the blanks"), with the world reached via
the entity pop-up (nav count → list → record → copy → paste plain).
The build order below keeps the three step numbers for now (they have
different dependencies — accessibility, sync, curves) but they should
be reconciled into a single writing-surface build once THE CLICK-TO-
WRITE decision is made (see OPEN, top of current-state.md). In Step 1
the app shell carries The Treatment as a nav entry and a placeholder
until that build.

STEP 1 — v4.0 App Shell Rebuild
All screens, all navigation, all interactions in the single HTML file.
Platform layout: top menu / left sidebar / main work area (the WP /
Treatment) / footer. The entity POP-UP floats over the page (built with
the writing surface). No DCW strip, no board, no shutter.
What goes in during this step:

Three-panel layout shell (left sidebar / main work area / right side).
NAV SECTION COUNTS — each section shows its .length (Characters · 5,
  Locations · 3, Factions · 0; zero greyed). New 4 June.
The Treatment as the main work-area target (placeholder until the
  writing-surface build; nav entry present).
Manuscript Format screen (new — first step in project setup, before
  Overview. Writer chooses format before anything else. Format drives
  toolbar, workspace, and AI context.)
All existing screens carried across and confirmed in correct position.
All stubbed screens built to same pattern as existing screens:
  Research & Reference / Notes & Scratchpad / Sandbox /
  Tutorial / Manual / FAQs / What's New.
(The old DCW sub-entries Timeline / Storyboard are superseded —
  collapse the nav: The Treatment is the home of the DCW.)
Note: Subplots, Themes & Motifs, Events & Timeline, Chapters and The
  Treatment shell already built — carry across, confirm in position.
Note: Research & Reference, Notes & Scratchpad and Sandbox are deferred
  until after the writing surface (Step 10). Build shells only here.
Pattern: same two-panel layout (list left, detail right), same AI
  Generate and Expand buttons, same auto-save, same field structure.
Style Field: tone/voice dropdown + free text on Overview.
Genre: three fields — primary + two sub-genres (replace the temporary
  combined dropdown built 28 May).
New Project modal: Start Fresh / Import Existing Work.
Format-aware formatting toolbar SHELL (adapts to manuscript type:
  Prose / Script / Verse / Hybrid groups; each shows only relevant
  tools. Full toolbar built with the writing surface — shell only here.)
Button layout: AI Generate / AI Expand / Read in vertical column.
AI ON/OFF theatrical transition (gradual).
Animated speaker on Read (four frames).
All AI Generate and Expand buttons on all screens.
Help section carried across.
Home-page launchpad row (four items, icons, straps) on My Projects —
  confirm strap wording before building.
Section help pill (SECTION ?) — template pattern, add to every screen.
  Top-right, gold border. Slide-in guide headed with the screen's name
  (what it is / how to use it / a tip). Separate from the Help-menu
  manual. Intended to float — not yet built.
Cover thumbnail: REMOVED — not being built.

STEP 2 — Walk the Platform
Walk every screen as a zero-knowledge user.
Resolve outstanding user flow gaps:
Font import placement (confirmed: Publishing Suite / Press Templates).
Document types in New Project modal (UX map gap 5).
Ada intervention points must be tested here.

STEP 3 — Sign Off Layout and Journey
Gate. Nothing moves to Step 4 until Kev confirms layout and journey.

STEP 4 — Supabase
Database and authentication. PostgreSQL.
Free tier during development and beta. Pro ($25/month, ~£20) before launch.

STEP 5 — Lifetime Membership Flag
Server-side flag in Supabase: is_lifetime: true. Bypasses all prompt
counting. Header shows infinity symbol instead of number. Confirm
working before Step 6.

STEP 6 — F12 / Security Blocker
Blocks localStorage manipulation via dev tools. Safe because the
lifetime flag is server-side.

STEP 7 — Server-Side Prompt Tracking
Prompt counter moves from localStorage to Supabase per user.
Non-negotiable before launch. Current localStorage counter is a
development placeholder only.

STEP 8 — Stripe
Payment processing. Needs Supabase user accounts.
Monthly £9.95 / Annual £99.50 (two months free) / top-up £1.99 for 500
prompts / publication fee £1 GBP (paid users one free per week, £1
after). The Press per-book fee for non-subscribers — to be confirmed.

STEP 9 — Resend
Email delivery. Needs Supabase user accounts.
Signup verification codes (unique, 20 min, max 3 requests); password
resets; The InkySwot Bugle newsletter; notifications. Signup is not
live until this step is complete.

STEP 10 — The Writing Surface (the WP) + Accessibility
NB (4 June): this is the writing surface for the new model — and it
converges with The Treatment (Step 11) and the DCW (Step 13). Build it
once, reconciled, once THE CLICK-TO-WRITE decision is made.
The WP is a REAL DOCUMENT PAGE:
— White page, Letter proportions, generous margins, page shadow,
  centred on the dark workspace.
— MAGNIFY/zoom control (70%–200%; view only; page shape fixed).
— Centred page numbers; optional UNNUMBERED title page (numbering
  starts at 1 after it) with a toggle; title + author from Overview.
— Slim dark gold-on-hover scrollbars.
The page shows the TIMELINE OF EVENTS: Chapter → Scene → Event. Scenes
labelled "Scene 1" with an optional title. Events at the margin; "—
click to write this scene —" the writing invitation.
THE CLICK-TO-WRITE — UNDECIDED (decide before building): writing space
grows INLINE in the page, OR the scene opens a FOCUSED surface.
THE ENTITY POP-UP (built here): two-step from the nav counts (list →
record); stable (click open, click close; no vanish-on-click-away; no
close-on-text-select); draggable by its header; quiet-note grammar in
section colour; copy buttons; copy-and-paste into the WP as PLAIN ink.
This REPLACES the old Index Card system (superseded).
Format-aware toolbar (shell in Step 1, fully built here): Bold /
Italic / Underline / Font / Size / Alignment / Lists. Hotkeys.
Chapter selector. Live word count (top-right). Auto-save.
Distraction-free writing (was "Full Screen", shutter definition
retired): redefine as WP + chrome hidden — NOT yet locked.
Accessibility (CRITICAL DIFFERENTIATOR):
— Spell checker: 5–8 suggestions, AI phonetic interpretation,
  text-to-speech on hover, option to disable red underlines.
— Read Aloud: browser speechSynthesis, zero cost, resume from point,
  click to set read-head. (Chrome async cancel() fix already in place.)
— Inline AI Thesaurus (Ctrl+Shift+T): 3–4 contextual alternatives in
  story tone, speaker icon on each.
— Collaborative Editing: bidirectional, AI at human pace, cursor to
  flagged word one at a time, user sees everything, both can flag.
  Vital for dyslexic users.
Real PAGINATION (prose flowing and breaking onto new numbered pages as
you write) belongs here — the mockup uses fixed-height sheets.
Library section (Research & Reference, Notes & Scratchpad, Sandbox)
fully built after this step.
Open: where the chapter/scene MOOD words live (parked 4 June); event
ORDER within a scene (events need a position); the tag set (Prose vs
Action; Dialogue's place; Emotion as tag vs Map).

STEP 11 — The Treatment (the timeline of events / fill-in-the-blanks)
NB (4 June): The Treatment IS the DCW switched on, and IS the WP's
default view — see the convergence note up top. It assembles itself
from the project database (Characters, Locations, Events, Plot Threads,
Subplots, Themes, Chapters) into the Chapter → Scene → Event spine,
with the SUBSTANCE laid in and the prose left as blanks. Only events
become prose. The world is reached via the pop-up (Step 10).
The empty placeholder shell (built 29 May) is the named home for this.
Ada renders / improves where AI is ON, but the Treatment works AI-OFF
(assembly + copy-paste are plain mechanics).
Bidirectional: editing a database entry updates wherever it appears
(the pop-up is the live handle). The old "screenplay-style block
editor" framing is superseded by the timeline-of-events model.

STEP 12 — Ada
Needs the screens and the writing surface to exist.
Full specification in ada.md. Ada spec must be complete before this
step. Ada voice alternative to be confirmed before this step.
NB (4 June): AI is never required for the Treatment to work; Ada
improves the experience (e.g. shaping pasted substance into prose).

STEP 13 — DCW
NB (4 June): the DCW is NOT a separate board or screen. InkySwot IS the
DCW; The Treatment is it switched on. This step is therefore the same
build as Steps 10/11 (the writing surface + the timeline-of-events
Treatment) — kept as a separate number only to hold the CARRIED, not-
yet-placed pieces below until they are fitted to the new model.
CARRIED, to be re-fitted to the timeline-of-events model:
— Tension curve — three modes (Manual / AI-guided / Analysis).
— Emotional Maps — multiple per character, colour coded, toggleable.
— Ambient — Atmosphere / Weather / Time (Time as a block).
— The "lift" (Prologue / Backstory below Chapter 1).
— Dark Thoughts (private, never exported).
HOW these live in a linear timeline-of-events page is OPEN — decide
when reached. The vertical board, shutter, three-track-columns, cards,
cascade, and "card as bridge to writing" are SUPERSEDED (history only).
Design source: the 4 June WP / Treatment mockup (store in CODE locker).
CODE/dcw-vertical.html and CODE/map-plotter.html are history, not build
targets.

STEP 14 — Export Suite and Format Conversion
Needs the writing surface and The Treatment.
HEADLINE FEATURE — one click exports the entire story world.
Formats: Word / Google Docs / PDF / JSON / Email / Claude / ChatGPT /
Gemini / EPUB. Format conversion both directions: prose ↔ script
(Screenplay / Radio Drama / Stage Play). Full revised spec before build.
Note: the Export Suite is for working writers sharing and backing up.
The Press (Step 15) is for publication. Different things.

STEP 15 — The Press
Replaces and significantly expands the former Publishing Suite.
Full specification in press.md. Needs Export Suite (Step 14) first.
Where the writer goes when the book is done. Also a standalone
pay-per-book product for non-subscribers. An acquisition funnel.
Includes: Cover Creator (Fixed Spine System; three-panel canvas;
real-time spine adjustment; 3D book preview); Book Layout Tool (open
book on screen, flippable pages, drop content, WYSIWYG print);
Front and Back Matter Assembly (auto-assembled; Ada writes blurb, bio,
acknowledgements; writer refines); Platform Requirements Database
(live, maintained); Validation layer (green lights only before export);
Metadata (pre-filled, writer completes); The Guide (honest, platform-
agnostic publishing guidance).
Formats: Paperback / Hardback / Ebook. Audiobook — future.
Platforms — Print: KDP / IngramSpark / Lulu / Barnes & Noble Press /
Other. Ebook: KDP / Draft2Digital / Kobo / Apple Books / Other.
Maintenance: requirements database monitored and updated whenever a
platform changes its specs. Ongoing operational commitment.
Public-facing entry point: press.inkyswot.com (or similar) — pay per
book, no subscription required (two-door model; cloned for a separate
payment gateway).
Build complexity: Cover Creator and Book Layout Tool may each need a
sub-step. Full timeline assessed before Step 14 begins.

STEP 16 — Admin Panel
Needs Supabase, Stripe, full platform.

STEP 17 — PWA Manifest
Platform complete. Windows first. Mac second.

STEP 18 — Beta
All above signed off. Supabase Pro active before beta users invited.
Ada voice recording at this step. Beta programme structure to be
defined before this step.

STEP 19 — Launch
DNS to production. Triple redundancy. Testbed at
www.inkyswot.com/testbed, password protected during transition.

ONGOING — Content & Operations
Run alongside build, continue post-launch:
Platform Comparison Chart.
User Experience Timeline (v1 map built; gaps 4 and 5 to resolve Step 2).
FAQs / Manual / Videos (YouTube — no build content).
Monthly Newsletter (The InkySwot Bugle).
Beta Programme (not yet defined — Facebook page natural channel).
Platform Requirements Database — ongoing maintenance.
The Guide — written in parallel with build, updated post-launch.