File: inkyswot/current-state.md
Last updated: 7 June 2026

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
If a question genuinely cannot be answered without a choice, ask it as
a single plain either/or in prose — never a stacked list of options.
InkySwot = always capital I and capital S. Never inkyswot or Inkyswot.
PUBLISH AND BE DAMNED — no full stop. Ever.
If a decision is in the files, do not revisit it unless Kev asks.
GitHub organisation: PitchDarkPress.
At the start of any build session, ask Kev to paste in the current
code (index.html, or the current mockup) before any work begins.
The code is the truth. Never assume the files tell the whole story.
Update the files at the end of a session. Rebuild clean — never patch
on patch. The .md is the single source of truth; the code is the truth
above it.
When updating a file, always rewrite the WHOLE file clean — never hand
back a list of patches or "replace this block" edits.
WHEN DESIGNING A LIVE MECHANISM (motion, scroll, interaction): do not
design it by description alone — build a small STATIC mockup FIRST, get
the still picture agreed, THEN add the movement. Trying to specify
moving behaviour in words wastes Kev's time (learned the hard way on
the wheel). A picture or screenshot from Kev is worth more than ten
descriptions — ASK FOR ONE rather than guessing and nudging.
DISPLAY FREEZE: if edits stop showing on screen, do NOT keep editing —
do a CLEAN REBUILD in a fresh artifact. The artifact display freezes on
an old version; a clean rebuild fixes it instantly. (Bit us more than
once on the wheel.)

================================================================
THE MODEL — INKYSWOT *IS* THE DCW (settled 4 June 2026)
================================================================
Read this before anything else.
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
Three tiers: CHAPTER → SCENE → EVENT.
- Only EVENTS sit on the line and become prose — only events HAPPEN.
  Characters, Locations, Objects, etc. do not happen; they are REACHED
  INTO by the events that use them (via the pop-up).
- Chapters and Scenes are the dividers. A SCENE is labelled "Scene 1",
  "Scene 2"… with an optional title ("Scene 1 — The Counting-House").
  Events live under their scene.

"FILL IN THE BLANKS" — THE DESIGN PRINCIPLE
The Treatment assembles itself from everything in the database — not
just names, the SUBSTANCE — and leaves the writer the blanks: the prose
and dialogue no database can hold. The writer is never facing a blank
page; assembled, the sections ARE the draft; the writing is the last
layer, not the first.

================================================================
THE PAGE + THE WHEEL — AS BUILT (4 June settled; 6–7 June refined)
================================================================
Full spec in dcw.md. This is the heart of the writing experience.

THE PAGE — ONE SCENE PER FULL PAGE (6 June)
- ONE SCENE PER PAGE. Each scene sits on its own full US-Letter sheet
  (816 × 1056px). The old long-scrolling multi-event page is gone (too
  busy; made the wheel track too many close points).
- Pages are ALWAYS full height — a short scene leaves white space below
  it, like a real document page. Never shrunk to hug content.
- STAVE HEADING ON EVERY PAGE, top, for navigation — always know which
  stave you are in.
- On a page: running head top-right ("A Christmas Carol by Charles
  Dickens"); stave heading (JetBrains Mono caps, ruled under); scene
  heading (mono caps + optional italic title); the event(s) with a
  "— click to write this scene —" line; the writing surface (hidden
  until Writing Mode).

THE WHEEL — LAYOUT
- The page sits SHIFTED RIGHT. The LEFT of the dark workspace is for the
  entity POP-UP note (draggable; built and working). A 230px right
  sidebar sits far right (purpose TBD). The wheel lives in the CHANNEL
  between the page's right edge and that sidebar (grid 230px 1fr 230px).
- The wheel is a single hairline gold RAIL with small nodes and labels
  to its right, with a fixed gold CENTRE.

THE WHEEL — LABELS (two lines, 7 June)
- Every label is TWO LINES: a small gold JetBrains Mono caps KICKER
  ("STAVE ONE — SCENE ONE") and the SCENE TITLE beneath ("The
  Counting-House"). Every scene carries its full position.
- NO separate stave markers, NO blank stave pages — the stave is named
  on every scene via the kicker. (Separate stave rail-points were tried
  7 June and rejected: forced a blank page, didn't read right.)
- Stave/scene numbers computed in JS from a data-stave-open marker on
  each stave's first page.

THE WHEEL — BEHAVIOUR (as built)
- Page-scroll driven (not wheel-scroll). Whatever label is at centre is
  WHERE YOU ARE.
- CENTRE MARK: gold RING (17px, 2px border) + filled gold dot + a short
  gold LEADER line toward the centre label; the centre title lights
  gold. The bloom glow and » chevron were REMOVED (6 June) — one clean
  mark, no pointing at the obvious.
- WINDOW of NINE labels each side of centre (a map of the book using
  the full page height). Fade in/out at the edges.
- FADE even and gentle, with a brightness FLOOR so outer labels stay
  readable; centre + the two either side full brightness, the rest
  dimmed (~71%). Dimming is opacity only; label text colour uniform.
- MOTION eased and slow, ease rate 0.072; TIGHT=46, GAP=64.
- BELT IS STRAIGHT (BOW=0). A slight bow was tried/liked then removed —
  it ran the two-line labels together.
- LIVE HAND-OFF SMOOTHED: 0.35s CSS transition so the gold eases in/out
  as labels pass centre rather than snapping.
- HOVER lights ONLY the node gold; the text does not change on hover.
- positionWheel() centres the wheel block live in the channel at any
  width; labels wrap to ~half the channel width.

TWO STATES — OVERVIEW and WRITING MODE
- OVERVIEW: the assembled Treatment shows (one scene per page); the
  wheel turns with the scroll; centre = where you are. Click a wheel
  label to go to that scene; click the centre label (or "— click to
  write this scene —") to enter Writing Mode.
- WRITING MODE: the page opens CLEAN for that scene — scene line + event
  title near the top, then the whole page given to a full-height writing
  area. The wheel stays lit, locked with that scene at centre. Click any
  wheel label to open THAT scene to write — travel scene-to-scene BY THE
  WHEEL without leaving Writing Mode; each scene's text is remembered.
- "‹ overview" (top-right, Writing Mode only) returns to the Treatment.
- THE PRINCIPLE: the writing position and the map position are the SAME
  thing.

>>> FIRST THING NEXT SESSION — THE PAGE-TOP BUG (7 June) <<<
Clicking a scene label on the wheel (and opening a scene generally)
leaves the TOP OF THE PAGE CUT OFF above the fold — the running head /
stave heading / scene line are clipped. The page should sit with its
TOP just below the header bar, reading from the top down (Kev has a
screenshot of the correct look). WHAT WE TRIED, not yet working: a
rollToTop(target) function landing the sheet's top a small offset below
the header (tried −28, −16; behavior:'auto'); pointed both the wheel-
label click and the writing-open at it instead of rollToCentre (which
centred the page MIDPOINT on screen and clipped the top of a full-height
page); two requestAnimationFrames before scrolling in writing mode
because body.writing changes .stage padding 40vh→34px and hides content.
STILL CUTTING OFF. Get a fresh screenshot; likely needs measuring after
layout settles, or computing the offset from the real sheet top, and
ensuring no competing smooth-scroll is running. rollToCentre may now be
unused — check before deleting.

THE WHEEL MOCKUP (the LIVE DESIGN SOURCE)
Built on "A Christmas Carol", whole book loaded: 5 staves, 25 scenes,
25 full pages. The live design source for the wheel + page. STORE +
INDEX the latest in the CODE locker (supersedes all earlier wheel
mockups). Built static-first then animated.

STILL OPEN ON THE WHEEL (small)
- The pop-up is built into the mockup and working; the 230px right
  sidebar has no purpose yet.
- Whether multiple events per scene stay listed on a page or collapse,
  now there is one scene per page.

HOW THE WORLD IS REACHED — THE POP-UP (settled 4 June; built)
On the LEFT (page moved right to make room). Two steps from the nav:
click a counted section → list of names → click a name → the record.
STABLE (click to open, ✕ to close; no vanish on click-away; stays open
when you select text inside it). DRAGGABLE by its header. QUIET-NOTE
GRAMMAR throughout: SUB-TITLE in the section's colour, DESCRIPTION in
neutral ink, SOLID end-line in the section colour; colour = wayfinding
(Characters gold, Locations teal, each section its own colour). Record
view: per-field rows, each with a COPY button, section-colour dividers
and end-line. COPY AND PASTE is how substance reaches the WP — copy is
TEXT ONLY, coloured in the pop-up, landing PLAIN in the WP. The writer
stays in charge; nothing lands they did not choose.

THE WP — A REAL DOCUMENT PAGE (settled 4 June; refined 6 June)
US Letter (816 × 1056px), generous margins, page shadow, on the dark
workspace — not a thin panel. Shifted right (pop-up left, wheel right).
One scene per page (see THE PAGE).
- MAGNIFY (zoom): − / 100% / + scales the whole document (70%–200%).
  ZOOM, not page-width — the page shape never changes. (Specced.)
- PAGE NUMBERS centred at the foot; optional UNNUMBERED TITLE PAGE with
  a toggle; title + author pull from Overview. (Specced.)
- Scrollbars slim, dark, gold-on-hover. No Windows defaults.
- NOTE: pages are fixed-height sheets in the mockup. REAL pagination
  (prose flowing onto new numbered pages) is a bigger build for when the
  writing surface is real. Kev understands.

OPEN DECISIONS — STILL TO SETTLE (one at a time)
0. >>> THE PAGE-TOP BUG (above) — FIRST THING NEXT SESSION. <<<
1. WHERE THE MOOD WORDS LIVE (Cold · Bleak · Biting) — pulled off the
   page; wanted, but no home yet. Parked.
2. EVENT ORDER WITHIN A SCENE — events group by chapter, no sequence
   within a scene. (Events store characters[] and location; lack a
   POSITION.)
3. EVENTS ON THE PAGE — with one scene per page, confirm whether
   multiple events per scene stay listed or collapse.
4. TAG SET opens — Prose vs Action; Dialogue's place; Emotion tag vs
   Map (see THE TAG SET).
5. WHERE THE CARRIED FEATURES LIVE — tension curve, Emotional Maps,
   Ambient, the lift — in the wheel model.
6. THE 230px RIGHT SIDEBAR — its purpose.
7. PLOT MAPPING beside The Treatment — both views of one database.

THE TAG SET (working list — carried, nothing pruned)
Action · Chapter · Character · Emotion · Event · Location · Note ·
Prose · Scene · Time. Sorted:
  SPINE (the timeline)        — Chapter · Scene · Event
  FLESH (the writing)         — Prose · Action · (Dialogue — see NB)
  REFERENCE (via the pop-up)  — Character · Location · Time · Emotion ·
                                Note
OPEN: Prose vs Action (working split: Action = what they do; Prose =
description/narration) UNDECIDED. Dialogue's place — not on the list but
a scene needs spoken lines. Emotion as per-beat tag vs the seed of an
Emotional Map UNDECIDED.

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
Landing line: The world's first Digital Creative Workstation for writers
(no full stop)
Owned term: DCW — Digital Creative Workstation. Said as three letters:
D.C.W.
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
Section colours (pop-up): Character #cba36a (gold-tan) / Location
  #5fa898 (teal) / Event #b08a6a / Chapter #9a8fb0 / others per section.
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
Publication fee: £1 GBP per publication / base currency GBP / Stripe
handles international conversion / Paid users: one free publication per
week / £1 after that
Ada's contextual observations are FREE — do not count against prompt
allowance. Ada conversational responses count.
Lifetime members: infinity symbol in header instead of number.
Server-side flag: is_lifetime: true in Supabase. Must be before F12
blocker.

NOTE ON PROMPT COUNTER IN CODE
The current code shows a 20-call daily counter in localStorage. This is
a development placeholder only — not product pricing. Real prompt
tracking moves server-side in Step 7. Pricing is locked — see
locked-decisions.md. Adjust counter limits when final costs are
confirmed pre-launch.

TECHNICAL
Version: v4.7 — pre-Step 1 rebuild.
Autumn 2026 launch target.
Repo: PitchDarkPress/inkyswot-app
Vercel Hobby (free). Auto-deploys on push to main.
API: claude-haiku-4-5-20251001
Key: inkyswot-app-2 — Vercel Environment Variables ONLY. NEVER IN
GITHUB.
Read Aloud bug fix in place: Chrome async cancel() fix — captures
wasThisField and wasSpeaking before cancel fires, then setTimeout 100ms
before re-speaking. Do not revisit.

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
CODE/home-icons.svg — the four home-page launchpad icons, clean SVG
line art using stroke="currentColor" so they recolour with Tone. Stored
31 May 2026. Awaiting integration into the My Projects screen.
CODE/dcw-vertical.html — the vertical DCW + shutter frame. SUPERSEDED
(shutter dumped 3 June 2026). Kept as history.
NOTE: all earlier DCW/Treatment/wheel mockups are SUPERSEDED by the
current WHEEL mockup (one scene per page, two-line kicker labels, the
whole Carol loaded). The current wheel mockup is the LIVE DESIGN SOURCE
— store and index it in the locker.

FILES IN REPO — inkyswot (landing page)
index.html — the landing page
CNAME — www.inkyswot.com

BUILD RULES
Fix before moving on. No snag lists. No deferred problems. No patches on
patches. One step at a time. Explain before doing. Wait for
confirmation. Persistent bugs: rebuild from scratch. Never overwhelm.
When updating files, rewrite the whole file clean — never patch.

WHAT IS BUILT AND WORKING
Landing page (inkyswot.com) — ticker, clocks, Log In / Sign Up buttons.
Login page (app.inkyswot.com/login.html) — members access gate, fixed
panel, Log In and Sign Up tabs. Stubbed — not yet wired to Supabase.
Both forms show "not yet open" message on submit — no routing to app.
My Projects / Trash / New Project modal / Overview / Characters /
Relationships / Factions & Orgs / Language & Dialogue / Locations /
Buildings / Objects & Artefacts / Rules & Lore / Plot Threads /
Subplots / Themes & Motifs / Events & Timeline / Chapters / The
Treatment (placeholder shell only) / AI Expand / AI ON/OFF toggle /
Read Aloud (with Chrome async cancel() bug fix) / Light-dark mode /
Voice selector.
NB (from the code): The Treatment screen in index.html is still an EMPTY
placeholder — "The Treatment builds itself. Keep writing." No editor, no
logic. It is the named, waiting home for the timeline-of-events Treatment
— now THE WHEEL. Every database screen already collects the connections
the Treatment needs (Events store characters[] and location; Chapters
store characters[], location, plotthreads[], subplots[]). The data is
already there. The WHEEL itself lives in the standalone mockup, NOT yet
in index.html.

NAV — CONFIRMED (31 May), with 4 June additions
Navigate: My Projects / The Press / Plot Mapping
Project: Overview / Cast (Characters / Relationships / Factions & Orgs /
Language & Dialogue) / World (Locations / Buildings / Objects &
Artefacts / Rules & Lore) / Plot (Plot Threads / Subplots / Themes &
Motifs / Events & Timeline) / Library (Research & Reference / Notes &
Scratchpad / Sandbox) / Chapters (Chapters / The Treatment) / DCW
(Timeline / Storyboard — superseded; see below)
Help: Tutorial / Manual / FAQs / What's New
Trash: its own section at the foot of the sidebar.
PENDING:
- Each nav section to show a LIVE COUNT (read .length from the saved
  array): Characters · 5, Locations · 3, Factions · 0 (zero greyed).
  Clicking a counted section opens the two-step pop-up (list → record),
  on the LEFT. (Built and working in the wheel mockup.)
- Under "InkySwot IS the DCW": Plot Mapping and the DCW collapse toward
  The Treatment. The old DCW sub-entries (Timeline / Storyboard) are
  superseded. Re-work the nav now the Treatment/wheel direction is
  agreed. The Treatment is the live home of the DCW.

HOME PAGE — MY PROJECTS (31 May 2026)
My Projects is the home page — landed on at login, returned to. The hub,
not a fixed path. After login the writer navigates freely (only
exception: one-time NEW project setup, which must create the project
first). Launchpad: four items live BOTH in the nav AND on the home page,
each with an icon, a title, a two-line strap:
- Plot Mapping — "Map ideas. See the pattern." — constellation icon
- The Press — "Publish. Make it permanent." — printing press icon
- Create First Project — "Begin the work. Claim the page." — typewriter
- Open Project — "Return to what matters." — drawer-chest icon
Icons at CODE/home-icons.svg (stroke="currentColor", recolour with Tone;
no PNGs). Straps not finally signed off — confirm before building. Build
step still to do: lay out the four-item row on My Projects using the
stored icons. Preview before touching index.html.

WHAT IS STUBBED (placeholder screen only — Step 1)
Research & Reference / Notes & Scratchpad / Sandbox / Tutorial / Manual
/ FAQs / What's New / The Press / Plot Mapping (both show Coming Soon).
All stubbed screens show "Coming Soon". Build to the same pattern as
existing screens. Research & Reference, Notes & Scratchpad and Sandbox
are deferred until after the writing surface is built (Step 10).

WHAT IS NOT YET IN THE APP (Step 1 work)
Home-page launchpad row (four items with icons and straps)
Nav section live counts
Manuscript Format screen (new — first step before Overview)
Format-aware formatting toolbar (adapts to manuscript type)
Style Field (tone/voice dropdown + free text on Overview)
Three-field genre (replaces single dropdown)
Import option in New Project modal
Section help pill (SECTION ?) — template pattern for every screen
The Treatment / DCW — now THE WHEEL (page shifted right; one scene per
page; two-line kicker labels; windowed/eased/straight wheel; Overview ↔
Writing Mode; entity pop-up on the left). Currently a standalone mockup,
not yet in index.html.
All remaining stubbed screens.

MANUSCRIPT FORMAT LIST — CONFIRMED
Academic Essay / Thesis / Audio Drama / Audiobook / Autobiography /
Biography / Children's Book / Comic Script / Cookbook / Essay
Collection / Flash Fiction / Game Script / Graphic Novel / Literary
Journal / Memoir / Non-Fiction / Novel / Novella / Personal Essay /
Creative Non-Fiction / Picture Book / Poetry Collection / Radio Drama /
Screenplay / Short Story / Stage Play / Teleplay / Travel Writing /
Other.

FORMAT GROUPS — CONFIRMED
Prose — Novel / Novella / Short Story / Flash Fiction / Children's Book
/ Picture Book / Memoir / Biography / Autobiography / Travel Writing /
Non-Fiction / Personal Essay / Academic Essay / Essay Collection /
Literary Journal / Cookbook
Script — Screenplay / Teleplay / Radio Drama / Audio Drama / Stage Play
/ Comic Script / Game Script
Verse — Poetry Collection
Hybrid — Graphic Novel / Audiobook

GENRE LIST — CONFIRMED
48 entries. Flat alphabetical. No optgroups.
Academic Essay / Thesis / Adventure / Audio Drama / Audiobook /
Autobiography / Memoir / Biography / Children's Book / Comedy / Humour /
Comic Script / Coming of Age / Cookbook / Crime & Thriller / Drama /
Dystopian / Erotic / Essay Collection / Fantasy / Flash Fiction / Game
Script / Gothic / Graphic Novel / Historical Fiction / History / Horror
/ Literary Fiction / Literary Journal / Non-Fiction / Novel / Novella /
Other / Paranormal / Personal Essay / Creative Non-Fiction / Picture
Book / Poetry / Radio Drama / Romance / Science Fiction / Self-Help /
Short Story / Speculative Fiction / Stage Play / Teleplay / Thriller &
Suspense / Travel Writing / True Crime / Urban & Contemporary / Western
Locked: 28 May 2026.

LANDING PAGE — inkyswot.com
Ticker strip — InkySwot promo lines, seamless scroll, 15s speed.
World clocks — Tokyo / Sydney / New York / London (centre) / Frankfurt /
Dubai / Hong Kong.
Log In and Sign Up buttons — top right of ticker strip. Both link to
app.inkyswot.com/login.html.

LOGIN PAGE — app.inkyswot.com/login.html
Single file with two tabs — Log In and Sign Up. Full screen dark panel.
Fixed size — never moves between tabs.
Log In tab: Email / Password / Enter button / Forgot password.
Sign Up tab: Email / Password / Confirm Password / Request Admission.
Both tabs show "not yet open" message on submit. Authentication stubbed
— wires to Supabase in Step 4. Do not add routing to index.html until
Step 4 is complete.

UX MAP — USER JOURNEY (31 May 2026)
BEFORE login it is a fixed path — no nav menu yet: Landing Page → Decide
Sign Up or Log In → Login page.
AFTER login it is an open hub: → My Projects (home — the launchpad) →
nav takes the writer anywhere. The four launchpad options are reachable
from nav and home page. Only surviving sequence after login: one-time
NEW project setup — New Project → Manuscript Format → Overview — because
the project must exist before it can be navigated. Import Project follows
the same setup path.

THE PRESS — TWO DOORS (31 May 2026)
One tool, two entry points.
INSIDE (members): a nav screen where a logged-in subscriber publishes.
OUTSIDE (public): the same tool behind its own public door —
press.inkyswot.com — reached also from the landing page. A non-sub signs
up here (lightweight Press sign-up), pays per book, publishes without a
platform subscription. A public Press sign-up = member of THE PRESS
ONLY: a login to The Press, no platform access. The paid-only platform
stays sealed. Upsell gentle: email captured → The InkySwot Bugle.
BUILD NOTE: the public Press must be CLONED, not re-skinned — it needs a
DIFFERENT payment gateway. Shared publishing engine; separate sign-up,
login, payment. Full spec in press.md. Replaces/expands Step 15.

UX MAP GAPS — STATUS
Gap 1: Free-to-paid upgrade trigger — RESOLVED. Paid only.
Gap 2: Publishing fee presentation — RESOLVED. £1 GBP upfront.
Gap 3: Export Suite conversion moment — RESOLVED. No upgrade wall.
Gap 4: Font import in Publishing Suite — NOT RESOLVED. TBD before Step 14.
Gap 5: Document types in New Project modal — NOT RESOLVED. TBD before Step 1.
Gap 6: Import/migration route — RESOLVED. Manual entry, same fields.
Open question (public Press): where a non-sub's book data comes from with
no platform project — enter cold, or upload a finished manuscript. TBD.
Post-launch consideration: AI inference from imported manuscript.

PLATFORM LAYOUT (updated for the wheel)
Top menu (project name; word count + magnify + title-page controls
top-right; "‹ overview" appears top-right in Writing Mode; Ada when AI
ON), left nav (with counts). The WP / Treatment is the main work area (a
real document page, one scene per page) but SHIFTED RIGHT — the LEFT of
the dark workspace holds the entity POP-UP note. In the channel to the
RIGHT of the page is THE WHEEL; a 230px right sidebar sits beyond it
(purpose TBD). No shutter, no strip, no board, no separate Writing Panel.
The Press — separate section, own entry point (two doors).

SECTION HELP PILL — TEMPLATE PATTERN
First built on the Plot Mapping mockup (30 May 2026). Every screen
carries a help pill, top-right, gold border, reading SECTION ? —
clicking opens a slide-in guide headed with that screen's name (what it
is / how to use it / a tip). Same pill, same place, every screen; each
supplies its own words. The in-context help system. The full manual
stays separate (Help menu). Intended to float — not yet built.

THE TREATMENT / THE DCW — THE CORE
Full spec in dcw.md (rewritten 7 June for the wheel as built). In short:
InkySwot IS the DCW. The Treatment is it switched on — a timeline of
events (Chapter → Scene → Event), assembled from the database, written
by filling in the blanks. You navigate AND write by THE WHEEL (page
right, pop-up left). One scene per full page; two-line kicker labels;
windowed, eased, straight belt; ring + leader centre mark.

CARRIED, TO BE RE-FITTED (from earlier DCW thinking — not yet placed in
the new model): Tension curve (three modes — Manual / AI-Guided /
Analysis), Emotional Maps, Ambient (Atmosphere / Weather / Time, Time as
a block). Dark Thoughts (private, never exported). The lift (Prologue /
Backstory below Chapter 1). The SECTION ? help pill carries.

THE PRESS — CONTENTS
Full spec in press.md. (Two-door model above.) Where the writer goes
when the book is done. Separate section, not part of the project nav.
Also a standalone pay-per-book product for non-subs. An acquisition
funnel for InkySwot. Includes: Cover Creator / Book Layout Tool / Front
and Back Matter Assembly / Platform Requirements Database / Metadata /
Validation / The Guide. Supports: Paperback / Hardback / Ebook. Future:
Audiobook. Platforms: KDP / IngramSpark / Lulu / Draft2Digital / Kobo /
Apple Books / Barnes & Noble Press / Other. Replaces/expands Step 15.

ADA
Full spec in ada.md. Name: Ada. Named after Ada Lovelace — the first
programmer. Female. Fixed. Not a user setting. A contextual creative
collaborator. Not a search engine. Not a writing generator. She gives
the writer's answer — filtered through everything they have already
built. Position: top menu, between project name and prompt counter. AI
tools surface contextually; visible when AI ON, hidden when AI OFF.
Voice: Google UK English Female (browser speechSynthesis). Ada spec must
be complete before any further screens are built. Ada build is Step 12.
NB: AI is never required for the Treatment to work — assembling the
database into the page, the wheel, and copy-paste are all plain
mechanics. Ada IMPROVES the experience but the writer's book stands
without her.

SECURITY
Full security system in security.md. Core principle: paid only removes
the primary abuse vector. Seven-layer system locked 24 May 2026. API
key: Vercel Environment Variables ONLY. Never in GitHub, never in client
code. Prompt counter security: Steps 5–7. Non-negotiable before launch.
Signup route: Email + password → email verification code → platform
access. No SSO. No third-party auth. Email and password only.

SPECIALIST FILES — INKYSWOT ONLY
build-list.md — paste in at the start of any build session.
Others: paste in only when working on that area. Always tell Kev which
file you need and why before asking.
ada.md — Full Ada specification.
security.md — Full security system.
dcw.md — Full DCW specification (rewritten 7 June for the wheel as
built; one scene per page, two-line kicker labels, etc.). All earlier
DCW/Treatment/wheel models are history within it.
press.md — Full Press specification.
future.md — Future ideas, not yet on the build list (includes the two
pre-filled demo books).
locked-decisions.md — the locked decisions (rewritten 7 June).
CODE/ — the code locker.

BUILD ORDER — CONFIRMED
Step 1 — v4.0 App Shell Rebuild (NOT YET STARTED)
Step 2 — Walk the Platform
Step 3 — Sign Off Layout and Journey (Gate)
Step 4 — Supabase
Step 5 — Lifetime Membership Flag
Step 6 — F12 / Security Blocker
Step 7 — Server-Side Prompt Tracking
Step 8 — Stripe
Step 9 — Resend
Step 10 — Writing surface (the WP page — one scene per page, magnify,
  page numbers, title page; the entity pop-up on the left; the wheel).
  NB: the writing surface, The Treatment (Step 11) and the DCW (Step 13)
  are CONVERGING into the WHEEL — likely ONE build. Reconcile the step
  list when the wheel is built into the app for real.
Step 11 — The Treatment (the timeline of events / fill-in-the-blanks /
  the wheel)
Step 12 — Ada
Step 13 — DCW (now = The Treatment / the wheel; converging)
Step 14 — Export Suite and Format Conversion
Step 15 — The Press (replaces Publishing Suite)
Step 16 — Admin Panel
Step 17 — PWA Manifest
Step 18 — Beta
Step 19 — Launch

CURRENT STATUS & NEXT ACTIONS
v4.7 pre-Step 1 rebuild. Autumn 2026 launch target.
Pricing locked — 24 May. Security designed — 24 May. Landing page
updated — 25 May. Login page built — 25 May. Genre list rebuilt (48,
flat) — 28 May. Subplots / Themes & Motifs / Events & Timeline built —
28 May. Chapters built & wired — 29 May. The Treatment SHELL built &
wired — 29 May (empty placeholder). The Press conceived & specced — 29
May. Section help pill pattern built — 30 May. CODE locker created — 30
May.
31 May: user journey reworked (open hub; My Projects home); Press two-
door locked; nav updated; home launchpad decided; icons stored.
1 June: DCW × Plot Mapper fusion (later superseded).
2 June: vertical board + shutter (superseded).
3 June: one-screen X-ray / linear tagged cells (superseded).
4 June (morning): THE SECOND TURN — InkySwot IS the DCW; the Treatment
  is the database assembled; the entity pop-up; the WP as a real page.
4 June (later): THE WHEEL — click-to-write resolved.
6 June: ONE SCENE PER FULL PAGE; stave heading on every page; whole
  Carol loaded (25 scenes); wheel refined — window opened to nine each
  side, bloom + chevron removed, ring made smaller/thicker, leader
  restored, hover lights node only, outer labels brightened then dimmed
  to taste, live hand-off smoothed; bow tried and removed (straight
  belt). Entity pop-up built into the mockup.
7 June: STAVES ON THE WHEEL resolved as the TWO-LINE KICKER label
  ("STAVE ONE — SCENE ONE" + title) on every scene — no separate stave
  markers, no blank stave pages. The three .md files (dcw, locked-
  decisions, current-state) rewritten clean to match the wheel as built.

NEXT (do in order, one at a time)
1. >>> FIX THE PAGE-TOP BUG (clicking a wheel label clips the top of the
   page; see the wheel section). FIRST THING. <<<
2. Settle WHERE THE MOOD WORDS LIVE.
3. Settle EVENT ORDER WITHIN A SCENE (give events a position).
4. Settle EVENTS ON THE PAGE (multiple events per scene — list or
   collapse).
5. Settle the tag-set opens: Prose vs Action; Dialogue's place; Emotion
   as tag vs Map.
6. Decide the 230px RIGHT SIDEBAR's purpose.
7. Store + index the current WHEEL mockup in the CODE locker (live
   design source; supersedes all earlier wheel mockups).
8. Build the home-page launchpad row + nav counts on My Projects
   (preview first; confirm the four straps).
9. Begin Step 1 — v4.0 app shell rebuild.
10. Resolve UX map gaps 4 and 5, and the public-Press data question.

PARKED / FUTURE (confirmed possible, NOT now — see future.md)
- TWO PRE-FILLED DEMO BOOKS: fully-populated, every-section-complete
  demo projects of "A Christmas Carol" and "The Wind in the Willows", so
  a new user can explore a finished world. Both out of copyright (Dickens
  1843; Grahame 1908). A demo = a normal project, pre-filled, ideally
  read-only. Build Carol first as the template (its bones are in the
  mockup), then Willows. DEPENDS ON the app shell and sections being
  final. Confirmed feasible 4 June; not scheduled. Open question: whether
  the in-scene prose is written by Kev/adapted or sample-generated.

================================================================
SUPERSEDED — KEPT AS HISTORY (do NOT build from any of this)
================================================================
- 6–7 JUNE wheel detail now superseded by the wheel as built: the
  original ~3-label window; big roomy uniform single-line labels; the
  bloom glow + » chevron; the slight outward bow; separate stave marker
  labels / a blank stave page. (The current wheel: one scene per page,
  two-line kicker labels, nine-each-side window, straight belt, ring +
  dot + leader, hover lights node only, smoothed hand-off.)
- 4 JUNE (morning): the first WP/Treatment mockup (assembled list with
  "— click to write this scene —" growing an inline gap). The MODEL
  (database assembled; pop-up; real page) stands; the click-to-write
  MECHANISM is superseded by THE WHEEL.
- 4 JUNE multi-event long-scrolling Treatment page — superseded 6 June
  by one scene per full page.
- 3 JUNE: the ONE-SCREEN DCW / X-RAY model (DCW on = bones, off =
  flesh); LINEAR screenplay-style TAGGED CELLS (TAG + CONTENT) with (*)
  handles; write-with-it-off-then-switch-on-and-it-asks; AI as a quality
  setting (render once, store). Superseded 4 June.
- 2 JUNE: the VERTICAL board DCW (tracks as columns) + the SHUTTER
  (curtain covering/revealing DCW vs WP); the fused "one manuscript seen
  at two distances"; the prose-band reported onto the board.
- The horizontal STRIP DCW (inkyswot-daw.html).
- The old note CARD (type tab, knot, full-stop, flip-from-tab).
- "Snap to Default" / drag-to-reorder tracks; bright-red freeform /
  make-your-own tracks; Ideas columns — all from the column-board
  thinking; not part of the current model unless re-introduced.
- The INDENTATION RULE (timeline events at the margin, everything
  indented under its event) — belonged to the multi-event page; gone
  with one scene per page.
- CODE/dcw-vertical.html, CODE/map-plotter.html, and the 3 June one-
  screen study mockups — kept only as history, NOT build targets.
RETAINED FROM HISTORY (still live, re-fitted to the new model): the
QUIET NOTE visual grammar (now the pop-up's grammar); the database
handle (now the pop-up + copy); Dark Thoughts; the SECTION ? help pill;
and CARRIED-but-unplaced: Tension curve (three modes), Emotional Maps,
Ambient (Atmosphere / Weather / Time), the lift.