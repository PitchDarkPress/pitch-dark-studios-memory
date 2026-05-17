# InkySwot — Build List
*Last updated: 14 May 2026*

Build order locked 14 May 2026.
Principle: get every user-facing element right in the single HTML
file first. Walk it. Sign it off. Then go deep with infrastructure.
Wire things up once, to something confirmed correct.

---

## CURRENT POSITION — Step 1 not yet started.

---

## STEP 1 — v4.0 App Shell Rebuild
All screens, all navigation, all interactions in the single HTML file.
Three-panel layout: left sidebar / centre panel / right panel (white,
like a page) / timeline strip below.

What goes in during this step:
- Three-panel layout shell
- All existing screens carried across and confirmed in correct position
- Style Field: tone/voice dropdown + free text on Overview
- Genre: three fields — primary + two sub-genres
- New Project modal: Start Fresh / Import Existing Work
- Button layout: AI Generate / AI Expand / Read in vertical column
- AI ON/OFF theatrical transition (gradual)
- Animated speaker on Read (four frames)
- All AI Generate and Expand buttons on all screens
- Help section carried across
- Cover thumbnail: REMOVED — not being built

## STEP 2 — Walk the Platform
Walk every screen as a zero-knowledge user.
Resolve six outstanding user flow gaps:
- Import/migration route for existing writers
- Free-to-paid upgrade trigger
- Publishing fee presentation
- Conversion placement (confirmed: Export Suite)
- Font import placement (confirmed: Publishing Suite Templates)
- Document types in New Project modal
Ada intervention points must be tested here.

## STEP 3 — Sign Off Layout and Journey
Gate. Nothing moves to Step 4 until Kev confirms layout
and journey correct.

## STEP 4 — Supabase
Database and authentication. PostgreSQL.
Free tier during development and beta.
Pro ($25/month, ~£20) before launch.

## STEP 5 — Lifetime Membership Flag
Server-side flag in Supabase: is_lifetime: true.
Bypasses all prompt counting.
Header shows infinity symbol instead of number.
Must be confirmed working before Step 6.

## STEP 6 — F12 / Security Blocker
Blocks localStorage manipulation via dev tools.
Safe because lifetime flag is server-side.

## STEP 7 — Server-Side Prompt Tracking
Prompt counter moves from localStorage to Supabase per user.
Non-negotiable before launch.

## STEP 8 — Stripe
Payment processing. Needs Supabase user accounts.
- Monthly subscription: £7.95
- Annual subscription: £79.50 (two months free)
- Prompt top-up: £1.99 for 500 prompts
- Store publication fees: £1.99 per publication
Note: micro-transactions below £1.99 not viable with Stripe fees.

## STEP 9 — Resend
Email delivery. Needs Supabase user accounts.
- Signup verification codes (unique, 20 min, max 3 requests)
- Password resets
- The InkySwot Bugle newsletter
- Notifications
Signup is not live until this step is complete.

## STEP 10 — Writing Panel with Accessibility Features
White background — like a page.
Formatting toolbar: Bold / Italic / Underline / Font / Size /
Alignment / Lists. Hotkeys. Distraction-free mode.
Chapter selector. Live word count. Auto-save.

Accessibility (CRITICAL DIFFERENTIATOR):
- Spell checker: 5-8 suggestions, AI phonetic interpretation,
  text-to-speech on hover, option to disable red underlines
- Read Aloud: browser speechSynthesis, zero cost, resume from
  point, click to set read-head
- Inline AI Thesaurus (Ctrl+Shift+T): 3-4 contextual alternatives
  in story tone, speaker icon on each

Collaborative Editing: bidirectional, AI at human pace, cursor to
flagged word one at a time, user sees everything, both can flag.
Vital for dyslexic users.

Note: Writing panel tagline undecided.
Note: Chapters screen spec superseded — new spec needed before build.

## STEP 11 — The Treatment
Screenplay-style block editor. Needs writing panel.
Bidirectional sync with all screens.
Blocks: Character / Location / Building / Object / Faction /
Plot Thread / Subplot / Theme / Event / Rule / Chapter /
Action / Dialogue / Note (private, no export) / Section Header.
AI Expand global.

## STEP 12 — Ada
Needs all screens and writing panel to exist.
Full specification in ada.md.

## STEP 13 — Timeline Strip (DCW)
Needs Treatment in place.
Full width below panels. Chapters as ruler.
Character / Plot / Location tracks.
Scene blocks colour-coded. Toggleable.
Tension Thread: curve not blocks.

## STEP 14 — Export Suite and Format Conversion
Needs writing panel and Treatment.
HEADLINE FEATURE — one click exports entire story world.
Formats: Word / Google Docs / PDF / JSON / Email /
Claude / ChatGPT / Gemini / EPUB.
Format Conversion both directions: prose to script / script to prose.
Screenplay / Radio Drama / Stage Play.
Full revised spec needed before build.

## STEP 15 — Publishing Suite
After Export Suite.
- Cover Creator (three-panel canvas, spine from page count)
- Templates + Google Fonts API + licensing disclaimer
- The Guide (platform-agnostic, honest)
- Store (paid only — full anti-spam strategy needed before build)

## STEP 16 — Admin Panel
Needs Supabase, Stripe, full platform.

## STEP 17 — PWA Manifest
Platform complete. Windows first. Mac second.

## STEP 18 — Beta
All above signed off. Supabase Pro active before beta users invited.
Ada voice recording at this step.

## STEP 19 — Launch
DNS to production. Triple redundancy.
Testbed at www.inkyswot.com/testbed password protected
during transition.

---

## ONGOING — Content & Operations
Run alongside build, continue post-launch:
- Platform Comparison Chart
- User Experience Timeline (v1 map built, six gaps to resolve Step 2)
- FAQs / Manual / Videos (YouTube — no build content)
- Monthly Newsletter (The InkySwot Bugle)
- Beta Programme (not yet defined — Facebook page natural channel)