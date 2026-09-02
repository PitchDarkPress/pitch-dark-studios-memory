File: inkyswot/locked-decisions.md
Last updated: 1 September 2026 — ADD-ONLY update. Four new locks from the
1 September session are added under WORKING PRACTICE, THE MANUSCRIPT AND
THE WHEEL, and a new BASICS block. Nothing has been deleted or moved.

NOTE ON THIS FILE
Normally add-only. Rewritten whole when a model shift supersedes a block
of locks (4, 7, 9, 11, 17 June; 15 August; 31 August). Superseded locks
are NOT deleted — they move to the foot, dated.

WHAT CHANGED SINCE 15 AUGUST, IN ONE LINE EACH
- THE DATABASE IS UPDATED AT THE END OF EVERY SESSION. New, and the
  reason it is new is that it was not.
- THE PLOT MAPPER IS LIVE as pockets/plot-mapper.html, and it SAVES.
- THE ENCLOSURE READS THE CORRIDOR, not a maintained list, and reports
  "Placed N of N pockets".
- THE CHECKER exists, with a body of locks of its own.
- THE DESK is settled in shape: a synth, not a mixing desk.
- THE EVENT PLANNER is designed: offsets are the truth.

AND SINCE 31 AUGUST
- THE WHEEL IS STRIPPED, NOT REBUILT. Its mechanism is correct and is not
  to be rewritten.
- THE FOOT OF A SCREEN IS ONE SET OF BUTTONS, ALL THE SAME SIZE.
- SAVING IS SHOWN, NOT PERFORMED.
- EVERY DOOR OFF A SCREEN SAVES BEFORE IT OPENS.

================================================================
LIVE LOCKED DECISIONS
================================================================

--- WORKING PRACTICE ---

UPDATE THE DATABASE AT THE END OF EVERY SESSION — LOCKED (31 August 2026)
Before a session closes, current-state.md, locked-decisions.md,
completed.md, thinking.md and future.md are brought current. Not when
there is time. Not next session. AT THE END OF THE SESSION THAT DID THE
WORK, while the reasoning is still in the room.
WHY: the code survives on disk; the REASONING does not. A repository shows
WHAT was built. Only these files show WHY, what was tried and rejected,
and what the trap was. When 15–31 August went unwritten the code was still
there, but two weeks of decisions were nearly lost and were recovered only
because the session record could be searched.
IF A SESSION ENDS ABRUPTLY, the next one begins by writing up the last.

EVERY WORKING FILE IS RECORDED UNDER ITS FILENAME — LOCKED
(1 September 2026)
The Wheel could not be assessed for a whole session because no database
file had ever written down which file it was. The Plot Mapper had
code-plot-mapper-10.html; the mystery grid had code-mystery-grid.html; the
Wheel had only "a mockup built on A Christmas Carol". A description is not
a filename. WHEN A THING IS BUILT, ITS FILENAME GOES IN THE FILE.

FILE DISCIPLINE — LOCKED (2 June 2026)
When updating any .md file, rewrite the WHOLE file clean and hand it back
complete. Never a list of patches. The .md is the single source of truth;
the code is the truth above it.

WORK FROM THE IMAGE / THE CODE — LOCKED (9 June 2026, reinforced 31
August) A screenshot from Kev IS the template — match it, do not
reinterpret it. When changing a built file, work from the pasted code,
never a reconstruction. SMALL CHANGES MEAN SMALL CHANGES.
ADDED 31 AUGUST: A SCREENSHOT IS NOT A SOURCE FOR DIAGNOSIS. Two
diagnoses of the sidebar were made from screenshots and both were wrong,
because the two images were of different screens and neither was the file.
AND index.html IS THE OUTPUT, NOT A SOURCE — corridor.html is where the
menu lives and where a menu fix belongs.

ABSENCE IS NOT ACCIDENT — LOCKED (31 August 2026)
Chapters and The Treatment are stitched into index.html with no way in,
and that is DELIBERATE (11 August). Claude read it as an orphaning fault
and proposed a check for unreachable screens. Kev: "I don't think anything
is unreachable." He was right. BEFORE CALLING SOMETHING MISSING, CHECK
WHETHER IT WAS REMOVED ON PURPOSE. If a reachability check is ever built
it must know the difference.

WHEN A FAULT SURVIVES ONE FIX, MAKE THE SCREEN SAY WHAT IT DID — LOCKED
(15 August 2026, reinforced 28 August)
Build a version that prints each step to a line on the page rather than
guessing a third time. That is how the history clash was found.
ADDED 28 AUGUST: A DIAGNOSTIC PAGE MUST SHOW THE ENGINE'S OWN WORKINGS,
never its own separate calculation of what it thinks the engine did. Four
builds of the checker were spent chasing numbers the page had worked out
for itself while the engine believed something different.

WHEN A TOOL CAN FAIL QUIETLY, MAKE IT COUNT WHAT IT DID — LOCKED
(25 August 2026)
The Enclosure placed 15 of 16 pockets and said nothing. It now reports
"Placed N of N". The checker reports "Checked 47,074 words, found
nothing", because zero findings and a pass that never ran look identical
otherwise. THE PATTERN IS GENERAL: a silent success and a silent failure
must never look the same.

NEVER NAME A VARIABLE history, name, location, status, top, self or
parent — LOCKED (15 August 2026)
The window already owns them and a top-level var will not override it.
"var history = []" silently killed every action that changed the Plot
Mapper for two days.

CLEAN-REBUILD RULE — LOCKED (6 June 2026)
If edits stop showing on screen, do NOT keep editing — clean rebuild in a
fresh file.

DESIGN-A-MECHANISM RULE — LOCKED (4 June 2026)
Build a small STATIC mockup first, agree the still picture, THEN add
movement. A sketch from Kev beats ten descriptions — ask for one.

A TEST PAGE CARRIES ITS ENGINE INSIDE IT — LOCKED (28 August 2026)
A test page that loads its engine from a separate file fails silently when
the two drift apart, and browsers save duplicates rather than overwriting.
An hour was lost to a new page sitting beside an old engine.
AND EVERY TEST PAGE CARRIES A BUILD STAMP in its top corner ("BUILD 12 ·
28 AUG"), so which copy is open can be seen at a glance.

--- PLATFORM ---

PLATFORM IDENTITY
InkySwot is a writing platform. Not a content generation engine.
Assisted creation. Not instant generation. Non-negotiable.
Tagline: Publish and be damned. Always.
"Publish and be prepared" must never be used.

PROAUTHORISM
Declared human-AI collaboration. The writer's voice is ALWAYS primary.
Ada proposes and assists; she never writes the prose. Every word stays the
writer's to change.
CLARIFIED 25 AUGUST (the Desk): what matters is the writer's hand on the
control, the writer's choice of which version to use, and the writer's
ability to edit any of them — NOT whether Ada produced sentences. Claude
argued the stricter line and withdrew it when Kev pointed at their own
prior collaborative work. THE CORRECT CONSTRAINT IS THAT THE WRITER'S
ORIGINAL SURVIVES AND CANNOT BE OVERWRITTEN.
CLARIFIED 31 AUGUST: a tool that HIDES machine authorship would run
against Proauthorism, but a writer who declares the collaboration either
way is not hiding anything. The declaration is the point; the disguise
never was.

INKYSWOT IS THE DCW
The DCW is not a screen, strip, board or panel. It is the WHOLE platform.
Every section already built is part of the instrument. The database is the
bones of the story. Locked: 4 June 2026.

CORRIDOR PLUS POCKETS — THE ARCHITECTURE — LOCKED (August 2026)
- corridor.html is the shared shell: header, sidebar, all shared CSS and
  JavaScript. Pockets drop into it at <!-- POCKET:id --> slots.
- pockets/ holds one HTML file per screen. HTML only, though a pocket may
  carry its own scoped <style> and <script>.
- THE ENCLOSURE, at core/enclosure.html in the memory database: STITCH
  assembles corridor + pockets into index.html; PUBLISH TO LIVE pushes it
  to PitchDarkPress/inkyswot-app; Vercel deploys to app.inkyswot.com.
- INDEX.HTML IS THE OUTPUT, NOT A SOURCE.
Private repo: PitchDarkPress/inkyswot-rebuild.

A SCREEN'S OWN FURNITURE LIVES IN ITS POCKET — LOCKED (1 September 2026)
Established by reading both files rather than assuming. The corridor holds
the SLOT and the SHARED FUNCTIONS a screen calls (autoSave,
saveProjectHeader, showScreen, getProjects/saveProjects); the pocket holds
all of that screen's markup, including its buttons. So the Basics save row
is a one-file change with no corridor edit and no risk to the shared
shell.
THE COROLLARY: before deciding which file a change belongs in, READ BOTH.
The corridor's autoSave reaching into the Basics screen by element name
(ph-format, ph-audience, ph-outline and the hidden stubs) makes it look
from the outside as though the corridor owns that screen. It does not.

THE ENCLOSURE READS THE CORRIDOR — LOCKED (25 August 2026)
(SUPERSEDES the hard-coded pocket list.)
The Enclosure takes its list of pockets FROM THE CORRIDOR'S OWN SLOTS, not
from a list kept inside itself. There is no longer a list to forget to
update. IT REPORTS "PLACED N OF N POCKETS" at the end of every stitch, so
a silent miss is impossible. Tested against three deliberate scenarios
before deploying: all present, one missing, and a corridor with no slots.
The Split side was left untouched.

THE PUBLISHING RULE — LOCKED, LEARNED TWICE
WAIT A FULL MINUTE between Stitch and Publish. Publishing twenty seconds
after Stitch reads the PREVIOUS index.html and silently deploys stale
code. Stitch's character count and Publish's character count MUST MATCH
before a hard refresh is trusted. NEVER press Split unless deliberately
re-splitting a whole index.html. NEVER press "ADD SPELL CHECK TO
CORRIDOR" — it pushes an older corridor back over the fix.

--- BASICS (THE OVERVIEW SCREEN) ---

THE FOOT OF THE SCREEN IS ONE SET OF BUTTONS, ALL THE SAME SIZE — LOCKED
(1 September 2026)
Kev: "I am finding it hard to reconcile three buttons of different sizes."
Three buttons across the foot of a form read as untidy when each takes the
width of its own wording. They now share ONE FIXED WIDTH, sized to the
longest, with their text centred.
AND THE CONSEQUENCE THAT MATTERS: THE WIDTH DECIDES THE WORDING, NOT THE
OTHER WAY ROUND. "Save and go to the Plot Mapper" at three-across will not
fit an 800px column. The wording was cut to fit the set, not the set
stretched to fit the wording.
This extends the 15 August rules rather than replacing them: a control's
size must not depend on what is beside it, and must not change with its
wording — and now, a ROW of controls doing the same kind of job is one
size throughout.

THE THREE DOORS AT THE FOOT OF BASICS — LOCKED (1 September 2026)
SAVE · PLOT MAPPER → · BACK TO PROJECTS. All three always present, always
in that order, none ever hidden behind a first-visit rule.
- Save saves and stays.
- Plot Mapper → saves and goes forward.
- Back to Projects saves and goes back.
THE ARROW IS THE CROSSING'S SHAPE. It matches "Edit in Basics →" already
on the Plot Mapper's header, so the writer learns one mark for "this takes
you to another screen" — and that is the pattern Job Three will use in
both directions.
FIRST VISIT ONLY, the Plot Mapper button is the filled one so a new
writer's eye lands on the way forward; afterwards the two sit as equals. A
project has "been to the Plot Mapper" if it carries a plotMapper record.
NO NEW FLAG WAS ADDED.
WHY IT IS NOT CLEVERER THAN THAT: a button that quietly behaves
differently depending on hidden state is what makes a platform feel
unpredictable. Only the FILL changes; nothing appears or disappears.

EVERY DOOR OFF A SCREEN SAVES BEFORE IT OPENS — LOCKED (1 September 2026)
Not just the forward one. Back to Projects saves too. A writer should
never have to work out which exits are safe, and "which button keeps my
work" is not a question a writing platform may ask.

SAVING IS SHOWN, NOT PERFORMED — LOCKED (1 September 2026)
Kev, on the first build: it is not clear the work is saved on the Plot
Mapper and Back to Projects buttons. THE SCREEN HAD BEEN SAVING ON EVERY
KEYSTROKE SINCE 12 AUGUST AND HAD NEVER SAID SO.
THE TICK WAS THE CAUSE, NOT THE CURE. A confirmation that appears only
when Save is pressed teaches the writer that saving is something the Save
button does — which makes every other button look like a way to lose work.
A save that happens continuously must be reported continuously.
SO: a standing line beneath the row, reading "Saved · 14:32" in gold,
updating on every save, present all the time. Before the first save it
says plainly that the screen saves as you type.
THIS IS THE SAME LOCK AS "MAKE IT COUNT WHAT IT DID", pointed at the
writer rather than at the builder: a silent success and a silent failure
must never look the same — and to a writer, an unreported save is silent.

--- THE PLOT MAPPER ---

THE SYNOPSIS SCREEN IS THE PLOT MAPPER — LOCKED (15 August 2026)
Not a screen that feeds a mapper. It IS the mapper. The writer writes the
story down in one continuous piece, breaks it into chapters and scenes,
and names the people, places and things inside it. That is plot mapping.
AND IT IS THE ONLY ONE. The corkboard, the rotated board, the vertical DCW
and the horizontal work area are all out. If a board is ever revived it
needs a DIFFERENT NAME.
LIVE SINCE 25 AUGUST as pockets/plot-mapper.html.

THE PLOT MAPPER SAVES WITH THE PROJECT — LOCKED (25 August 2026)
The document is written onto the project in localStorage "is-projects"
under plotMapper: parts, made, the budget, and the indent and details
switches, with currentWords and lastEdited updated. Debounced, and also on
beforeunload.

THE PLOT MAPPER AND THE WHEEL ARE A PAIR — LOCKED (31 August 2026)
Basics and Publishing are one-way gates at either end of the journey. THE
PLOT MAPPER AND THE WHEEL ARE NOT: the writer must be able to move back
and forth between them freely, as often as the work demands. Plotting is
not done once and finished.

F2 IS THE ONE KEY — LOCKED (15 August 2026)
It reads the situation. Bare cursor: Chapter break (1) or Scene break (2).
A phrase highlighted: the SIXTEEN sections of the sidebar. Nothing appears
from highlighting alone — selecting a word to correct it must never summon
a menu.

THE SECTION MENU IS THE SIDEBAR — LOCKED (15 August 2026)
All sixteen sections, in the sidebar's own order, under its four group
headings, in the four family colours, four columns so none is hidden. The
screen you are on is left out of its own list.

CATCHING PART OF A WORD IS ENOUGH — LOCKED (15 August 2026)
Selections grow out to whole words. Precision is NEVER required of the
writer. Kev: "a tired writer would get pissed off damn quick."

A MARK IS A DASHED LINE BENEATH, NEVER A TINTED WORD — LOCKED
(15 August 2026)
The writing stays the writer's; the colour is an annotation on it, the way
a pencil marks a page. Colour is by FAMILY, not by section — four colours
read at a glance, sixteen do not.

THE BREAK — KEV'S DIVIDER — LOCKED (15 August 2026)
A dashed gold hairline through the writing, the "Ch. 1" pill out in a left
gutter, a gold dot at the far end. Scene breaks are the same mark in pale
stone. The same divider is used wherever chapters and scenes are shown, so
the writer learns one mark. A break never falls mid-word.

ADA SITS BESIDE WHAT SHE WORKS ON — LOCKED (15 August 2026)
Prompt and Expand belong ON the chapter or scene line, right-hand end, and
on a card. NEVER floating at the foot of a page with no subject.
AND HER BUTTONS READ THEIR CONTENT: nothing to expand means Expand goes
quiet and says why. A BUTTON THAT CANNOT WORK SAYS SO rather than failing
when pressed. On the live Plot Mapper both buttons are shown QUIET and
disabled, because Ada is not yet connected to that screen.

ALSO CALLED — ONE CARD, SEVERAL NAMES — LOCKED (15 August 2026)
Mr. Toad is also Toad. The first name is the proper one; the rest are ways
of referring to it. The platform PROPOSES the obvious ones as faint dashed
pills; nothing is ever added behind the writer's back.
A REJECTED SUGGESTION GOES QUIET, NOT AWAY — it stops being offered and
gathers behind a "2 set aside" line. Rejection belongs to that card only.

--- THE CHECKER (27–28 August 2026) ---

THE TEXT NEVER LEAVES THE MACHINE — LOCKED (28 August 2026)
The checker runs entirely in the browser. Not "we don't store it" — the
text does not go anywhere. This is a fact about the architecture, not a
promise, and it is the one claim Grammarly structurally cannot make.
Fetching a dictionary is not sending text: the dictionary comes down, the
checking happens here.

THE CHECKER PROPOSES, IT NEVER REWRITES — LOCKED (28 August 2026)
It marks and offers. The writer decides. Where nothing safe can be offered
it says so plainly rather than pretending.

THE PASTE-IN POP-UP — LOCKED (27 August 2026)
The writer copies a passage in and copies the result back. THE MANUSCRIPT
IS NEVER TOUCHED; the instrument cannot reach it. The friction is accepted
deliberately, because it keeps the writer as the only party who decides
what enters the manuscript.

MARKS ARE PAINTED, NOT INSERTED — LOCKED (28 August 2026)
The CSS Custom Highlight API draws the underlines. NOTHING IS PUT INTO THE
WRITER'S TEXT — no tags, no wrappers. Wrapping words in spans would break
undo, jump the caret, and risk corrupting the document. Rejected on those
grounds.
NOTE: this also solves the hard half of InkySwot's own spell checker,
which had been specced as an invisible mirrored overlay.

THE CHECKER HAS NO SIZE LIMIT — LOCKED (28 August 2026)
Not a large one. NONE. Telling a writer to chop their manuscript up, or
letting them paste it all in and having it fail, would both damage the
platform's credibility. The work is done IN SLICES with the screen handed
back between each, so the window never freezes and the browser never
offers to kill the page. A longer manuscript takes longer; that is all.
AND A PROGRESS BAR IS HELD BACK a quarter of a second — a bar that flashes
for a fifth of a second is worse than no bar.

FALSE POSITIVES COST MORE THAN MISSES — LOCKED (28 August 2026)
Taken from the master specification and kept: CORRECT ERRORS. QUESTION
DOUBTFUL CASES. PRESERVE VOICE. Twelve findings worth checking beats a
hundred and forty-seven that need sorting. Missing an arguable issue costs
a writer very little; telling them good prose is wrong costs their trust
in the whole instrument.
IN PRACTICE: the test suite has more SILENCE tests than CATCH tests, and
every false positive found in use is fixed at the rule or the parser and
then added permanently to the regression corpus.

RULES ASSERT, QUERIES ONLY ASK — LOCKED (28 August 2026)
Two kinds of finding, marked differently and worded differently. A rule
says this is wrong. A query says I am not sure about this one, and NEVER
offers a rewrite. A query dressed as a fault is the worst thing this tool
could do — particularly for a writer who cannot judge which it is.

THE PARSER COMES BEFORE THE RULES — LOCKED (28 August 2026)
Almost every false positive comes from a rule firing on text the parser
should have marked as something else. Sentence boundaries, protected
regions, paragraph kinds, quote roles and dialogue state are worked out
FIRST. A pile of regular expressions is the wrong architecture, and it
stays wrong when the input is small.

RAGGED EDGES — LOCKED (28 August 2026)
A pasted passage is usually cut out of the middle of a scene. Every rule
that depends on things matching in pairs is GENTLER AT THE EDGES than in
the middle: near-certain in the body, no more than a query in the first
and last sentence.

RAW FREQUENCY IS THE MISLEADING SIGNAL — LOCKED (28 August 2026)
Deciding which speech marks a manuscript uses by counting them is wrong.
Emphasis is common and dialogue is structured, so a passage with little
speech and much emphasis votes the wrong way. THE VOTE COUNTS ONLY
STRUCTURE: a speech tag after a closing mark, and an opening mark at the
head of a paragraph. Frequency is given no weight at all.

A SPEECH TAG NEEDS A SUBJECT — LOCKED (28 August 2026)
Many speech verbs are also ordinary verbs — went, put, called, added,
began. Looking only for the verb turns "'chill out' and went on his way"
into a dialogue tag. A real tag has a subject beside the verb: he said,
Agnes replied, asked Constance.

A SPEECH TAG CANNOT FOLLOW A FULL STOP — LOCKED (28 August 2026)
A tag follows a comma, a question mark or an exclamation mark. Where the
speech closes on a full stop, whatever comes next is a new sentence of
narration, however much it reads like a tag: "a complete and utter fool."
I said nothing.

WHERE BOTH SPEECH MARKS ARE IN USE, SAY SO — LOCKED (28 August 2026)
The Christmas Murders Act One punctuates some dialogue with double marks
and some with single. Forcing a choice would flag every line of the other
kind as faulty — around forty confident false positives on good prose. THE
HONEST ANSWER IS "BOTH ARE IN USE", reported as a consistency finding for
the writer to settle. Converting one to the other is mechanical and safe.

THE FINDING ALWAYS SHOWS; THE EXPLANATION IS SWITCHABLE — LOCKED
(31 August 2026)
Two levels. What is wrong, always. Why, beneath it, with one switch for
the whole screen — not thirty. Turning it off makes the tool terser, never
mute. The wording carries no grammatical terminology.

--- THE DESK (25 August 2026) ---

THE DESK IS A SYNTH, NOT A MIXING DESK — LOCKED (25 August 2026)
The controls GENERATE rather than balance existing material. Established
by testing it live on a passage from "Revenge of an Ordinary Man".
THE CONSEQUENCE: a paragraph with no dread in it is not a limitation, it
is A SOURCE WAITING FOR A SETTING.
AND RAISING INTENSITY REQUIRES COMPRESSION AND DIRECTNESS, NOT ADDITION.

THE WRITER'S ORIGINAL IS PERMANENT — LOCKED (25 August 2026)
It sits at the foot of the stack of windows and cannot be overwritten. The
writer chooses between VISIBLE ALTERNATIVES, never approving a replacement
they can no longer compare against.

THE BASE MIX BUTTON IS HELD, NOT TOGGLED — LOCKED (25 August 2026)
Press and hold: every fader drops, every window collapses, the original
prose stands alone. Let go and the mix returns. YOU GLANCE AT THE BARE
TRUTH; YOU DO NOT TRAVEL TO IT AND HAVE TO FIND YOUR WAY BACK.
AND IT DOES SOMETHING PROAUTHORISM NEEDS: one button shows at any moment
exactly how far the work has drifted.

THE WRITER'S EDIT IS THE FIXED POINT — LOCKED (25 August 2026)
The writer's hand goes into the middle of the ladder and THE LADDER
RESHAPES TO FIT. The collaboration is not turn-based. This is what makes
the Desk an instrument rather than a menu.

EVERYTHING IS "HOW MUCH", AND EVERYTHING COMBINES — LOCKED
(25 August 2026)
One shape doing every job. Faders are how much of a FEELING; plug-ins are
how much of a VOICE.

PLUG-IN NAMES — GENERIC AND HISTORICAL ONLY — LOCKED (25 August 2026)
Shakespeare, Wordsworth, the angry young men, street, hard-boiled, fairy
tale. NEVER A LIVING WRITER. Nobody says JK Rowling. SETTLED AND NOT TO
BE REOPENED. Plug-ins carry their own levels and combine with each other
and with the faders — a touch of Shakespeare is a cadence, all of it is
pastiche. Version three.

THE PROAUTHORISM OBJECTION TO THE DESK IS ANSWERED — LOCKED
(25 August 2026)
Claude objected that a fader asking Ada to rewrite a scene darker breaks
Proauthorism. THE OBJECTION WAS WRONG AND WAS WITHDRAWN. Kev pointed at
THE YULETIDE PROMISE — a full screenplay where Claude wrote text and Kev
cut it, redirected it and threw scenes out, a work with his name on it
that he would defend in a room. PROAUTHORISM WAS NEVER "THE AI MUST NOT
PRODUCE SENTENCES"; it is declared collaboration where the writer's voice
stays primary. A desk does not ask for a new take — it decides what you
hear from the take you have.
IF A NEW SESSION RAISES THE SAME OBJECTION, THIS IS THE ANSWER. DO NOT
RELITIGATE IT.

--- THE MYSTERY PLOTTER (25 August 2026) ---

A PUZZLE-CONSTRUCTION TOOL, NEVER A HOW-TO — LOCKED (25 August 2026)
The mystery plotter never holds METHOD. It does not care how anyone died,
only WHO WAS WHERE AND WHO KNEW WHAT. Realistic method is not what makes a
mystery good — Christie's murders are mostly implausible; what works is
the STRUCTURE OF THE CONCEALMENT. The constraint is what keeps it a
plotting tool rather than a manual, and it is not negotiable.

A MYSTERY HAS TWO TIMELINES — LOCKED (25 August 2026)
The truth, and what the reader is shown. Every good mystery is the
friction between them, and holding both at once is the genuinely hard part
of the job. THE TOOL HOLDS BOTH AND SHOWS WHERE THEY CONTRADICT.
The question it exists to answer: DOES THE READER HAVE ENOUGH TO SOLVE IT,
AND WHEN? Too early and it is obvious; too late and it is a cheat.

IT READS THE EXISTING STORE — LOCKED (25 August 2026)
Not a new store. Characters, Locations and Events are already there. This
is a screen that reads and cross-references them, which is what makes it a
plug-in rather than a new platform.

--- THE EVENT PLANNER (26 August 2026) ---

OFFSETS ARE THE TRUTH; CLOCK TIME IS A DERIVED COAT — LOCKED
(26 August 2026)
Zero hour is the one fixed point — the moment the event occurs. Every
other moment is an offset from it. A real clock time may be PINNED to zero
hour and everything else derived; multiple pins are supported; A FIXED
TIME CAN ALWAYS BE CHANGED AND THE ENGINE ADJUSTS EVERYTHING ELSE
ACCORDINGLY. THE ENGINE FLAGS CONFLICTS BETWEEN PINS AND OFFSETS RATHER
THAN SILENTLY RESOLVING THEM.

THE BOARD CARRIES PEOPLE ONLY — LOCKED (26 August 2026)
Locations, objects, weapons and context live behind pop-ups drawn from the
corridor's existing system. Nothing is ever entered twice. The board begins
with a victim (track ends at zero hour) and a killer (track crosses it);
more come from the manuscript's cast.

THE EVENT IS ONE CONTINUOUS VERTICAL AXIS — LOCKED (26 August 2026)
A drop line falls from the top timeline THROUGH an event box and continues
down through every character track. Not a separate element sitting beside
the tracks.

TWO PHASES — LOCKED (26 August 2026)
Phase one: plan the TRUE event, with no thought for the reader. Phase two:
CONCEALMENT AND MISDIRECTION — explicitly deferred.

THE EVENT PLANNER IS NOT IN THE FLOW — LOCKED (31 August 2026)
It is an extension, reached from the right-hand Site Map menu, not the
left working menu. How its output reaches the main work screen is
DELIBERATELY PARKED until more of the platform exists.

--- THE SIDEBAR AND THE GUIDE ---

THE SIDEBAR — LOCKED (11 August 2026)
BASICS, then:
  STORY    Plot Threads · Subplots · Themes & Motifs · Events & Timeline
  PEOPLE   Characters · Relationships · Factions & Orgs · Language & Dialogue
  WORLD    Locations · Buildings · Objects & Artefacts · Rules & Lore
  LIBRARY  Research & Reference · Notes · Images · Sandbox
  DCW      Plot Mapper · Manuscript · Publish
Synopsis has gone from Story. "Library" has RETURNED as a group heading.
CHAPTERS AND THE TREATMENT were dropped DELIBERATELY; their pockets remain
in the repo and showScreen is guarded so the removed nav ids do not throw.
OPEN: "Basics" vs "Overview" vs "Front Matter". Sandbox should move from
Library to DCW. Group headings should become live rooms. AND the "Plot
Mapping" item under NAVIGATE points at Coming Soon while the real Plot
Mapper is live under DCW — two similar names, one working.
CONFIRMED AGAINST THE LIVE FILE 1 SEPTEMBER: the sidebar is as locked.
nav-manuscript points at Coming Soon, and there is NO POCKET:manuscript
slot in the corridor — both are Job Two's to change.

THE SECTION ? GUIDE — PLATFORM-WIDE — LOCKED (15 August 2026)
- EVERY SCREEN carries a SECTION ? pill at the TOP RIGHT of its header,
  gold-bordered, same corner everywhere. A screen with no guide written
  yet still gets the pill and an honest short panel.
- IT OPENS A MOVABLE, RESIZABLE WINDOW. Drag by the head, resize by a
  corner grip, close with x or Escape. NO SCRIM — the page stays live.
- DO NOT USE CSS resize:both: it makes the panel its own layer and the
  text renders soft. Use a grip, and round every position and size to
  whole pixels.
- ONE LINE PER THING: a gold label, one plain sentence. Kev: "You are not
  writing a 3 act play explaining what everything does."

CONTROLS DO NOT CHANGE SIZE — LOCKED (15 August 2026)
- A CONTROL THAT CHANGES ITS WORDING MUST NOT CHANGE ITS SIZE. Fixed width
  sized to its longest state, text centred.
- A CONTROL'S SIZE MUST NOT DEPEND ON WHAT IS BESIDE IT.
- OPENING SOMETHING MUST NOT PUSH WHAT IS ABOVE IT.
EXTENDED 1 SEPTEMBER: A ROW OF CONTROLS DOING THE SAME KIND OF JOB IS ONE
SIZE THROUGHOUT — see the Basics block above.
TO BE SWEPT ACROSS THE CORRIDOR when it is next in hand. STILL NOT DONE.

--- THE DATA MODEL ---

THE DCW IS ONE BODY OF DATA — THE MIXDOWN — LOCKED (16 June 2026)
The DCW is NOT separate screens you move between. It is ONE body of
material seen through OVERLAYS, like a mixdown in music — the tracks
beneath never go away; an overlay RENDERS them together without destroying
them, so going back is free.
THE FUNNEL: SANDBOX (wide, loose) → THE PLOT MAPPER (the same material
divided into chapters and scenes) → THE MANUSCRIPT (one scene, the close
end). LIVING LINK, BOTH WAYS; NOTHING ENTERED TWICE.
THE KEYSTONE, still open: each overlay's structure must be STORED ON THE
SHARED DATA itself, not inside a view. THIS IS STEP TWO OF THE PLOT MAPPER
GOING LIVE.

THE TREATMENT IS THE DCW SWITCHED ON
Everything in the database ASSEMBLES into a readable, writable whole. A
plotline is a VIEW of data that already exists, not a new thing to author.
Locked: 4 June 2026.

THE SPINE IS A TIMELINE OF EVENTS
Tiers: CHAPTER → SCENE → EVENT. Only EVENTS sit on the line and become
prose — because only events happen. Characters, Locations, Objects and the
rest do not happen; they are reached into. Locked: 4 June 2026.

THE CUT — WHAT TRANSFERS TO THE MANUSCRIPT — LOCKED (9 June 2026)
- EVENTS + LOCATIONS form the SYNOPSIS content of every chapter and scene.
- CHARACTERS · OBJECTS · THEMES · TENSION are related to the scene but do
  NOT pour into prose; they are REACHED INTO, and their home is the SCENE
  MENU on the left of the page.

TEST FOR ANY PLOT MAPPER — LOCKED
Can it produce chapter, scene number, title and summary? If not it is not
a Plot Mapper, whatever else it does well. The Wheel needs all four.

RANGES, NEVER A SINGLE TARGET — LOCKED (12 August 2026)
The Overview gives word and chapter counts as RANGES, and everything
downstream must agree. Warnings inform; they never block.

--- THE MANUSCRIPT AND THE WHEEL ---

THE WHEEL IS STRIPPED, NOT REBUILT — LOCKED (1 September 2026)
The June standalone file is a mockup of the whole platform. Turning it
into pockets/manuscript.html means CUTTING AWAY THE OUTSIDE AND KEEPING
THE MIDDLE — its own header, its own left sidebar and its Site Map all go,
because the corridor already draws those. The page, the scene menu and the
wheel stay.
THE WHEEL CODE ITSELF IS NOT TO BE REWRITTEN. Every locked number in it is
correct (TIGHT 46, GAP 64, WINDOW 9, BOW 0, ease 0.072, READ_PAD 28), and
a fresh write would get some of them subtly wrong and cost a session
finding out which. It comes across unchanged.
THE ONE THING THAT DOES CHANGE IS THE JOIN: labels currently hard-coded in
the HTML must be built from the project's real chapters and scenes. That
is where a fault will appear, and the first still is pointed at a real
project precisely so a wrong turn can be blamed on the join and not the
mechanism.

THE TWO LEFT MENUS ARE DIFFERENT THINGS — LOCKED (1 September 2026)
Worth writing down because it caused real confusion in conversation. On
the finished Wheel screen there are TWO things to the left of the page:
- THE PLATFORM SIDEBAR, furthest out. The corridor's. Basics / Story /
  People / World / Library / DCW. The pocket does not carry one.
- THE SCENE MENU, in the channel between it and the page. The Wheel's own,
  and it STAYS. Characters, Objects, Themes, Tension for the scene you are
  on.
The old four-heading menu inside the June file (Projects / DCW / World
Building / Notes) is neither of these. It is the superseded spine and it
is deleted.

THE MANUSCRIPT — THE CLOSE / WRITING VIEW — LOCKED (16 June 2026)
The close end of the funnel, where the writer completes the book. Earlier
locks saying "WP" or "Writing Panel" refer to THE MANUSCRIPT.

ONE SCENE PER FULL PAGE — LOCKED (6 June 2026)
Each scene on its own full US-Letter sheet (816 × 1056px). Pages are ALWAYS
full height — a short scene leaves white space.

THE CLICK-TO-WRITE IS THE WHEEL
The page sits shifted right; in the dark channel to its right, a vertical
belt of labels on a hairline gold RAIL with a fixed gold CENTRE. Scrolling
the page turns the wheel; whatever sits at the centre is where you are.
Locked: 4 June 2026.

THE WHEEL LABELS ARE TWO LINES — LOCKED (7 June 2026)
A small gold mono caps KICKER ("STAVE ONE — SCENE ONE") and the SCENE
TITLE beneath in Crimson Pro.
NOTE 1 SEPTEMBER: in the June file the kicker's number words come from a
list that stops at TEN, so an eleventh chapter reads "Stave undefined".
Fix it when the labels are rebuilt from the real project.

THE WHEEL — WINDOWED, EASED, STRAIGHT — LOCKED (7 June 2026)
Window of NINE labels each side of centre, fading at the edges with a
brightness floor. Motion eased and slow (rate 0.072). Row spacing
TIGHT=46, centre gap GAP=64. The belt is STRAIGHT (BOW=0). The live
hand-off carries a 0.35s transition.

THE WHEEL CENTRE MARK — LOCKED (6 June 2026)
A gold RING (17px, 2px border) with a filled dot and a short gold LEADER
toward the centre label, whose title lights gold.

THE WHEEL HOVER — LOCKED (6 June 2026)
Hovering lights ONLY its node gold; the label text does not change.

ONE SHARED READING LINE — LOCKED (7 June 2026)
Page and wheel share one line, READ_PAD = 28px below the header.

WRITING MODE SHOWS ONLY THE LIVE SCENE — LOCKED (7 June 2026)

TWO STATES — OVERVIEW AND WRITING MODE — LOCKED (4 June 2026)

PAGE CENTRE, SCENE MENU LEFT, WHEEL RIGHT — LOCKED (9 June 2026)

THE SCENE MENU — LOCKED (9 June 2026)
The home of the four reached-into tracks, in the channel left of the page.
Right-aligned list, coloured group headers, names in plain ink. Tied to
the PAGE, not the book.

TENSION IS A SEGMENTED BAR METER — LOCKED (9 June 2026)
NOTE 1 SEPTEMBER: the June Wheel file still shows the plain text "55%",
which is one of the versions rejected on 9 June. Correct it during the
strip.

THE ENTITY POP-UP — LOCKED (4 June 2026)
Click to open, ✕ to close; does not vanish on click-away; does not close
when text is selected inside it. Draggable by its header.

POP-UPS ARE MULTIPLE AND INDEPENDENT — LOCKED (7 June 2026)

THE QUICK-NOTE — PINNED POST-IT — LOCKED, BUILT (17 June 2026)
The writer's OWN scrap — NEVER story data, never prose, never mixed down.
Drag by its top strip, ✕ to delete, cascades, raises on click. Auto-grows;
the folded corner is a real resize handle. Summon → jot → KEEP (Enter) /
BIN (esc) / PIN. THE PIN is a two-state THUMBTACK. PIN-HEAD COLOUR is
assignable from the six track colours, default Tension red. NO IMAGES.
Not yet wired in.

THE EMPTY-CARD IDIOM — LOCKED
An empty or unfiled card is a DASHED OUTLINE only — no fill. It earns its
colour by being filled.

COPY AND PASTE IS HOW INFO REACHES THE MANUSCRIPT — LOCKED (4 June 2026)
Copy takes TEXT ONLY: coloured in the pop-up, it lands PLAIN.

THE SIX TRACK COLOURS — LOCKED (9 June 2026)
  EVENTS gold #c9923a · LOCATIONS teal #5fa898 · CHARACTERS terracotta
  #cf7f57 · OBJECTS steel blue #7a9bd0 · THEMES violet #a07d9a ·
  TENSION red #c45b48
NB: the SIDEBAR groups carry FOUR FAMILY COLOURS — Story #c9923a, People
#cf7f57, World #5fa898, Library #9a8f72.
NOTE 1 SEPTEMBER: the June Wheel file's pop-ups still use the superseded
4 June section colours (#cba36a, #b08a6a). Correct them during the strip.

SCENES ARE LABELLED, TITLE OPTIONAL — Locked: 4 June 2026.

THE CHAPTER HAS A SYNOPSIS OF ITS OWN — LOCKED (11 June 2026)

THE AI PROMPT — PROMPT + EXPAND, SCOPED TO THE SYNOPSIS — LOCKED
(11 June 2026)
The button expands the SYNOPSIS of the scene or chapter — NOT the prose.
It scales with the spine. "Stop AI writing the whole thing" is built into
the shape: scoped buttons, a server-side system prompt that forbids prose,
and output that lands by CHOICE.

--- SPELL CHECK ---

SPELL CHECK — THE MUTATIONOBSERVER PATTERN — LOCKED (11 August 2026)
enableSpellCheck must catch fields created LATER. It watches for
input[type="text"] and textarea appearing and marks each
data-spellReady="1". NB: it does NOT cover contenteditable.
THE GRAMMARLY TRAP: if a spell-check fault is reported, CHECK FOR
GRAMMARLY FIRST. It masks the browser's own underlines, and must be
REMOVED AND THE PC RESTARTED. Chrome must be set to BASIC (not Enhanced)
with English (United Kingdom) ticked.

--- COMMERCIAL AND STRUCTURAL ---

ADA
Female, named after Ada Lovelace. Voice fixed as Google UK English Female.
Sara Martin will NOT voice Ada. A contextual creative collaborator.
AI is never REQUIRED: assembling the database, the wheel, copy-paste, the
scene menu and the Plot Mapper's breaks are plain mechanics. The AI switch
turns Ada off entirely and the platform still works.

DEMO BOOKS — DECIDED (7 June 2026)
"A Christmas Carol" (1843) and "The Wind in the Willows" (1908), both out
of copyright. Carol first. A demo is a NORMAL project, fully populated,
with the scene-writing left blank. FULLY EDITABLE. RESET TO PRISTINE
returns it. SAVE = SAVE AS A COPY.

PRICING
Paid only. No free tier. Monthly £9.95, annual £99.50. 14-day money back.
One tier, no feature gates. Locked: 24 May 2026.

PUBLICATION FEE
£1 GBP per publication. Paid users get one free publication per week.
Anti-scam friction, not a revenue stream. Locked: 24 May 2026.

SECURITY SYSTEM — LOCKED LAYERS
Invisible: device fingerprinting, IP tracking, behaviour patterns,
disposable email detection, Stripe fraud detection. Visible but
acceptable: email verification, paid upfront, money-back guarantee,
support ticket for a new device. Locked: 24 May 2026.

MARKETING POSITIONING — NEVER USE
Never: "Write books instantly" / "Passive income publishing" / "Make 100
books a week" / "AI author riches". InkySwot markets to writers, creators,
worldbuilders, playwrights, serious independents, disabled writers,
dyslexic writers. Locked: 24 May 2026.

FORMAT LIST / FORMAT GROUPS / FORMAT-AWARE TOOLBAR / FORMAT CHOSEN FIRST
— LOCKED (26 May 2026), unchanged.

GENRE — LOCKED (27 May 2026, extended 12 August)
One primary genre, two sub-genres. All three feed AI context. EVERY GENRE
CARRIES its industry word-count range, its words per chapter, and ITS OWN
SENTENCE WORDING. PAGES ARE NOT USED.

DCW TENSION CURVE — THREE MODES — LOCKED (26 May 2026)
DCW EMOTIONAL MAPS — LOCKED (28 May 2026). Carried, not yet placed.

HOME PAGE — MY PROJECTS — LOCKED (31 May 2026)
A hub, not a path. CONCEPTS lives here too.

USER JOURNEY — TWO SHAPES — LOCKED (31 May 2026)
Before login a fixed path; after login an open hub.

THE FLOW THROUGH THE PLATFORM — LOCKED (31 August 2026)
Basics (through New/Load Project) → Plot Mapper → Wheel/Manuscript →
Publishing preparation (Platform/KDP · Book size · Page layout · Cover
creator) → Publish. The world-building screens are POCKETS USED WHEN
NEEDED, reached from the Wheel's own side menu, not steps in the sequence.

THE PRESS — TWO DOORS — LOCKED (31 May 2026)
One tool, two entry points: inside for members, outside at
press.inkyswot.com. The public Press must be CLONED, not re-skinned.

THE PRESS — LOCKED (29 May 2026)
Cover Creator (Fixed Spine System); Book Layout Tool; Platform
Requirements Database; Front and Back Matter Assembly. Paperback /
Hardback / Ebook, audiobook later.

SIGNUP / AUTHENTICATION — email + password → verification → access. No
SSO. Locked: 25 May 2026.

DATA — InkySwot never sells user data. Ever. GDPR compliant. Deletion
within 30 days.

SCROLLBARS — slim, dark, gold-on-hover, everywhere.

MEMORY DATABASE — LOCKED (9 June 2026)
Everything InkySwot — notes AND code — lives in the InkySwot division of
the Pitch Dark Studios Memory system. Code files carry a "code-" prefix.
A file must be saved INSIDE its division folder.

HOUSE STYLE
#0a0806 near-black · #0f0d0a background · #c9923a gold · #e8b060 bright
gold. Crimson Pro (body) · JetBrains Mono (labels and interface) ·
Playfair Display (wordmark and titles). Muted danger red #c43a2a.
Light/dark toggle platform-wide.
GOLD MARKS ANYTHING ALIVE AND RESPONDING. NEVER DECORATIVE.

================================================================
OPEN — NOT YET DECIDED
================================================================
WHETHER "EQUAL" MEANS BOTH OUTLINED. After a project has been to the Plot
Mapper, Save and Plot Mapper → are both shown outlined. Two filled gold
buttons side by side was judged too loud. NOT RULED ON BY KEV. (New,
1 September.)
STEP TWO OF THE PLOT MAPPER — the cards writing into the same store
Characters, Locations and the rest read from. THE VANISHING TINTS MUST BE
SOLVED AS PART OF IT.
ADA'S BUTTONS ON THE PLOT MAPPER — built but quiet.
THE "PLOT MAPPING" DEAD END under NAVIGATE.
THE CARD FACT FIELDS — a factual layer under the prose fields, and what
wins when facts and prose disagree.
"BASICS" vs "OVERVIEW" vs "FRONT MATTER".
SANDBOX moving from Library to DCW.
THE FIVE ROOMS.
THE LIBRARY's shape.
THE EVENT PLANNER's drop line — fixed at centre or moving with the pan.
THE MYSTERY PLOTTING GRID — built 25 August, never reviewed.
THE SERIES BIBLE IMPORT — whether writers confirm extracted data before it
lands in Characters.
WHAT "MORE" SHOULD SHOW on the Plot Mapper; whether STATUS should be
editable there.
THE QUICK-NOTE — persistence; a "see all"; whether a pinned note crosses
between views.
THE SITE MAP — built in June against the old nav.
THE STAVE PAGE'S WHEEL LABEL.
EVENT ORDER WITHIN A SCENE.
TAG SET: Prose vs Action; Dialogue's place; Emotion as a per-beat tag or
the seed of an Emotional Map.
AMBIENT (Atmosphere / Weather / Time).
CONCEPTS still uses the OLD Cast / World / Plot grouping.
MEMORY DIVISION IMAGES: whether the division can hold .png/.jpg.

================================================================
SUPERSEDED LOCKS — HISTORY, DO NOT BUILD
================================================================

THE FLASHING SAVE TICK ON BASICS (SUPERSEDED 1 September 2026) — a green
"✓ Saved" that appeared for 2.5 seconds when Save Overview was pressed and
at no other time. It made continuous saving invisible and made the other
buttons look unsafe. Replaced by the standing saved line. The corridor's
saveProjectHeader still drives the element; the pocket hides it.

"SAVE OVERVIEW" AS THE BUTTON'S WORDING (SUPERSEDED 1 September 2026) —
now simply SAVE, so the three foot buttons can share one width.

THE ENCLOSURE'S HARD-CODED POCKET LIST (SUPERSEDED 25 August 2026) — the
Enclosure kept its own list of pockets, which was never updated when the
Plot Mapper was added, so it placed 15 of 16 in silence. Replaced by
reading the corridor's own slots and reporting "Placed N of N".

SINGLE FILE ARCHITECTURE (locked 26 May, SUPERSEDED August 2026) —
replaced by CORRIDOR PLUS POCKETS. The single file survives only as the
stitched index.html output.

PLOT MAPPING — DROPPED (locked 11 June, SUPERSEDED 15 August 2026) —
REVERSED: the Plot Mapper exists, it is the screen that was the Synopsis,
and it is the only mapper.

THE BOARD IS PLOT MAPPING REBORN (locked 9 June, SUPERSEDED 15 August
2026) — scenes down a sticky left spine with six tracks across the top.
Reached a working state (code-board-rotated-5.html) with a compass rose,
an arrival state reading chapterRange, header-band cards, drag-to-reorder
tracks and snap-to-grid. OUT as the Plot Mapper. Its parts are worth
robbing; its name is taken. code-board-rotated-6 to -11 were a failed
rescue on 15 August — do not build on them.

PLOT MAPPING TIMELINE — "THE LIFT" (locked 30 May, SUPERSEDED 15 August
2026) — the backstory as the basement of the same map. THE IDEA IS GOOD
and could return in the Plot Mapper as breaks going the other way.

SECTION HELP PILL AS A SLIDE-IN (locked 30 May, SUPERSEDED 15 August
2026) — the pill and its corner survive; the slide-in does not.

THE MENU SPINE'S PROJECT NAV (recorded 16 June, SUPERSEDED 11 August
2026) — PROJECTS / DCW / WORLD BUILDING / NOTES. Replaced by the rebuilt
sidebar. NOTE 1 SEPTEMBER: this superseded menu is still drawn inside the
June Wheel file, complete with "Writing Panel" and a "Scenes" item. It is
deleted when the Wheel is stripped.

THE SPELL CHECKER'S MIRRORED OVERLAY (specced, SUPERSEDED 28 August
2026) — an invisible copy of the text behind the box, kept in step as the
writer types and scrolls, described as "the hard part". Replaced by the
CSS Custom Highlight API, which paints ranges without inserting anything.

THREE VIEWS OF ONE BODY OF DATA (locked 9 June, SUPERSEDED 16 June) —
replaced by THE MIXDOWN.

"WRITING PANEL" / "WP" AS THE NAME (from 4 June, SUPERSEDED 16 June) —
now THE MANUSCRIPT.

THE RIGHT-HAND ROADMAP (SUPERSEDED 16 June) — duplicated the wheel.

"LIBRARY" AS A NOTES ITEM (SUPERSEDED 16 June, PARTLY REVERSED August).

THE FIRST SITE MAP — A BRANCHING TREE (SUPERSEDED 11 June).
SITE MAP STYLING TRIES (11 June). THE "ROAD MAP" NAME (9 June).
THE QUICK-NOTE ROUND RED PUSHPIN (17 June).
PROMPT / EXPAND BUTTON TREATMENTS B / C / D (11 June).
SECTION COLOURS Character #cba36a / Event #b08a6a (4 June).
TENSION AS A VU NEEDLE / FLAT LINE / PLAIN "55%" (9 June).
MERGE THE SCENE MENU INTO THE WHEEL (9 June, REJECTED).
PAGE RIGHT, POP-UP LEFT (4 June, REVISED 9 June).
DEMO BOOKS "ideally read-only" (SUPERSEDED 7 June).
rollToCentre (SUPERSEDED 7 June). SINGLE REUSED POP-UP (SUPERSEDED
7 June). THE 4 JUNE WHEEL DETAIL (SUPERSEDED 6–7 June). SEPARATE STAVE
MARKER LABELS (7 June). THE WHEEL BLOOM + CHEVRON and THE WHEEL BOW
(REMOVED 6 June). THE SHUTTER (2 June). THE DCW AS A VERTICAL BOARD
(2 June). DCW × PLOT MAPPER FUSION AS BUILT (1–2 June). DCW TERMINOLOGY
TRACKS / THREADS (29 May). THE NOTE CARD FACE (30 May). WRITE SCREEN /
FULL SCREEN / INDEX CARD (28 May & 2 June). INDENTATION RULE (4 June).
THE WRITING CARD (4 June). "SNAP TO DEFAULT" / DRAG-TO-REORDER TRACKS /
BRIGHT-RED FREEFORM / IDEAS COLUMNS / MAKE-YOUR-OWN TRACKS (3 June).
THE ONE-SCREEN DCW / X-RAY / LINEAR TAGGED CELLS (3 June).
THE FIRST 4 JUNE CLICK-TO-WRITE — replaced by the WHEEL.

THE IDEAS BOX / FILING-BOX (13 July, SUPERSEDED) — chased theatre over
usability. Replaced by CONCEPTS. The header-band card idiom and the
dashed-empty state survived. Do not rebuild the box.

THE SYNOPSIS AS BOXES (code-synopsis-boxes.html, SUPERSEDED 12 August) —
wrong because it asked the writer to know their chapter breaks before they
knew their story.