InkySwot — Current State
Last updated: 25 May 2026

---

WHAT INKYSWOT IS
Web-based story world-building and production platform.
The world's first Digital Creative Workstation (DCW)
for writers. Single HTML file.
Live at: inkyswot-app.vercel.app
DNS to app.inkyswot.com pending (UK Cheapest).

IDENTITY & BRANDING
Name: InkySwot (capital I, capital S. Always.)
Tagline: Publish and be prepared.
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

BUILD RULES
Fix before moving on. No snag lists. No deferred problems.
No patches on patches. One step at a time.
Explain before doing. Wait for confirmation.
Persistent bugs: rebuild from scratch. Never overwhelm.

WHAT IS BUILT AND WORKING
Landing page / My Projects / Trash / New Project modal /
Overview / Characters / Relationships / Factions & Orgs /
Language & Dialogue / Locations / Buildings / Read Aloud /
AI Expand / AI ON/OFF toggle / Light-dark mode /
Voice selector / Help section in sidebar.

WHAT SHOWS AS COMING SOON (in nav, not yet built)
Objects & Artefacts / Rules & Lore / Plot / Library /
Chapters / DCW / Tutorial / Manual / FAQs / What's New.

WHAT IS NOT YET IN THE APP (Step 1 work)
Style Field (tone/voice dropdown + free text on Overview)
Three-field genre (replaces single dropdown)
Sandbox
Import option in New Project modal
Three-panel layout (left sidebar / centre / right white
panel / timeline strip below)

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

ADA
Name: Ada. Named after Ada Lovelace — the first programmer.
Female. Fixed. Not a user setting.
The writer's assistant — no artificial boundaries.
INTERNAL POSITIONING — NEVER USE PUBLICLY:
'ChatGPT knows the world. Ada knows your world.'
Position: Header. Between project name and prompt counter.
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

UX MAP — USER JOURNEY
Last reviewed: 24 May 2026
Two distinct journeys. Both end at WRITE.

JOURNEY 1 — NEW PROJECT
Landing Page
→ Sign Up or Log In
→ DECIDE: New Project or Import Project
→ New Project selected
→ Project Setup: Title / Format / Genre / Style/Tone
→ Create Project
→ Workspace Opens
→ Two parallel tracks available:
   TRACK A — Build World:
   Character / Location / Building / Faction / Lore / Timeline
   → Add to Database
   → Write
   TRACK B — Write directly
   → Write
Both tracks feed into WRITE.

JOURNEY 2 — IMPORT PROJECT
Landing Page
→ Sign Up or Log In
→ DECIDE: New Project or Import Project
→ Import Project selected
→ Import Manuscript
→ Workspace Opens
→ Highlight Entity/s in manuscript
→ Categorise: Character / Location / Building /
  Faction / Lore / Timeline
→ Add to Database
→ Write

THE DCW — NOT YET ON THE MAP
The Digital Creative Workstation is the full platform
vision. It is not yet represented in the UX map.
Where it sits in the user journey has not been decided.
This is a significant open question.

UX MAP GAPS — STATUS
Gap 1: Free-to-paid upgrade trigger
RESOLVED — paid only, no free tier, no upgrade moment.

Gap 2: Publishing fee presentation
RESOLVED — £1 GBP per publication, upfront, transparent
to all users at the point of publishing.

Gap 3: Export Suite conversion moment
RESOLVED — export is the same for all users. No upgrade
wall at export. The platform earns loyalty through quality
not through restricting access to export formats.

Gap 4: Font import in Publishing Suite Templates
NOT RESOLVED — TBD before Step 14.

Gap 5: Document types in New Project modal
NOT RESOLVED — full list of document types needed.
Affects what changes in the workspace based on selection.

Gap 6: Import/migration route for existing writers
NOT RESOLVED — format TBD, what happens to imported
content TBD. Critical for Step 1.

CURRENT STATUS & NEXT ACTIONS
v4.7 pre-Step 1 rebuild. Autumn 2026 launch target.
Pricing locked — 24 May 2026.
Security system designed — 24 May 2026.
UX map reviewed — gaps identified — 24 May 2026.
Working on UX map implementation — 25 May 2026.

NEXT
1. Resolve remaining UX map gaps (4, 5, 6)
2. Place DCW in the user journey
3. Begin Step 1 — v4.0 app shell rebuild
4. Three-panel layout
5. All existing screens carried across
6. Style Field added to Overview
7. Three-field genre implemented
8. Import option in New Project modal