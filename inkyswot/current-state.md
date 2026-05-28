File: inkyswot/current-state.md
Last updated: 28 May 2026

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
Events & Timeline /
AI Expand / AI ON/OFF toggle /
Read Aloud (with Chrome async cancel() bug fix in place) /
Light-dark mode / Voice selector

WHAT IS STUBBED (placeholder screen only — to be built in Step 1)
Research & Reference / Notes & Scratchpad / Sandbox /
Chapters / The Treatment /
Timeline (DCW) / Storyboard (DCW) /
Tutorial / Manual / FAQs / What's New
All stubbed screens show "Coming Soon" placeholder.
Build to same pattern as existing screens.
Full spec for each in build-list.md.
Note: Research & Reference, Notes & Scratchpad and Sandbox
are deferred until after the Write screen is built (Step 10).
They are part of the same ecosystem and cannot be fully
built without the writing panel in place.

NAV — CONFIRMED COMPLETE
Navigate: My Projects / Trash
Project: Overview / Cast (Characters / Relationships /
Factions & Orgs / Language & Dialogue) /
World (Locations / Buildings / Objects & Artefacts / Rules & Lore) /
Plot (Plot Threads / Subplots / Themes & Motifs / Events & Timeline) /
Library (Research & Reference / Notes & Scratchpad / Sandbox) /
Chapters (Chapters / The Treatment) /
DCW (Timeline / Storyboard)
Help: Tutorial / Manual / FAQs / What's New

WHAT IS NOT YET IN THE APP (Step 1 work)
Manuscript Format screen (new — first step before Overview)
Format-aware formatting toolbar (adapts to manuscript type)
Style Field (tone/voice dropdown + free text on Overview)
Three-field genre (replaces single dropdown)
Import option in New Project modal
Three-panel layout (left sidebar / main work area / right panel)
DCW strip (below main panels, above footer)
Timeline strip
Chapters / The Treatment — next to be built
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

UX MAP — USER JOURNEY
Last reviewed: 26 May 2026
Two entry paths. Both arrive at the same workspace.
Landing Page (inkyswot.com)
→ Decide: Sign Up or Log In
→ Login page (app.inkyswot.com/login.html)
→ Decide: New Project or Import Project
→ Manuscript Format (chosen first — drives everything)
→ Overview (Title / Genre / Style / Tone / ETC)
→ Workspace (three-panel layout)
→ Write
Import Project follows same path.
Writer uploads manuscript, enters workspace,
highlights entities, categorises and adds to database,
then writes.

UX MAP GAPS — STATUS
Gap 1: Free-to-paid upgrade trigger — RESOLVED. Paid only.
Gap 2: Publishing fee presentation — RESOLVED. £1 GBP upfront.
Gap 3: Export Suite conversion moment — RESOLVED. No upgrade wall.
Gap 4: Font import in Publishing Suite — NOT RESOLVED. TBD before Step 14.
Gap 5: Document types in New Project modal — NOT RESOLVED. TBD before Step 1.
Gap 6: Import/migration route — RESOLVED. Manual entry, same fields.
Post-launch consideration: AI inference from imported manuscript.

PLATFORM LAYOUT — CONFIRMED
Top menu (includes Ada when AI ON)
Left sidebar / Main work area / Right panel
DCW strip (below panels, above footer — toggleable)
Footer menu

DCW — DIGITAL CREATIVE WORKSTATION
Full spec in dcw.md.
Timeline strip below all three panels. Always present. Toggleable.
Chapters as ruler across the top.
Tracks for characters, plot, subplots, locations,
events, objects, themes, tension, notes.
Tracks are called TRACKS throughout the UI.
Tension curve — three modes:
Manual — writer drags the curve.
AI-guided — writer sets target, Ada advises how to get there.
Analysis — Ada reads text and plots curve automatically.
Emotional Maps — curves tracking the rise and fall of specific
emotions per character across chapters. New feature — 28 May 2026.
Full spec in dcw.md.
DCW mockup: https://inkyswot-app.vercel.app/inkyswot-daw.html

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
future.md — Future ideas, not yet on the build list.
Ask for when: discussing post-launch possibilities.

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
Step 15 — Publishing Suite
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
Login page text sizes increased — 26 May 2026.
Both forms stubbed with "not yet open" message — 26 May 2026.
UX map reviewed and updated — 26 May 2026.
Manuscript format list confirmed and grouped — 26 May 2026.
Format-aware toolbar decided — 26 May 2026.
DCW tension curve spec decided — 26 May 2026.
Platform layout confirmed — 26 May 2026.
Nav confirmed complete — 26 May 2026.
All nine database files revised and corrected — 27 May 2026.
Genre list rebuilt — 48 entries, flat alphabetical — 28 May 2026.
Subplots screen built and wired — 28 May 2026.
Themes & Motifs screen built and wired — 28 May 2026.
Events & Timeline screen built and wired — 28 May 2026.
DCW Emotional Maps conceived, specced, mockup built — 28 May 2026.
DCW tracks confirmed as Tracks — 28 May 2026.
Ada contextual creative collaborator principle established — 28 May 2026.
Write screen named and locked — 28 May 2026.
Full Screen mode named and locked — 28 May 2026.
Index Card system conceived and specced — 28 May 2026.
Research & Reference, Notes & Scratchpad, Sandbox deferred
until after Write screen — 28 May 2026.

NEXT
Build Chapters screen
Build The Treatment screen
Write full Write screen spec before Step 10
Write full Chapters spec
Update all specialist files with today's decisions
Resolve UX map gaps 4 and 5
Begin Step 1 — v4.0 app shell rebuild