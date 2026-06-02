File: inkyswot/locked-decisions.md
Last updated: 1 June 2026

PLATFORM IDENTITY
InkySwot is a writing platform. Not a content generation engine.
Assisted creation. Not instant generation.
This distinction is non-negotiable and must never be compromised.
Tagline: Publish and be damned. Always.
"Publish and be prepared" must never be used.

PRICING
Paid only. No free tier. No exceptions.
Monthly: £9.95. Annual: £99.50 (two months free).
14-day money back guarantee. No questions asked.
Locked: 24 May 2026.

PRICING PHILOSOPHY
One tier only. No feature gates.
The annual subscription is a loyalty reward. The product is identical.

PUBLICATION FEE
£1 GBP per publication. Base currency GBP.
Stripe handles international conversion automatically.
Paid users: one free publication per week. £1 after that.
Anti-scam friction. Not a revenue stream. Upfront and transparent.
Locked: 24 May 2026.

SECURITY SYSTEM — LOCKED LAYERS
Invisible to genuine users:
Device fingerprinting
IP tracking and location detection
Behaviour pattern detection
Disposable email detection
Stripe fraud detection
Visible but acceptable:
Email verification at signup
Paid upfront
14-day money back guarantee
Support ticket required for new device
Locked: 24 May 2026.

MARKETING POSITIONING — NEVER USE
Never market: "Write books instantly" / "Passive income publishing" /
"Make 100 books a week" / "AI author riches"
InkySwot markets to: writers, creators, worldbuilders, playwrights,
serious independents, disabled writers, dyslexic writers.
Locked: 24 May 2026.

FORMAT LIST — LOCKED
Academic Essay / Thesis / Audio Drama / Audiobook /
Autobiography / Biography / Children's Book / Comic Script /
Cookbook / Essay Collection / Flash Fiction / Game Script /
Graphic Novel / Literary Journal / Memoir / Non-Fiction /
Novel / Novella / Personal Essay / Creative Non-Fiction /
Picture Book / Poetry Collection / Radio Drama / Screenplay /
Short Story / Stage Play / Teleplay / Travel Writing / Other
Locked: 26 May 2026.

FORMAT GROUPS — LOCKED
Prose — Novel / Novella / Short Story / Flash Fiction /
Children's Book / Picture Book / Memoir / Biography /
Autobiography / Travel Writing / Non-Fiction /
Personal Essay / Academic Essay / Essay Collection /
Literary Journal / Cookbook
Script — Screenplay / Teleplay / Radio Drama / Audio Drama /
Stage Play / Comic Script / Game Script
Verse — Poetry Collection
Hybrid — Graphic Novel / Audiobook
Locked: 26 May 2026.

FORMAT-AWARE FORMATTING TOOLBAR — LOCKED
The writing panel toolbar adapts to the document format.
Each format displays only the tools relevant to it.
One codebase, conditional display.
Locked: 26 May 2026.

MANUSCRIPT FORMAT CHOSEN FIRST — LOCKED
Format is the first decision in project setup, before
Title, Genre, Style, Tone, or any other field.
Format drives the toolbar, the workspace layout, and the AI context.
Locked: 26 May 2026.

DCW TENSION CURVE — THREE MODES — LOCKED
Manual — writer drags the curve themselves.
AI-guided — writer sets target tension, Ada advises how to achieve it.
Analysis — Ada reads the text and plots the curve automatically.
Locked: 26 May 2026.

DCW TERMINOLOGY — LOCKED
DCW lanes are called TRACKS throughout the UI.
THREADS are the connections between Chapters and DCW Tracks.
Threads feed into Tracks. The Chapter stores Threads.
The DCW displays them as Tracks.
Locked: 29 May 2026.

DCW EMOTIONAL MAPS — LOCKED
Emotional Maps are curves tracking the rise and fall of a specific
emotion belonging to a specific character across chapters.
The word Map is deliberate — it names the line now and
future-proofs a full cartographic emotional view of a character.
Multiple Maps per character. Colour coded. Toggleable.
Full spec in dcw.md.
Locked: 28 May 2026.

GENRE — THREE FIELDS — LOCKED
One primary genre, two sub-genres. Three fields, not a dropdown.
All three feed AI context.
Note: a temporary combined genre dropdown was built on 28 May 2026
as a development placeholder. The three-field system is the locked
decision and will be implemented in Step 1.
Locked: 27 May 2026.

WRITE SCREEN — LOCKED DECISIONS
The writing panel is called Write. Locked: 28 May 2026.
Distraction-free mode is called Full Screen. Locked: 28 May 2026.
Desktop only. No mobile. Locked: 28 May 2026.
Index Card system — floating cards tethered to highlighted
entities in the manuscript. Cards only appear on deliberate
click — never automatically. Locked: 28 May 2026.
Scan on space bar press only — current page only.
Database change triggers full manuscript rescan in background.
Locked: 28 May 2026.

THREADS — LOCKED
Threads are the connections between a Chapter and the DCW.
When a character, location, plot thread or subplot is tagged
in a Chapter, that connection is a Thread.
Threads feed directly into DCW Tracks.
The Chapter stores Threads. The DCW displays them as Tracks.
Locked: 29 May 2026.

HOME PAGE — MY PROJECTS — LOCKED
My Projects is the home page. It is the screen a writer lands on
at login and returns to. It is the hub, not a fixed path.
After login the writer navigates freely from the nav menu —
no forced route. The only unavoidable sequence is the one-time
setup of a NEW project (New Project → Manuscript Format → Overview),
because the project must exist before it can be navigated.
LAUNCHPAD: four items live BOTH in the nav menu AND on the
My Projects home page —
Plot Mapping / The Press / Create First Project / Open Project.
Each home-page item carries an icon, a title, and a two-line strap.
Icons: clean SVG line art using stroke="currentColor" so they
recolour with Tone (gold on dark, ink on light). No PNGs.
Stored at CODE/home-icons.svg.
(Strap wording not yet finally signed off — confirm before building.)
Locked: 31 May 2026.

USER JOURNEY — TWO SHAPES — LOCKED
Before login: a fixed path (no nav menu yet) —
Landing Page → Sign Up / Log In → Login page.
After login: an open hub — My Projects (home), then the nav menu
takes the writer anywhere, in any order. No forced route.
The only surviving sequence is the one-time new-project setup,
which is necessity, not an imposed path.
Locked: 31 May 2026.

THE PRESS — TWO DOORS — LOCKED
The Press is ONE tool with two entry points.
INSIDE (members): a screen reached from the nav, where a logged-in
subscriber publishes their book.
OUTSIDE (public): the same publishing tool behind its own public
door — press.inkyswot.com — also reachable from the landing page.
A non-subscriber signs up here (a lightweight Press sign-up),
pays per book, and publishes without a platform subscription.
A public Press sign-up makes someone a member of THE PRESS ONLY.
They get a login to The Press and may use it as often as they wish.
They have NO access to the platform itself. The paid-only platform
stays sealed.
Upsell: gentle, no push. Their email is captured, so they receive
The InkySwot Bugle — the slow funnel.
BUILD NOTE: the public Press must be CLONED, not merely re-skinned,
because it needs a DIFFERENT payment gateway from the in-platform
Press. Shared publishing engine; separate sign-up, login and payment
for the public version.
Locked: 31 May 2026.

THE PRESS — LOCKED
Named: The Press. Locked: 29 May 2026.
Where the writer goes when the book is done.
Separate section of InkySwot — not part of the project nav.
Also a standalone pay-per-book product for non-subscribers (see
THE PRESS — TWO DOORS above).
The Press is an acquisition funnel for InkySwot.
Replaces and significantly expands Step 15 in the build order.
Full spec in press.md.
Key features locked:
Cover Creator — Fixed Spine System. The spine is built at
maximum width. Front and back covers slide over it,
masking whatever is not needed. No recalculating. No rebuilding.
Book Layout Tool — open book on screen. Flippable pages.
What the writer sees is what prints.
Platform Requirements Database — live, maintained, always current.
Front and Back Matter Assembly — auto-assembled from database.
Ada writes blurb, bio, acknowledgements. Writer refines.
Supported formats: Paperback / Hardback / Ebook.
Audiobook: future.
Supported platforms: KDP / IngramSpark / Lulu /
Draft2Digital / Kobo / Apple Books / Barnes & Noble / Other.
Maintenance commitment: platform requirements database
monitored and updated whenever any platform changes its specs.
This is an ongoing operational commitment. Non-negotiable.
Locked: 29 May 2026.

PLOT MAPPING — LOCKED
Named: Plot Mapping. The story corkboard — a thinking space for
sketching a story before committing to it.
ONE Plot Mapper. Per project — each project has its own board.
On 31 May 2026 its NAV LINK was moved up into Navigate so it is
reachable front-of-house (a writer can open it to think before
committing to a project). The tool itself stays per-project,
unchanged. There is no second mapper.
Standalone mockup complete 30 May 2026. Code stored at
CODE/map-plotter.html. To be built into index.html.
Saved the same way as everything else for now; moves to Supabase
at Step 4 with the rest.
Note types: Character / Location / Plot Thread / Event / Object /
Subplot / Free Note. Type is chosen when the note is made.
No change-type after creation — delete and remake if wrong.
The note tab carries the type label, with a full-stop after it.
The tab does three jobs: shows the type, click to flip, drag to connect.
Click the tab — the note flips to its back: DARK THOUGHTS, a private
panel, the writer's eyes only. Never exported. Never sent to InkySwot.
The full-stop after the type goes RED when a note has Dark Thoughts.
Drag from the tab — pulls a thread to another note (no mode needed).
The Connect button stays as the alternative way to join notes.
Copy system: a note can be copied to place one beat in several chapters.
The front is shared across the whole set — edit any copy's front and
all change. Each back (Dark Thoughts) is independent — its own per copy.
A copy starts with a blank back. Counter bottom-right reads "n of n",
showing only when the set has more than one. Renumbers on add/delete.
Chapter dividers: each chapter boundary has a toggle button on the
timeline strip — click to raise the divider full height, click to drop
it. A grip at the top of a raised divider drags it to any height.
SECTION ? help pill — top-right of the screen, gold border.
Opens a slide-in guide headed with the section name.
This is a TEMPLATE pattern for every screen — same pill, same place,
each screen supplies its own words. The general manual stays separate
in the Help menu.
Note: the help pill is intended to float (for theatre) — not yet built.
Locked: 30 May 2026. Nav-link move locked: 31 May 2026.
NOTE (1 June 2026): Plot Mapping and the DCW now FUSE into one
instrument — see DCW × PLOT MAPPER FUSION below. Everything locked
above (note types, tab, Dark Thoughts, copy system, dividers, the lift)
carries forward unchanged into the fused tool.

PLOT MAPPING TIMELINE — BELOW CHAPTER 1 — LOCKED ("the lift")
One Plot Map per project — never multiple maps.
The backstory is not a separate map; it is the basement of the same one.
Think of the timeline like a lift. Above the line the chapters climb;
below it you descend into the Prologue, and below that the Backstories.
Top to bottom: Chapter 3 / Chapter 2 / Chapter 1 / Prologue /
Backstory 1 / Backstory 2 / Backstory 3.
Same board, same notes, same threads — the timeline just has a downstairs.
Locked: 30 May 2026.

DCW × PLOT MAPPER FUSION — LOCKED (1 June 2026)
The Plot Mapper and the DCW are ONE instrument. Not two screens.
Float (corkboard thinking) and Pin (timeline structure) are two states
of the same board. Same notes, same gesture: scatter → arrange → pin.
The DCW is a full top-down screen in its own right — tracks cascade
down from the chapter ruler. This SUPERSEDES the old "strip below the
three panels" model.
THREE TRACK TYPES:
  Type 1 — Structural (block-based): Character / Plot / Subplot /
    Location / Event / Object / Theme / Notes.
  Type 2 — Curve (a continuous line): Tension / Emotional Maps.
  Type 3 — Ambient / world (block-based): Atmosphere / Weather / Time.
TIME IS A BLOCK, not a ruler mode. The horizontal axis is fixed
reading order; Time blocks declare story-time, so a single chapter can
hold present / past / future blocks (flashbacks, intercut timelines).
CARDS HOLD TEXT. A note card is not a label — it opens to hold prose.
THE CASCADE: zoom is the main control. Book → chapters → scenes →
words. Open a beat and it unfolds; write at the bottom and it rolls up
(block, curve and summary all update). Nothing is entered twice.
THE CARD IS THE BRIDGE from planning to writing. Closed on the board it
is a beat in context; opened it is the page you write on. The Write
screen is the DCW opened all the way down.
A dedicated WRITING card type exists — the keystone. The other types
describe the story; this one contains it. Working name "Scene." —
NAME NOT YET LOCKED.
Full detail in dcw.md. Mockups built 1 June 2026: the scene-level DCW
and the fusion trial (Plot Mapper cards on the DCW board).

SECTION HELP PILL — TEMPLATE PATTERN — LOCKED
Every screen carries a help pill, top-right, gold border, reading
SECTION ? — clicking it opens a slide-in guide headed with that
screen's name (what it is / how to use it / a tip).
Same pill, same place, every screen. Each screen supplies its own words.
This is the in-context help system. The full manual stays separate
in the Help menu (Tutorial / Manual / FAQs / What's New).
First built on Plot Mapping (30 May 2026) as the template.
Locked: 30 May 2026.

SIGNUP
Email + password → Email verification → Platform access.
No SSO. No third party authentication. Email and password only.
Locked: 25 May 2026.

DATA
InkySwot never sells user data. Ever.
GDPR compliant. Deletion within 30 days.

SINGLE FILE ARCHITECTURE
The app is a single HTML file.
Locked: 26 May 2026.

ADA
Female. Named after Ada Lovelace. Voice fixed as
Google UK English Female. Sara Martin will NOT voice Ada.
Ada is a contextual creative collaborator — not a search engine,
not a writing generator. She gives the writer's answer, filtered
through everything they have already built.
Ada spec must be complete before any further screens are built.
Ada build is Step 12. This does not change.
Locked: confirmed.

COVER THUMBNAIL — REMOVED
Not being built. AI-generated cover concepts post-launch only.

AUTHENTICATION
Email + password only. No SSO. No third party authentication.
Locked: 25 May 2026.

UX MAP GAP 6 — RESOLVED
Import Project uses the same setup screen as New Project.
Manual entry. Same fields. No AI inference at this stage.
Post-launch consideration: AI inference from imported manuscript.
Locked: 26 May 2026.

OPEN — NOT YET DECIDED
Plot Mapping: whether a note can span a chapter range in the DCW
(e.g. a thread running Ch.3–Ch.9), in addition to the
copy-per-chapter system. Revisit when the DCW is built.
Home-page launchpad: final strap wording for the four items.
The Press (public door): where a non-subscriber's book data comes
from when they have no project on the platform — enter cold, or
upload a finished manuscript. Revisit before building the public Press.
Card fields: the per-type fields shown on the FRONT of each note card.
Writing card type: its final name (working name "Scene.").
Right-hand panel: whether the separate entity detail panel survives
the fusion, or the card's own front/back makes it redundant.