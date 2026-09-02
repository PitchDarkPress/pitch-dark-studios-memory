File: inkyswot/thinking.md
Last updated: 1 September 2026 — rewritten clean. The Wheel's state is now
known and its conversion is the live thread at the top. The Basics foot is
built and has moved out to current-state.md and completed.md, leaving one
open question behind it.

This is the LIVE-IDEAS file (overwrite). Settled things belong in
locked-decisions.md; build state belongs in current-state.md.

REMINDER: THIS FILE IS UPDATED AT THE END OF EVERY SESSION, along with
the other four. See the lock in locked-decisions.md and the reason for it
at the head of current-state.md.

================================================================
SECTION A — OPEN NOW (1 September 2026)
================================================================

--- THE WHEEL'S CONVERSION — THE LIVE THREAD ---

THE FILE IS FOUND AND READ. Full state in current-state.md. In one line:
the mechanism is right and everything round it is a June mockup of a
platform that no longer looks like that.

THE PLAN AGREED IN SHAPE, NOT YET BUILT:
1. STRIP, DO NOT REBUILD. Cut the header, both sidebars and the Site Map.
   Keep the page, the scene menu and the wheel. The wheel's code comes
   across byte-for-byte — every locked number in it is correct, and a
   fresh write would get some of them subtly wrong and cost a session
   finding out which.
2. POINT IT AT A REAL PROJECT. This is the join, and the join is where a
   fault will be. Twenty-five hard-coded sheets of Dickens become chapters
   and scenes read from the project.
3. THEN the corridor: a POCKET:manuscript slot, and nav-manuscript
   pointing at it instead of Coming Soon.
The Plot Mapper's own going-live on 25 August is the pattern — same steps,
same order.

THE FIRST DELIVERABLE IS A STATIC STILL: one page, the wheel beside it,
the scene menu, real project data, no writing mode and no movement. Look
at it before anything moves. If it turns wrong at that point we know it is
the join and not the mechanism.

THREE CORRECTIONS TO MAKE DURING THE STRIP, all settled after the file was
written: Tension becomes the segmented bar meter (it is currently the
plain text "55%"); the pop-up colours move to the locked six; and the
screen gains its SECTION ? pill.

WHAT WE DO NOT KNOW AND WILL NOT UNTIL WE RUN IT. Twenty-five pages is
about 26,000 pixels of scroll. A real novel is four hundred pages. THE
BELT HAS NEVER BEEN TESTED AT THAT LENGTH. Watch it on the first real
project.

AND THE HONEST GAP TO STATE PLAINLY RATHER THAN FAKE. The scene menu is
fed by the naming done in the Plot Mapper, and the Plot Mapper's cards do
not write into a shared store yet — that is step two, and it is not built.
So the menu will be EMPTY. It should say so, not invent names.

--- THE ONE QUESTION LEFT ON THE BASICS FOOT ---

After a project has been to the Plot Mapper, the two save buttons sit as
equals. Built as BOTH OUTLINED, because two solid gold buttons side by
side read as loud. Kev has not ruled. If he wants both filled instead, it
is a one-line change.

--- THE CARDS NEED A FACTUAL LAYER (31 August, still open) ---

WHERE IT CAME FROM. Kev raised a "humaniser" — the device on a drum
machine that shifts each hit off the grid so it stops sounding like a
machine — and asked whether the same could be done for AI writing. His
own framing was sharper than the analogy: "The problem with AI generated
content is that it falls back on the same type of sentence. That's the
bit I am trying to stop." NOT LENGTH, CONSTRUCTION.

WHERE THE ANALOGY BREAKS, AND IT IS WORTH KNOWING. A humanise knob works
because the notes are already right and the only fault is that they are
too exact, so controlled inexactness fixes it completely. Prose is not
like that. The evenness is a SYMPTOM of how the text was made, not a layer
on top of it. Randomising sentence lengths gives prose that is irregular
in the WRONG PLACES, which reads as odd rather than alive.

ONE SET OF MEASUREMENTS, TWO TOOLS. Both are legitimate because Kev would
declare the collaboration either way: "even if it were possible to hide
the AI generated text I would still be open about how it was constructed."
  1. A STYLE METER — marks where the writer's own prose has flattened.
     Not correcting it; marking it, the way the checker marks punctuation.
  2. THE SAME MEASUREMENTS applied to generated text before it goes near
     the manuscript.
WHAT TO MEASURE: sentence OPENINGS (subject, participle, subordinate
clause), sentence SHAPES (simple, compound, complex, fragment), lengths
and whether they vary or hover, and REPEATED CONSTRUCTIONS — the same
frame recurring within a few paragraphs. All countable from the passage
using the parser already built.

THEN THE BETTER IDEA UNDERNEATH IT. Measured against what? A count alone
is meaningless. Kev's answer: "I want the ability to have previous work
studied by the platform so it can flag inconsistencies." AND THEN THE
CORRECTION THAT MATTERS: "it's not so much the writing style I want
studied but inconsistencies in the writing. EG: Bill has dark hair in book
one and I give him blond in another."

WHY THAT IS THE STRONGER TOOL. Style consistency is fuzzy — the most it
can say is "this doesn't sound like you". FACT CONSISTENCY IS HARD. Bill
has dark hair or he doesn't. When the tool says his hair changed it is
right or wrong, and the writer can check in a second. It is also the kind
of mistake that genuinely gets through: nobody re-reads book one to check
a hair colour before writing book three.

INCOMPLETE BOOKS ANSWER THEMSELVES. For style, an unfinished draft is a
problem — you would be measuring against something half-formed. FOR
FACTS IT DOES NOT MATTER: a half-written book contributes the facts it
contains and nothing is spoiled by the rest being missing.

THE LOCAL VERSION AND THE WIDE VERSION.
· LOCAL leans on what the platform already knows. If Bill's card says
  dark hair, the tool can scan the manuscript for other hair statements
  near his name and flag disagreements. Narrow, honest, and it uses the
  world-building the writer is already doing.
· WIDE reads the prose and works out the facts itself, no cards needed.
  That needs a model, which means sending text away.

WHICH BRINGS IT TO THE CARDS, AND THIS IS THE OPEN JOB. The character
card is built for THINKING — Personality, Motivation, Secrets, Arc,
Backstory, long prose fields. Good for that, and NEARLY USELESS FOR
CHECKING. "A tall man, greying now, with the sort of face that gives
nothing away" reads as writing, not as facts; the tool cannot reliably
pull "hair: grey" out of it.

THE PROPOSAL, AGREED IN SHAPE:
· A small FACTUAL LAYER under the prose fields. Hair. Eyes. Height.
  Build. Age at the story's start. Distinguishing marks. One word or two
  each, not sentences. Same logic for Locations and Objects with their own
  fields.
· ONE PLACE TO ENTER SOMETHING, TWO THINGS TO USE IT FOR. THE FACTS BUILD
  THE DESCRIPTION: the card assembles a plain sentence from the fields and
  offers it; the writer writes over it in their own words; the facts stay
  underneath regardless. No entering anything twice.
· PROMPT EARNS ITS PLACE PROPERLY. Not "invent me a character" — the
  writer already knows the character. Instead: here are the facts, give me
  a description that uses them. Ada works from what the writer has
  decided. That sits far more comfortably with Proauthorism than a
  blank-field Prompt.
· EXPAND becomes: develop my description, keeping every fact intact.

THE ONE QUESTION LEFT OPEN. When the facts and the prose disagree — the
field says grey, the description says dark — which wins? Claude's
instinct: THE FACTS WIN FOR CHECKING, and the tool FLAGS THE DISAGREEMENT
rather than silently choosing. Kev has not ruled.

THE TRAP TO REMEMBER. A tool that measures a writer against their own past
work REWARDS CONSISTENCY. Pushed too hard it becomes a machine for
stopping a writer developing — flagged every time they try something new.
Useful for catching accidental drift; a cage for a writer growing. IT
SHOULD BE VOLUNTARY AND OCCASIONAL, NEVER ALWAYS ON.

--- THE CHECKER ACROSS THE PLATFORM (31 August) ---

Kev: "Why can't we apply the checker across the entire InkySwot
platform?" No reason. The engine is one self-contained file with nothing
depending on it, and the privacy claim survives wherever it runs.

TWO THINGS CHANGE, AND BOTH NEED DECIDING:
1. THE MANUSCRIPT STOPS BEING OUT OF REACH. The paste-in pop-up was
   chosen partly because the checker structurally COULD NOT touch the
   writing. Embedded in a writing surface, a fix button writes into the
   real text. Fine, but UNDO HAS TO WORK PROPERLY, and that is real work
   rather than an afterthought.
2. THE MARKS MAY NOT BE POSSIBLE EVERYWHERE. The dotted underlines are
   painted over rendered text. That works on a proper writing surface but
   NOT INSIDE AN ORDINARY TEXT BOX. Any plain field would need a list of
   findings instead, or to become a proper surface first.
   NOW PARTLY KNOWN (1 September, from reading the files): the Plot Mapper
   uses contenteditable, so it can take marks. Basics and every
   world-building screen use plain inputs and textareas, so they cannot.
   AND THE WHEEL'S WRITING AREA IS A PLAIN TEXTAREA in the June file —
   which means the manuscript itself, the screen the checker most wants,
   cannot take painted marks as things stand. WORTH SETTLING DURING THE
   WHEEL'S CONVERSION RATHER THAN AFTER, because changing the writing
   surface later is a rebuild.

THE ORDER AGREED: (1) make the engine a shared part in the corridor;
(2) build the attachment — one piece that can be given any writing area
and adds the button, the marks and the panel; (3) attach it to ONE screen
and live with it for a week on real writing before the rest.

THE ORDER WAS THEN DEFERRED at Kev's own suggestion, and rightly: the
platform's flow and missing sections come first, or the attachment gets
built against a shape that is about to change.

--- THE PLOT MAPPING DEAD END (31 August) ---

The live corridor has "Plot Mapping" under NAVIGATE pointing at Coming
Soon, while the real Plot Mapper is under DCW. Two items, similar names,
one working — and the more prominent one does nothing. A writer would try
it first. NEEDS RESOLVING when the corridor is next in hand — which is
Job Two, since the corridor must be opened anyway to add the manuscript
slot and repoint nav-manuscript.

--- THE VANISHING TINTS — STILL OPEN, STILL NOT A SEPARATE JOB ---

A mark is held as "characters 14 to 22 of this paragraph". Edit the words
and the numbers point at the wrong place. The live screen's readBack()
DROPS the marks on edit rather than following them.
GOING LIVE DID NOT FIX THIS — it preserved it. It must be solved WHILE
step two is built, because both need the same thing: the platform
following a phrase as the text moves around it. Build the store first and
it gets built twice.

--- ADA ON THE PLOT MAPPER ---

Prompt and Expand are built on every chapter and scene line and on every
card, but Ada is NOT CONNECTED to that screen. They are shown quiet and
disabled with a title saying why. Named as the next piece of work on that
screen on 25 August; still not done.

--- THE MYSTERY PLOTTER AND THE EVENT PLANNER MAY BE ONE TOOL ---

The mystery grid was built on 25 August; the Event Planner was designed on
26 August. TWO APPROACHES TO THE SAME PROBLEM, A DAY APART, AND NEITHER
CONVERSATION MENTIONED THE OTHER.
· The mystery grid holds people against CLOCK TIME across the top.
· The Event Planner holds people against OFFSETS FROM ZERO HOUR, with
  clock time as a derived coat.
THE EVENT PLANNER'S MODEL IS THE SHARPER ONE — offsets survive a change of
mind about when the murder happened; clock times do not.
BUT THE MYSTERY GRID HAS THE SECOND HALF the Event Planner lacks: the
SHOWN timeline, and the checks that run across both. That second half is
the point of the whole thing, and it is where "does the reader have enough
to solve it, and when?" gets answered.
LOOK AT BOTH TOGETHER BEFORE BUILDING MORE ON EITHER. The grid has never
been reviewed since the day it was built.

--- THE DESK'S TWO OPEN QUESTIONS ---

1. IS THE DESK ONE INSTRUMENT PER SCENE, OR IS THE WHOLE BOOK THE
   INSTRUMENT? Raised by the envelope idea (attack, decay, sustain,
   release — shape over time rather than intensity). A synth patch holds
   across a performance. IF THE SAME SETTINGS RAN ACROSS EVERY SCENE, THAT
   IS NOT A MIXING TOOL ANY MORE — THAT IS THE VOICE OF THE BOOK. Where do
   the settings live: the scene, or the manuscript?
2. HOW MANY FADERS, AND WHAT ARE THEY CALLED? "Any number" was
   enthusiasm. TWENTY FADERS IS A COCKPIT, AND A COCKPIT IS A SCREEN
   NOBODY OPENS. Likely four or five.

--- THE EVENT PLANNER'S REMAINING QUESTIONS ---

Does the zero hour drop line stay fixed at the centre of the screen, or
move with the timeline as the writer pans? And Kev sees the board as "more
dynamic" than static draggable bars, so the interaction model is still
open and wants exploring before any prototype.
HOW IT REACHES THE MAIN WORK SCREEN IS DELIBERATELY PARKED.

--- THE SERIES BIBLE IMPORT ---

Raised 25 August for Research & Reference, not built. The writer uploads
THEIR OWN finished books; the platform reads them for continuity and as a
reference for the writer's own voice.
CLAUDE'S FRAMING, WORTH KEEPING: it is the writer teaching Ada their own
voice from their own books — not the AI imposing a style but the opposite,
and arguably THE STRONGEST PROAUTHORIST THING ON THE PLATFORM.
TWO THINGS TO DECIDE BEFORE IT IS BUILT:
· THE BOUNDARY. The writer's own books, yes. Someone else's books uploaded
  in order to write like them is a different thing entirely, and the
  position wants taking before somebody does it rather than after.
· THE OPEN QUESTION THAT DECIDES THE SHAPE: does the writer confirm what
  gets extracted before it lands in Characters, or does it just appear?
A HARD LIMIT ALREADY KNOWN: Ada cannot read a whole novel every time
Prompt is pressed. Style reference must be A DISTILLED THING — the sense
of the sentences, the rhythms, the handling of dialogue — produced once
and carried, never the book itself.
Same machinery as the continuity library, the public Press and the
post-launch import inference. BUILD ONE AND THE REST ARE NEARLY FREE, and
the confirm-or-appear question should be answered once for all four.

--- CARRIED FROM 15 AUGUST, STILL OPEN ---

WHAT "MORE" SHOULD SHOW ON THE PLOT MAPPER. Currently Genre,
Classification, Status, Author. Parked by Kev: "We will sort that later."

SHOULD STATUS BE EDITABLE ON THE PLOT MAPPER? The rule is one field, one
door: Basics. But Status changes as a book progresses. Watch it in use.
The same question arrives on every screen showing a fact from elsewhere.

DOES A SCENE NEED ITS OWN WORD COUNT? Chapters show "171 / 50–500";
scenes show nothing. Offered and not taken up. Revisit if scenes start
feeling unmeasured.

THE FIVE ROOMS. If Library is clickable, all five group headings must be.
Five screens, none started.

"BASICS" vs "OVERVIEW" vs "FRONT MATTER". Still deliberately Basics.
NOTE: the screen's own title still reads "Overview" while the sidebar says
Basics. Two names for one screen, live, today.

CONCEPTS IS OUT OF STEP — still the old Cast / World / Plot grouping.

THE SIZING SWEEP. Three house rules locked 15 August, a fourth added
1 September (a row of controls is one size throughout). Done on the Plot
Mapper and now on the Basics foot. THE CORRIDOR HAS STILL NOT BEEN SWEPT.
Do it when the corridor is next in hand rather than screen by screen —
which is Job Two.

================================================================
SECTION B — WHAT HAPPENED TO THE 18 JUNE THINKING
================================================================

THE CODE-SIZE FEAR — RESOLVED. Nothing was wrong with reading or changing
the code; what had outgrown a single pass was a FULL REWRITE OF THE WHOLE
INDEX FILE IN ONE GO. Splitting removed the problem.

THE POCKET RE-ARCHITECTURE — BUILT, BUT NOT BY THE PLANNED ROUTE. The
June plan was RUNTIME JOINING. What was built is BUILD-TIME STITCHING.
THE NO-TOOLING PRINCIPLE SURVIVED ANYWAY, because the Enclosure is a
BUTTON, not a terminal.
THE COST MOVED to the publishing ritual, and that ritual has its own trap
(publish too soon after stitch and it silently deploys the previous file).
NOTE (25 August): AND THE ENCLOSURE ITSELF HAD A TRAP — a maintained list
of pockets that could silently fall behind the corridor. Fixed. The
lesson is general and now locked: when a tool can fail quietly, make it
count what it did.

THE DCW AS THE STAGE — NOT BUILT, AND NOT NEEDED SO FAR. What exists is
the sidebar and pockets: screens replace one another in the corridor. If
it returns, the question it left open is still right: what does the DCW
show when nothing is open?

THE PRESS — the locked two-door version stands. The payment / eligibility
gate is still the one piece that is more than presentation.

THE DCW VISION — the mixdown, the funnel and the keystone all survive,
and the keystone now has a name and a place: it is STEP TWO of the Plot
Mapper going live.

THE BANNER JOB — retired. Pockets made it unnecessary.

================================================================
SECTION C — LIVE OPEN QUESTIONS CARRIED
================================================================

THE LIBRARY'S SHAPE. Rejected: shelves of spines, a filing drawer of
hanging files, a tree of coloured pills. Settled: folders are FIXED and
platform-provided, with no New Folder button — the writer never makes a
filing decision, so there is nothing to tidy. Sub-folders mirror the
sidebar sections. An entry is filed in a sub-folder AND may optionally
name the location or character it is about.
THE INSIGHT WORTH KEEPING is Kev's own: "Damn we already have it." Every
screen is already list-on-the-left, detail-on-the-right. NEVER FOLLOWED
TO ITS END, AND IT SHOULD BE.

THE QUICK-NOTE — persistence; a "see all"; whether a pinned note crosses
between views. Then wiring it across all screens.

THE SITE MAP was built in June against the old four-heading nav. Needs
checking against what is live. NOTE 1 SEPTEMBER: the only copy of it we
have seen is the one inside the Wheel file, and it is the old one. When
the Wheel is stripped the Site Map goes with the cut — so if it is wanted,
lift it out first rather than losing it.

WHERE THE MOOD WORDS LIVE (Cold · Bleak · Biting). Wanted, not placed.

EVENT ORDER WITHIN A SCENE. Events group by chapter but have no sequence
within a scene, and a line needs order.

THE TAG SET. Is PROSE the same as ACTION or distinct? DIALOGUE is not on
the list but a scene cannot be written without spoken lines. Is EMOTION a
per-beat tag or the seed of an Emotional Map?

CARRIED FEATURES STILL NEEDING A HOME: Emotional Maps; Ambient
(Atmosphere / Weather / Time); Dark Thoughts (private, never exported).
THE LIFT — Prologue and Backstory below chapter one — went with the
board, but the idea is good and could return in the Plot Mapper as breaks
going the other way, before the beginning.

SANDBOX moving from Library to DCW. Agreed in principle, not done.

THE STAVE PAGE'S WHEEL LABEL.

================================================================
SECTION D — BACKLOG (still live)
================================================================
- Distraction-free writing — redefine as the Manuscript with its chrome
  hidden. Not locked.
- Export Suite full spec — needed before Step 14.
- Manuscript storage 5MB decision — pending before Step 14.
- Proauthorism credit in app — undecided.
- Beta programme structure — undecided before Step 18.
- Full anti-spam strategy — needed before Step 15.
- Ada voice alternative — decide before Step 12. (Sara will NOT voice
  Ada.)
- Ada full spec — current spec in ada.md, needs more work.
- Cloudflare adoption — recommended pre-launch.
- Device key storage method — before security implementation.
- Export friction detail — metadata completion, AI disclosure prompts,
  publication checklist — before Step 14.
- New device verification — support ticket security questions.
- UX Gap 4 — font import in the Press templates.
- UX Gap 5 — document types in the New Project modal, full list.
- PUBLIC PRESS DATA — where a non-subscriber's book data comes from with
  no platform project: entered COLD, or UPLOADED as a finished
  manuscript. THE SAME MACHINERY as the continuity library and the series
  bible import.
- POST-LAUNCH, Gap 6 — AI inference from an imported manuscript,
  pre-filling setup fields. Same machinery again.

CHAPTERS SPEC — FRAMEWORK (28 May 2026, still live)
Chapters are living synopses, not just summaries — in constant
conversation with the whole database. Ada guides chapter creation.
Conflict detection: Ada flags a database contradiction once, without
drama. Cross-pollination: a new idea in a chapter prompts Ada to suggest
adding it to the database (one button: go there, record it, come back).
NB: the Plot Mapper is now where this happens. Highlighting a name and
pressing F2 IS the one-button "record it and come back". THE CONFLICT
DETECTION HALF IS NOT BUILT, and it is the same thing as Ada-as-
continuity-guard, the fact-consistency idea in Section A, and the
continuity library in future.md. FOUR NAMES, ONE FEATURE.

================================================================
RETIRED FROM THIS FILE (so nothing feels lost)
================================================================
- The 4 June "NEW MODEL IN BRIEF" — superseded by the MIXDOWN in dcw.md.
- The pre-4-June DCW open questions — full history in dcw.md.
- CLICK-TO-WRITE — resolved by the wheel.
- PLOT MAPPING beside THE TREATMENT — resolved twice.
- THE BANNER JOB — pockets ended it.
- THE CODE-SIZE FEAR — resolved by pockets.
- "NOTHING SAVES" ON THE PLOT MAPPER — closed 25 August; it saves with
  the project.
- "NOT YET A POCKET" — closed 25 August; it is pockets/plot-mapper.html
  and it is live.
- THE SPELL CHECKER'S OVERLAY PROBLEM — closed 28 August. The CSS Custom
  Highlight API does it without inserting anything, and it is built and
  working in the checker.
- WHERE THE BASICS SAVE ROW LIVES — closed 1 September. The pocket, not
  the corridor. Read both files before deciding, every time.
- WHAT STATE THE WHEEL FILE IS IN — closed 1 September. Read and written
  up in current-state.md.
- "THE JOURNEY STOPS DEAD AT STEP ONE" — closed 1 September. The foot of
  Basics now points forward.