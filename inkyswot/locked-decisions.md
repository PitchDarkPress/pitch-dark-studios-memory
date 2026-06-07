File: inkyswot/locked-decisions.md
Last updated: 7 June 2026

NOTE ON THIS FILE
This file is normally add-only. On 4 June (morning) it was rewritten
whole because the 1–3 June DCW locks (the shutter, the vertical board,
the fusion-as-built, the one-screen cell-grid) were SUPERSEDED by the
"InkySwot IS the DCW / The Treatment" model. Superseded locks are NOT
deleted — they are moved to SUPERSEDED LOCKS at the foot, dated, kept
as history.
On 7 June it was rewritten whole again to bring the WHEEL and PAGE locks
into line with the wheel AS BUILT across 6–7 June (one scene per page,
two-line kicker labels, straight belt, window of 9, ring+leader with the
bloom/chevron removed, hover lights node only, smoothed hand-off). The
4 June wheel locks that those refinements replaced are moved to
SUPERSEDED LOCKS, dated, kept as history. The live part of this file
holds only decisions that are still true.

================================================================
LIVE LOCKED DECISIONS
================================================================

PLATFORM IDENTITY
InkySwot is a writing platform. Not a content generation engine.
Assisted creation. Not instant generation. Non-negotiable.
Tagline: Publish and be damned. Always.
"Publish and be prepared" must never be used.

INKYSWOT IS THE DCW
The DCW is not a screen, strip, board, or panel. It is the WHOLE
platform. Every section already built (Characters, Locations, Events,
Plot Threads, etc.) is part of the instrument. The database is the
bones of the story. Locked: 4 June 2026.

THE TREATMENT IS THE DCW SWITCHED ON
The Treatment is where everything in the database ASSEMBLES into a
readable, writable whole. A plotline is a VIEW of data that already
exists, not a new thing to author. Locked: 4 June 2026.

THE SPINE IS A TIMELINE OF EVENTS
The Treatment is a timeline of events. Tiers: CHAPTER → SCENE → EVENT.
Only EVENTS sit on the line and become prose — because only events
happen. Characters, Locations, Objects, etc. do not happen; they are
reached into by the events that use them. Locked: 4 June 2026.

SCENES ARE LABELLED, TITLE OPTIONAL
Scenes are labelled "Scene 1", "Scene 2"… The writer may add an
optional title ("Scene 1 — The Counting-House"). Events live under
their scene. Locked: 4 June 2026.

FILL IN THE BLANKS
The Treatment assembles the SUBSTANCE from the database (not just
names) and leaves the writer the blanks — the prose and dialogue no
database can hold. The writer never faces a blank page; assembled, the
sections ARE the draft; the writing is the last layer, not the first.
Locked: 4 June 2026.

ONE SCENE PER FULL PAGE — LOCKED (6 June 2026)
The Treatment is read and written ONE SCENE PER PAGE. Each scene sits on
its own full US-Letter sheet (816 × 1056px). The old long-scrolling
multi-event page is gone (it felt too busy and made the wheel track too
many close points). Pages are ALWAYS full height — a short scene simply
leaves white space below it, exactly like a real document page; pages
are never shrunk to hug content. Locked: 6 June 2026.

STAVE HEADING ON EVERY PAGE — LOCKED (6 June 2026)
The stave/chapter heading shows at the top of EVERY scene page, for
navigation, so the writer always knows which stave they are in — not
only on the page where the stave opens. Locked: 6 June 2026.

THE CLICK-TO-WRITE IS THE WHEEL
Resolves the old open decision (inline-grow vs focused surface) — the
answer is neither: a WHEEL. The page sits SHIFTED RIGHT; out in the dark
channel to its right (between the page and the 230px right sidebar) is a
vertical belt of labels on a single hairline gold RAIL, with a fixed
gold CENTRE. Scrolling the PAGE turns the wheel (page-scroll driven, not
wheel-scroll); whatever label sits at the centre is WHERE YOU ARE.
Locked: 4 June 2026.

THE WHEEL LABELS ARE TWO LINES — LOCKED (7 June 2026)
Every wheel label is TWO LINES: a small gold JetBrains Mono caps KICKER
giving the exact position ("STAVE ONE — SCENE ONE"), and the SCENE TITLE
beneath it in Crimson Pro ("The Counting-House"). Every scene therefore
carries its full stave+scene position on the wheel. There are NO
separate stave marker labels and NO blank stave pages — the stave is
named on every scene via the kicker. Stave/scene numbers are computed in
JS from a data-stave-open marker on each stave's first page.
Locked: 7 June 2026. (Supersedes the 4 June single-line uniform labels.)

THE WHEEL — WINDOWED, EASED, STRAIGHT — LOCKED (7 June 2026)
- WINDOW of NINE labels each side of centre (a real map of the book
  using the full page height). Labels fade in/out at the edges so the
  wheel stays calm however long the book is.
- FADE: even and gentle across the window, with a brightness FLOOR so
  outer labels stay readable; the centre and the two labels either side
  of it are full brightness, the rest dimmed (~71%). Label text colour
  is uniform; the dimming is opacity only.
- MOTION: eased and slow — glides toward target, never snaps 1:1 to
  scroll. Ease rate 0.072. Row spacing TIGHT=46, centre gap GAP=64.
- BELT IS STRAIGHT (BOW=0). A slight outward bow was tried and liked as
  a "felt not seen" cue but REMOVED because it ran the two-line labels
  together. Any future bow must not cost two-line legibility.
- THE LIVE HAND-OFF IS SMOOTHED: 0.35s CSS transition on the label text
  so the gold eases in/out as labels pass centre rather than snapping.
Locked: 7 June 2026. (Supersedes the 4 June "split bunches / ~3-label
window / big roomy uniform labels" lock.)

THE WHEEL CENTRE MARK — LOCKED (6 June 2026)
The centre is marked by a gold RING (17px, 2px border) with a filled
gold dot, plus a short gold LEADER line from the ring toward the centre
label. The centre label's title lights gold. The centre node is hidden
behind the ring. REMOVED: the radial bloom glow and the » chevron — one
clean mark, no pointing at what is already obvious. Locked: 6 June 2026.

THE WHEEL HOVER — LOCKED (6 June 2026)
Hovering a wheel label lights ONLY its node gold. The label TEXT does
not change on hover. Clicking a label navigates to that scene.
Locked: 6 June 2026.

TWO STATES — OVERVIEW AND WRITING MODE
OVERVIEW: the assembled Treatment shows (one scene per page); the wheel
turns with the scroll; centre = where you are. Click a wheel label to go
to that scene; click the centre label (or a "— click to write this
scene —" on the page) to enter Writing Mode.
WRITING MODE: the page opens CLEAN for that one scene — scene line +
event title near the top, then the whole page given to a full-height
writing area. The wheel stays lit, locked with that scene at centre.
CLICK ANY WHEEL LABEL to open THAT scene to write — the writer travels
scene-to-scene BY THE WHEEL without leaving Writing Mode; each scene's
text is remembered. A "‹ overview" control (top-right, Writing Mode
only) returns to the assembled Treatment. The writing position and the
map position are the SAME thing. Locked: 4 June 2026.

PAGE RIGHT, POP-UP LEFT
The WP / Treatment page sits shifted to the RIGHT of the dark
workspace; the wheel is in the channel to the right of the page. The
LEFT of the workspace is reserved for the entity POP-UP note. Locked:
4 June 2026.

THE ENTITY POP-UP
The writer reaches the database without leaving the page, via a stable
pop-up (on the LEFT). Two steps from the nav: click a section → list of
names → click a name → the record. STABLE: click to open, click (✕) to
close; does not vanish on click-away; does not close when text is
selected inside it. DRAGGABLE by its header; stays where put. Locked:
4 June 2026.

NAV SECTION COUNTS
Each nav section shows a live count read from its saved array
(Characters · 5, Locations · 3, Factions · 0; zero greyed). Clicking a
counted section opens the pop-up list. Locked: 4 June 2026.

POP-UP USES QUIET-NOTE GRAMMAR IN SECTION COLOUR
Throughout the pop-up (list, entries, kicker, back link): a SUB-TITLE
in the SECTION's colour, a DESCRIPTION in neutral ink beneath, closed
by a SOLID end-line in the section colour. Colour = wayfinding. Record
view: per-field rows each with a COPY button, section-colour dividers,
section-colour end-line. Characters gold; Locations teal; each section
its own colour. Locked: 4 June 2026.

COPY AND PASTE IS HOW INFO REACHES THE WP
The mechanism for getting database substance into the writing is copy
and paste. Each pop-up entry/field has a COPY button. Copy takes TEXT
ONLY: coloured in the pop-up, but it lands in the WP PLAIN, taking the
page's own ink. Colour for finding in the panel; neutral ink for reading
on the page. The writer stays in charge — nothing lands they did not
choose. Locked: 4 June 2026.

THE WP IS A REAL DOCUMENT PAGE
The main work area / The Treatment is a proper document page (US Letter,
816 × 1056px, generous margins), on the dark workspace with a page
shadow — not a thin panel. (Shifted right; see PAGE RIGHT, POP-UP LEFT;
one scene per page; see ONE SCENE PER FULL PAGE.) Running head top-right;
stave heading mono caps ruled under; scene heading mono + optional
italic title; writing area Crimson Pro 18px / line-height 1.5.
Locked: 4 June 2026 (page proportions); refined 6 June 2026.

WP MAGNIFY (ZOOM)
A − / 100% / + control magnifies the whole document (70%–200%). It is
ZOOM, not page-width — the page shape never changes. Locked: 4 June 2026.

WP PAGE NUMBERS + OPTIONAL TITLE PAGE
Page numbers centred at the foot of each page. An optional first TITLE
PAGE (centred title + "by [author]") is UNNUMBERED; numbering starts at
1 on the page after it (manuscript convention). A toggle turns the title
page on/off. Title + author pull from Overview. Locked: 4 June 2026.

SCROLLBARS
Slim, dark, gold-on-hover, everywhere. No Windows defaults. Locked:
4 June 2026.

DESIGN-A-MECHANISM RULE
When designing a live mechanism (motion, scroll, interaction), build a
small STATIC mockup first, agree the still picture, THEN add movement.
Designing moving behaviour by description alone wastes time. A sketch
from Kev beats ten descriptions — ask for one. Locked: 4 June 2026.

CLEAN-REBUILD RULE (display freeze) — LOCKED (6 June 2026)
If edits stop showing on screen, do NOT keep editing — do a CLEAN
REBUILD in a fresh artifact. The artifact display freezes on an old
version; a clean rebuild fixes it instantly. (Learned the hard way more
than once.) Locked: 6 June 2026.

PRICING
Paid only. No free tier. No exceptions.
Monthly: £9.95. Annual: £99.50 (two months free).
14-day money back guarantee. No questions asked. Locked: 24 May 2026.

PRICING PHILOSOPHY
One tier only. No feature gates. The annual subscription is a loyalty
reward. The product is identical.

PUBLICATION FEE
£1 GBP per publication. Base currency GBP. Stripe handles international
conversion automatically. Paid users: one free publication per week,
£1 after that. Anti-scam friction, not a revenue stream. Upfront and
transparent. Locked: 24 May 2026.

SECURITY SYSTEM — LOCKED LAYERS
Invisible to genuine users: device fingerprinting; IP tracking and
location detection; behaviour pattern detection; disposable email
detection; Stripe fraud detection.
Visible but acceptable: email verification at signup; paid upfront;
14-day money back guarantee; support ticket required for new device.
Locked: 24 May 2026.

MARKETING POSITIONING — NEVER USE
Never market: "Write books instantly" / "Passive income publishing" /
"Make 100 books a week" / "AI author riches".
InkySwot markets to: writers, creators, worldbuilders, playwrights,
serious independents, disabled writers, dyslexic writers.
Locked: 24 May 2026.

FORMAT LIST — LOCKED
Academic Essay / Thesis / Audio Drama / Audiobook / Autobiography /
Biography / Children's Book / Comic Script / Cookbook / Essay
Collection / Flash Fiction / Game Script / Graphic Novel / Literary
Journal / Memoir / Non-Fiction / Novel / Novella / Personal Essay /
Creative Non-Fiction / Picture Book / Poetry Collection / Radio Drama /
Screenplay / Short Story / Stage Play / Teleplay / Travel Writing /
Other. Locked: 26 May 2026.

FORMAT GROUPS — LOCKED
Prose — Novel / Novella / Short Story / Flash Fiction / Children's
Book / Picture Book / Memoir / Biography / Autobiography / Travel
Writing / Non-Fiction / Personal Essay / Academic Essay / Essay
Collection / Literary Journal / Cookbook.
Script — Screenplay / Teleplay / Radio Drama / Audio Drama / Stage
Play / Comic Script / Game Script.
Verse — Poetry Collection.
Hybrid — Graphic Novel / Audiobook. Locked: 26 May 2026.

FORMAT-AWARE FORMATTING TOOLBAR — LOCKED
The writing panel toolbar adapts to the document format. Each format
displays only the tools relevant to it. One codebase, conditional
display. Locked: 26 May 2026.

MANUSCRIPT FORMAT CHOSEN FIRST — LOCKED
Format is the first decision in project setup, before Title, Genre,
Style, Tone, or any other field. Format drives the toolbar, the
workspace layout, and the AI context. Locked: 26 May 2026.

GENRE — THREE FIELDS — LOCKED
One primary genre, two sub-genres. Three fields, not a dropdown. All
three feed AI context. (A temporary combined dropdown was built 28 May
as a placeholder; the three-field system is the lock, built in Step 1.)
Locked: 27 May 2026.

DCW TENSION CURVE — THREE MODES — LOCKED
Manual — writer drags the curve. AI-guided — writer sets target
tension, Ada advises how to achieve it. Analysis — Ada reads the text
and plots the curve automatically. Locked: 26 May 2026.
NB (4 June): carried but not yet PLACED in the timeline-of-events
Treatment. How the curve lives in the new model is open.

DCW EMOTIONAL MAPS — LOCKED
Emotional Maps are curves tracking the rise and fall of a specific
emotion belonging to a specific character across chapters. The word
Map is deliberate — names the line now, future-proofs a full
cartographic emotional view. Multiple Maps per character. Colour coded.
Toggleable. Locked: 28 May 2026.
NB (4 June): carried but not yet PLACED in the new model. Also: whether
the "Emotion" tag is a per-beat tag or the seed of a Map is open.

HOME PAGE — MY PROJECTS — LOCKED
My Projects is the home page — the screen a writer lands on at login
and returns to. The hub, not a fixed path. After login the writer
navigates freely; no forced route. The only unavoidable sequence is the
one-time NEW project setup (New Project → Manuscript Format →
Overview), because the project must exist before it can be navigated.
LAUNCHPAD: four items live BOTH in the nav AND on the home page —
Plot Mapping / The Press / Create First Project / Open Project. Each
home-page item carries an icon, a title, a two-line strap. Icons: clean
SVG line art, stroke="currentColor" (recolour with Tone; no PNGs),
stored at CODE/home-icons.svg. (Strap wording not finally signed off —
confirm before building.) Locked: 31 May 2026.

USER JOURNEY — TWO SHAPES — LOCKED
Before login: a fixed path (no nav yet) — Landing Page → Sign Up /
Log In → Login page. After login: an open hub — My Projects (home),
then the nav takes the writer anywhere, in any order. The only
surviving sequence is the one-time new-project setup (necessity, not an
imposed path). Locked: 31 May 2026.

THE PRESS — TWO DOORS — LOCKED
The Press is ONE tool with two entry points.
INSIDE (members): a nav screen where a logged-in subscriber publishes.
OUTSIDE (public): the same tool behind its own public door —
press.inkyswot.com — reachable also from the landing page. A non-sub
signs up here (lightweight Press sign-up), pays per book, publishes
without a platform subscription. A public Press sign-up = member of
THE PRESS ONLY: a login to The Press, no platform access. The paid-only
platform stays sealed. Upsell gentle: email captured → The InkySwot
Bugle (the slow funnel).
BUILD NOTE: the public Press must be CLONED, not re-skinned — it needs
a DIFFERENT payment gateway. Shared publishing engine; separate
sign-up, login, payment. Locked: 31 May 2026.

THE PRESS — LOCKED
Named: The Press (29 May 2026). Where the writer goes when the book is
done. Separate section — not part of the project nav. Also a standalone
pay-per-book product for non-subscribers (see TWO DOORS). An acquisition
funnel for InkySwot. Replaces/expands Step 15. Full spec in press.md.
Key features locked:
Cover Creator — Fixed Spine System. The spine is built at maximum
width; front and back covers slide over it, masking what is not needed.
No recalculating, no rebuilding.
Book Layout Tool — open book on screen, flippable pages; what the
writer sees is what prints.
Platform Requirements Database — live, maintained, always current.
Front and Back Matter Assembly — auto-assembled from database; Ada
writes blurb, bio, acknowledgements; writer refines.
Supported formats: Paperback / Hardback / Ebook. Audiobook: future.
Platforms: KDP / IngramSpark / Lulu / Draft2Digital / Kobo / Apple
Books / Barnes & Noble / Other.
Maintenance commitment: the requirements database is monitored and
updated whenever any platform changes its specs. Ongoing operational
commitment. Non-negotiable. Locked: 29 May 2026.

PLOT MAPPING — LOCKED (the corkboard itself)
Named: Plot Mapping. The story corkboard — a thinking space for
sketching a story before committing to it. ONE Plot Mapper per project
(each project its own board; no second mapper). On 31 May its NAV LINK
moved up into Navigate so it is reachable front-of-house; the tool
itself stays per-project. Saved like everything else for now; moves to
Supabase at Step 4. Standalone mockup complete 30 May (CODE/map-plotter
.html). Locked: 30 May 2026. Nav-link move locked: 31 May 2026.
NB (4 June): under "InkySwot IS the DCW", Plot Mapping's relationship
to The Treatment is being reconsidered — both are views of the same
database. The corkboard as a thinking space is retained; how it sits
beside The Treatment is open. The note-card mechanics that were locked
into the column-board fusion (tab, knot, full-stop, card face) are
SUPERSEDED — see SUPERSEDED LOCKS. The QUIET-NOTE grammar survives (now
the pop-up's grammar). Dark Thoughts survives (private, never exported).

PLOT MAPPING TIMELINE — BELOW CHAPTER 1 — LOCKED ("the lift")
One Plot Map per project. The backstory is not a separate map; it is
the basement of the same one. Like a lift: above the line the chapters
climb; below it you descend into the Prologue, then the Backstories
(Ch.3 / Ch.2 / Ch.1 / Prologue / Backstory 1 / 2 / 3). Same board, same
notes, same threads — the timeline has a downstairs. Locked: 30 May 2026.
NB (4 June): carried; re-fit to the timeline-of-events model when the
event-ordering question is settled.

SECTION HELP PILL — TEMPLATE PATTERN — LOCKED
Every screen carries a help pill, top-right, gold border, reading
SECTION ? — clicking opens a slide-in guide headed with that screen's
name (what it is / how to use it / a tip). Same pill, same place, every
screen; each supplies its own words. The in-context help system; the
full manual stays separate (Help menu). First built on Plot Mapping
(30 May) as the template. Intended to float — not yet built.
Locked: 30 May 2026.

SIGNUP / AUTHENTICATION
Email + password → email verification → platform access. No SSO. No
third-party authentication. Email and password only. Locked: 25 May 2026.

DATA
InkySwot never sells user data. Ever. GDPR compliant. Deletion within
30 days.

SINGLE FILE ARCHITECTURE
The app is a single HTML file. Locked: 26 May 2026.

ADA
Female. Named after Ada Lovelace. Voice fixed as Google UK English
Female. Sara Martin will NOT voice Ada. A contextual creative
collaborator — not a search engine, not a writing generator. She gives
the writer's answer, filtered through everything they have already
built. Ada spec must be complete before any further screens are built.
Ada build is Step 12. Locked: confirmed.
NB (4 June): AI is never required for the Treatment to work — assembling
the database into the page, the wheel, and copy-paste are plain
mechanics. Ada improves the experience; the writer's book stands
without her.

COVER THUMBNAIL — REMOVED
Not being built. AI-generated cover concepts post-launch only.

UX MAP GAP 6 — RESOLVED
Import Project uses the same setup screen as New Project. Manual entry,
same fields, no AI inference at this stage. Post-launch: AI inference
from imported manuscript a consideration. Locked: 26 May 2026.

FILE DISCIPLINE — LOCKED
When updating any .md file, rewrite the WHOLE file clean and hand it
back complete. Never a list of patches or "replace this block" edits.
The .md is the single source of truth; the code is the truth above it.
Locked: 2 June 2026.

================================================================
OPEN — NOT YET DECIDED
================================================================
>>> THE PAGE-TOP BUG (FIRST THING NEXT SESSION, 7 June) <<<
Clicking a scene label on the wheel (and opening a scene generally)
leaves the TOP OF THE PAGE CUT OFF above the fold — the running head /
stave heading / scene line are clipped. The page should sit with its
TOP just below the header bar, reading from the top down (Kev showed a
screenshot of the correct look). A rollToTop() function was added and
pointed at both the wheel-label click and the writing-open (offset tried
at −28 and −16, behavior:'auto', two requestAnimationFrames before
scrolling in writing mode because body.writing changes .stage padding
40vh→34px and hides content). STILL CUTTING OFF. First thing to fix.

(The CLICK-TO-WRITE is no longer here — it is a lock: THE WHEEL.)
WHERE THE MOOD WORDS LIVE: the chapter/scene mood words (e.g. Cold ·
Bleak · Biting) were pulled off the page; Kev wants them but not yet
sure where they belong. Parked.
EVENT ORDER WITHIN A SCENE: events group by chapter but have no
sequence within a scene. The spine needs "this before that." (Events
already store characters[] and location; they lack a position.)
EVENTS ON THE PAGE: with one-scene-per-page, confirm whether multiple
events per scene stay listed on the page or collapse.
TAG SET: Prose vs Action (working split: Action = what they do; Prose =
description / narration). Dialogue's place (not on the 4 June list but
needed). Emotion as a per-beat tag vs the seed of an Emotional Map.
TENSION CURVE / EMOTIONAL MAPS / AMBIENT (Atmosphere / Weather / Time):
carried from earlier DCW thinking; how they live in the timeline-of-
events Treatment is open.
THE 230px RIGHT SIDEBAR: its purpose (currently blank).
PLOT MAPPING beside The Treatment: how the corkboard and the Treatment
relate now both are views of one database.
HOME-PAGE LAUNCHPAD: final strap wording for the four items.
THE PRESS (public door): where a non-subscriber's book data comes from
with no platform project — enter cold, or upload a finished manuscript.

================================================================
PARKED / FUTURE (feasible, not scheduled — also in future.md)
================================================================
TWO PRE-FILLED DEMO BOOKS: fully-populated, every-section-complete demo
projects of "A Christmas Carol" and "The Wind in the Willows" so a new
user can explore a finished world. Both out of copyright (Dickens 1843;
Grahame 1908). A demo = a normal project, pre-filled, ideally read-only.
Carol first (its bones are in the mockup), then Willows. Depends on the
app shell and sections being final. Confirmed feasible 4 June; not
scheduled; NOT a lock.

================================================================
SUPERSEDED LOCKS — HISTORY, DO NOT BUILD
(Kept as the record of how we got here.)
================================================================
THE 4 JUNE WHEEL DETAIL (SUPERSEDED 6–7 June by the wheel as built) —
the 4 June wheel was locked as: split bunches (centre alone, everything
before bunched above a fixed gap, everything after below, gaps never
closing); a WINDOW of ~3 labels each side; big roomy uniform single-line
labels (Crimson Pro ~21px); a leader on the centre. These are
superseded by: one scene per page; two-line kicker labels; a window of
NINE; straight belt; the smoothed hand-off; the ring+dot+leader centre
with the bloom and chevron removed; hover lights node only. The
PRINCIPLE (windowed, eased, page-scroll driven, centre = where you are,
leader on the centre) survives; the numbers and the label form changed.
SEPARATE STAVE MARKER LABELS / BLANK STAVE PAGE (tried 7 June,
SUPERSEDED same day) — putting the stave on the wheel as its own rail
point forced a blank stave page and did not read right. Replaced by the
two-line kicker on every scene label.
THE WHEEL BLOOM + CHEVRON (4 June, REMOVED 6 June) — the soft radial
glow behind the centre and the » chevron pointing in. Removed: the ring
+ dot + leader is the whole centre mark now.
THE WHEEL BOW (tried 6 June, REMOVED 6 June) — a slight outward curve of
the belt. Liked as a subtle cue but ran the two-line labels together;
belt is straight.

THE SHUTTER (locked 2 June, SUPERSEDED 4 June) — DCW and WP as one
manuscript divided by a curtain that covers/reveals without resizing;
WP always on top; DCW left, WP right; Full Screen = shutter to the page
side; grab-handle. Gone: there is one document (the WP / Treatment), no
curtain.
THE DCW AS A VERTICAL BOARD (locked 2 June, SUPERSEDED 4 June) —
scenes/chapters down a left spine, tracks as columns across the top,
stave dividers, chevron headers. Gone: the DCW is not a board of
columns; it is the timeline-of-events Treatment.
DCW × PLOT MAPPER FUSION AS BUILT (locked 1–2 June, SUPERSEDED 4 June)
— Float/Pin states of one column-board; three track types (Structural
note-cards / Curve / Ambient) as columns; the cascade (book → chapters
→ scenes → words); the entity panel on the right; the card as the
bridge to writing. The PRINCIPLE that planning and writing are one
instrument SURVIVES — but as "InkySwot IS the DCW / The Treatment", now
realised as the WHEEL, not as a column board.
DCW TERMINOLOGY — TRACKS / THREADS (locked 29 May, SUPERSEDED 4 June) —
"lanes are called Tracks; Threads are connections feeding Tracks." The
column/track model is gone. Connections still exist (Events/Chapters
store characters[], location, plotthreads[], subplots[]) but are not
displayed as Tracks.
THE NOTE CARD FACE (locked 30 May within Plot Mapping, SUPERSEDED
4 June) — type tab with full-stop, knot, flip-from-tab, red full-stop =
Dark Thoughts. Replaced by the QUIET NOTE grammar (no box/tab/knot/
full-stop), which is now the pop-up's grammar. Dark Thoughts the
feature survives; the tab mechanics do not.
WRITE SCREEN / FULL SCREEN / INDEX CARD (locked 28 May & 2 June,
SUPERSEDED/ABSORBED 4 June) — "Write" as a separate screen; "Full
Screen = shutter to the page side"; the floating Index Card system
tethered to highlighted entities. Absorbed: the WP / Treatment IS the
writing surface (now via the wheel's Writing Mode); the entity pop-up +
copy-paste replaces the Index Card mechanism. (Distraction-free writing
may return, redefined as WP + chrome hidden — not locked.)
INDENTATION RULE (locked 4 June, SUPERSEDED 6 June) — "timeline events
at the margin; everything else indented under its event." Belonged to
the multi-event long-scrolling page; with one scene per page it no
longer applies. The page now shows a scene's event(s) with a
"click to write" line; how multiple events sit on a page is OPEN.
THE WRITING CARD ("Scene." / Dialogue + Descriptive) (open since 2 June,
SUPERSEDED 4 June) — the keystone card you write inside. Gone with the
card model; writing now happens in the WP page at the event, opened via
the wheel.
"SNAP TO DEFAULT" / DRAG-TO-REORDER TRACKS / BRIGHT-RED FREEFORM /
IDEAS COLUMNS / MAKE-YOUR-OWN TRACKS (3 June column-board thinking,
SUPERSEDED 4 June) — all belonged to the grid-of-columns; not part of
the 4 June model unless re-introduced.
THE ONE-SCREEN DCW / X-RAY / LINEAR TAGGED CELLS (3 June, SUPERSEDED
4 June) — DCW on = bones, off = flesh; cells of TAG + CONTENT with (*)
handles; write-off-then-switch-on-and-it-asks; AI as a quality setting
(render once, store). Gone: the database is the bones; The Treatment
assembles them — no separate cell-grid to type into. The (*) handle
survives as the pop-up + copy.
THE FIRST 4 JUNE CLICK-TO-WRITE (inline gap growing under the event)
(SUPERSEDED later 4 June) — clicking "— click to write this scene —"
grew a small inline writing space in the assembled list. Superseded by
the WHEEL: clicking the centre opens the whole page clean in Writing
Mode, and the writer travels by the wheel.