File: inkyswot/current-state.md
Last updated: 26 May 2026

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
COLOURS
#0f0d0a / #18120d / #221a14
Ink: #e8e0d0 / #b0a090 / #706050
Gold: #c9923a / #e8b060
Rule: #221709 / #352815
Light: #fafaf8 / #1a1410 / #b07820
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
TECHNICAL
Version: v4.7 — pre-Step 1 rebuild.
Autumn 2026 launch target.
Repo: PitchDarkPress/inkyswot-app
Vercel Hobby (free). Auto-deploys on push to main.
API: claude-haiku-4-5-20251001
Key: inkyswot-app-2 — Vercel Environment Variables ONLY.
NEVER IN GITHUB.
FILES IN REPO — inkyswot-app
index.html — the app workspace
login.html — the login / sign up gate (single tabbed page)
inkylogin-bg.png — login page background image (currently unused)
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
Rules & Lore / Read Aloud / AI Expand / AI ON/OFF toggle /
Light-dark mode / Voice selector / Help section in sidebar
(Tutorial / Manual / FAQs / What's New).
NAV — CONFIRMED COMPLETE
Navigate: My Projects / Trash
Project: Overview / Cast (Characters / Relationships /
Factions & Orgs / Language & Dialogue) /
World (Locations / Buildings / Objects & Artefacts / Rules & Lore) /
Plot / Library / Chapters / DCW
Help: Tutorial / Manual / FAQs / What's New
WHAT IS NOT YET IN THE APP (Step 1 work)
Manuscript Format screen (new — first step before Overview)
Format-aware formatting toolbar (adapts to manuscript type)
Style Field (tone/voice dropdown + free text on Overview)
Three-field genre (replaces single dropdown)
Sandbox
Import option in New Project modal
Three-panel layout (left sidebar / main work area / right panel)
DCW strip (below main panels, above footer)
Timeline strip
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
Chapters as ruler. Tracks for characters, plot, locations,
events, subplots, themes, tension.
Tension curve — three modes:

Manual — writer drags the curve.
AI-guided — writer sets target, Ada advises how to get there.
Analysis — Ada reads text and plots curve automatically.
DCW mockup file: inkyswot-daw.html — built, ready to integrate.

ADA
Name: Ada. Named after Ada Lovelace — the first programmer.
Female. Fixed. Not a user setting.
The writer's assistant — no artificial boundaries.
INTERNAL POSITIONING — NEVER USE PUBLICLY:
'ChatGPT knows the world. Ada knows your world.'
Position: Top menu. Between project name and prompt counter.
Visible when AI ON. Hidden when AI OFF.
Visual states:
SLEEPING — idle. Dim. Small zzz animation floating upward.
ACTIVE — gold underline, slow pulse.
HIDDEN — when AI is OFF.
Ada asks once, early: 'What would you like me to call you?'
Remembers forever. Never asks again.
Voice: Google UK English Female — browser speechSynthesis.
Free. No API. No external cost.
Ada's voice never changes.
Note: Sara Martin will NOT be voicing Ada. Alternative TBD.
Personality: Warm and friendly by default.
Stern when required — says what needs to be said once,
without drama, then leaves it to the writer.
Never patronises. Never overwhelms.
Never performs enthusiasm.
Speaks when worth saying. Silent otherwise.
Ada navigates, searches, monitors prompts, raises support
tickets. Ada's observations are FREE.
Ada is Step 12 in the build order.
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
These files exist in addition to the standard five.
Ask Kev to open the file in the admin panel and paste
it into the chat when required.
Always tell Kev which file you need and why before asking.
ada.md — Full Ada specification: personality, behaviour,
navigation, voice, visual states, support, presence page.
Ask for when: working on Ada in any capacity.
security.md — Full security system: the seven layers,
threat levels, behaviour pattern detection, device key
model, anti-spam architecture.
Ask for when: working on security, anti-spam, or signup flow.
build-list.md — Detailed spec for all 19 build steps.
Step names only are in current-state.md — the full detail
is here.
Ask for when: working on any specific build step.
dcw.md — Full DCW specification: layout, track types,
tension curve modes, minimap, toggle states, integration.
Ask for when: working on the DCW in any capacity.
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
Step 10 — Writing Panel with Accessibility Features
Step 11 — The Treatment
Step 12 — Ada
Step 13 — Timeline Strip (DCW)
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
NEXT

Resolve UX map gaps 4 and 5
Begin Step 1 — v4.0 app shell rebuild
Three-panel layout
Manuscript Format screen
All existing screens carried across
Style Field added to Overview
Three-field genre implemented
Import option in New Project modal
DCW mockup integrated