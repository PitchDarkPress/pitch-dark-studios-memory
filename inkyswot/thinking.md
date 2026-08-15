File: inkyswot/thinking.md
Last updated: 15 August 2026 — rewritten clean. The 18 June session's
Section A has been overtaken by what was actually built: the pocket
re-architecture EXISTS, though not by the route planned there. That is
recorded honestly below rather than quietly dropped. Today's open
questions are folded in at the top.

This is the LIVE-IDEAS file (overwrite). Settled things belong in
locked-decisions.md; build state belongs in current-state.md.

================================================================
SECTION A — OPEN NOW (15 August 2026)
================================================================

THE VANISHING TINTS — AND WHY THEY ARE NOT A SEPARATE JOB.
A mark is held as "characters 14 to 22 of this paragraph". Edit the words
and the numbers point at the wrong place, so the dashed line under Mole
disappears. GOING LIVE DOES NOT FIX THIS — it preserves it. It has to be
solved WHILE saving is built, because both need the same thing: the
platform following a phrase as the text moves around it. Build saving
first and the store gets built twice.

WHAT "MORE" SHOULD SHOW ON THE PLOT MAPPER.
Currently the four facts the old header line held — Genre, Classification,
Status, Author. Kev asked for "ALL the info that was there before"; those
four ARE all of it. If Basics carries fields worth surfacing while
mapping, they need naming. PARKED by Kev: "We will sort that later."

SHOULD STATUS BE EDITABLE ON THE PLOT MAPPER?
The rule is one field, one door: Basics. But Status changes as a book
progresses, and if the writer keeps opening More to change it, that one
field may want to be live on the screen. Watch it in use before deciding.
The same question will arrive on every screen that shows a fact from
somewhere else.

DOES A SCENE NEED ITS OWN WORD COUNT?
Chapters show "171 / 50–500". Scenes show nothing. Offered and not taken
up — the chapter line already tells the writer what is beneath it, and two
counts meaning different things could confuse. Left as it is; revisit if
scenes start feeling unmeasured.

THE FIVE ROOMS.
If Library is clickable, all five group headings must be. Each room is a
view of what is inside it. Five screens to build, none started, and the
Library's own shape is still unsettled — see Section C.

"BASICS" vs "OVERVIEW" vs "FRONT MATTER".
Still unresolved, still deliberately left as Basics. Overview is the
better of the two for a writing platform; Front Matter is the genuinely
literary option, and it is what publishing calls everything before the
story starts.

CONCEPTS IS OUT OF STEP.
It still uses the old Cast / World / Plot grouping. The sidebar is now
Story / People / World / Library / DCW and the Plot Mapper's menu carries
sixteen sections. Bring Concepts into line when it is next touched.

THE SIZING SWEEP.
Three new house rules were locked on 15 August — a control that changes
its wording must not change its size; a control's size must not depend on
what is beside it; opening something must not push what is above it. They
are done on the Plot Mapper. THE CORRIDOR HAS NOT BEEN SWEPT. Do it when
the corridor is next in hand rather than screen by screen.

================================================================
SECTION B — WHAT HAPPENED TO THE 18 JUNE THINKING
================================================================

THE CODE-SIZE FEAR — RESOLVED, AND THE DIAGNOSIS HELD.
The finding was right: nothing was wrong with reading or changing the
code; what had outgrown a single pass was a FULL REWRITE OF THE WHOLE
INDEX FILE IN ONE GO. Splitting the file removed the problem.

THE POCKET RE-ARCHITECTURE — BUILT, BUT NOT BY THE PLANNED ROUTE.
The June plan was RUNTIME JOINING: the spine fetching a pocket when its
menu item was clicked, chosen specifically to avoid build tooling sitting
on Kev's way of working.
WHAT WAS ACTUALLY BUILT IS BUILD-TIME STITCHING: the Enclosure assembles
corridor + pockets into one index.html, then publishes it.
THE NO-TOOLING PRINCIPLE SURVIVED ANYWAY, because the Enclosure is a
BUTTON in the memory database, not a terminal. No npm, no jargon-filled
errors, no setup — Stitch, wait a minute, Publish.
WORTH KNOWING: the one-time pause the June plan accepted as a small
honest cost never arrived, because there is nothing to fetch at runtime.
The cost moved instead to the publishing ritual, and that ritual has its
own trap (see the publishing rule — Publish too soon after Stitch and it
silently deploys the previous file).

THE DCW AS THE STAGE — NOT BUILT, AND NOT NEEDED SO FAR.
The idea was a permanent DCW stage with screens opening centred in front
of it, summoned and dismissed from the left menu. What exists instead is
the sidebar and pockets: screens replace one another in the corridor.
The idea is not dead, but nothing has demanded it. If it returns, the
question it left open is still the right one: what does the DCW show when
nothing is open?

THE PRESS — the locked two-door version stands, unchanged. The payment /
eligibility gate is still the one piece that is more than presentation,
still likely the last thing built, and may still force a conversation
about what handles payment.

THE DCW VISION — the June worry was that DAW-for-words had been diluted.
It had not. The mixdown, the funnel and the keystone all survive, and the
keystone now has a name and a place in the build: it is STEP TWO of the
Plot Mapper going live. How one record carries its position, its order
and its chapter/scene home at once is no longer an abstract question —
it is what has to happen for making Mole put him in Characters.

THE BANNER JOB — retired. It belonged to the single big index file, which
no longer exists. Pockets made it unnecessary.

================================================================
SECTION C — LIVE OPEN QUESTIONS CARRIED
================================================================

THE LIBRARY'S SHAPE. Long design conversation, no resolution. Rejected:
shelves of spines, a filing drawer of hanging files, a tree of coloured
pills. What is settled: folders are FIXED and platform-provided, with no
New Folder button — the writer never makes a filing decision, so there is
nothing to tidy. Sub-folders mirror the sidebar sections. An entry is
filed in a sub-folder AND may optionally name the location or character it
is about, so it appears on that record's screen too.
THE INSIGHT WORTH KEEPING is Kev's own: "Damn we already have it." Every
screen is already list-on-the-left, detail-on-the-right. The Library may
need no new metaphor at all. That line of thought has never been followed
to its end, and it should be.

THE QUICK-NOTE — three follow-ups, all still open: persistence (scraps
must survive a refresh); a "see all" (a panel listing them, or gather them
onto the screen); and whether a pinned note crosses between views — pinned
to the THING and riding the funnel, or pinned to the VIEW. Then wiring it
across all screens.

THE SITE MAP was built in June against the old four-heading nav. The
sidebar has since been rebuilt. It needs checking against what is live
before it is trusted, and its deeper-level "+" behaviour was never
settled.

WHERE THE MOOD WORDS LIVE (Cold · Bleak · Biting). Pulled off the page on
4 June; wanted, but not yet placed. Candidates: a summonable scene-level
mood line, part of the pop-up, or a margin note.

EVENT ORDER WITHIN A SCENE. Events group by chapter but have no sequence
within a scene, and a line needs order. Decide the mechanism — a position
field, drag-to-order, or a number.

THE TAG SET. Is PROSE the same as ACTION or distinct (working split:
Action = what they do; Prose = description and narration)? DIALOGUE is not
on the list but a scene cannot be written without spoken lines — confirm
its place. Is EMOTION a per-beat tag or the seed of an Emotional Map?

CARRIED FEATURES STILL NEEDING A HOME: Emotional Maps; Ambient
(Atmosphere / Weather / Time); Dark Thoughts (private, never exported).
Tension has a home. THE LIFT — Prologue and Backstory below chapter one —
went with the board on 15 August, but the idea is good and could return in
the Plot Mapper as breaks going the other way, before the beginning.

SANDBOX moving from Library to DCW. Agreed in principle, not done.

THE STAVE PAGE'S WHEEL LABEL — how the wheel shows a chapter page.

================================================================
SECTION D — BACKLOG (still live)
================================================================
- Distraction-free writing — redefine as the Manuscript with its chrome
  hidden; relates to the Manuscript View comfort toggle. Not locked.
- Export Suite full spec — needed before Step 14.
- Manuscript storage 5MB decision — pending before Step 14.
- Proauthorism credit in app — undecided.
- Beta programme structure — undecided before Step 18.
- Full anti-spam strategy — needed before Step 15.
- Ada voice alternative — decide before Step 12. (Sara will NOT voice Ada.)
- Ada full spec — current spec in ada.md, needs more work.
- Cloudflare adoption — recommended pre-launch.
- Device key storage method — before security implementation.
- Export friction detail — metadata completion, AI disclosure prompts,
  publication checklist — before Step 14.
- New device verification — support ticket security questions.
- UX Gap 4 — font import in the Press templates.
- UX Gap 5 — document types in the New Project modal, full list.
- PUBLIC PRESS DATA — where a non-subscriber's book data comes from with
  no platform project: entered COLD, or UPLOADED as a finished manuscript.
  NB (15 August): the continuity library in future.md needs the same
  upload-and-read machinery. If one is built, the other is nearly free.
- POST-LAUNCH, Gap 6 — AI inference from an imported manuscript,
  pre-filling setup fields. Same machinery again.

CHAPTERS SPEC — FRAMEWORK (28 May 2026, still live)
Chapters are living synopses, not just summaries — in constant
conversation with the whole database. Ada guides chapter creation.
Conflict detection: Ada flags a database contradiction once, without
drama. Cross-pollination: a new idea in a chapter prompts Ada to suggest
adding it to the database (one button: go there, record it, come back;
the chapter remembers where it was). The reverse: the database feeds
chapter creation contextually.
NB (15 August): the Plot Mapper is now where this happens. Highlighting a
name and pressing F2 IS the one-button "record it and come back" — the
card opens over the page and the writer returns to exactly where they
were. The conflict detection half is not built, and is the same thing as
Ada-as-continuity-guard in future.md.

================================================================
RETIRED FROM THIS FILE (so nothing feels lost)
================================================================
- The 4 June "NEW MODEL IN BRIEF" — superseded by the MIXDOWN in dcw.md.
- The pre-4-June DCW open questions (writing-card naming, the shutter,
  track controls, the (*) markers, note range, the planning-to-writing
  seam as card mechanics) — they belonged to the column-board / card
  model. Full history in dcw.md.
- CLICK-TO-WRITE — resolved by the wheel.
- PLOT MAPPING beside THE TREATMENT — resolved twice. Dropped 11 June;
  reinstated 15 August as the Plot Mapper, which is the screen that was
  the Synopsis.
- THE BANNER JOB — belonged to the single index file. Pockets ended it.
- THE CODE-SIZE FEAR — resolved by pockets. Whole-file rewrites are now
  per pocket, which is the size they were always meant to be.