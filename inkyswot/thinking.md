File: inkyswot/thinking.md
Last updated: 24 September 2026. Covers the previous session, written up
at the start of this one. NOTHING FROM THE 22 SEPTEMBER VERSION IS
SHORTENED OR REMOVED; today's changes sit beside what they affect.
*** THE BIG ONE: THE CONNECTION IS NO LONGER A THREAD. It is proved and
in use, and THE FRONT DOOR IS LIVE. What is open now is the LOCK on it,
the email sender, and the shelf. ***

[The 22 September header follows, kept as written.]
Last updated: 22 September 2026. Covers the previous session, whose date
was not recorded, written up at the start of this one.
NOT REWRITTEN CLEAN THIS TIME, though that is this file's usual rule. Kev:
"dont lose anything yet." Every word of the 16 September version is kept;
what changed is written beside it, dated. THE SILENT SAVE IS FIXED. What
moves to Supabase is decided FOR NOW — the library alone. THE IMPORT HAS
CHANGED PURPOSE and is still being built on. The factual layer is now its
own file with three questions open.

*** THE SUPABASE WORK IS SUBJECT TO CHANGE ***
Kev, 22 September: "I have no idea how things will work on Supabase and
until then I can't nail things down." Everything below about the library,
the shelf, the import and the check is A WORKING IDEA. Where something is
marked decided, read it as decided for now. Build small, show Kev, let
what he sees decide.

This is the LIVE-IDEAS file (overwrite). Settled things belong in
locked-decisions.md; build state belongs in current-state.md.

REMINDER: THIS FILE IS UPDATED AT THE END OF EVERY SESSION, along with
the other four. See the lock in locked-decisions.md and the reason for it
at the head of current-state.md.
AND THE ADDITION OF 16 SEPTEMBER: IF WORK CONTINUES AFTER THE WRITE-UP,
THE WRITE-UP IS NOT FINISHED. Five milestones from 1 September were done
after that session's files were brought current, and reached no file until
a fortnight later.

================================================================
SECTION A — OPEN NOW (16 September 2026, updated 22 September)
================================================================

--- THE SUPABASE CONNECTION — THE LIVE THREAD, AND JOB ZERO ---
*** CLOSED IN PART, 24 SEPTEMBER. THE CONNECTION IS PROVED AND IN USE —
for ACCOUNTS, not yet for the library. A throwaway page sent a line and
read it back, first time; login.html now signs people in and out for
real. WHAT REMAINS OPEN IN THIS SECTION is the LIBRARY's own connection
and the behaviour on a bad network. The text below is kept as written. ***

THE ACCOUNT EXISTS AND NOTHING IS WIRED. Organisation Pitch Dark Studios,
project InkySwot, London, Free plan, RLS on by default. Full detail in
current-state.md. InkySwot still reads and writes localStorage and knows
nothing about any of it.

THIS IS INFRASTRUCTURE, NOT A POCKET — the first thing in this rebuild
that cannot be done by writing a screen. Kev: "Let's go slow."

WHAT IS NOT YET DECIDED, AND ALL OF IT NEEDS DECIDING BEFORE ANY CODE:
1. WHAT MOVES FIRST. The whole of "is-projects" in one go, or the library
   alone with projects staying in the browser for now? The second is
   gentler and lets the import proceed; the first stops the platform
   living in two places at once, which is its own kind of trouble.
2. HOW EXISTING WORK IS CARRIED ACROSS WITHOUT LOSS. There is one real
   book in the Plot Mapper already — The Man Who Learnt To Fly. IT MUST
   NOT BE THE THING THAT PROVES THE MIGRATION WRONG. Whatever route is
   taken, the browser copy stays untouched until the server copy has been
   read back and looked at.
3. WHAT HAPPENS WHEN THE NETWORK IS NOT THERE. localStorage never failed
   for that reason; a server does. A writer mid-scene on a bad connection
   is the case to design for, not the exception to apologise for.
4. LOGINS. Supabase brings them, and the platform has never had one. Who
   Kev is when he opens the app, and what happens to work already in his
   browser when an account appears around it.

THE ONE THING THAT SHOULD HAPPEN FIRST, WHATEVER ELSE IS DECIDED: FIX THE
SILENT SAVE. See below.

UPDATED 22 SEPTEMBER — WHAT HAPPENED TO THE FOUR QUESTIONS ABOVE.
They were put to Kev as a list. KEV: "To be completely honest I am not
sure I know the answers to any of those questions!!" THAT WAS A FAULT IN
THE ASKING. Two of the four were engineering questions dressed up as
decisions for him; only two were genuinely his.
· QUESTION 1, WHAT MOVES FIRST — KEV'S, AND ANSWERED FOR NOW: "we move as
  little as possible. That way as we move forward we are not having to
  make changes on another platform." THE LIBRARY ALONE. His reason beats
  Claude's: the platform is still changing shape, so moving it all now
  means building everything twice.
· QUESTION 2, CARRYING WORK ACROSS — CLAUDE'S TO PROPOSE. Largely
  dissolved by the answer to 1: nothing in the browser moves, so The Man
  Who Learnt To Fly is not at risk.
· QUESTION 3, NO NETWORK — CLAUDE'S TO PROPOSE. Much reduced: only the
  library depends on the connection. Still to be designed for the shelf.
· QUESTION 4, LOGINS — KEV'S, AND ANSWERED FOR NOW: "I dont mind logging
  in." Later, once the store exists.
  *** OVERTAKEN 24 SEPTEMBER. NOT LATER — FIRST. *** Kev: "Then we need to
  start having account numbers." A book on a shelf must belong to
  somebody, and an owner cannot be retrofitted, so the front door was
  built before the shelf. Kev: "I think we are moving in that direction."
  AND THE WORRY THAT CAME WITH IT WAS UNFOUNDED: the session persists in
  the browser, so signing in is occasional, not a daily toll.

THE SHAPE OF THE SHELF — CLAUDE'S PROPOSAL, NOT DECIDED (22 September).
Researched against Supabase's own documentation before recommending.
  · The ORIGINAL FILE in the file store, untouched, as the record of what
    was handed over.
  · A ROW PER BOOK — title, author, when it went in.
  · A ROW PER CHAPTER — number, heading, words. THE FINDING THAT SHAPED
    IT: one row holding 90,000 words works, but every request for a
    paragraph pulls half a megabyte, and someone running a large document
    system on Supabase found cells near a megabyte noticeably slower.
    Storing by chapter matches how the platform already thinks.
KEV'S REQUIREMENTS, WHICH ARE HIS: whatever is stored must let the
platform pull information into the screens, and must be SEARCHABLE.
Claude read both as pointing at chapter rows. KEV'S VERDICT ON THE SHAPE
ITSELF: not sure — "I have no idea how things will work on Supabase and
until then I can't nail things down." FAIR, AND RIGHT. Build a small piece,
look at it, then decide.
TO VERIFY ON SUPABASE'S OWN PAGES BEFORE BUILDING: the largest single file
the free tier accepts, and whether a single text row has a ceiling worth
respecting.

AND THREE COLUMNS THAT GO IN WHATEVER THE SHAPE — 24 SEPTEMBER. Kev asked
the right question: "are there things, functions, systems etc that we
should be adding now. I ask so we dont have to go back over stuff." Most
things are cheaper later. THESE ARE PAINFUL TO RETROFIT:
  1. WHICH PROJECT the book belongs to.
  2. WHOSE BOOK IT IS — the account's identifier. KEV'S OWN, and the
     reason the front door was built first.
  3. WHEN IT ARRIVED, AND A DELETED-MARKER rather than a real deletion —
     the same thinking as the Trash screen.
[1 and 3 are Claude's proposal; 2 is Kev's. Nothing else is added now:
the chapter split, the muster, the check and the search can all be added
to a shelf that already works.]

--- *** THE SILENT SAVE — A LIVE FAULT, NOT A DESIGN QUESTION *** ---
*** FIXED AND LIVE — the previous session, written up 22 September. ***
Done first, as argued below. A save guard bolted onto the end of
corridor.html wraps saveProjects and saveTrash; a failed save raises a
red bar across the top that stays until a save succeeds, and never
blocks. The Basics line now reads the guard's flag and says "NOT SAVED"
in red rather than claiming a time. Full account in current-state.md.
THE TEXT BELOW IS KEPT AS THE RECORD OF WHY IT MATTERED.

saveProjects calls localStorage.setItem BARE. No try, no catch, no check.
When the box is full the write does not happen AND NOTHING TELLS THE
WRITER.
AND IT IS WORSE THAN THAT, because of what was built on 1 September. The
Basics screen's standing line reports that a save was ATTEMPTED, not that
it SUCCEEDED — it wraps autoSave, autoSave calls saveProjects, and
saveProjects cannot fail loudly. SO THE LINE WILL SAY "Saved · 14:32" ON A
SAVE THAT DID NOT HAPPEN.
THE SCREEN THE PLATFORM TRUSTS MOST IS CAPABLE OF LYING TO THE WRITER. Of
everything found today this is the only thing that could actually cost Kev
work, and it can do so before the Supabase connection is anywhere near
finished.
IT IS ALSO THE THIRD TIME THE SAME PATTERN HAS BEEN FOUND — the Enclosure
placing 15 of 16 pockets in silence, the checker's zero findings looking
like a pass that never ran, and now this. IT IS THE HOUSE FAULT. Worth a
deliberate sweep for it rather than waiting to stumble on the fourth.

--- *** THE LOCK ON THE DOOR — THE LIVE THREAD, AND THE NEXT PIECE OF
    WORK (24 September) *** ---

THE FRONT DOOR IS BUILT AND THE APP IS STILL OPEN. login.html signs people
up and in, but app.inkyswot.com does not check whether anyone has. ANYONE
WITH THE ADDRESS STILL WALKS IN.
KEV: "We need to close this off."
WHAT IT IS: a small block in the corridor that asks Supabase whether there
is a session and, if not, sends the person to login.html. The same
bolted-on-block pattern as the save guard.
WHAT TO THINK ABOUT BEFORE WRITING IT, because a gate on the front of
everything is the one piece that can lock Kev out of his own platform:
· IT MUST FAIL OPEN OR FAIL LOUD, NOT FAIL SILENT. If Supabase is
  unreachable, a gate that quietly decides nobody is signed in would
  bounce the writer away from work that is sitting safely in their own
  browser. THE PROJECTS ARE STILL IN localStorage; the gate must not
  stand between the writer and their own machine's copy.
· THE CHECK IS ASYNCHRONOUS. The page will draw before the answer comes
  back. Either hold the screen for a moment or accept a flash of the app
  before the redirect — and a held screen must say why it is held.
· SIGNING OUT NEEDS SOMEWHERE TO LIVE. There is no sign-out control
  anywhere in the platform yet.
NOT DESIGNED. NOT BUILT.

--- THE EMAIL SENDER — OPEN (24 September) ---

The confirmation email arrives from Supabase, not from InkySwot. Kev
spotted it straight away and it needs fixing — but it is ONE JOB WITH A
SECOND, because Supabase's built-in sender is FOR TESTING ONLY: a handful
of emails an hour, and it says so itself. Fine for one writer; useless the
day three people sign up at once.
ATTACHING A PROPER SENDER FIXES THE NAME AND THE LIMIT TOGETHER. It means
choosing a service, proving InkySwot owns its domain, adding records to
the domain's settings, and pointing Supabase at it.
IT IS A SESSION OF ITS OWN, and it is domain settings rather than code.
IT BLOCKS NOTHING TODAY. NOT CHOSEN.

--- THE IMPORT — THE NEW THREAD ---
*** UPDATED 22 SEPTEMBER: ITS PURPOSE HAS CHANGED, AND IT IS STILL BEING
BUILT ON. READ THIS FIRST, THEN THE 16 SEPTEMBER TEXT BENEATH IT. ***
KEV CORRECTED THE FIRST SHAPE: "We DONT need ALL that info, just the
ability to check it. so what we really need is the ability to find the
above information and have it 'ping' the user when they get things wrong
in the new book — IE: hair colour etc."
THEN, ASKED WHAT THE CHECK SHOULD RUN AGAINST — BOOK ONE'S TEXT OR THE
CHARACTERS SCREEN: "YES info should be in certain fields — characters
being one of them. There is no point in rebuilding a character profile
when it already exists."
AND THEN: "We will be still building on how uploaded work is referenced."
CLAUDE'S WORKING READING OF THOSE THREE, OFFERED AND NOT AGREED: the book
is read once; what it finds about people lands in their cards, behind the
muster; from then on the new book is checked against the cards rather
than against the old text; and a disagreement pings with WHERE — "he was
dark in chapter nine of book one" — so the writer can look, and may have
changed it on purpose. THAT IS A PROPOSAL. It is not Kev's decision and
it is not locked.
WHAT KEV HAS SAID STANDS: check, not fill everything; character facts in
character cards; still being built on.
THE SIX STAGES BELOW WERE CLAUDE'S OUTLINE. The heading "agreed in shape"
overstated it, and is kept only as the record.
ONE MORE WORKING IDEA OF CLAUDE'S: the checker's parser already classifies
CHAPTER TITLES (stage 3 of the eight). The chapter split may be mostly
built already. Worth checking before writing anything new.

HOW CHAPTERS WOULD BE RECOGNISED — ASKED AND ANSWERED 24 SEPTEMBER.
KEV: "How will it recognise chapters?" By the headings: A SHORT LINE,
ALONE, NO FULL STOP, often in capitals. CHAPTER ONE · Chapter 1 · 1. ·
Stave One · Part Three.
WHERE IT STRUGGLES, said plainly rather than promised away: chapters
marked only by an ornament or a gap; a number on one line and the title on
the next; prologues, epilogues and interludes that never say "chapter".
AND KEV'S REFINEMENT, WHICH IS THE RIGHT ONE: "we should have a checking
function. So where the system is not sure it asks for clarity."
SO THE FINDINGS SPLIT THREE WAYS:
  · CERTAIN — shown, ticked, no question asked.
  · UNSURE — flagged, and the writer says yes or no.
  · MISSED — the count stated plainly, so 11 chapters in a 24-chapter book
    is obviously wrong.
IT ONLY ASKS WHERE ASKING EARNS ITS PLACE. A list of twenty-four with
three queried is a minute's work; a list where all twenty-four are queried
is a chore nobody does. SAME RULE AS THE CHECKER: rules assert, queries
ask, and a query dressed as a fault is the worst thing the tool can do.
AND THE REAL ANSWER IS STILL TO RUN IT ON RAPSCALLION AND LOOK. Kev's own
books may be perfectly tidy, in which case the clever version never needs
building.
AND IT IS THE CONTINUITY LIBRARY — described by Kev on 15 August and again
on 31 August, and now wanted for a real book. Three arrivals, three
directions.

WHAT IT IS, AND IT IS NOT WHAT ANYONE THOUGHT. Kev has Rapscallion
finished and book two half written, and wants book one in the platform.
NOT AS A REFERENCE CARD — "the first thing would be to auto fill all the
locations characters etc." Hand it the book; it fills the screens.
IT LIVES IN THE LIBRARY, because the shelf will eventually hold more than
his own previous books.

THE SIX STAGES, AGREED IN SHAPE:
  1. THE ROOM — pockets/research.html replaces the Coming Soon. Lists
     what is on the shelf, allows removal. STATIC STILL FIRST.
  2. THE WAY IN — a file picker. PLAIN TEXT FIRST. Word and PDF are
     packed formats needing their own machinery and can follow.
  3. THE CHAPTER SPLIT — find the headings, build the Plot Mapper's
     chapters. NO AI AT ALL, costs nothing, more reliable than anything
     the AI does. Probably the first thing built.
  4. THE READ — the book through the AI for cast and locations. ONE PASS,
     front to back, in sections because the reply comes back in pieces.
  5. THE MUSTER — everything found shown as a list to tick.
  6. THE LANDING — ticked items become records in Characters, Locations
     and Buildings.

WHAT IS NOT YET KNOWN AND WILL NOT BE UNTIL IT IS RUN:
· HOW WELL THE CHAPTER SPLIT ACTUALLY WORKS ON A REAL BOOK. "Chapter One"
  is easy. A book that numbers its chapters with nothing else, or uses
  ornaments, or has a prologue, is not. RUN IT ON RAPSCALLION AND LOOK,
  rather than specifying it in the abstract.
· WHETHER ONE PASS IS ENOUGH TO CATCH THE CAST. A character who appears
  once in chapter three and again in chapter thirty is the test.
· WHAT THE MUSTER LOOKS LIKE WHEN IT FINDS TWO HUNDRED THINGS. A tick
  list of forty is a task; a tick list of two hundred is a wall. It may
  need grouping, or a confidence order, or a "everyone who appears more
  than twice" default. NOT DESIGNED.

AND THE STAGE 6 JOIN IS THE SAME JOIN AS STEP TWO OF THE PLOT MAPPER.
Both write records into the store Characters and Locations read from. ONE
PIECE OF WORK, APPROACHED FROM TWO ENDS. Build it once.

--- THE BOUNDARY QUESTION — RAISED TWICE, STILL OPEN ---

Raised 25 August, raised again 16 September, deliberately not settled
either time. THE WRITER'S OWN BOOKS, YES. SOMEONE ELSE'S NOVEL UPLOADED
IN ORDER TO WRITE LIKE THEM IS A DIFFERENT THING ENTIRELY — legally, and
in terms of what InkySwot says it stands for.
"Always writer-led" is a strong position precisely because it means the
writer's OWN voice. A feature that absorbs another author's is the first
thing a sceptical writer would point at.
KEV'S OWN FRAMING PUSHES THE OTHER WAY, and it is not unreasonable: he
wants stories by other people "for style and tone", which is what every
writer has always done by reading. The difference is between a writer
learning from a book and a machine extracting from one.
TAKE THE POSITION BEFORE SOMEBODY DOES IT, NOT AFTER.
NOTE: the confirm-or-appear half of this question IS NOW CLOSED. The
writer always confirms. See the muster.

--- THE WHEEL'S CONVERSION — STILL READY, NOW BEHIND JOB ZERO ---

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
The Plot Mapper's own going-live on 25 August is the pattern.

THE FIRST DELIVERABLE IS A STATIC STILL: one page, the wheel beside it,
the scene menu, real project data, no writing mode and no movement. If it
turns wrong at that point we know it is the join and not the mechanism.

THREE CORRECTIONS TO MAKE DURING THE STRIP: Tension becomes the segmented
bar meter (currently the plain text "55%"); the pop-up colours move to the
locked six; and the screen gains its SECTION ? pill.

WHAT WE DO NOT KNOW UNTIL WE RUN IT. Twenty-five pages is about 26,000
pixels of scroll. A real novel is four hundred pages. THE BELT HAS NEVER
BEEN TESTED AT THAT LENGTH.

AND THE HONEST GAP TO STATE PLAINLY RATHER THAN FAKE. The scene menu is
fed by the naming done in the Plot Mapper, and those cards do not write
into a shared store yet. So the menu will be EMPTY. It should say so, not
invent names.
NOTE 16 SEPTEMBER: THE IMPORT MAY FILL IT FIRST. If the import's landing
is built before the Plot Mapper's step two, then a project that has had a
book read into it will have characters and locations to show — arriving by
the other road.

--- THE ONE QUESTION LEFT ON THE BASICS FOOT ---

After a project has been to the Plot Mapper, the two save buttons sit as
equals. Built as BOTH OUTLINED, because two solid gold buttons side by
side read as loud. Kev has not ruled. A one-line change either way.

--- THE CARDS NEED A FACTUAL LAYER (31 August, still open — AND THE
    IMPORT HAS JUST MADE IT MORE URGENT) ---

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
WHAT TO MEASURE: sentence OPENINGS, sentence SHAPES, lengths and whether
they vary or hover, and REPEATED CONSTRUCTIONS — the same frame recurring
within a few paragraphs. All countable using the parser already built.

THEN THE BETTER IDEA UNDERNEATH IT. Measured against what? Kev's answer:
"I want the ability to have previous work studied by the platform so it
can flag inconsistencies." AND THE CORRECTION THAT MATTERS: "it's not so
much the writing style I want studied but inconsistencies in the writing.
EG: Bill has dark hair in book one and I give him blond in another."

WHY THAT IS THE STRONGER TOOL. Style consistency is fuzzy — the most it
can say is "this doesn't sound like you". FACT CONSISTENCY IS HARD. Bill
has dark hair or he doesn't. It is also the kind of mistake that genuinely
gets through: nobody re-reads book one to check a hair colour before
writing book three.

*** AND THIS IS EXACTLY KEV'S SITUATION NOW. *** Rapscallion book one is
finished; book two is half written. THE HAIR-COLOUR PROBLEM IS NO LONGER
HYPOTHETICAL — it is the next thing he will hit. The import puts book
one's facts into the platform; the factual layer is what lets anything
check them.

INCOMPLETE BOOKS ANSWER THEMSELVES. For style, an unfinished draft is a
problem. FOR FACTS IT DOES NOT MATTER: a half-written book contributes the
facts it contains and nothing is spoiled by the rest being missing.

THE LOCAL VERSION AND THE WIDE VERSION.
· LOCAL leans on what the platform already knows. If Bill's card says
  dark hair, the tool can scan for other hair statements near his name
  and flag disagreements. Narrow, honest, and it uses the world-building
  the writer is already doing.
· WIDE reads the prose and works out the facts itself, no cards needed.
  That needs a model, which means sending text away.

WHICH BRINGS IT TO THE CARDS, AND THIS IS THE OPEN JOB. The character
card is built for THINKING — Personality, Motivation, Secrets, Arc,
Backstory, long prose fields. Good for that, and NEARLY USELESS FOR
CHECKING. "A tall man, greying now, with the sort of face that gives
nothing away" reads as writing, not as facts.

THE PROPOSAL, AGREED IN SHAPE:
· A small FACTUAL LAYER under the prose fields. Hair. Eyes. Height.
  Build. Age at the story's start. Distinguishing marks. One word or two
  each, not sentences. Same logic for Locations and Objects.
· ONE PLACE TO ENTER SOMETHING, TWO THINGS TO USE IT FOR. THE FACTS BUILD
  THE DESCRIPTION: the card assembles a plain sentence from the fields and
  offers it; the writer writes over it in their own words; the facts stay
  underneath regardless.
· PROMPT EARNS ITS PLACE PROPERLY. Not "invent me a character" — instead:
  here are the facts, give me a description that uses them.
· EXPAND becomes: develop my description, keeping every fact intact.

AND A NEW REASON TO BUILD IT SOONER (16 September): THE IMPORT NEEDS
SOMEWHERE TO PUT WHAT IT FINDS. A read of Rapscallion will return facts —
this character, this hair, this place. Landing them in long prose fields
throws away exactly the structure that made them worth extracting. THE
FACTUAL LAYER IS THE IMPORT'S TARGET.

THE ONE QUESTION LEFT OPEN. When the facts and the prose disagree — the
field says grey, the description says dark — which wins? Claude's
instinct: THE FACTS WIN FOR CHECKING, and the tool FLAGS THE DISAGREEMENT
rather than silently choosing. Kev has not ruled.

THE TRAP TO REMEMBER. A tool that measures a writer against their own past
work REWARDS CONSISTENCY. Pushed too hard it becomes a machine for
stopping a writer developing. IT SHOULD BE VOLUNTARY AND OCCASIONAL,
NEVER ALWAYS ON.

UPDATED 22 SEPTEMBER — THE FACTUAL LAYER IS NOW ITS OWN FILE:
inkyswot/factual-layer.md. A working list, not a lock.
KEV ASKED FOR IT TO BE COMPREHENSIVE, and it now covers Characters,
Relationships, Factions, Language & Dialogue, Locations, Buildings,
Objects, Rules & Lore, Events, and the project as a whole — each field
under one test: A WRONG ANSWER MUST BE CHECKABLE.
AND KEV ADDED A NOTES SECTION ON EVERY RECORD "for things like
preferences etc." A GOOD ADDITION: habits are checkable too — "drinks
only tea", then coffee in book two.
THE CHECK NOW DEPENDS ON THIS LAYER ENTIRELY, which is why it has moved up
the order of work.
THREE QUESTIONS WAITING FOR KEV, all in factual-layer.md:
  1. THE NOTES SECTION. The cards already have a free prose Notes field. A
     checker reading prose is back to guessing. Reuse it, or a SEPARATE
     LIST of short lines, one fact each? Claude's view: the separate list.
  2. WHICH WINS when the facts and the prose disagree. (The question
     already open above, now carried there too.)
  3. HOW MANY FIELDS SHOW AT ONCE. The whole list on one card is a form
     nobody would fill in.
ONE FIELD WORTH POINTING AT: "who knows about a thing, and from when", on
Relationships and Events. It is the same fact the mystery plotter turns
on. TWO TOOLS, ONE FACT.

--- THE CHECKER ACROSS THE PLATFORM (31 August) ---

Kev: "Why can't we apply the checker across the entire InkySwot
platform?" No reason. The engine is one self-contained file with nothing
depending on it, and the privacy claim survives wherever it runs.
NOTE 16 SEPTEMBER: MOVING THE PLATFORM'S STORE TO SUPABASE DOES NOT TOUCH
THE PRIVACY CLAIM. The checker checks what is handed to it, in the
browser. If the claim is made in marketing it is made about the CHECKER,
not about where the manuscript is stored — and that distinction must be
kept straight, because it would be an easy and damaging thing to blur.

TWO THINGS CHANGE, AND BOTH NEED DECIDING:
1. THE MANUSCRIPT STOPS BEING OUT OF REACH. The paste-in pop-up was
   chosen partly because the checker structurally COULD NOT touch the
   writing. Embedded in a writing surface, a fix button writes into the
   real text. Fine, but UNDO HAS TO WORK PROPERLY.
2. THE MARKS MAY NOT BE POSSIBLE EVERYWHERE. The Plot Mapper uses
   contenteditable, so it can take marks. Basics and every world-building
   screen use plain inputs and textareas, so they cannot. AND THE WHEEL'S
   WRITING AREA IS A PLAIN TEXTAREA — the screen the checker most wants
   cannot take painted marks as things stand. SETTLE IT DURING THE
   WHEEL'S CONVERSION, because changing the writing surface later is a
   rebuild.

THE ORDER AGREED: (1) make the engine a shared part in the corridor;
(2) build the attachment; (3) attach it to ONE screen and live with it for
a week on real writing before the rest. DEFERRED at Kev's own suggestion,
and rightly: the platform's flow and missing sections come first.

--- THE VANISHING TINTS — STILL OPEN, STILL NOT A SEPARATE JOB ---

A mark is held as "characters 14 to 22 of this paragraph". Edit the words
and the numbers point at the wrong place. readBack() DROPS the marks on
edit rather than following them.
GOING LIVE DID NOT FIX THIS — it preserved it. Solve it WHILE step two is
built, because both need the same thing: the platform following a phrase
as the text moves around it. Build the store first and it gets built
twice.

--- ADA ON THE PLOT MAPPER ---

Prompt and Expand are built on every chapter and scene line and on every
card, but Ada is NOT CONNECTED to that screen. Shown quiet and disabled
with a title saying why. Named as the next piece of work on that screen on
25 August; still not done.

--- THE MYSTERY PLOTTER AND THE EVENT PLANNER MAY BE ONE TOOL ---

Built and designed a day apart, and neither conversation mentioned the
other. The mystery grid holds people against CLOCK TIME; the Event Planner
holds people against OFFSETS FROM ZERO HOUR with clock time derived. THE
EVENT PLANNER'S MODEL IS THE SHARPER ONE — offsets survive a change of
mind about when the murder happened.
BUT THE MYSTERY GRID HAS THE SECOND HALF the Event Planner lacks: the
SHOWN timeline and the checks across both, which is where "does the reader
have enough to solve it, and when?" gets answered.
LOOK AT BOTH TOGETHER BEFORE BUILDING MORE ON EITHER. The grid has never
been reviewed since the day it was built.

--- THE DESK'S TWO OPEN QUESTIONS ---

1. IS THE DESK ONE INSTRUMENT PER SCENE, OR IS THE WHOLE BOOK THE
   INSTRUMENT? A synth patch holds across a performance. IF THE SAME
   SETTINGS RAN ACROSS EVERY SCENE, THAT IS THE VOICE OF THE BOOK. Where
   do the settings live: the scene, or the manuscript?
2. HOW MANY FADERS, AND WHAT ARE THEY CALLED? TWENTY FADERS IS A COCKPIT,
   AND A COCKPIT IS A SCREEN NOBODY OPENS. Likely four or five.

--- THE EVENT PLANNER'S REMAINING QUESTIONS ---

Does the zero hour drop line stay fixed at the centre of the screen, or
move with the timeline as the writer pans? Kev sees the board as "more
dynamic" than static draggable bars, so the interaction model wants
exploring before any prototype. HOW IT REACHES THE MAIN WORK SCREEN IS
DELIBERATELY PARKED.

--- CARRIED FROM 15 AUGUST, STILL OPEN ---

WHAT "MORE" SHOULD SHOW ON THE PLOT MAPPER. Currently Genre,
Classification, Status, Author. Parked by Kev: "We will sort that later."

SHOULD STATUS BE EDITABLE ON THE PLOT MAPPER? The rule is one field, one
door: Basics. But Status changes as a book progresses. Watch it in use.

DOES A SCENE NEED ITS OWN WORD COUNT? Chapters show "171 / 50–500";
scenes show nothing. Offered and not taken up.

THE FIVE ROOMS. If Library is clickable, all five group headings must be.
Five screens, none started. NOTE: the Library room is now the first of
them that has a real job — it is where the import lives.

"BASICS" vs "OVERVIEW" vs "FRONT MATTER". Still deliberately Basics. The
screen's own title still reads "Overview" while the sidebar says Basics.
NOTE 22 SEPTEMBER: the MISMATCH is separate from the naming question.
Whatever it is called, it should be called one thing. A small fix, listed
among the niggles.

CONCEPTS IS OUT OF STEP — still the old Cast / World / Plot grouping.

THE SIZING SWEEP. Four house rules now. Done on the Plot Mapper and the
Basics foot. THE CORRIDOR HAS STILL NOT BEEN SWEPT.

--- AND A NEW ONE: WHAT "FIX BEFORE WE MOVE ON" MEANS NOW ---

The rule was made when nothing was in real use. Now Kev is writing in the
platform, and real use throws up a steady drip of small irritations. If
every snag stops the press, the Wheel never gets built.
THE SHAPE AGREED: KEEP WRITING, LOG WHAT THE WRITING SURFACES, AND ONLY A
THING THAT ACTUALLY BLOCKS THE WORK STOPS THE DAY. Said out loud rather
than allowed to happen by drift — but it has not yet been tested against a
real irritation, and the first time it is, watch whether the log becomes
the snag list the original rule existed to prevent.
FIRST TESTED IN THE PREVIOUS SESSION (written up 22 September). Kev,
checking the save guard on the live screen, saw the Author and Status
boxes out of line and asked for it fixed. It was — small, done, published
in the same sitting. THAT IS "USE WINS" WORKING. It did not stop the day,
and it did not become a snag list. One case is not a pattern yet.
AND KEV'S COUNTERWEIGHT, SAID IN THE SAME SESSION: "we can't really
progress the platform until we can start adding my work to a database."
The niggles are cosmetic; the store is what everything else waits on.

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
of pockets that could silently fall behind the corridor. Fixed.
NOTE (16 SEPTEMBER): THE NO-TOOLING PRINCIPLE NOW MEETS ITS FIRST REAL
TEST. Supabase is an account, a dashboard and keys — it is not a terminal,
but it is the first thing in this project that lives outside a browser tab
and a button. Watch whether it stays that simple.
NOTE (24 SEPTEMBER): SO FAR IT HAS. Everything done on Supabase was a
dashboard page or a paste into the SQL Editor — no terminal, no install,
no build step. ONE DEPARTURE, MADE DELIBERATELY: login.html loads
Supabase's own library from a CDN, because that is what keeps the writer
signed in between visits and renews the session quietly. Writing that by
hand is fiddly and easy to get wrong. IT IS A SCRIPT TAG IN A FILE, NOT A
BUILD STEP, so the principle bends rather than breaks — but it is the
first outside library the platform depends on, and worth watching.

THE DCW AS THE STAGE — NOT BUILT, AND NOT NEEDED SO FAR. If it returns,
the question it left open is still right: what does the DCW show when
nothing is open?

THE PRESS — the locked two-door version stands. The payment / eligibility
gate is still the one piece that is more than presentation.

THE DCW VISION — the mixdown, the funnel and the keystone all survive,
and the keystone now has a name and a place: it is STEP TWO of the Plot
Mapper going live, AND IT IS ALSO THE IMPORT'S LANDING.

THE BANNER JOB — retired. Pockets made it unnecessary.

================================================================
SECTION C — LIVE OPEN QUESTIONS CARRIED
================================================================

THE LIBRARY'S SHAPE — HALF ANSWERED. Settled: it is SERVER-SIDE, and it
is where the import lives. [UPDATED 22 SEPTEMBER: both for now, and it is
the ONLY thing that moves to the server. The shelf's inner shape is
Claude's proposal only — see Section A.] Settled previously: folders are FIXED and
platform-provided, with no New Folder button; sub-folders mirror the
sidebar sections; an entry may optionally name the location or character
it is about.
STILL TO BUILD: the room itself. The REBUILD-5 drawing stands — three rows
(Research & Reference, Notes, Images), each with an arrow running
rightwards into its folders, and those folders opening in turn. A row per
section, growing rightwards, not a tree with a panel beside it.
THE INSIGHT WORTH KEEPING is Kev's own: "Damn we already have it." Every
screen is already list-on-the-left, detail-on-the-right.

THE QUICK-NOTE — persistence; a "see all"; whether a pinned note crosses
between views. Then wiring it across all screens.

THE SITE MAP was built in June against the old four-heading nav. NOTE:
the only copy we have seen is the one inside the Wheel file, and it is the
old one. WHEN THE WHEEL IS STRIPPED THE SITE MAP GOES WITH THE CUT — lift
it out first if it is wanted.

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
- *** MANUSCRIPT STORAGE 5MB DECISION — ANSWERED 16 SEPTEMBER. *** This
  sat in the backlog for months as a thing to decide before Step 14. It
  decided itself the moment a library was wanted: the 5MB was the browser,
  and the browser is being left. Recorded rather than deleted because the
  question was right and waiting on it was not.
- Proauthorism credit in app — undecided.
- Beta programme structure — undecided before Step 18.
- Full anti-spam strategy — needed before Step 15.
- Ada voice alternative — decide before Step 12. (Sara will NOT voice
  Ada.)
- Ada full spec — current spec in ada.md, needs more work.
- Cloudflare adoption — recommended pre-launch. NOTE 16 SEPTEMBER:
  Cloudflare R2 was weighed as a store and set aside (files only, no
  database, no logins). That does not touch the CDN question, which is a
  different thing and still live.
- Device key storage method — before security implementation.
- Export friction detail — metadata completion, AI disclosure prompts,
  publication checklist — before Step 14.
- New device verification — support ticket security questions.
- UX Gap 4 — font import in the Press templates.
- UX Gap 5 — document types in the New Project modal, full list.
- PUBLIC PRESS DATA — where a non-subscriber's book data comes from with
  no platform project: entered COLD, or UPLOADED as a finished
  manuscript. THE SAME MACHINERY as the continuity library and the
  import.
- POST-LAUNCH, Gap 6 — AI inference from an imported manuscript,
  pre-filling setup fields. SAME MACHINERY AGAIN, and the import being
  built now is the first of the four to become real.

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
continuity library in future.md. FOUR NAMES, ONE FEATURE — and the import
is now a fifth road to the same place.

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
  Highlight API does it without inserting anything.
- WHERE THE BASICS SAVE ROW LIVES — closed 1 September. The pocket, not
  the corridor. Read both files before deciding, every time.
- WHAT STATE THE WHEEL FILE IS IN — closed 1 September. Read and written
  up in current-state.md.
- "THE JOURNEY STOPS DEAD AT STEP ONE" — closed 1 September. The foot of
  Basics now points forward.
- THE PLOT MAPPING DEAD END — closed 1 September. The duplicate item
  under NAVIGATE was deleted from the corridor and published.
- DOES THE WRITER CONFIRM WHAT AN IMPORT EXTRACTS? — closed 16 September.
  THEY DO, ALWAYS. The muster. Nothing lands in the writer's work until
  they have seen it and said so.
- WHERE A LIBRARY OF BOOKS CAN LIVE — closed 16 September. Not the
  browser. Supabase.
- THE SILENT SAVE — closed in the previous session (written up
  22 September). The save guard is live, and the Basics line reports
  success rather than attempt. Kept in full in Section A as the record.
- WHAT MOVES TO SUPABASE FIRST — closed FOR NOW, 22 September. The library
  alone. Subject to change once something is built.
- LOGINS — closed FOR NOW, 22 September. Later; Kev does not mind them.
- THE AUTHOR AND STATUS BOXES OUT OF LINE — closed in the previous
  session. Found by Kev in use, fixed and live.
- WHETHER INKYSWOT CAN TALK TO SUPABASE AT ALL — closed 24 September.
  Proved with a throwaway page, first time: 201 on the write, 200 on the
  read. The page has done its job; the table it used should be deleted.
- WHERE ACCOUNT WORK HAPPENS — closed 24 September. The app, never the
  marketing site. The security reasoning is in locked-decisions.md.
- WHETHER THERE IS A MEMBER NUMBER — closed 24 September. There is, and
  Kev is 1.
- WHEN LOGINS HAPPEN — closed 24 September, the other way round from
  22 September: FIRST, not later, because an owner cannot be retrofitted.
- THE SIGN UP BUTTON LANDING ON THE LOG IN TAB — closed 24 September.
  login.html#signup, and the front page's button carries it.
- "MEMBERS ACCESS" AND "REQUEST ADMISSION" — closed 24 September. Both
  gone. Kev: "Sounds too exclusive, like some silly club."
- WHETHER THE FRONT PAGE NEEDS REWORKING NOW — closed 24 September, for
  now. It is a holding page and it is right for one. The writer's-desk
  idiom Kev showed is recorded in future.md and current-state.md.