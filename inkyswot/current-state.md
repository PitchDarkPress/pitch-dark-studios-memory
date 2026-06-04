File: inkyswot/current-state.md
Last updated: 4 June 2026

WHO YOU ARE WORKING WITH
Kevin Martin (Kev). Writer, former professional actor and voice artist.
Based in Devon, England.
Runs Pitch Dark Press — one-person independent publishing imprint.
Works with his wife Sara, also a writer.
Has dyslexia — one step at a time always. Never overwhelm.
Never give multiple instructions at once.
Mid-to-late sixties. Anthropic Max plan subscriber.
Coined Proauthorism — transparent, declared human-AI creative
collaboration. Website: proauthorist.com.

HOW TO WORK WITH KEV
One step at a time. Always. Never multiple instructions at once.
Explain before doing. Wait for confirmation before proceeding.
"n", "next", or "done" = confirmed, proceed.
Never assume a step is complete — wait for Kev to confirm.
Show changes locally before uploading to GitHub.
Persistent bugs — rebuild from scratch. Never patch on patch.
British English. Witty and direct. Match his register.
Never rush. Kev may be slow at some steps — this is fine.
Do NOT use multiple-choice button lists to ask questions — plain
questions only.
InkySwot = always capital I and capital S. Never inkyswot or Inkyswot.
PUBLISH AND BE DAMNED — no full stop. Ever.
If a decision is in the files, do not revisit it unless Kev asks.
GitHub organisation: PitchDarkPress.
At the start of any build session, ask Kev to paste in
the current index.html before any work begins.
The code is the truth. Never assume the files tell the
whole story.
Update the files at the end of a session. Rebuild clean —
never patch on patch. The .md is the single source of truth.
When updating a file, always rewrite the WHOLE file clean — never
hand back a list of patches or "replace this block" edits.
WHEN DESIGNING A LIVE MECHANISM (motion, scroll, interaction): do not
design it by description alone — build a small static mockup FIRST,
get the still picture agreed, THEN add the movement. Trying to specify
moving behaviour in words wastes Kev's time (learned the hard way on
the wheel, 4 June). A picture or sketch from Kev is worth more than
ten descriptions — ask for one.

================================================================
4 JUNE 2026 — THE SECOND TURN. INKYSWOT *IS* THE DCW.
(Plus, later the same day: THE WHEEL — click-to-write resolved.)
================================================================
Read this before anything else. Today simplified the whole platform,
then settled the heart of the writing experience.
The 3 June one-screen / X-ray / linear-tagged-cells model is
SUPERSEDED (kept as history at the foot of this file). It was still
too clever — it kept inventing a new authoring surface and towing the
old screens behind it as "to be reconciled" loose ends.

THE REALISATION
Stop inventing. Use what is already built.
- InkySwot IS THE DCW — all of it. The DCW was never a screen or a
  strip or a board. It is the whole instrument. Every section already
  built (Characters, Locations, Events, Plot Threads, etc.) is part of
  it. The database IS the bones of the story.
- THE TREATMENT is the DCW switched on — the place where everything
  already entered ASSEMBLES into a readable, writable whole.
- A plotline is not a new thing to author. It is a VIEW of data that
  already exists. The writer fills in the sections; The Treatment
  gathers them, in order, onto the page.

THE SPINE — A TIMELINE OF EVENTS
The DCW / The Treatment is a TIMELINE OF EVENTS. Three tiers:
  CHAPTER  →  SCENE  →  EVENT
- Only EVENTS sit on the line and become prose — because only events
  HAPPEN. Characters, Locations, Objects, etc. do not happen; they are
  REACHED INTO by the events that use them (via the pop-up).
- This answers the old "what is a row?" knot: the line is made of
  events, not of everything.
- Chapters and Scenes are the dividers. A SCENE is labelled "Scene 1",
  "Scene 2"… and the writer may add an optional title ("Scene 1 — The
  Counting-House"). Events live under their scene.

"FILL IN THE BLANKS" — THE DESIGN PRINCIPLE
The Treatment assembles itself from everything in the database — not
just names, the SUBSTANCE — and leaves the writer the blanks: the
prose and dialogue no database can hold. The writer is never facing a
blank page; they face a page three-quarters built, with holes shaped
exactly like the writing only they can do. The sections are not
reference material off to one side — assembled, they ARE the draft;
the writing is the last layer, not the first.

================================================================
THE WHEEL — CLICK-TO-WRITE, RESOLVED (4 June, later session)
================================================================
The old "OPEN DECISION 1" (inline-grow vs focused writing surface) is
SETTLED — and the answer was neither. It is a WHEEL.

THE LAYOUT
- The WP / Treatment page sits SHIFTED TO THE RIGHT of the dark
  workspace. The LEFT is kept clear for the entity POP-UP note (which
  will live on the left, draggable, as already specced).
- Out in the dark to the RIGHT of the page is THE WHEEL — a vertical
  belt of section labels (staves, scenes, events) with a FIXED gold
  CENTRE LINE (a small gold node marks it).

HOW THE WHEEL WORKS (the mechanism)
- The labels are big, roomy text (Crimson Pro ~21px) with generous
  line spacing — calm and grand, not a cramped list.
- As you SCROLL THE PAGE, the wheel TURNS. Whatever label sits on the
  fixed centre line is WHERE YOU ARE. It lights gold and grows a
  horizontal leader line out to the right (only the centre gets the
  line).
- THE SPLIT: the centre label floats ALONE on the line. Everything
  BEFORE it bunches tight just above a FIXED gap; everything AFTER it
  bunches tight just below a FIXED gap. The gap above and below the
  centre never closes — the bunches grow away from it. (Kev confirmed
  the clusters/gaps are "in EXACTLY the right places".)
- A WINDOW only: the wheel shows only ~3 labels each side of centre.
  Labels FADE IN as they enter the window and FADE OUT as they leave,
  so the wheel stays calm however long the book is — it never tries to
  move the whole list past you.
- The motion is EASED (glides toward target, doesn't snap 1:1 to
  scroll) and deliberately SLOW. Glide rate in the mockup is 0.072
  (was 0.12 — slowed 40% at Kev's request). Bigger line spacing also
  means each label covers more scroll, which calms it further.

TWO STATES — OVERVIEW and WRITING MODE
- OVERVIEW: the assembled Treatment shows on the page; the wheel turns
  with the scroll; centre = where you are. Click a NON-centre wheel
  label to roll it to centre. Click the CENTRE label (or a
  "— click to write this scene —" on the page) to enter Writing Mode.
- WRITING MODE: the page opens CLEAN for that one scene — the scene
  line + the event title near the top, then the whole page given over
  to a full-height writing area (this matches the image Kev approved).
  The wheel stays lit beside you, locked with that scene at centre.
  CLICK ANY WHEEL LABEL to open THAT section to write — you travel
  scene-to-scene BY THE WHEEL without leaving Writing Mode. Each
  scene's text is remembered as you move between them.
- A "‹ overview" control (top-right, shown only in Writing Mode)
  returns to the assembled Treatment, rolling the scene you were
  writing back to centre.

THE PRINCIPLE: the writing position and the map position are the SAME
thing. You write at the centre line; the wheel always shows what you
have passed (above), where you are (centre), and what is coming
(below). You never leave the writing to move about the book.

MOCKUP BUILT THIS SESSION (the LIVE DESIGN SOURCE — supersedes the
earlier 4 June WP/Treatment mockup; store + index in the CODE locker):
the WHEEL on "A Christmas Carol" — page shifted right; big eased
windowed wheel with fixed centre line and leader; split bunches with
fixed gaps; Overview ↔ Writing Mode; wheel-driven travel between
scenes; "‹ overview" to leave. Built up from an agreed STATIC sketch
first (bundles/labels), then the movement added — that method worked
where description alone failed.

STILL OPEN ON THE WHEEL (small, next time):
- The pop-up note that lives on the LEFT is not yet built into this
  mockup — the space is reserved for it.
- Whether wheel labels should be bigger/brighter AT centre vs uniform
  size — kept UNIFORM for now (Kev: "keep it the same, just get the
  mechanics right"). Revisit if wanted.
- How chapters/staves vs scenes vs events are visually distinguished
  on the wheel (tier styling) — currently all one treatment.

HOW THE WORLD IS REACHED — THE POP-UP (settled 4 June)
The writer reaches the database WITHOUT leaving the page, via a
stable, draggable pop-up panel. NOW SITS ON THE LEFT (the page having
moved right to make room).
- TWO STEPS from the NAV. Each nav section shows a live COUNT
  (Characters · 5, Locations · 3, Factions · 0). Click a section →
  a LIST of names pops up → click a name → that record opens. A
  "‹ back to list" link steps back. (A search box on the list is the
  natural future touch once a project has many entries — not yet
  needed, not yet built.)
- STABLE: click to open, click (✕) to close. It does NOT vanish on
  click-away and does NOT close when you select text inside it — so
  copy-and-paste is easy. DRAGGABLE: grab the header, move it clear of
  the prose; it stays where put.
- QUIET-NOTE GRAMMAR throughout (list, entries, kicker, back link):
  each entry is a SUB-TITLE in the SECTION's colour, a DESCRIPTION in
  neutral ink beneath, closed by a SOLID end-line in the section
  colour. Characters read gold; Locations read teal; each section its
  own colour. Colour = wayfinding (what kind of thing this is).
- Each entry has a COPY button. The mechanism for getting info into
  the WP is COPY AND PASTE (Kev's call — honest, learnable, unbreakable,
  writer stays in charge; nothing lands the writer didn't choose).
  Copy takes TEXT ONLY: in the pop-up it wears the section colour; once
  pasted into the WP it arrives PLAIN, taking the page's own ink.
  Colour for FINDING in the panel; neutral ink for READING on the page.

THE WP — A REAL DOCUMENT PAGE (settled 4 June)
The main work area / The Treatment is a proper document page, Google-
Docs proportions (Letter, generous margins), on the dark workspace
with a page shadow — not a thin panel. NOW SHIFTED RIGHT (pop-up left).
- MAGNIFY (zoom): a − / 100% / + control scales the whole document in
  and out (70%–200%). It is ZOOM, not page-width. The page shape never
  changes; only the view magnifies.
- PAGE NUMBERS: centred at the foot of each page.
- TITLE PAGE: an optional first page, vertically-centred title + "by
  [author]", UNNUMBERED. Numbering starts at 1 on the page after it
  (manuscript convention). A "Title pg" toggle turns it on/off.
- TITLE + AUTHOR pull from Overview (Book Title, Author Name). Title
  centred on the page; "by [author]" beneath.
- Scrollbars: slim, dark, gold-on-hover everywhere. No Windows defaults.
- NOTE: pages are fixed-height sheets in the mockup. REAL pagination
  (prose flowing and breaking onto new numbered pages as you write) is
  a bigger build, for when the writing surface is real. Kev understands
  this.

OPEN DECISIONS — STILL TO SETTLE (one at a time, next sessions)
1. WHERE THE MOOD WORDS LIVE. The chapter/scene mood words (e.g. Cold ·
   Bleak · Biting) were pulled OFF the page on 4 June — Kev wants them,
   but doesn't yet know where they belong. Parked, not lost.
2. EVENT ORDER WITHIN A SCENE. Events currently group by Chapter but
   have no sequence within a scene. The spine needs "this event before
   that one." Small but necessary — a line needs order. (The Events
   data already stores characters[] and location per event; it just
   lacks a position.)
(The old OPEN DECISION 1 — click-to-write — is now RESOLVED: the wheel.)

THE TAG SET (working list — carried, nothing pruned)
From Kev's working list: Action · Chapter · Character ·
Emotion · Event · Location · Note · Prose · Scene · Time.
Sorted by job:
  SPINE (the timeline)           — Chapter · Scene · Event
  FLESH (the writing)            — Prose · Action · (Dialogue — see NB)
  REFERENCE (via the pop-up)     — Character · Location · Time ·
                                   Emotion · Note
OPEN on the tag set:
- Is PROSE the same as ACTION, or distinct? (Working split: Action =
  what they do; Prose = description / narration.) UNDECIDED.
- DIALOGUE is not on Kev's list but a scene cannot be written
  without spoken lines — confirm Dialogue's place.
- Is EMOTION a per-beat TAG, or the seed of the old Emotional Map
  (a curve over time)? UNDECIDED.

WHAT INKYSWOT IS
Web-based story world-building and production platform.
The world's first Digital Creative Workstation (DCW) for writers.
Single HTML file. InkySwot IS the DCW — see the top of this file.
Live at: inkyswot-app.vercel.app
DNS to app.inkyswot.com pending (UK Cheapest).

IDENTITY & BRANDING
Name: InkySwot (capital I, capital S. Always.)
Tagline: Publish and be damned.
App hero text: PUBLISH AND BE DAMNED (no full stop)
Landing line: The world's first Digital Creative Workstation
for writers (no full stop)
Owned term: DCW — Digital Creative Workstation.
Said as three letters: D.C.W.
Newsletter: The InkySwot Bugle
AI position: AI welcome. AI optional. Always writer-led.

COLOURS — FROM LIVE CODE
Dark: #0f0d0a / #18120d / #221a14 (deepest #0a0806)
Ink: #e8e0d0 / #b0a090 / #706050
Gold: #c9923a / #e8b060
Rule: #221709 / #352815 / #241a10
Light: #fafaf8 / #f0ede6 / #e8e4dc
Danger: #c43a2a
Success: #2a6b3a
Page (WP white): #f7f4ec / page ink #221a14 / page mute #8a7d68
Section colours (pop-up, provisional): Character #cba36a (gold-tan) /
  Location #5fa898 (teal) / others to be assigned per section.
Dark-thoughts marker: grey-violet (#8f8fa6, provisional).
Input bg: #18120d / Input border: #352815
Card bg: #18120d / Card border: #352815

FONTS
Playfair Display 900
Crimson Pro 300/400/600
JetBrains Mono 300/400/500
All Google Fonts.

PRICING
Paid only. No free tier. No exceptions.
Monthly: £9.95 / 150 prompts per day / everything included
Annual: £99.50 / two months free / same everything
Top-up: £1.99 for 500 prompts / available, never pushed
Lifetime: by invitation / Kev, Sara, early testers / everything forever
14-day money back guarantee / no questions asked
Publication fee: £1 GBP per publication / base currency GBP /
Stripe handles international conversion /
Paid users: one free publication per week / £1 after that
Ada's contextual observations are FREE — do not count against
prompt allowance. Ada conversational responses count.
Lifetime members: infinity symbol in header instead of number.
Server-side flag: is_lifetime: true in Supabase.
Must be before F12 blocker.

NOTE ON PROMPT COUNTER IN CODE
The current code shows a 20-call daily counter in localStorage.
This is a development placeholder only — not product pricing.
Real prompt tracking moves server-side in Step 7.
Pricing is locked — see locked-decisions.md.
Adjust counter limits when final costs are confirmed pre-launch.

TECHNICAL
Version: v4.7 — pre-Step 1 rebuild.
Autumn 2026 launch target.
Repo: PitchDarkPress/inkyswot-app
Vercel Hobby (free). Auto-deploys on push to main.
API: claude-haiku-4-5-20251001
Key: inkyswot-app-2 — Vercel Environment Variables ONLY.
NEVER IN GITHUB.
Read Aloud bug fix in place: Chrome async cancel() fix —
captures wasThisField and wasSpeaking before cancel fires,
then uses setTimeout 100ms before re-speaking. Do not revisit.

FILES IN REPO — inkyswot-app
index.html — the app workspace
login.html — the login / sign up gate (single tabbed page)
inkylogin-bg.png — login page background image (currently unused)
inkyswot-daw.html — DCW mockup (OLD horizontal strip — SUPERSEDED).
Kept only as history.
CODE/ — the code locker (finished and in-progress code, stored
separately from the .md notes). See CODE/README.md for the index.
CODE/README.md — locker index, lists each stored file and status.
CODE/map-plotter.html — Plot Mapping standalone mockup (30 May 2026).
SUPERSEDED; kept as history.
CODE/home-icons.svg — the four home-page launchpad icons, clean
SVG line art using stroke="currentColor" so they recolour with Tone.
Stored 31 May 2026. Awaiting integration into the My Projects screen.
CODE/dcw-vertical.html — the vertical DCW + shutter frame.
SUPERSEDED (shutter dumped 3 June 2026). Kept as history.
NOTE: the 3 June one-screen mockups AND the earlier 4 June WP/Treatment
mockup are now SUPERSEDED by the 4 June WHEEL mockup. The WHEEL mockup
is the live design source — store and index it in the locker.

FILES IN REPO — inkyswot (landing page)
index.html — the landing page
CNAME — www.inkyswot.com

BUILD RULES
Fix before moving on. No snag lists. No deferred problems.
No patches on patches. One step at a time.
Explain before doing. Wait for confirmation.
Persistent bugs: rebuild from scratch. Never overwhelm.
When updating files, rewrite the whole file clean — never patch.

WHAT IS BUILT AND WORKING
Landing page (inkyswot.com) — ticker, clocks, Log In / Sign Up buttons.
Login page (app.inkyswot.com/login.html) — members access gate,
fixed panel, Log In and Sign Up tabs. Stubbed — not yet wired to Supabase.
Both forms show "not yet open" message on submit — no routing to app.
My Projects / Trash / New Project modal /
Overview / Characters / Relationships / Factions & Orgs /
Language & Dialogue / Locations / Buildings / Objects & Artefacts /
Rules & Lore / Plot Threads / Subplots / Themes & Motifs /
Events & Timeline / Chapters / The Treatment (placeholder shell only) /
AI Expand / AI ON/OFF toggle /
Read Aloud (with Chrome async cancel() bug fix in place) /
Light-dark mode / Voice selector
NB (from the code, 4 June): The Treatment screen is an EMPTY
placeholder — "The Treatment builds itself. Keep writing." No editor,
no logic. It is the named, waiting home for the timeline-of-events /
fill-in-the-blanks Treatment — now the WHEEL. Every database screen
already collects the connections the Treatment needs — Events store
characters[] and location; Chapters store characters[], location,
plotthreads[], subplots[]. The data is already there.

NAV — CONFIRMED (31 May), with 4 June ADDITIONS
Navigate: My Projects / The Press / Plot Mapping
Project: Overview / Cast (Characters / Relationships /
Factions & Orgs / Language & Dialogue) /
World (Locations / Buildings / Objects & Artefacts / Rules & Lore) /
Plot (Plot Threads / Subplots / Themes & Motifs / Events & Timeline) /
Library (Research & Reference / Notes & Scratchpad / Sandbox) /
Chapters (Chapters / The Treatment) /
DCW (Timeline / Storyboard)
Help: Tutorial / Manual / FAQs / What's New
Trash: its own section at the foot of the sidebar.
4 JUNE ADDITIONS / PENDING:
- Each nav section to show a LIVE COUNT (read .length from the saved
  array): Characters · 5, Locations · 3, Factions · 0 (zero greyed).
  Clicking a counted section opens the two-step pop-up (list → record),
  which now appears on the LEFT.
- Under "InkySwot IS the DCW": Plot Mapping and the DCW collapse toward
  The Treatment. The old DCW sub-entries (Timeline / Storyboard) are
  superseded. Re-work the nav now the Treatment/wheel direction is
  agreed. The Treatment is the live home of the DCW.

HOME PAGE — MY PROJECTS (31 May 2026)
My Projects is the home page — the screen a writer lands on at login
and returns to. The hub, not a fixed path. After login the writer
navigates freely; no forced route (only exception: one-time NEW project
setup, which must create the project before it can be navigated).
Launchpad: four items live BOTH in the nav AND on the home page, each
with an icon, a title, and a two-line strap:
- Plot Mapping — "Map ideas. See the pattern." — constellation icon
- The Press — "Publish. Make it permanent." — printing press icon
- Create First Project — "Begin the work. Claim the page." — typewriter
- Open Project — "Return to what matters." — drawer-chest icon
Icons stored at CODE/home-icons.svg (stroke="currentColor", recolour
with Tone; no PNGs). Straps not finally signed off — confirm before
building. Build step still to do: lay out the four-item row on My
Projects using the stored icons. Preview before touching index.html.

WHAT IS STUBBED (placeholder screen only — Step 1)
Research & Reference / Notes & Scratchpad / Sandbox /
Tutorial / Manual / FAQs / What's New /
The Press / Plot Mapping (both show Coming Soon until built).
All stubbed screens show "Coming Soon". Build to same pattern as
existing screens. Research & Reference, Notes & Scratchpad and Sandbox
are deferred until after the writing surface is built (Step 10).

WHAT IS NOT YET IN THE APP (Step 1 work)
Home-page launchpad row (four items with icons and straps)
Nav section live counts (4 June)
Manuscript Format screen (new — first step before Overview)
Format-aware formatting toolbar (adapts to manuscript type)
Style Field (tone/voice dropdown + free text on Overview)
Three-field genre (replaces single dropdown)
Import option in New Project modal
Section help pill (SECTION ?) — template pattern for every screen
The Treatment / DCW — now THE WHEEL (the page shifted right; the eased
windowed wheel; Overview ↔ Writing Mode; the entity pop-up on the left)
All remaining stubbed screens

MANUSCRIPT FORMAT LIST — CONFIRMED
Academic Essay / Thesis / Audio Drama / Audiobook /
Autobiography / Biography / Children's Book / Comic Script /
Cookbook / Essay Collection / Flash Fiction / Game Script /
Graphic Novel / Literary Journal / Memoir / Non-Fiction /
Novel / Novella / Personal Essay / Creative Non-Fiction /
Picture Book / Poetry Collection / Radio Drama / Screenplay /
Short Story / Stage Play / Teleplay / Travel Writing / Other

FORMAT GROUPS — CONFIRMED
Prose — Novel / Novella / Short Story / Flash Fiction /
Children's Book / Picture Book / Memoir / Biography /
Autobiography / Travel Writing / Non-Fiction /
Personal Essay / Academic Essay / Essay Collection /
Literary Journal / Cookbook
Script — Screenplay / Teleplay / Radio Drama / Audio Drama /
Stage Play / Comic Script / Game Script
Verse — Poetry Collection
Hybrid — Graphic Novel / Audiobook

GENRE LIST — CONFIRMED
48 entries. Flat alphabetical. No optgroups.
Academic Essay / Thesis / Adventure / Audio Drama / Audiobook /
Autobiography / Memoir / Biography / Children's Book /
Comedy / Humour / Comic Script / Coming of Age / Cookbook /
Crime & Thriller / Drama / Dystopian / Erotic / Essay Collection /
Fantasy / Flash Fiction / Game Script / Gothic / Graphic Novel /
Historical Fiction / History / Horror / Literary Fiction /
Literary Journal / Non-Fiction / Novel / Novella / Other /
Paranormal / Personal Essay / Creative Non-Fiction / Picture Book /
Poetry / Radio Drama / Romance / Science Fiction / Self-Help /
Short Story / Speculative Fiction / Stage Play / Teleplay /
Thriller & Suspense / Travel Writing / True Crime /
Urban & Contemporary / Western
Locked: 28 May 2026.

LANDING PAGE — inkyswot.com
Ticker strip — InkySwot promo lines, seamless scroll, 15s speed.
World clocks — Tokyo / Sydney / New York / London (centre) /
Frankfurt / Dubai / Hong Kong.
Log In and Sign Up buttons — top right of ticker strip.
Both link to app.inkyswot.com/login.html.

LOGIN PAGE — app.inkyswot.com/login.html
Single file with two tabs — Log In and Sign Up.
Full screen dark panel. Fixed size — never moves between tabs.
Log In tab: Email / Password / Enter button / Forgot password.
Sign Up tab: Email / Password / Confirm Password / Request Admission.
Both tabs show "not yet open" message on submit.
Authentication stubbed — wires to Supabase in Step 4.
Do not add routing to index.html until Step 4 is complete.

UX MAP — USER JOURNEY (31 May 2026)
BEFORE login it is a fixed path — no nav menu yet:
Landing Page (inkyswot.com) → Decide: Sign Up or Log In →
Login page (app.inkyswot.com/login.html).
AFTER login it is an open hub:
→ My Projects (home — the launchpad) → nav takes the writer anywhere.
The four launchpad options are reachable from nav and home page.
Only surviving sequence after login: one-time NEW project setup —
New Project → Manuscript Format → Overview — because the project must
exist before it can be navigated. Import Project follows the same setup
path, then the writer enters the workspace, adds entities to the
database, then writes.

THE PRESS — TWO DOORS (31 May 2026)
One tool, two entry points.
INSIDE (members): a nav screen where a logged-in subscriber publishes.
OUTSIDE (public): the same tool behind its own public door —
press.inkyswot.com — reached also from the landing page. A non-sub
signs up here (lightweight Press sign-up), pays per book, publishes
without a platform subscription. A public Press sign-up = member of
THE PRESS ONLY: a login to The Press, no access to the platform. The
paid-only platform stays sealed. Upsell gentle: email captured → The
InkySwot Bugle (the slow funnel).
BUILD NOTE: the public Press must be CLONED, not re-skinned — it needs
a DIFFERENT payment gateway. Shared publishing engine; separate
sign-up, login, payment. Full spec in press.md. Replaces/expands Step 15.

UX MAP GAPS — STATUS
Gap 1: Free-to-paid upgrade trigger — RESOLVED. Paid only.
Gap 2: Publishing fee presentation — RESOLVED. £1 GBP upfront.
Gap 3: Export Suite conversion moment — RESOLVED. No upgrade wall.
Gap 4: Font import in Publishing Suite — NOT RESOLVED. TBD before Step 14.
Gap 5: Document types in New Project modal — NOT RESOLVED. TBD before Step 1.
Gap 6: Import/migration route — RESOLVED. Manual entry, same fields.
Open question (public Press): where a non-sub's book data comes from
with no platform project — enter cold, or upload a finished manuscript.
TBD. Post-launch consideration: AI inference from imported manuscript.

PLATFORM LAYOUT (4 June — updated for the wheel)
Top menu (project name; word count + magnify + title-page controls
top-right; "‹ overview" appears top-right in Writing Mode; Ada when
AI ON), left nav (with counts). The WP / Treatment is the main work
area (a real document page) but SHIFTED RIGHT — the LEFT of the dark
workspace holds the entity POP-UP note. To the RIGHT of the page is
THE WHEEL (the navigate-and-write instrument). No shutter, no strip,
no board, no separate Writing Panel. The Press — separate section,
own entry point (two doors).

SECTION HELP PILL — TEMPLATE PATTERN
First built on the Plot Mapping mockup (30 May 2026). Every screen
carries a help pill, top-right, gold border, reading SECTION ? —
clicking opens a slide-in guide headed with that screen's name (what
it is / how to use it / a tip). Same pill, same place, every screen;
each supplies its own words. The in-context help system. The full
manual stays separate (Help menu). Intended to float — not yet built.

THE TREATMENT / THE DCW — THE CORE (see top of file for the model and
the wheel). Full spec in dcw.md (rewritten 4 June for the wheel). In
short: InkySwot IS the DCW. The Treatment is it switched on — a timeline
of events (Chapter → Scene → Event), assembled from the database,
written by filling in the blanks. You navigate AND write by THE WHEEL
(page right, pop-up left). The WP is a real document page (magnify,
page numbers, optional title page).

CARRIED, TO BE RE-FITTED (from earlier DCW thinking — not yet placed
in the new model): Tension curve (three modes — Manual / AI-Guided /
Analysis), Emotional Maps, Ambient (Atmosphere / Weather / Time, Time
as a block). HOW these live in the timeline-of-events / wheel Treatment
is open. Dark Thoughts (private, never exported) also carried. The
SECTION ? help pill carries.

THE PRESS — CONTENTS
Full spec in press.md. (Two-door model above.)
Where the writer goes when the book is done. Separate section, not part
of the project nav. Also a standalone pay-per-book product for non-subs.
An acquisition funnel for InkySwot.
Includes: Cover Creator / Book Layout Tool / Front and Back Matter
Assembly / Platform Requirements Database / Metadata / Validation /
The Guide. Supports: Paperback / Hardback / Ebook. Future: Audiobook.
Platforms: KDP / IngramSpark / Lulu / Draft2Digital / Kobo / Apple
Books / Barnes & Noble Press / Other. Replaces/expands Step 15.

ADA
Full spec in ada.md.
Name: Ada. Named after Ada Lovelace — the first programmer.
Female. Fixed. Not a user setting.
A contextual creative collaborator. Not a search engine. Not a writing
generator. She gives the writer's answer — filtered through everything
they have already built. Position: top menu, between project name and
prompt counter. AI tools surface contextually; visible when AI ON,
hidden when AI OFF. Voice: Google UK English Female (browser
speechSynthesis). Ada spec must be complete before any further screens
are built. Ada build is Step 12.
NB: under the 4 June model, AI is never required for the Treatment to
work — assembling the database into the page, the wheel, and copy-paste
are all plain mechanics. Ada IMPROVES the experience (e.g. helping shape
pasted substance into prose) but the writer's book stands without her.

SECURITY
Full security system in security.md.
Core principle: paid only removes the primary abuse vector.
Seven-layer system locked 24 May 2026.
API key: Vercel Environment Variables ONLY. Never in GitHub, never in
client code. Prompt counter security: Steps 5–7. Non-negotiable before
launch. Signup route: Email + password → email verification code →
platform access. No SSO. No third-party auth. Email and password only.

SPECIALIST FILES — INKYSWOT ONLY
build-list.md — paste in at the start of any build session.
Others: paste in only when working on that area. Always tell Kev which
file you need and why before asking.
ada.md — Full Ada specification.
security.md — Full security system.
dcw.md — Full DCW specification (rewritten 4 June for "InkySwot IS the
DCW / The Treatment / THE WHEEL"). The 3 June one-screen spec and the
column-board specs are history within it.
press.md — Full Press specification.
future.md — Future ideas, not yet on the build list. (Includes the
two pre-filled demo books — see below.)
locked-decisions.md — the locked decisions.
CODE/ — the code locker.

BUILD ORDER — CONFIRMED (Treatment/DCW redefined 4 June; wheel settled)
Step 1 — v4.0 App Shell Rebuild (NOT YET STARTED)
Step 2 — Walk the Platform
Step 3 — Sign Off Layout and Journey (Gate)
Step 4 — Supabase
Step 5 — Lifetime Membership Flag
Step 6 — F12 / Security Blocker
Step 7 — Server-Side Prompt Tracking
Step 8 — Stripe
Step 9 — Resend
Step 10 — Writing surface (the WP page — magnify, page numbers, title
  page; the entity pop-up on the left). NB: under "InkySwot IS the DCW",
  the writing surface, The Treatment (Step 11) and the DCW (Step 13)
  are CONVERGING into the WHEEL — likely ONE build. Reconcile the step
  list when the wheel is built for real.
Step 11 — The Treatment (the timeline of events / fill-in-the-blanks /
  the wheel)
Step 12 — Ada
Step 13 — DCW (now = The Treatment / the wheel; see above — converging)
Step 14 — Export Suite and Format Conversion
Step 15 — The Press (replaces Publishing Suite)
Step 16 — Admin Panel
Step 17 — PWA Manifest
Step 18 — Beta
Step 19 — Launch

CURRENT STATUS & NEXT ACTIONS
v4.7 pre-Step 1 rebuild. Autumn 2026 launch target.
Pricing locked — 24 May. Security designed — 24 May.
Landing page updated — 25 May. Login page built — 25 May.
Genre list rebuilt (48, flat) — 28 May. Subplots / Themes & Motifs /
Events & Timeline built — 28 May. Chapters built & wired — 29 May.
The Treatment SHELL built & wired — 29 May (still an empty placeholder).
The Press conceived & specced — 29 May. Section help pill pattern
built — 30 May. CODE locker created — 30 May.
31 May: user journey reworked (open hub; My Projects home); Press two-
door locked; nav updated; home launchpad decided; icons stored.
1 June: DCW × Plot Mapper fusion (later superseded).
2 June: vertical board + shutter (superseded).
3 June: THE TURN — one-screen X-ray / linear tagged cells (superseded).
4 June (morning): THE SECOND TURN — InkySwot IS the DCW; the Treatment
  is the database assembled; the entity pop-up; the WP as a real page.
4 June (later): THE WHEEL — click-to-write resolved. Page shifted
  right; eased windowed wheel with fixed centre line, split bunches,
  leader on the centre; Overview ↔ Writing Mode; travel by the wheel;
  "‹ overview" to leave. Built static-first then animated. The wheel
  mockup is the live design source.

NEXT (do in order, one at a time)
1. Build the entity POP-UP note on the LEFT into the wheel mockup
   (the space is reserved; the pop-up spec already exists).
2. Settle WHERE THE MOOD WORDS LIVE.
3. Settle EVENT ORDER WITHIN A SCENE (give events a position).
4. Settle the tag-set opens: Prose vs Action; Dialogue's place;
   Emotion as tag vs Map.
5. Store + index the 4 June WHEEL mockup in the CODE locker (live
   design source; supersedes the earlier 4 June WP/Treatment mockup).
6. Build the home-page launchpad row + nav counts on My Projects
   (preview first; confirm the four straps).
7. Begin Step 1 — v4.0 app shell rebuild.
8. Resolve UX map gaps 4 and 5, and the public-Press data question.

PARKED / FUTURE (confirmed possible, NOT now — see future.md)
- TWO PRE-FILLED DEMO BOOKS: fully-populated, every-section-complete
  demo projects of "A Christmas Carol" and "The Wind in the Willows",
  so a new user can explore a finished world and see how InkySwot works.
  Both books are out of copyright (Dickens 1843; Grahame 1908) so text
  and characters are free to use. A demo = a normal project, pre-filled,
  ideally read-only. Build Carol first as the template (its bones are
  already in the mockup), then Willows to match. DEPENDS ON the app
  shell and sections being final — the demo must mirror the real thing.
  Open question for build time: whether the in-scene prose is written
  by Kev/adapted or sample-generated. Confirmed feasible 4 June; not
  scheduled.

================================================================
SUPERSEDED — KEPT AS HISTORY (do NOT build from any of this)
================================================================
- 4 JUNE (morning): the first WP/Treatment mockup (assembled list with
  "— click to write this scene —" growing an inline gap). The MODEL
  (database assembled; pop-up; real page) stands; the click-to-write
  MECHANISM is superseded by THE WHEEL (later 4 June).
- 3 JUNE: the ONE-SCREEN DCW / X-RAY model (DCW on = bones, off =
  flesh); LINEAR screenplay-style TAGGED CELLS (TAG + CONTENT) with (*)
  handles; write-with-it-off-then-switch-on-and-it-asks; AI as a
  quality setting (render once, store). Superseded 4 June: it was still
  inventing a new authoring surface.
- 2 JUNE: the VERTICAL board DCW (tracks as columns) + the SHUTTER
  (curtain covering/revealing DCW vs WP); the fused "one manuscript
  seen at two distances"; the prose-band reported onto the board.
- The horizontal STRIP DCW (inkyswot-daw.html).
- The old note CARD (type tab, knot, full-stop, flip-from-tab).
- "Snap to Default" / drag-to-reorder tracks; bright-red freeform /
  make-your-own tracks; Ideas columns — all from the column-board
  thinking; not part of the current model unless re-introduced.
- CODE/dcw-vertical.html, CODE/map-plotter.html, and the 3 June one-
  screen study mockups — kept only as history, NOT build targets.
RETAINED FROM HISTORY (still live, re-fitted to the new model):
the QUIET NOTE visual grammar (now the pop-up's grammar); the database
handle (now the pop-up + copy); Dark Thoughts; the SECTION ? help pill;
and CARRIED-but-unplaced: Tension curve (three modes), Emotional Maps,
Ambient (Atmosphere / Weather / Time).