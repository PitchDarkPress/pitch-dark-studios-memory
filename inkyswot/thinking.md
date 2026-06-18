File: inkyswot/thinking.md
Last updated: 18 June 2026

NOTE (18 June 2026): this file has been rewritten clean. Today's thinking
session (the code-size fear, the pocket re-architecture, the DCW-as-stage
idea, the Press reconfirmation, and the DCW-vision reassurance) is folded
in at the top as SECTION A. The older 4 June open questions are kept below
where still live; the few since RESOLVED are marked so, not silently
dropped. The stale "NEW MODEL IN BRIEF" has been retired — the live model
is the MIXDOWN in dcw.md; do not work from an older brief.

This is the LIVE-IDEAS file (overwrite). Settled things belong in
locked-decisions.md; build state belongs in current-state.md.

================================================================
SECTION A — TODAY'S THINKING (18 June 2026, chat / NO CODE CHANGED)
================================================================
A long thinking session. Trigger: a real fear that the code is growing too
big for Claude to cope with. It opened out into architecture and, near the
end, the DCW vision itself. Nothing here is built — it is direction, logged
so it cannot slip (the way the Press decision nearly did this session).

1. THE CORE FINDING — what actually broke.
   Not "Claude can't handle the code." Reading it, reasoning about it, and
   changing PARTS of it are all fine. The one thing that has outgrown a
   single pass is a FULL REWRITE OF THE WHOLE INDEX FILE IN ONE GO. That is
   the habit to retire — nothing else.
   Two safe modes that don't depend on it:
   - LINE-ANCHORED EDITS (now): Claude gives the new block + "paste this
     directly after THIS line." The change happens in the editor where the
     whole file already lives; nothing large crosses the chat, nothing
     jams. Does not worsen as the file grows. The banners we began adding
     make the anchors easy for the eye to find.
   - POCKETS (later): splitting the file makes each piece small enough that
     the whole-rewrite rescue move works again — per pocket, never the whole.

2. THE POCKET RE-ARCHITECTURE — agreed DIRECTION (not built).
   Word it RE-ARCHITECTURE, not rebuild — screens' guts carry over; only
   how the code is stored changes.
   - SPINE stays in the index: shell, colour variables, header, left menu,
     and the shared helpers everything leans on (the AI call, the save
     helpers, showScreen).
   - Each screen becomes its own small POCKET FILE in the SAME repo
     (characters.html, locations.html, …). Vercel deploys them together as
     now.
   - RUNTIME JOINING, NO BUILD TOOLING. The spine FETCHES a pocket when its
     menu item is clicked. Chosen over build-time stitching because build
     tooling (terminal, setup, jargon-filled errors) would sit heavily and
     permanently on Kev's way of working — that is the deciding factor, and
     it keeps the no-tooling principle. (Door not bolted: if a developer or
     team ever joins, build-time becomes reasonable — the tooling cost is
     light for someone who lives in terminals.)
   - THE DCW IS A SPECIAL POCKET: its own file (too big and too central to
     stay tangled in the index), BUT loaded first and never dismissed — it
     is the STAGE, not a pop-up. Different rules from the others, correctly.
   - MOST IMPORTANT MAPPING JOB: the line between shared-spine and
     pocket-specific. Right = the rest follows; fuzzy = pockets need things
     they can't reach.
   - BUILD ORDER FIXED: spine first, prove ONE simple pocket (not the DCW),
     then repeat. The big working file stays whole the whole time the test
     runs alongside it — risk is an afternoon on one screen, never months.
     This discipline is what keeps it out of the rabbit hole.
   - Small honest cost: a one-time, styleable pause the first time a screen
     opens (shell never goes black; can hold the previous screen until the
     new one is in hand). Instant every visit after.

3. THE DCW AS THE STAGE — presentation DIRECTION (own session).
   Separate axis from pockets (that is storage; this is presentation) —
   they marry well: each summonable screen is also a pocket.
   - DCW is the permanent STAGE, always there.
   - The LEFT MENU is KEPT as the way in.
   - Click a menu item → its screen opens CENTRED, IN FRONT, DCW hidden
     behind (FILL-IN-FRONT chosen over float-over — the deep-work forms
     want the room).
   - Click the X → screen closes, DCW returns untouched.
   - Only the FRAME changes (a centred panel); the screen's insides are
     unchanged.
   - New machinery: the SUMMON + DISMISS. Small, but it is the mechanism.
   - OPEN: what the DCW shows when nothing is open (default view, and the
     view between panels).

4. THE PRESS — confirmed to its LOCKED version.
   This session's loose "free inside, paid outside" talk is OVERRIDDEN by
   the locked decision (31 May INKYSWOT-6 / 24 May DATABASE REBUILD 1).
   One tool, two doors; inside via nav (subscriber, project + payment in
   place); outside via its own public address with its own sign-up
   (acquisition funnel). £1 per publication; subscribers one free a week,
   then £1. The payment/eligibility GATE is the one piece that is more than
   presentation — likely the LAST pocket built, and may force a
   conversation about what handles payment (outside the no-tooling world).
   Full locked spec lives in locked-decisions.md / security.md — do not
   re-spec it here.

5. THE DCW VISION — NOT lost.
   The day's real worry was that DAW-for-words had been diluted to almost
   nothing. dcw.md corrects this: the vision is fully specified (the
   mixdown; the funnel — board wide end, wheel + page close end, left scene
   menu the mixed-down side list; the Treatment as "the DCW switched on";
   Chapter → Scene → Event with only events becoming prose; fill-in-the-
   blanks). Nothing today shrank it. Today was spent on STORAGE and
   PRESENTATION, so the DCW had no air — absent from the room, not
   diminished. Making the code manageable FREES the ambition, it doesn't
   threaten it.

6. SEQUENCING — the recommendation.
   - Don't start construction at the tail of a long session.
   - The DCW (the KEYSTONE) deserves its OWN clean session, full energy, no
     code-storage talk in the room — get the vision sharp and on the page
     first. First job: the funnel data model (how ONE record carries its
     board position, timeline order AND chapter/scene home at once).
   - The POCKETS are the SAFETY move; their own session, current code
     pasted first, shared-vs-pocket mapped before any file is cut.

7. HOUSEKEEPING — the banner job (unfinished).
   A separate task this session: adding section BANNERS to the big index so
   it's easier to navigate. HALF-DONE — the CSS is fully bannered and the
   style block closed; the body and script are NOT written. That output
   file is INCOMPLETE — do NOT paste it over the working code. The real
   index in the editor is untouched and remains the truth. Finish it the
   line-anchored way: each banner handed with "paste this directly above
   THIS line."

(The standalone capture file inkyswot-thinking-2026-06-18.md was a bridge;
its content now lives here. It can be discarded.)

================================================================
SECTION B — LIVE OPEN QUESTIONS CARRIED (from 4 June, reconciled)
================================================================
STILL LIVE — decide one at a time:

- WHERE THE MOOD WORDS LIVE. Chapter/scene mood words (e.g. Cold · Bleak ·
  Biting) were pulled off the page 4 June; Kev wants them but not yet where.
  Candidates: a summonable scene-level mood line (not printed); part of the
  pop-up; a margin note. UNDECIDED.

- EVENT ORDER WITHIN A SCENE. Events group by Chapter but have no sequence
  within a scene. The spine needs "this event before that one." Events
  already store characters[] and location; they lack a POSITION. Decide the
  mechanism (a position field / drag-to-order / number). Small but
  necessary — a line needs order.

- THE TAG SET. Working list: Action · Chapter · Character · Emotion · Event
  · Location · Note · Prose · Scene · Time.
  SPINE: Chapter · Scene · Event. FLESH: Prose · Action · (Dialogue).
  REFERENCE: Character · Location · Time · Emotion · Note · Object · Theme.
  Opens: is PROSE the same as ACTION or distinct (working split: Action =
  what they do; Prose = description/narration)? DIALOGUE isn't on the list
  but a scene can't be written without spoken lines — confirm its place. Is
  EMOTION a per-beat TAG or the seed of an Emotional Map?

- CARRIED FEATURES — WHERE THEY LIVE IN THE MIXDOWN MODEL. Emotional Maps;
  Ambient (Atmosphere / Weather / Time, Time-as-a-block); the LIFT
  (Prologue / Backstory below Ch.1); Dark Thoughts (private, never
  exported). TENSION now HAS a home (board curve + WP segmented meter); the
  rest still need placing. Fit when reached (Step 13 holds them).

RESOLVED SINCE 4 JUNE (kept so the record shows why they left):
- CLICK-TO-WRITE — resolved by the built WHEEL: clicking enters WRITING
  MODE, a focused full-height surface for the one scene; the wheel stays
  lit so you travel scene-to-scene without leaving. (The "focused" answer
  won over "inline".) See dcw.md TWO STATES.
- PLOT MAPPING beside THE TREATMENT — resolved: Plot Mapping IS the
  Synopsis (the name was dropped, 14 June). The BOARD is the wide end of
  the same mixdown.
- REWRITE dcw.md for the new model — DONE (dcw.md rewritten, 17 June, to
  the mixdown model).
- STORE + INDEX the WP/Treatment mockup — DONE (code-treatment-wheel.html
  in the code locker; the live working file is now wheel-with-roadmap (7)).

================================================================
SECTION C — OTHER OPEN DECISIONS / BACKLOG (still live)
================================================================
- Distraction-free writing — redefine as WP + chrome hidden (the old "Full
  Screen = shutter" definition is retired). Relates to the MANUSCRIPT VIEW
  comfort toggle. Not locked.
- Export Suite full spec — needed before Step 14.
- Manuscript storage 5MB decision — pending before Step 14.
- Sandbox v4.0 position — Sandbox now sits at the HEAD of the DCW (the
  funnel's loose entry point). Confirm its v4.0 build position before Step 1.
- Proauthorism credit in app — undecided.
- Beta programme structure — undecided before Step 18.
- Store full anti-spam strategy — needed before Step 15.
- Ada voice alternative — decide before Step 12. (Sara will NOT voice Ada.)
- Ada full spec — must be complete before further screens are built;
  current spec in ada.md, needs more work.
- Cloudflare adoption — recommended pre-launch.
- Device key storage method — technical solution needed before security
  implementation.
- Export friction detail — metadata completion, AI disclosure prompts,
  publication checklist — spec needed before Step 14.
- New device verification process — support ticket security questions to be
  designed before launch.

CHAPTERS SPEC — FRAMEWORK (28 May 2026, still live)
Chapters are living synopses, not just summaries — in constant conversation
with the whole database. Ada guides chapter creation. Conflict detection:
Ada flags a database contradiction once, without drama. Cross-pollination:
a new idea in a chapter prompts Ada to suggest adding it to the database
(one button: go there, record it, come back; the chapter remembers where it
was). The reverse: the database feeds chapter creation contextually.
Navigation between chapter and database must be seamless. Proauthorism in
action. Full spec needed before build. NB: this sits naturally inside the
timeline-of-events model — chapters are a tier of the spine; the seamless
chapter↔database navigation is exactly what the entity pop-up provides.

LIBRARY / NOTES — reconciled (was "deferred until after Step 10")
The old "Library" wrapper is dropped. NOTES is now Snippets + Research (see
current-state.md MENU SPINE); Sandbox moved to the head of the DCW. The
inline research search still only makes sense once the writing surface
exists — so the build-after-Step-10 intent stands for the search; the menu
homes are settled.

UX MAP GAPS — still open
- Gap 4 — Font import experience in Publishing Suite / Press templates.
- Gap 5 — Document types in the New Project modal — full list needed.
- PUBLIC PRESS DATA — where a non-subscriber's book data comes from with no
  platform project: enter COLD, or UPLOAD a finished manuscript. The locked
  Press decision settles the doors and the money; this cold-vs-upload
  mechanism is still to confirm before building the public Press.

POST-LAUNCH
- Gap 6 — AI inference from an imported manuscript: the platform reads a
  manuscript and pre-fills setup fields where possible. Revisit when revenue
  supports the development cost.

NAV — reconciled
The old DCW sub-entries (Timeline / Storyboard) and a separate Plot Mapping
are gone. The grown MENU SPINE (Landing / Home / four-section nav; Sandbox
at the head of DCW; NOTES = Snippets + Research; Stickies parked as the
quick-note; Press in two homes) lives in current-state.md. Still to action:
add the live section COUNTS (Characters · 5, etc.) and build the nav into
index.html to the new spine.

================================================================
RETIRED FROM THIS FILE (so nothing feels lost)
================================================================
- The 4 June "NEW MODEL IN BRIEF" — superseded by the MIXDOWN model in
  dcw.md. Do not work from an older brief.
- The pre-4-June DCW open questions (writing-card naming, the shutter,
  track controls, the (*) loud/quiet markers, note range, the
  planning-to-writing seam as card mechanics) — already retired; they
  belonged to the column-board / card model. Full history in dcw.md.