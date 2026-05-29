File: inkyswot/build-list.md
Last updated: 29 May 2026
Build order locked 14 May 2026.
Principle: get every user-facing element right in the single HTML
file first. Walk it. Sign it off. Then go deep with infrastructure.
Wire things up once, to something confirmed correct.

CURRENT POSITION — Step 1 not yet started.
Progress since last update:
Subplots screen built and wired — 28 May 2026.
Themes & Motifs screen built and wired — 28 May 2026.
Events & Timeline screen built and wired — 28 May 2026.
Chapters screen built and wired — 29 May 2026.
The Treatment shell built and wired — 29 May 2026.
Genre list rebuilt — 48 entries, flat alphabetical — 28 May 2026.
These are pre-Step 1 additions to the existing v4.7 file.
Step 1 rebuild has not yet begun.

STEP 1 — v4.0 App Shell Rebuild
All screens, all navigation, all interactions in the single HTML file.
Platform layout: top menu / left sidebar / main work area /
right panel / DCW strip (below panels, above footer) / footer menu.
What goes in during this step:

Three-panel layout shell (left sidebar / main work area / right panel)
DCW strip placeholder (below panels, above footer — toggleable)
Manuscript Format screen (new — first step in project setup,
before Overview. Writer chooses format before anything else.
Format drives toolbar, workspace, and AI context.)
All existing screens carried across and confirmed in correct position.
All stubbed screens built to same pattern as existing screens:
Research & Reference / Notes & Scratchpad / Sandbox /
Timeline (DCW) / Storyboard (DCW) /
Tutorial / Manual / FAQs / What's New
Note: Subplots, Themes & Motifs, Events & Timeline,
Chapters and The Treatment already built —
carry across and confirm in correct position.
Note: Research & Reference, Notes & Scratchpad and Sandbox
are deferred until after Step 10. Build shells only in Step 1.
They cannot be fully built without the Write screen in place.
Pattern: same two-panel layout (list left, detail right),
same AI Generate and Expand buttons, same auto-save,
same field structure. Existing screens demonstrate the pattern.
Style Field: tone/voice dropdown + free text on Overview
Genre: three fields — primary + two sub-genres
Note: temporary combined genre dropdown built 28 May 2026.
Replace with three-field system in this step.
New Project modal: Start Fresh / Import Existing Work
Format-aware formatting toolbar shell (adapts to manuscript type.
Prose group / Script group / Verse group / Hybrid group.
Each group shows only relevant tools.
Full toolbar built in Step 10 — shell only here.)
Button layout: AI Generate / AI Expand / Read in vertical column
AI ON/OFF theatrical transition (gradual)
Animated speaker on Read (four frames)
All AI Generate and Expand buttons on all screens
Help section carried across
Cover thumbnail: REMOVED — not being built
DCW mockup (inkyswot-daw.html) integrated as placeholder

STEP 2 — Walk the Platform
Walk every screen as a zero-knowledge user.
Resolve outstanding user flow gaps:
Font import placement (confirmed: Publishing Suite Templates)
Document types in New Project modal
Ada intervention points must be tested here.

STEP 3 — Sign Off Layout and Journey
Gate. Nothing moves to Step 4 until Kev confirms layout
and journey correct.

STEP 4 — Supabase
Database and authentication. PostgreSQL.
Free tier during development and beta.
Pro ($25/month, ~£20) before launch.

STEP 5 — Lifetime Membership Flag
Server-side flag in Supabase: is_lifetime: true.
Bypasses all prompt counting.
Header shows infinity symbol instead of number.
Must be confirmed working before Step 6.

STEP 6 — F12 / Security Blocker
Blocks localStorage manipulation via dev tools.
Safe because lifetime flag is server-side.

STEP 7 — Server-Side Prompt Tracking
Prompt counter moves from localStorage to Supabase per user.
Non-negotiable before launch.
Current localStorage counter in code is development placeholder only.

STEP 8 — Stripe
Payment processing. Needs Supabase user accounts.
Monthly subscription: £9.95
Annual subscription: £99.50 (two months free)
Prompt top-up: £1.99 for 500 prompts
Publication fee: £1 GBP per publication
Paid users: one free publication per week. £1 after that.
The Press per-book fee for non-subscribers — to be confirmed.

STEP 9 — Resend
Email delivery. Needs Supabase user accounts.
Signup verification codes (unique, 20 min, max 3 requests)
Password resets
The InkySwot Bugle newsletter
Notifications
Signup is not live until this step is complete.

STEP 10 — Write Screen with Accessibility Features
The writing panel. Named: Write. Locked 28 May 2026.
Full Write screen built here. Step 1 builds the shell only.
Full Write screen spec must be written before this step begins.
Index Card system full spec must be written before this step begins.
White background — like a page.
Format-aware toolbar (shell in Step 1, fully built here).
Formatting: Bold / Italic / Underline / Font / Size /
Alignment / Lists. Hotkeys.
Chapter selector. Live word count. Auto-save.
Full Screen mode — distraction-free writing. Named: Full Screen.
When active: all UI steps back. Counter shows waiting suggestions.
Ada steps back. Patient. Waiting.
Index Card system:
— Known entities highlighted in gold on space bar press.
— Unregistered entities highlighted in a cooler colour.
— Scan on space bar press only — current page only.
— Database change triggers full manuscript rescan in background.
— Click highlighted word — floating Index Card appears.
— Known entity: card shows full database record, editable.
— New entity: card is blank with relevant fields.
— Cards only appear on deliberate click. Never automatically.
— Multiple cards open simultaneously.
— Cards grey out when writer returns to manuscript — they wait.
— Auto-save on every card.
— AI off: highlighting and cards still work. Ada's suggestions don't.
— Desktop only. No mobile.
Accessibility (CRITICAL DIFFERENTIATOR):
Spell checker: 5-8 suggestions, AI phonetic interpretation,
text-to-speech on hover, option to disable red underlines.
Read Aloud: browser speechSynthesis, zero cost, resume from
point, click to set read-head.
Inline AI Thesaurus (Ctrl+Shift+T): 3-4 contextual alternatives
in story tone, speaker icon on each.
Collaborative Editing: bidirectional, AI at human pace, cursor to
flagged word one at a time, user sees everything, both can flag.
Vital for dyslexic users.
Library section (Research & Reference, Notes & Scratchpad,
Sandbox) to be fully built after this step.
Note: Write screen tagline undecided.
Note: Chapters full spec established 29 May 2026 — see thinking.md.
Full spec needed before build.

STEP 11 — The Treatment
Screenplay-style block editor. Needs Write screen.
Bidirectional sync with all screens.
Blocks: Character / Location / Building / Object / Faction /
Plot Thread / Subplot / Theme / Event / Rule / Chapter /
Action / Dialogue / Note (private, no export) / Section Header.
AI Expand global.
The Treatment assembles itself from the project database.
Ada renders it in the correct professional format.
The writer reviews, refines, and makes it their own.

STEP 12 — Ada
Needs all screens and Write screen to exist.
Full specification in ada.md.
Ada spec must be complete before this step begins.
Ada voice alternative to be confirmed before this step.

STEP 13 — DCW (Timeline Strip)
Full specification in dcw.md.
Needs Treatment in place.
Full width below panels. Always present. Toggleable.
Chapters as ruler across the top.
Track types: Character / Plot / Subplot / Location /
Event / Object / Theme / Tension / Notes.
Tracks are called TRACKS throughout the UI.
Threads are the connections between Chapters and DCW Tracks.
Scene blocks colour-coded per track.
Tension curve — three modes:
Manual — writer drags the curve.
AI-guided — writer sets target, Ada advises how to get there.
Analysis — Ada reads text and plots curve automatically.
Emotional Maps — curves tracking the rise and fall of specific
emotions per character across chapters.
Multiple Maps per character. Colour coded. Toggleable.
Full spec in dcw.md.
Minimap — overview of full timeline, scrollable viewport.
DCW mockup (inkyswot-daw.html) already built — integrate here.

STEP 14 — Export Suite and Format Conversion
Needs Write screen and Treatment.
HEADLINE FEATURE — one click exports entire story world.
Formats: Word / Google Docs / PDF / JSON / Email /
Claude / ChatGPT / Gemini / EPUB.
Format Conversion both directions: prose to script / script to prose.
Screenplay / Radio Drama / Stage Play.
Full revised spec needed before build.
Note: Export Suite is for working writers sharing and backing up.
The Press (Step 15) is for publication. These are different things.

STEP 15 — The Press
Replaces and significantly expands the former Publishing Suite.
Full specification in press.md.
Needs Export Suite (Step 14) in place first.
Where the writer goes when the book is done.
Also a standalone pay-per-book product for non-subscribers.
The Press is an acquisition funnel for InkySwot.

What The Press includes:
Cover Creator — Fixed Spine System. Three-panel canvas.
Real-time spine adjustment. 3D book preview.
Book Layout Tool — open book on screen. Flippable pages.
Drop content. See exactly what prints before uploading anywhere.
Front and Back Matter Assembly — auto-assembled from database.
Ada writes blurb, bio, acknowledgements. Writer refines.
Platform Requirements Database — live, maintained, always current.
Validation layer — green lights only before export.
Metadata — pre-filled from project. Writer completes remainder.
The Guide — honest, platform-agnostic publishing guidance.

Supported formats:
Paperback / Hardback / Ebook.
Audiobook — future. Full spec in press.md.

Supported platforms:
Print: KDP / IngramSpark / Lulu / Barnes & Noble Press / Other.
Ebook: KDP / Draft2Digital / Kobo / Apple Books / Other.

Maintenance commitment:
Platform requirements database monitored and updated
whenever any platform changes its specs.
Ongoing operational commitment — not a one-time build.

Public-facing entry point:
The Press accessible to non-subscribers.
URL to be confirmed — press.inkyswot.com or similar.
Pay per book. No subscription required.

Build complexity:
Cover Creator — may need its own sub-step.
Book Layout Tool — may need its own sub-step.
Full timeline to be assessed before Step 14 begins.

STEP 16 — Admin Panel
Needs Supabase, Stripe, full platform.

STEP 17 — PWA Manifest
Platform complete. Windows first. Mac second.

STEP 18 — Beta
All above signed off. Supabase Pro active before beta users invited.
Ada voice recording at this step.
Beta programme structure to be defined before this step.

STEP 19 — Launch
DNS to production. Triple redundancy.
Testbed at www.inkyswot.com/testbed password protected
during transition.

ONGOING — Content & Operations
Run alongside build, continue post-launch:
Platform Comparison Chart
User Experience Timeline (v1 map built, gaps 4 and 5 to resolve Step 2)
FAQs / Manual / Videos (YouTube — no build content)
Monthly Newsletter (The InkySwot Bugle)
Beta Programme (not yet defined — Facebook page natural channel)
Platform Requirements Database — ongoing maintenance.
The Guide — written in parallel with build, updated post-launch.