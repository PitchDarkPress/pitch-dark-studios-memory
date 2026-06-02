File: inkyswot/current-state.md
Last updated: 1 June 2026

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

WHAT INKYSWOT IS
Web-based story world-building and production platform.
The world's first Digital Creative Workstation (DCW)
for writers. Single HTML file.
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
Dark: #0f0d0a / #18120d / #221a14
Ink: #e8e0d0 / #b0a090 / #706050
Gold: #c9923a / #e8b060
Rule: #221709 / #352815
Light: #fafaf8 / #f0ede6 / #e8e4dc
Danger: #c43a2a
Success: #2a6b3a
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
inkyswot-daw.html — DCW mockup. Live at:
https://inkyswot-app.vercel.app/inkyswot-daw.html
CODE/ — the code locker (finished and in-progress code, stored
separately from the .md notes). See CODE/README.md for the index.
CODE/README.md — locker index, lists each stored file and status.
CODE/map-plotter.html — Plot Mapping standalone mockup, complete
30 May 2026. Awaiting integration into index.html.
CODE/home-icons.svg — the four home-page launchpad icons, clean
SVG line art using stroke="currentColor" so they recolour with Tone.
Stored 31 May 2026. Awaiting integration into the My Projects screen.

FILES IN REPO — inkyswot (landing page)
index.html — the landing page
CNAME — www.inkyswot.com

BUILD RULES
Fix before moving on. No snag lists. No deferred problems.
No patches on patches. One step at a time.
Explain before doing. Wait for confirmation.
Persistent bugs: rebuild from scratch. Never overwhelm.

WHAT IS BUILT AND WORKING
Landing page (inkyswot.com) — ticker, clocks, Log In / Sign Up buttons.
Login page (app.inkyswot.com/login.html) — members access gate,
fixed panel, Log In and Sign Up tabs. Stubbed — not yet wired to Supabase.
Both forms show "not yet open" message on submit — no routing to app.
My Projects / Trash / New Project modal /
Overview / Characters / Relationships / Factions & Orgs /
Language & Dialogue / Locations / Buildings / Objects & Artefacts /
Rules & Lore / Plot Threads / Subplots / Themes & Motifs /
Events & Timeline / Chapters / The Treatment /
AI Expand / AI ON/OFF toggle /
Read Aloud (with Chrome async cancel() bug fix in place) /
Light-dark mode / Voice selector

NAV — CONFIRMED (updated 31 May 2026)
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
Notes on 31 May changes:
- The Press added to Navigate (it sits outside any single project).
- Plot Mapping moved up to Navigate (reachable front-of-house).
  Its link is no longer in the Project section.
- Trash moved out of Navigate into its own section at the bottom.
Both The Press and Plot Mapping currently point to the Coming Soon
placeholder until their real screens are built.
PENDING (1 June): Plot Mapping and the DCW fuse into one instrument
(see dcw.md / locked-decisions.md). Nav will collapse the two into a
single entry once that spec is written. Not yet actioned here.

HOME PAGE — MY PROJECTS (new 31 May 2026)
My Projects is the home page — the screen a writer lands on at
login and returns to. It is the hub, not a fixed path.
After login the writer navigates freely from the nav menu;
there is no forced route. (The only unavoidable sequence is the
one-time setup when making a NEW project: it cannot show an
Overview until the project exists.)
Launchpad: four items live BOTH in the nav menu AND on the
My Projects home page. Each home-page item has an icon, a title,
and a two-line strap:
- Plot Mapping — "Map ideas. See the pattern." — constellation icon
- The Press — "Publish. Make it permanent." — printing press icon
- Create First Project — "Begin the work. Claim the page." — typewriter icon
- Open Project — "Return to what matters." — drawer-chest icon
Icons stored at CODE/home-icons.svg — clean SVG line art,
stroke="currentColor" so they recolour with Tone (gold on dark,
ink on light). No PNGs.
Straps not yet finally signed off — confirm before building the row.
Build step still to do: lay out the four-item row on the
My Projects screen, using the stored icons. Preview before
touching index.html.

WHAT IS BUILT AS A STANDALONE MOCKUP (not yet in the app)
Plot Mapping — complete standalone mockup, stored at
CODE/map-plotter.html. To be folded into index.html in Step 1.
Full feature list in the PLOT MAPPING section below and in
locked-decisions.md.

WHAT IS STUBBED (placeholder screen only — to be built in Step 1)
Research & Reference / Notes & Scratchpad / Sandbox /
Timeline (DCW) / Storyboard (DCW) /
Tutorial / Manual / FAQs / What's New /
The Press / Plot Mapping (nav links — both show Coming Soon
until their real screens are built)
All stubbed screens show "Coming Soon" placeholder.
Build to same pattern as existing screens.
Full spec for each in build-list.md.
Note: Research & Reference, Notes & Scratchpad and Sandbox
are deferred until after the Write screen is built (Step 10).
They are part of the same ecosystem and cannot be fully
built without the writing panel in place.

WHAT IS NOT YET IN THE APP (Step 1 work)
Home-page launchpad row (four items with icons and straps on My Projects)
Manuscript Format screen (new — first step before Overview)
Format-aware formatting toolbar (adapts to manuscript type)
Style Field (tone/voice dropdown + free text on Overview)
Three-field genre (replaces single dropdown)
Import option in New Project modal
Three-panel layout (left sidebar / main work area / right panel)
DCW strip (below main panels, above footer)
Timeline strip
Plot Mapping screen (fold in CODE/map-plotter.html)
Section help pill (SECTION ?) — template pattern for every screen
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

UX MAP — USER JOURNEY (updated 31 May 2026)
The journey has two shapes joined together.
BEFORE login it is a fixed path — no nav menu exists yet:
Landing Page (inkyswot.com)
→ Decide: Sign Up or Log In
→ Login page (app.inkyswot.com/login.html)
AFTER login it is an open hub, not a path:
→ My Projects (home — the launchpad)
→ from here the nav menu takes the writer anywhere, in any order.
The four launchpad options (Plot Mapping / The Press /
Create First Project / Open Project) are reachable both from the
nav and from the home page.
The only sequence that survives after login is the one-time setup
of a NEW project — New Project → Manuscript Format → Overview —
because the project must exist before it can be navigated. This is
necessity, not an imposed route. After setup the hub is fully open.
Import Project follows the same setup path. Writer enters the
workspace, highlights entities, categorises and adds to database,
then writes.

THE PRESS — TWO DOORS (updated 31 May 2026)
The Press is one tool with two entry points.
INSIDE (members): a screen reached from the nav, where a logged-in
subscriber publishes their book.
OUTSIDE (public): the same publishing tool behind its own public
door — press.inkyswot.com — with its own front door reached also
from the landing page. A non-subscriber signs up here (a lightweight
Press sign-up), pays per book, and publishes without a platform
subscription.
A public Press sign-up makes someone a member of THE PRESS ONLY.
They get a login to The Press and may use it as often as they wish.
They have NO access to the platform itself. The paid-only platform
stays sealed.
Upsell: gentle, no push. Their email is captured, so they receive
The InkySwot Bugle (the monthly newsletter) — the slow funnel.
BUILD NOTE: the public Press must be CLONED, not merely re-skinned,
because it needs a DIFFERENT payment gateway from the in-platform
Press. Shared publishing engine; separate sign-up, login, and
payment for the public version.
Full spec in press.md. Build position: replaces and expands Step 15.

UX MAP GAPS — STATUS
Gap 1: Free-to-paid upgrade trigger — RESOLVED. Paid only.
Gap 2: Publishing fee presentation — RESOLVED. £1 GBP upfront.
Gap 3: Export Suite conversion moment — RESOLVED. No upgrade wall.
Gap 4: Font import in Publishing Suite — NOT RESOLVED. TBD before Step 14.
Gap 5: Document types in New Project modal — NOT RESOLVED. TBD before Step 1.
Gap 6: Import/migration route — RESOLVED. Manual entry, same fields.
Open question (public Press): where a non-sub's book data comes from
when they have no project on the platform — enter cold, or upload a
finished manuscript. TBD.
Post-launch consideration: AI inference from imported manuscript.

PLATFORM LAYOUT — CONFIRMED
Top menu (includes Ada when AI ON)
Left sidebar / Main work area / Right panel
DCW strip (below panels, above footer — toggleable)
Footer menu
The Press — separate section. Own entry point (two doors — see above).
PENDING (1 June): the DCW becomes a full top-down screen, not a
strip. See dcw.md / locked-decisions.md. This "DCW strip" line is
superseded once that spec is written. Not yet actioned here.

PLOT MAPPING
ONE Plot Mapper. Per project. The 31 May change was only to move
its NAV LINK up into Navigate so it is reachable front-of-house
(a writer can open it to think before committing to a project).
The tool itself remains per-project, exactly as specced below.
Standalone mockup complete 30 May 2026 — CODE/map-plotter.html.
The story corkboard — a thinking space for sketching a story
before committing to it. Saved like everything else now;
Supabase at Step 4. To be folded into index.html in Step 1.
Note types: Character / Location / Plot Thread / Event / Object /
Subplot / Free Note. Type chosen at creation — no change after
(delete and remake). Double-click the board to add a note.
The note tab carries the type label with a full-stop after it.
The tab does three jobs: shows the type; click to flip the note to
its back (DARK THOUGHTS — a private panel, never exported, never
sent to InkySwot); drag from the tab to pull a thread to another
note. The full-stop goes RED when a note has Dark Thoughts.
Connect button stays as the alternative way to join notes.
Copy system: copy a note to place one beat in several chapters.
Front shared across the set (edit one, all change); each back is
its own; a copy starts blank; "n of n" counter bottom-right, shown
only for sets greater than one; renumbers on add/delete.
Chapter timeline along the bottom. Drag a note onto a chapter to
pin it. Chapter dividers have a toggle button to raise/lower them;
a grip drags a raised divider to any height.
Map title in the header — pre-fills from / syncs two-way with the
Overview title once integrated.
Timeline extends below Chapter 1 — the "lift": Prologue and
Backstories live below the line on the same board. One map per
project, never multiple. See locked-decisions.md.
Open question: whether a note can also span a chapter range in the
DCW (e.g. Ch.3–Ch.9). Revisit when the DCW is built.
PENDING (1 June): Plot Mapper and DCW fuse into one instrument.
The fused spec lives in dcw.md from now on. See locked-decisions.md.

SECTION HELP PILL — TEMPLATE PATTERN
First built on the Plot Mapping mockup — 30 May 2026.
Every screen carries a help pill, top-right, gold border, reading
SECTION ? — clicking it opens a slide-in guide headed with that
screen's name (what it is / how to use it / a tip).
Same pill, same place, every screen; each supplies its own words.
This is the in-context help system. The full manual stays separate
in the Help menu (Tutorial / Manual / FAQs / What's New).
Intended to float (for theatre) — not yet built.

DCW — DIGITAL CREATIVE WORKSTATION
Full spec in dcw.md.
Timeline strip below all three panels. Always present. Toggleable.
Chapters as ruler across the top.
Tracks for characters, plot, subplots, locations,
events, objects, themes, tension, notes.
Tracks are called TRACKS throughout the UI.
Threads are the connections between Chapters and DCW Tracks.
Tension curve — three modes:
Manual — writer drags the curve.
AI-guided — writer sets target, Ada advises how to get there.
Analysis — Ada reads text and plots curve automatically.
Emotional Maps — curves tracking the rise and fall of specific
emotions per character across chapters. New feature — 28 May 2026.
Full spec in dcw.md.
DCW mockup: https://inkyswot-app.vercel.app/inkyswot-daw.html
PENDING (1 June): major rework — fuses with Plot Mapper, becomes a
full top-down screen, gains three track types, cards that hold text,
and the cascade. Full detail being written into dcw.md.

THE PRESS — CONTENTS
Full spec in press.md. (Two-door model: see THE PRESS — TWO DOORS above.)
Where the writer goes when the book is done.
Separate section — not part of the project nav.
Also a standalone pay-per-book product for non-subscribers.
The Press is an acquisition funnel for InkySwot.
Includes: Cover Creator / Book Layout Tool /
Front and Back Matter Assembly / Platform Requirements Database /
Metadata / Validation / The Guide.
Supports: Paperback / Hardback / Ebook.
Future: Audiobook.
Platforms: KDP / IngramSpark / Lulu / Draft2Digital /
Kobo / Apple Books / Barnes & Noble Press / Other.
Build position: replaces and expands Step 15.

WRITE SCREEN
Named: Write. Locked 28 May 2026.
The writing panel — where the writer writes.
Full Screen mode — distraction-free writing. Named: Full Screen. Locked.
Desktop only. No mobile.
Index Card system — floating cards tethered to highlighted
entities in the manuscript. Full spec to be written before Step 10.
Entity highlighting — known entities highlighted in gold.
Unregistered entities highlighted in a cooler colour.
Cards only appear on deliberate click — never automatically.
Multiple cards open simultaneously. Cards grey out when
writer returns to manuscript — they wait, they don't close.
Auto-save on every card.
Counter shows waiting suggestions when in Full Screen mode.
Scan on space bar press only — current page only.
Database change triggers full manuscript rescan in background.
AI off — highlighting and cards still work. Ada's suggestions don't.
Full spec to be written before Step 10.
PENDING (1 June): the Write screen relates to the fused DCW via the
note card — a card opens into the writing surface (the cascade).
New keystone card type for prose, working name "Scene." Reconcile
with this section when the fused dcw.md is written.

ADA
Full spec in ada.md.
Name: Ada. Named after Ada Lovelace — the first programmer.
Female. Fixed. Not a user setting.
Ada is a contextual creative collaborator.
Not a search engine. Not a writing generator.
She gives the writer's answer — filtered through everything
they have already built. Full principle in ada.md.
Position: Top menu. Between project name and prompt counter.
Visible when AI ON. Hidden when AI OFF.
Voice: Google UK English Female — browser speechSynthesis.
Ada spec must be complete before any further screens are built.
Ada build is Step 12 in the build order.

SECURITY
Full security system documented in security.md.
Core principle: paid only removes the primary abuse vector.
Seven-layer system locked 24 May 2026 — see security.md.
API key: Vercel Environment Variables ONLY.
Never in GitHub. Never in client code.
Prompt counter security: Steps 5-7 in build list.
Non-negotiable before launch.
Signup route: Email + password → email verification code → platform access.
No SSO. No third party authentication. Email and password only.

SPECIALIST FILES — INKYSWOT ONLY
These files exist in addition to current-state.md.
build-list.md — paste in at the start of any build session.
The other files: paste in only when working on that area.
Always tell Kev which file you need and why before asking.
ada.md — Full Ada specification.
Ask for when: working on Ada in any capacity.
security.md — Full security system.
Ask for when: working on security, anti-spam, or signup flow.
dcw.md — Full DCW specification.
Ask for when: working on the DCW in any capacity.
press.md — Full Press specification.
Ask for when: working on The Press, Cover Creator,
Book Layout Tool, publishing pipeline, or POD platforms.
future.md — Future ideas, not yet on the build list.
Ask for when: discussing post-launch possibilities.
CODE/ — the code locker. Finished and in-progress code files,
indexed in CODE/README.md. Holds map-plotter.html (Plot Mapping)
and home-icons.svg (the four home-page launchpad icons).

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
Step 10 — Write Screen with Accessibility Features
Step 11 — The Treatment
Step 12 — Ada
Step 13 — DCW (Timeline Strip)
Step 14 — Export Suite and Format Conversion
Step 15 — The Press (replaces Publishing Suite)
Step 16 — Admin Panel
Step 17 — PWA Manifest
Step 18 — Beta
Step 19 — Launch

CURRENT STATUS & NEXT ACTIONS
v4.7 pre-Step 1 rebuild. Autumn 2026 launch target.
Pricing locked — 24 May 2026.
Security system designed — 24 May 2026.
Landing page updated — 25 May 2026.
Login page built — 25 May 2026.
Genre list rebuilt — 48 entries, flat alphabetical — 28 May 2026.
Subplots / Themes & Motifs / Events & Timeline screens built — 28 May 2026.
DCW Emotional Maps conceived, specced, mockup built — 28 May 2026.
Write screen and Full Screen mode named and locked — 28 May 2026.
Index Card system conceived and specced — 28 May 2026.
Chapters screen built and wired — 29 May 2026.
The Treatment shell built and wired — 29 May 2026.
The Press conceived, named, and fully specced — 29 May 2026.
press.md created as new specialist file — 29 May 2026.
Plot Mapping standalone mockup built and complete — 30 May 2026.
Section help pill (SECTION ?) template pattern built — 30 May 2026.
CODE locker created — README.md and map-plotter.html stored — 30 May 2026.

31 May 2026:
User journey reworked — open hub after login; My Projects is the
home page. Fixed path only before login and for one-time new-project setup.
The Press two-door model locked — one tool, inside (members, via nav)
and outside (public, own door at press.inkyswot.com, own sign-up,
CLONED for a different payment gateway). Public Press sign-up = Press
member only, no platform access, gentle upsell via the Bugle.
Nav updated — The Press and Plot Mapping added to Navigate;
Trash moved to its own section at the foot of the sidebar.
Plot Mapping confirmed ONE mapper, per-project; only its nav link
moved to Navigate.
Home-page launchpad decided — four items (Plot Mapping / The Press /
Create First Project / Open Project) in BOTH the nav and the home
page, each with icon, title and two-line strap.
Four launchpad icons made as clean SVG line art (currentColor) and
stored at CODE/home-icons.svg.

1 June 2026:
DCW worked through at length. Major architectural decision —
the Plot Mapper and the DCW FUSE into one instrument.
Full detail in dcw.md. Locked calls in locked-decisions.md.
Key points: three track types (Structural / Curve / Ambient,
Time is a block); cards hold text; the cascade (beat → scenes →
words); DCW becomes a full top-down screen, not a strip;
the note card is the bridge from planning to writing.
New keystone card type for writing prose — working name "Scene."
Open: per-type fields on the front of each card.
Consequential edits flagged inline above (NAV, PLATFORM LAYOUT,
PLOT MAPPING, DCW, WRITE SCREEN) — to action once dcw.md and
locked-decisions.md are written.

NEXT
Write the fusion into dcw.md and locked-decisions.md (today's task).
Decide per-type fields on the front of each card.
Build the home-page launchpad row on My Projects (preview first,
then into index.html) — confirm the four straps before building.
Write full Write screen spec before Step 10.
Write full Chapters spec.
Begin Step 1 — v4.0 app shell rebuild.
Resolve UX map gaps 4 and 5, and the public-Press data question.
Update completed.md.