File: inkyswot/current-state.md
Last updated: 18 September 2026, written up at the start of the session
after the work, as the rule requires when a session ends without one.
COVERS 17 SEPTEMBER.
BUILT AND LIVE: the silent save is fixed; the Basics saved line reports
success rather than attempt; paired boxes on Basics line up.
DECIDED BY KEV: move as little as possible — THE LIBRARY ALONE goes to
Supabase. He does not mind logging in. The boxes should line up. And what
he wants from an uploaded book is the ability to CHECK the new book
against it, not to fill every screen from it.
*** NOT DECIDED, AND MARKED AS SUCH THROUGHOUT *** — the shape of the
shelf, how uploaded work is referenced, and how the check behaves. Kev,
18 September: "I have no idea how things will work on Supabase and until
then I can't nail things down." The first write-up of this file stated
Claude's proposals as agreed; that was corrected the same morning.
A new file, factual-layer.md, holds the checkable fields — a working
list, not a lock, with three questions open in it.

================================================================
*** EVERYTHING ABOUT THE SUPABASE WORK IS SUBJECT TO CHANGE ***
================================================================
KEV, 18 SEPTEMBER: "I have no idea how things will work on Supabase and
until then I can't nail things down."

THIS APPLIES TO ALL OF IT, INCLUDING WHAT IS MARKED AS DECIDED. Even "the
library alone" is Kev's decision on what he knows today, and it may move
once something real is built and he can see how it behaves. The shelf,
the import, the check and the factual layer are all working ideas.

FOR ANY FUTURE SESSION: READ THIS BEFORE TREATING ANYTHING BELOW AS
FIXED. Do not argue from these sections as though they were settled. Do
not build on them as though they were final. Build small, show Kev, and
let what he sees decide the next step. Where a section says "decided",
read it as "decided for now".

THE GAP FROM 1 TO 16 SEPTEMBER WAS ILLNESS, NOT NEGLECT. No work happened
in it, so nothing was lost and no lesson is owed. This is recorded only so
a future session does not read the fortnight as a second slippage.

THE GAP THAT PROMPTED THE 31 AUGUST REWRITE. All five database files had
been last written on 15 August. Between then and 31 August a fortnight of
work happened that never reached them, including the Plot Mapper going
LIVE and a real fault in the Enclosure. The gap was found when the
database was read against the repository and the two disagreed. It has
been filled from the session record. Kev, honestly: "I have been slack on
updating these files and have now been caught out."

THE RULE THAT COMES OUT OF IT IS NOW LOCKED — UPDATE THE DATABASE AT THE
END OF EVERY SESSION. See locked-decisions.md. Held to on 1 and
16 September. On 17 September the session ended with Kev tired and no
write-up; the rule's own fallback was followed — THE NEXT SESSION BEGAN BY
WRITING UP THE LAST.

================================================================
*** SESSION-END REMINDER — READ THIS FIRST, EVERY SESSION ***
================================================================

BEFORE A SESSION CLOSES, THESE FILES ARE BROUGHT CURRENT. Not "when
there is time". Not "next session". At the end of the session that did
the work, while the reasoning is still in the room.

WHAT GETS WRITTEN:
  · current-state.md    what is built, what is live, what is still to do
  · locked-decisions.md anything settled, with its date
  · completed.md        one line per milestone, dated
  · thinking.md         what is still open
  · future.md           anything conceived but not started
AND ONE SPECIFICATION FILE, NEW 17 SEPTEMBER:
  · factual-layer.md    the checkable fields the cards need. Not rewritten
                        every session — only when the fields change.

WHY IT MATTERS MORE HERE THAN ON MOST PROJECTS. The code survives on
disk; the REASONING does not. A repository shows WHAT was built. Only
these files show WHY, what was tried and rejected, and what the trap was.
When 15–31 August went unrecorded, the code was still there — the two
weeks of decisions behind it were nearly lost, and were only recovered
because the session record could be searched.

AND A SECOND KIND OF LOSS, FOUND 1 SEPTEMBER: THE WHEEL HAD NO FILENAME
ANYWHERE IN THE DATABASE. Every other built thing had one —
code-plot-mapper-10.html, code-mystery-grid.html, concepts-canvas.html.
The Wheel had only "a mockup built on A Christmas Carol". A whole session
opened without anyone able to say what state the largest missing piece was
in. WHEN A THING IS BUILT, ITS FILENAME GOES IN THE FILE.

IF A SESSION ENDS ABRUPTLY, the next one begins by writing up the last.
AND IF WORK CONTINUES AFTER THE WRITE-UP, THE WRITE-UP IS NOT FINISHED.
Five milestones from 1 September were done after that session's files
were brought current, and reached no file until 16 September.

NOTE 16 SEPTEMBER — THESE FILES ARE NOW TOO LONG. Much of the length is
finished work described at the length it needed while it was still being
decided. A CONDENSING PASS IS ITS OWN SESSION, and the method is agreed:
shorten by AGE AND SETTLEDNESS, never by cutting detail. A thing built,
working and undisputed keeps its filename, its shape in a few lines, and
its traps; the reasoning that got there has done its job. A thing still
open keeps every word. TWO THINGS ARE NEVER SHORTENED: the traps (the
Grammarly trap, the Enclosure warning, the publishing minute) because each
one cost an hour and would cost it again; and anything marked
settled-do-not-reopen, such as the Proauthorism argument, which exists
precisely so a future session cannot reopen it. SPLITTING IS THE OTHER
ANSWER — the checker alone justifies a file of its own, as the nine files
of May were split.

================================================================
*** THE SILENT SAVE — FOUND 16 SEPTEMBER, FIXED AND LIVE 17 SEPTEMBER ***
File: corridor.html (a self-contained block at the end of the script).
File: pockets/project-overview.html (the saved line).
================================================================

THE FAULT. saveProjects and saveTrash called localStorage.setItem bare.
When the browser's storage was full the write did not happen and NOTHING
TOLD THE WRITER. Worse, the Basics standing line reported that a save had
been ATTEMPTED, not that it had SUCCEEDED, so it would have read
"Saved · 14:32" over a save that never happened. The screen the platform
trusts most was capable of lying to the writer.

DONE FIRST, BEFORE ANY SUPABASE WORK, and for the stated reason: it was
the only thing on the list that could actually lose work, and it could do
so long before the Supabase connection was finished.

--- PART ONE: THE SAVE GUARD, IN THE CORRIDOR ---

A SELF-CONTAINED BLOCK added at the very end of corridor.html's script,
immediately before </script>, after the read-aloud block. The same place
and the same pattern as the spell-check and read-aloud blocks already
there: bolted on at the end, reaching back to improve something, touching
nothing else. If it ever goes wrong, delete the block and the corridor is
exactly as it was.

WHY A BLOCK AND NOT THE WHOLE FILE, which departs from the whole-file
rule and is recorded so it is not mistaken for carelessness: corridor.html
is about 147,000 characters. Handing it back whole meant retyping every
line, and the risk of a silent typo somewhere in the middle was greater
than the fault being fixed. The bolt-on block is the corridor's own
existing pattern, so it was the lower-risk route by some distance.

WHAT IT DOES. It wraps saveProjects and saveTrash. A save that works does
nothing visible. A save that fails raises a RED BAR across the top of the
screen, in the house danger red #c43a2a: "YOUR WORK IS NOT BEING SAVED —
the browser's storage is full. Do not close this tab. Copy anything
unsaved somewhere safe." THE BAR STAYS UNTIL A SAVE SUCCEEDS.
IT INFORMS; IT NEVER BLOCKS. The writer can keep typing with the bar up,
which is right — the thing they most need to do is get their words
somewhere safe.
IT SETS A FLAG, window.IS_SAVE_OK, which any screen can read.

VERIFIED LIVE: Stitch 16 of 16, corridor 147,527 characters, index.html
345,951 characters at both ends. Opened in the live app, typed into
Basics: NOTHING VISIBLE CHANGED — which is what success looks like, since
the bar only appears on a real failure.

--- PART TWO: THE SAVED LINE ON BASICS, MADE HONEST ---

markSaved in pockets/project-overview.html now READS THE GUARD'S FLAG
BEFORE CLAIMING ANYTHING. If the last save succeeded it reads
"Saved · 14:32" in gold as before. If it failed it reads
"NOT SAVED — see the warning at the top of the screen" in the danger red,
and claims no time. Opening a project clears both states.
THE RULE IT ENACTS, NOW LOCKED: A SAVE IS ONLY REPORTED WHEN IT HAS
ACTUALLY SUCCEEDED.

--- AND ONE MORE THING FIXED IN THE SAME FILE, BECAUSE KEV SAW IT ---

THE AUTHOR BOX AND THE STATUS BOX DID NOT LINE UP. Kev spotted it on the
live screen while checking the save guard. The cause: the Read button is
added to some labels after the page loads, which makes those labels
taller and pushes their box down. Two fields sit side by side in a grid
row, so the taller label drags its box out of line.
ASKED WHICH SHOULD ALIGN — the labels or the boxes. KEV: "they should
line up." The boxes, because they are what the eye follows.
FIXED BY MAKING EACH HALF OF A ROW A COLUMN AND PUSHING ITS BOX TO THE
FOOT. Whatever the labels do above, the two boxes sit level. It does not
depend on guessing the height of anything, so it cannot drift. It fixed
Start Date and Classification in the same stroke.
VERIFIED LIVE: index.html 347,456 characters at both ends. Kev: "all
good."

WORTH NOTING: THIS WAS THE FIRST FIX THAT CAME FROM USE RATHER THAN FROM
ANY FILE. It is the "use wins" rule working the first time it was tested.

================================================================
*** THE PLATFORM IS LEAVING THE BROWSER (16 September 2026) ***
AND HOW FAR IT GOES — DECIDED 17 SEPTEMBER: THE LIBRARY ALONE.
Account created and standing ready. NOTHING IS CONNECTED YET.
================================================================

--- WHAT THE CODE ACTUALLY DOES TODAY, READ FROM corridor.html ---

EVERYTHING LIVES IN THE BROWSER AND NOWHERE ELSE. getProjects and
saveProjects read and write ONE localStorage item called "is-projects".
Every project, every character, location, building, faction, chapter, and
the whole plotMapper record sit inside that single lump of text. There is
no server, no account, no login. The projects exist because Chrome on that
machine is holding them. CLEAR THE BROWSER DATA AND THE LOT IS GONE.

THREE CONSEQUENCES, ALL FOUND BY READING THE FILE:

1. THE BOX IS ABOUT 5MB. A 90,000-word novel as plain text is roughly half
   a megabyte. One book survives. A LIBRARY DOES NOT.

2. EVERY KEYSTROKE REWRITES THE WHOLE LUMP. autoSave fetches all projects,
   alters one, writes them all back — on every oninput. Harmless with form
   fields. With a novel in the same lump, every letter typed anywhere
   re-saves the entire book.

3. saveProjects HAD NO ERROR HANDLING AND FAILED SILENTLY.
   *** FIXED 17 SEPTEMBER. See THE SILENT SAVE above. ***

--- THE DECISION, AND KEV'S REASONING ---

KEV: "Two books is going to be too limiting. When we talk about a library
it has to be just that." AND: "I want, if possible, to avoid local
storage. That said there will have to be an upper limit that when reached
triggers a cost increase."

A REAL LIBRARY NEEDS A SERVER. Storing books in the browser was only ever
a way of dodging the real answer. And this was always coming: YOU CANNOT
SELL A SUBSCRIPTION TO A PLATFORM THAT KEEPS EVERY WRITER'S NOVEL IN THEIR
OWN BROWSER CACHE. The library merely brought it forward.

--- *** WHAT MOVES — DECIDED 17 SEPTEMBER: AS LITTLE AS POSSIBLE *** ---

Four questions were put to Kev before any code. HIS ANSWER, AND IT WAS
THE RIGHT ONE: "To be completely honest I am not sure I know the answers
to any of those questions!!"
THAT EXPOSED A FAULT IN THE ASKING, NOT IN THE ANSWERING. Two of the four
— how existing work crosses over safely, and what happens on a bad
connection — were engineering questions dressed up as decisions for him.
Those are Claude's to propose and Kev's to judge. Only two were genuinely
his.

1. WHAT MOVES FIRST — KEV'S CALL, AND HE MADE IT:
   "My feeling is that we move as little as possible. That way as we move
   forward we are not having to make changes on another platform."
   HIS REASON WAS BETTER THAN CLAUDE'S. Claude had argued for the library
   alone on grounds of RISK. Kev's ground is that THE PLATFORM IS STILL
   CHANGING SHAPE — the Wheel is not in, step two of the Plot Mapper is not
   built, the cards need a factual layer. Move all of it now and every one
   of those jobs becomes a job done in two places.
   SO: BOOKS GO TO SUPABASE. PROJECTS, CHARACTERS, THE PLOT MAPPER AND
   EVERYTHING ELSE STAY EXACTLY WHERE THEY ARE, IN THE BROWSER.
   THE HONEST COST, NAMED AT THE TIME: for a while a book lives on the
   server and its project lives in the browser. Two halves of one piece of
   work in two places. It has to be kept straight.

2. HOW EXISTING WORK CROSSES OVER — Claude's to propose. It largely
   DISSOLVES under the decision above: nothing already in the browser is
   moving, so nothing already there is at risk. The Man Who Learnt To Fly
   stays exactly where it is.

3. WHAT HAPPENS WHEN THE INTERNET IS NOT THERE — Claude's to propose.
   Also much reduced: only the library depends on the connection, and a
   writer can keep writing without it. Still to be designed for the shelf
   itself.

4. LOGINS — KEV'S CALL: "I dont mind logging in." LATER, once the store
   exists. A login means the app asks who you are before it shows
   anything; nothing else about the platform changes.

--- THE SHAPE OF THE SHELF — CLAUDE'S PROPOSAL, NOT DECIDED ---

*** NOT SETTLED. *** KEV, 18 SEPTEMBER: "I have no idea how things will
work on Supabase and until then I can't nail things down." Everything in
this subsection is Claude's recommendation. Kev said at the time he was
"not entirely sure", and he is right not to be: nobody knows yet how it
behaves until something is actually built on it. BUILD SMALL, LOOK, THEN
DECIDE.

CHECKED AGAINST SUPABASE'S OWN DOCUMENTATION BEFORE RECOMMENDING, because
picking the wrong store would mean rebuilding the shelf later.

THE FILE STORE holds files as files — built for images, video, documents
and general-purpose files with access controls. THE ORIGINAL GOES THERE:
the document Kev uploads, kept exactly as it came, as the record of what
was actually handed over.

THE DATABASE holds text. Postgres's own guidance prefers the "text" type,
which has no declared length limit and no performance penalty. So a
novel's words sit in the database perfectly well.

*** AND THE FINDING THAT CHANGED THE DESIGN: DO NOT STORE A BOOK AS ONE
LUMP. *** Claude had been picturing one row holding 90,000 words. It
works, but every request for a paragraph would pull half a megabyte, and
someone running a large document system on Supabase found single cells
around a megabyte workable but noticeably slower.
THE BETTER SHAPE IS TO STORE THE BOOK THE WAY THE PLATFORM ALREADY
THINKS: ONE ROW PER CHAPTER. And it costs nothing extra, because the
chapter split is needed anyway.

SO CLAUDE PROPOSED THREE THINGS:
  1. The ORIGINAL FILE in the file store, untouched.
  2. A ROW PER BOOK — title, author, when it went in.
  3. A ROW PER CHAPTER — its number, its heading, its words.

WHAT KEV ACTUALLY SAID was not a verdict on that shape. He named what the
thing has to DO: pull information into the cards, and be searchable.
Claude read those two requirements as pointing at chapters in separate
rows, and wrote it up as though Kev had arrived at the same answer. HE HAD
NOT. He stated the requirements; the shape is Claude's inference from
them. THE REQUIREMENTS ARE KEV'S AND THEY STAND. THE SHAPE IS OPEN.

TWO THINGS TO VERIFY ON SUPABASE'S OWN PAGES BEFORE BUILDING, NOT
TRUSTED FROM A SEARCH: the maximum size of a single uploaded file on the
free tier, and whether there is a practical ceiling on a single text row
worth respecting.

--- WHY SUPABASE, OVER THE ALTERNATIVES ---

Three were weighed. VERCEL'S OWN STORAGE: already on Vercel, simplest to
wire, but does less, needs something separate for logins, dearer as it
grows. CLOUDFLARE R2: cheapest by a distance for large files with no
egress charge, but files only — no database, no logins, bolted onto
something else. SUPABASE: database and file store in one, WITH LOGINS,
which InkySwot needs before it can take a penny from anyone. DOING
STORAGE AND LOGINS AS ONE JOB RATHER THAN TWO IS THE WHOLE ARGUMENT.
It was also the intended direction back in May.

--- WHAT WAS SET UP, 16 SEPTEMBER ---

  Organisation:  PITCH DARK STUDIOS  (Personal, Free plan)
  Project:       INKYSWOT
  Region:        West Europe (London), eu-west-2
  Signed in via: GitHub OAuth on the PitchDarkPress account
  Scope granted: user:email ONLY — read-only access to email addresses.
                 No repository access. Revoke at
                 github.com/settings/connections/applications
  Database password: GENERATED AND SAVED BY KEV OUTSIDE THE BROWSER.
                 Supabase will not show it again.
  Status on creation: Healthy. Advisor found no security, performance or
                 health issues.

THREE SECURITY SETTINGS, CHOSEN DELIBERATELY AT CREATION:
  · ENABLE DATA API — ON. This is how InkySwot talks to the database from
    the browser. Without it nothing works.
  · AUTOMATICALLY EXPOSE NEW TABLES — OFF. Supabase's own note recommends
    disabling it. It would open every new table to the outside world by
    default. THESE ARE WRITERS' NOVELS.
  · ENABLE AUTOMATIC RLS — ON. Row Level Security on every new table in
    the public schema. RLS is the rule that says a person sees only their
    own rows — THE THING THAT STOPS ONE WRITER READING ANOTHER'S BOOK.
    Automatic means it cannot be forgotten.

--- THE PRICING, CHECKED TWICE AND CONFIRMED ---

FREE PLAN: two active projects, 500MB database, 1GB file storage, 50,000
monthly active users. Egress is reported as either 5GB or 500MB depending
on source — READ IT OFF SUPABASE'S OWN PAGE WHEN IT MATTERS. 1GB of file
storage is around two thousand novels: ample for building.
THE ONE CATCH: FREE PROJECTS ARE PAUSED AFTER SEVEN DAYS OF INACTIVITY.
Nothing is deleted; it restarts from the dashboard. Fine while building,
no good once anyone depends on it.

PRO: $25/month PER ORGANISATION — *** NOT PER PROJECT, AND NOT PER USER
*** — covering every subscriber InkySwot ever has. Includes 8GB database,
100GB file storage, 250GB egress, 100,000 monthly active users, daily
backups, no inactivity pause, and a $10 compute credit covering one Micro
instance. A SPEND CAP IS ON BY DEFAULT, so runaway usage cannot quietly
produce a large bill. Beyond 100GB, file storage is about 2p per GB —
which is where Kev's cost-trigger idea belongs, and it is years away.
A SECOND PROJECT in the same organisation adds about $10 of compute, NOT
another $25 of plan fee.
CLAUDE WAS WRONG FIRST TIME and reported "$25 per project" as a live
doubt. Supabase's own billing documentation is explicit that billing is
per organisation. Several pricing write-ups name the per-project claim as
the commonest error made about Supabase.

THE PLAN: BUILD AND TEST ON FREE, SWITCH TO PRO WHEN IT GOES LIVE.
Nothing is rebuilt at that point — it is a switch on the account.

--- THE PAUSING QUESTION, AND WHAT WAS DECIDED ---

Kev opens InkySwot most days, so the seven-day pause may never bite. ONCE
THE APP IS WIRED UP, OPENING IT IS ITSELF THE ACTIVITY — loading the
library is a request to the database and the clock resets. TODAY IT IS
NOT, because InkySwot does not talk to Supabase yet.
NOTE 17 SEPTEMBER: with only the library moving, OPENING THE APP WILL NOT
BY ITSELF TOUCH SUPABASE unless the library is opened, or something on
the first screen reads from it. Worth remembering when the shelf is built.

A SCHEDULED KEEP-ALIVE FROM VERCEL WAS CONSIDERED AND SET ASIDE. It cannot
come from inside InkySwot, because the app only runs when a browser has it
open and the whole problem is the weeks when nobody opens it. And a
keep-alive ping works against the terms of the free tier rather than
within them. KEV'S BETTER ANSWER: Vercel reminds HIM to open the platform,
and he opens it. That is real use and needs no disguise.
SETTLED, AND WORTH KEEPING AS A PRINCIPLE: A NUDGE TO THE WRITER, YES. A
THING PRETENDING TO BE THE WRITER, NO.
AND THE DASHBOARD SETTLES IT BY OBSERVATION rather than by argument — it
reports when the project last saw activity.

--- WHERE THIS LEAVES THE PLATFORM ---

NOTHING IS CONNECTED. InkySwot still reads and writes localStorage and
knows nothing about Supabase. The account is a place for the library to
live, and that is all it is today.
THE NEXT JOB IS THE SHELF ITSELF — somewhere for a book to live, and a
way to put one there. SMALL, BECAUSE ONLY THE LIBRARY MOVES.
IT IS INFRASTRUCTURE, NOT A POCKET — the first thing hit in this rebuild
that cannot be done by writing a screen. KEV: "Let's go slow."

================================================================
*** THE IMPORT — RESHAPED 17 SEPTEMBER INTO A CHECK ***
Conceived 16 September. NOT BUILT. Read this section whole before
building any of it — its purpose changed twice in one conversation, and
the final shape is not the first one.
================================================================

WHAT KEV ASKED FOR. He has written THE ADVENTURES OF A. RAPSCALLION and
is half way through THE FURTHER ADVENTURES OF A. RAPSCALLION, book two of
the series. He wants book one in InkySwot as a reference for book two.

--- HOW THE PURPOSE CHANGED, IN ORDER, BECAUSE THE ORDER MATTERS ---

FIRST SHAPE (16 September): AN IMPORT THAT FILLS THE SCREENS.
"The first thing would be to auto fill all the locations characters etc."
Claude then listed every screen it might fill — all sixteen — and noted
that some (Characters, Locations, Buildings, Objects, Factions, Events)
are nouns that appear in the text, while others (Plot Threads, Subplots,
Themes, Rules & Lore) are INTERPRETATIONS a machine can only guess at.

SECOND SHAPE (17 September): A CHECK, NOT A FILL. KEV CORRECTED IT:
"We DONT need ALL that info, just the ability to check it. so what we
really need is the ability to find the above information and have it
'ping' the user when they get things wrong in the new book — IE: hair
colour etc."
THAT IS A MUCH SMALLER THING AND A MUCH BETTER ONE. Extraction fills the
screens — two hundred records to tick, a wall of work before a word is
written. Checking fills nothing: book one sits as a reference, and when
book two says "Barnaby's blond hair" the platform says he was dark in
chapter nine of book one.

THEN THE QUESTION THAT SETTLED IT, and Kev said Claude had "touched it":
WHEN IT PINGS, WHAT IS IT CHECKING AGAINST — BOOK ONE'S TEXT, OR THE
CHARACTERS SCREEN? KEV: "YES info should be in certain fields — characters
being one of them. There is no point in rebuilding a character profile
when it already exists."

*** THE SHAPE SO FAR, 17 SEPTEMBER — STILL BEING BUILT ON ***
KEV, THE MORNING AFTER: "We will be still building on how uploaded work
is referenced." SO THIS IS A DIRECTION, NOT A LOCK. It is recorded here
and in thinking.md, and deliberately NOT in locked-decisions.md, because a
lock is exactly where a half-built idea should not live.
  · THE BOOK IS READ ONCE.
  · WHAT IT FINDS LANDS IN THE CARDS — Characters and the rest — so the
    cast is not typed in again from scratch. Behind the muster, always.
  · FROM THEN ON, THE CHECK RUNS AGAINST THE CARDS, NOT THE BOOK. Write
    blond in book two; Barnaby's card says dark; the platform pings.
  · THE BOOK HAS DONE ITS JOB BY THEN AND GOES QUIET ON THE SHELF.
FILL THE CARDS ONCE. CHECK AGAINST THE CARDS FOREVER. Both halves of
Kev's two statements were right, and this is how they fit together.

AND IT IS THE CONTINUITY LIBRARY, arrived at from the other end — the
thing Kev described on 15 August and again on 31 August, and now wanted
this week for a real book.

--- WHAT THE CHECK DEPENDS ON: THE FACTUAL LAYER ---
Full specification in factual-layer.md.

A CARD THAT SAYS "a tall man, greying now, with the sort of face that
gives nothing away" CANNOT BE CHECKED AGAINST ANYTHING. A card with a hair
field can. So the factual layer, flagged on 31 August as a nice idea,
IS NOW THE THING THE WHOLE CHECK DEPENDS ON.

THE TEST FOR EVERY FIELD: A WRONG ANSWER MUST BE CHECKABLE. Hair colour
passes. Personality does not.

KEV ASKED FOR IT TO BE COMPREHENSIVE, AND ADDED A NOTES SECTION ON EVERY
RECORD "for things like preferences etc." A GOOD ADDITION, because
preferences and habits ARE checkable — "drinks only tea", then coffee in
book two, is exactly the fault that gets through.
BUT THE CARDS ALREADY HAVE A NOTES FIELD, and it is free prose. A checker
reading prose is back to guessing. Claude's view: a SECOND, SEPARATE list
of short lines, one fact each. NOT RULED ON.

THREE QUESTIONS IN factual-layer.md ARE WAITING FOR KEV, and he said he
would look at them the next day:
  1. The Notes question above — reuse the existing field, or a separate
     list of short lines.
  2. Which wins when the facts and the prose disagree.
  3. How many fields show at once — the full list on one card is a form
     nobody would fill in.

--- THE RUN, AS IT NOW STANDS ---
  0. THE SHELF — Supabase. Its shape is NOT DECIDED; see Claude's
     proposal in the Supabase section.
  1. THE ROOM — pockets/research.html replaces the Coming Soon. STATIC
     STILL FIRST.
  2. THE WAY IN — a file picker. PLAIN TEXT FIRST; Word and PDF can
     follow.
  3. THE CHAPTER SPLIT — find the headings. No AI. Both the shelf and the
     Plot Mapper want it.
  4. THE FACTUAL LAYER ON THE CARDS — before the read, because the read
     needs somewhere to put what it finds.
  5. THE READ — once, front to back, in sections.
  6. THE MUSTER — what was found, shown for ticking. Much smaller than
     first imagined, because it is only filling checkable facts.
  7. THE LANDING — ticked facts into the cards.
  8. THE CHECK — the new book tested against the cards, and a ping with
     the chapter reference when something disagrees.

CLAUDE'S VIEW, NOT DECIDED: the ping should say WHERE, not just what.
"That's wrong" is useless. "He was dark in chapter nine of book one" lets
the writer go and look — and the writer may have changed it on purpose.
So it asks rather than corrects. Offered, not ruled on.

--- STILL CARRIED FROM 16 SEPTEMBER ---

WHERE IT LIVES — THE LIBRARY, on Kev's reasoning: "what if I want to add
stories by other people for style and tone?" The moment the shelf holds
anything but your own previous books it is a reference collection.

A FLAG RAISED TWICE AND LEFT FOR KEV. Someone else's novel used to teach
the platform a style is a different matter, legally and in terms of what
InkySwot says it stands for. NOT SETTLED. And note that the reshaping into
a CHECK makes this question smaller for the continuity use: a check runs
against YOUR cards, filled from YOUR book.

COST AND ALLOWANCES — PARKED by the build-for-one-user rule. Reading a
whole novel costs about 15p. Claude's view that the import should not
touch the prompt counter stands, unruled.

================================================================
*** BUILD FOR ONE USER — KEV'S RULE, 16 SEPTEMBER ***
================================================================

KEV: "ALWAYS picture me as the ONLY user. Therefore questions on prompts
and their cost are void. Once we have the platform sorted for me only then
do we add the cost/benefits equation into the mix and go from there. The
reason I say this is that I am probably going to be the most difficult
customer for the platform, so if it works for me then all else follows."

PROMPT CAPS, PER-USER COSTS AND ALLOWANCES ARE OFF THE TABLE until the
platform works for him. If the import needs to read a book forty times to
get it right, it reads it forty times.

THE ONE EXCEPTION, AND IT IS WHY THE SUPABASE DECISION COULD NOT WAIT:
A STORAGE CEILING IS A LIMIT OF THE MACHINE, NOT A BUSINESS DECISION. Kev
as a single user hits 5MB with two books just as surely as three thousand
writers would. "Will the book fit" is not a cost question.

================================================================
*** THE WHEEL / MANUSCRIPT — STANDALONE, NOT A POCKET ***
Read and assessed 1 September 2026. The largest missing piece of the
platform. NOT IN THE CORRIDOR: nav-manuscript points at Coming Soon and
there is no POCKET:manuscript slot.
================================================================

WHAT THE FILE ACTUALLY IS. A mockup of the WHOLE PLATFORM as it stood in
June, not a screen. It draws its own header, its own left sidebar and a
right sidebar holding the Site Map. Roughly half of it is corridor work
that the corridor now does properly.

THE SIDEBAR INSIDE IT IS THE SUPERSEDED SPINE — Projects / DCW / World
Building / Notes, still carrying "Writing Panel" as the name and a
"Scenes" item that no longer exists. Replaced platform-wide on 11 August.
The Site Map beside it is the June one, built against that same old nav.
All of this is deleted in the conversion.

--- WHAT SURVIVES INTACT, AND IT IS THE IMPORTANT HALF ---

EVERY LOCKED NUMBER IS PRESENT AND CORRECT. TIGHT 46, GAP 64, WINDOW 9,
BOW 0, ease rate 0.072, READ_PAD 28. The centre mark is the 17px two-pixel
gold ring with its filled dot and short leader. Labels are two lines, mono
gold kicker over Crimson Pro title. Hover lights the node only, never the
text. Both states are built — Overview and Writing Mode — and the hand-off
between them waits two animation frames for the layout to settle before
landing the page on the reading line.

THE WHEEL TURNS OFF SCROLL POSITION. It measures where each page's top
sits against the reading line and eases toward it. That arithmetic does
not care whose book it is or how many pages there are, which is why the
conversion is a strip rather than a rebuild.

THE ENTITY POP-UPS ARE THE LOCKED ONES — multiple, independent, dragged by
the header, closed by ✕ only, rising on click, with copy buttons that take
plain text.

--- THREE THINGS IN IT ARE OUT OF DATE ---

All three were settled AFTER the file was written, and all three are
corrected during the strip:
1. TENSION SHOWS AS THE PLAIN TEXT "55%" in the scene menu — one of the
   versions rejected on 9 June in favour of the segmented bar meter.
2. THE POP-UP COLOURS use the old section colours #cba36a and #b08a6a,
   superseded 4 June by the six track colours.
3. THERE IS NO SECTION ? PILL, which every screen now carries.

--- AND NOTHING IN IT IS REAL ---

The whole of A Christmas Carol is twenty-five sheets of hard-coded HTML.
THERE IS NO localStorage ANYWHERE IN THE FILE. Writing goes into a plain
object in memory and is gone on refresh. The scene menu's Objects and
Themes are literally the word "Something".

ONE SMALL TRAP, FOUND AND RECORDED. The scene kicker builds "Stave One —
Scene One" from a word list that stops at ten. A book with an eleventh
chapter would read "Stave undefined".

--- THE CONVERSION, AGREED IN SHAPE ---

STRIP, DO NOT REBUILD. Cut the header, both sidebars and the Site Map;
keep the page, the scene menu and the wheel. THE WHEEL'S CODE COMES ACROSS
UNCHANGED — a fresh write would get some of those numbers subtly wrong and
cost a session finding out which.
THEN POINT IT AT A REAL PROJECT. The labels are currently hard-coded in
the HTML and must be built from the project's chapters and scenes. THIS IS
THE JOIN, AND THE JOIN IS WHERE A FAULT WILL BE.
THEN THE CORRIDOR: add a POCKET:manuscript slot and repoint
nav-manuscript. The Plot Mapper's going-live on 25 August is the pattern.
THE FIRST DELIVERABLE IS A STATIC STILL — one page, the wheel, the scene
menu, real data, nothing moving.

TWO THINGS WE DO NOT YET KNOW. The belt has never been run at novel
length — twenty-five pages is about 26,000 pixels of scroll and a real
book is four hundred pages. And the scene menu will be EMPTY, because it
is fed by the Plot Mapper's cards and those do not write into a shared
store yet (step two). It must say so plainly rather than fake it.

AND ONE THING WORTH SETTLING DURING THE CONVERSION RATHER THAN AFTER. The
Wheel's writing area is a PLAIN TEXTAREA. The checker's painted marks need
a proper writing surface and cannot work inside an ordinary text box —
so the screen the checker most wants cannot take marks as things stand.
Changing the writing surface later is a rebuild.
NOTE 17 SEPTEMBER: THE CONTINUITY CHECK WILL WANT THE SAME. A ping that
points at the exact phrase in the manuscript is a painted mark. The case
for a proper writing surface in the Wheel just doubled.

================================================================
*** THE CHECKER — PUNCTUATION · BUILT TO BUILD 12 (27–28 August 2026) ***
Working files: checker.html (one file, engine inside it).
Also: checker-parser.js, checker-rules.js and their test suites.
NOT YET A POCKET. Standalone, working, tested on real manuscript.
================================================================

WHAT IT IS
A proofreading instrument for InkySwot. The writer hands it a passage, it
marks what may need looking at, and offers corrections. IT PROPOSES. IT
NEVER REWRITES. Not a Grammarly clone and it should never be sold as one.

THE HEADLINE CLAIM — THE TEXT NEVER LEAVES THE MACHINE
Grammarly sends every check to servers in American data centres; there is
no local mode. They protect that text with contracts and audits, and by
all appearances honour them — BUT THE TEXT GOES. Ours does not. That is a
fact about the architecture, not a promise needing defence. For a writer
with an unfinished manuscript it is the only claim that matters, and it
is one Grammarly structurally cannot make.
NOTE 16 SEPTEMBER: moving the LIBRARY to Supabase does not touch this.
The claim is about the CHECKER, not about where anything is stored. Keep
the two apart in every sentence written about it.

HOW THE WRITER MEETS IT — THE PASTE-IN POP-UP
The writer copies a passage in, presses Check, reads the marks, takes what
they want, copies back. THE MANUSCRIPT IS NEVER TOUCHED. The instrument
cannot reach it; it only ever sees what was handed over. The friction of
copying back is ACCEPTED DELIBERATELY — it keeps the writer as the only
party who decides what enters the manuscript.

THE MARKS
Red dotted underline for a fault, gold dotted for a note or query. Drawn
with the CSS CUSTOM HIGHLIGHT API — ranges handed to the browser, which
paints them. NOTHING IS INSERTED INTO THE TEXT. No tags, no wrappers, no
markup. The alternative (wrapping words in spans) would put markup into
the writer's prose, break undo, and jump the caret. Rejected on those
grounds alone.

THE POP-UP ON A MARK
Click a marked word and a panel opens: what is wrong in plain British
English, why underneath (switchable), and the correction where there is a
safe one. "Use …" applies and re-checks. "Take it out" for a deletion.
"LEAVE IT" dismisses that mark for the session. Where nothing safe can be
offered it says so plainly rather than pretending.

EXPLANATIONS ARE SWITCHABLE, THE FINDING IS NOT. Two levels: the finding
always shows; the teaching sentence beneath can be turned off. One switch
for the whole screen, not thirty. Kev is dyslexic and cannot judge whether
a flag is correct, so the tool must say what is wrong in words he can act
on, not merely mark and expect recognition.

--- THE PARSER (stage 1a) — BUILT, 110 TESTS PASSING ---

Built FIRST, before any rule, because almost every false positive in a
punctuation checker comes from a rule firing on text the parser should
have marked as something else. Eight stages, in order:

1. CHARACTERS. Every mark identified for what it is — straight against
   curly, apostrophe against closing single quote, hyphen / non-breaking
   hyphen / en dash / em dash, three dots against the ellipsis character,
   and the invisible spaces.
2. PROTECTED REGIONS. Sixteen kinds of thing prose rules never enter:
   URLs, emails, paths, filenames, version numbers, [sic], currency,
   thousands separators, decimals, numeric dates, times, measurements,
   ordinals, initials.
3. PARAGRAPHS, classified as prose, scene break, chapter title, heading,
   salutation, sign-off, list item or address. THE HEADING TEST IS
   DELIBERATELY TIGHT — calling a short fragment a heading would switch
   off every rule inside it.
4. TOKENS.
5. SENTENCES, with a British abbreviation list. A full stop is not a
   sentence end until the parser says so.
6. QUOTES. Each single mark decided as apostrophe, opening, closing or
   ambiguous.
7. DIALOGUE. Nesting on a stack. Multi-paragraph speech recognised.
   Spoken dialogue told apart from quoted words, including speech resumed
   after an interrupting tag.
8. RAGGED EDGES. See below.

PLUS the findings plumbing: confidence threshold, severity ordering, and
overlap resolution so three rules describing one problem produce one
finding.
NOTE 17 SEPTEMBER: STAGE 3 ALREADY CLASSIFIES CHAPTER TITLES. The
import's chapter split may not need writing at all — the parser may
already do most of it. WORTH CHECKING BEFORE BUILDING.

--- RAGGED EDGES — AN ADDITION THE SPECIFICATION COULD NOT HAVE MADE ---

A pasted passage is usually cut out of the middle of a scene. A speech
mark left open at the top may simply be where the paste began. EVERY RULE
THAT DEPENDS ON THINGS MATCHING IN PAIRS MUST BE GENTLER AT THE EDGES
THAN IN THE MIDDLE — near-certain in the body, no more than a query in
the first and last sentence. A manuscript has no ragged edges; a pasted
passage always might.

--- THE RULES (stage 1b) — 31 BUILT, 75 TESTS PASSING ---

RULES THAT ASSERT (mechanical, near-certain):
space before punctuation · no space after comma/semicolon/colon · more
than one space · duplicated punctuation · "?." and "!." combinations ·
two dots where three belong · unmatched round brackets, square brackets
and braces (nesting validated, not merely counted) · space inside a
bracket · unclosed speech marks · straight and curly mixed · both speech
mark families in use · its' · apostrophe turned the wrong way ('Twas) ·
missing apostrophe in 29 shortened words · decade apostrophe (1970's) ·
time and quantity possessives (a day's work, five years' experience) ·
hyphen for a numeric range · comma and dash together · small letter
starting a sentence · three dialogue rules · three for characters broken
in copying.

STYLE, NEVER A FAULT: repeated end marks · mixed ellipsis styles · four
or more dots · two hyphens.

--- THE SUPPRESSION LIST — AS IMPORTANT AS ANY RULE ---

Built knowing these are CORRECT and never reporting them: fragments ·
one-word sentences · sentences opening with And/But/So · stammering
(I-I, W-what) · speech trailing off on an ellipsis · speech interrupted
by an em dash · deliberate repetition (No. No. No.) · British logical
punctuation outside quoted words · a question mark inside speech marks
doing the terminal work · scene breaks, headings, chapter titles,
addresses, salutations, sign-offs · titles carrying their own terminal
punctuation · every ornamental and reference mark.

--- WHAT IT MEASURES ---

ZERO FALSE POSITIVES on a page of deliberately awkward but entirely
correct British fiction. That page is now a permanent test.
185 TESTS PASSING across both suites.
250,000 WORDS in 711 milliseconds, parse and rules together.

--- NO SIZE LIMIT, EVER — A PRINCIPLE, NOT AN OPTIMISATION ---

Kev's position, and it is right: telling a writer the checker is limited
to X words would mean asking them to chop their manuscript up, and that
would put him off using it. Either that, or they paste it all in and it
does not work. BOTH DAMAGE THE PLATFORM'S CREDIBILITY.

So: the work is done IN SLICES with the screen handed back between each.
The window never freezes, the browser never offers to kill the page, and
a longer manuscript simply takes longer.

MEASURED: 22,000 words (Act One) 57ms · 100,000 words 184ms · 250,000
words 376ms · 500,000 words 618ms.

TWO QUADRATIC FAULTS WERE FOUND AND FIXED getting there — the parser
looked things up by walking whole lists once per character, and the
findings resolver compared every finding against every other. THE
GIVEAWAY WAS THE SHAPE, NOT THE NUMBER: doubling the words quadrupled the
time. Kev's correction was fair — "when you talk about 150 ms as being a
long time, it is only a long time to you" — and the right defence is not
speed but the CLIFF. Quadratic growth is fine until suddenly it isn't,
and the failure arrives without warning.

THE PROGRESS BAR. Kev's own pattern from Prompt and Expand: clock, bar,
"please wait". Writers don't mind waiting as long as they know for how
long. BUT A BAR THAT FLASHES FOR A FIFTH OF A SECOND IS WORSE THAN NO
BAR — it is held back and only appears if the work is still going after
a quarter of a second.

--- WHAT ACT ONE TAUGHT US (47,074 words, real manuscript) ---

Running the real book through it found four faults in the engine and one
in the book. All four engine faults were the same class: A REASONABLE
RULE THAT WAS WRONG ABOUT REAL PROSE.

1. THE SPEECH MARK FAMILY WAS DECIDED BY COUNTING. The Christmas Murders
   uses double quotes for dialogue and SINGLE quotes for emphasis —
   'maids', 'slave', 'baby', 'the blond baggage', 'chill out'. 132 double
   marks against 353 single. Counting made it a single-quote manuscript
   and would have flagged every line of double-quoted dialogue as wrong.
   RAW FREQUENCY IS PRECISELY THE MISLEADING SIGNAL: emphasis is common,
   dialogue is structured. The vote now ignores frequency entirely and
   counts only structure.

2. THE SPEECH VERB LIST WAS TOO LOOSE. It held went, put, called, added,
   began — all ordinary verbs. So "'chill out' and went on his way"
   looked like a dialogue tag. Worse, the test accepted any two words
   where either was a verb, so "and went" passed. A TAG NOW NEEDS A
   SUBJECT BESIDE THE VERB: he said, Agnes replied, asked Constance.

3. A TAG CANNOT FOLLOW A FULL STOP. "a complete and utter fool." I said
   nothing. — the full stop closes the speech, so what follows is a new
   sentence of narration, not a tag. A tag follows a comma, a question
   mark or an exclamation mark.

4. AND THE FINDING IN THE BOOK: ACT ONE USES BOTH KINDS OF SPEECH MARK
   FOR DIALOGUE. Roughly 31 passages in double and 43 in single, not
   divided by scene. Both are correct English; a book settles on one.
   THE ENGINE'S ANSWER IS NOW "MIXED" — forcing a choice would flag every
   line of the other kind as faulty, around forty confident false
   positives on good prose. Kev could not judge whether the departure was
   deliberate, which is itself the point: the tool reports, the writer
   decides, and converting one style to the other is mechanical and safe.

--- THE METHOD THAT FOUND ALL OF IT ---

KEV'S OWN LOCKED RULE, APPLIED AGAIN: when a fault survives one fix, stop
guessing and make the screen say what it did. Four builds were spent
treating a CORRECT answer as a bug because the diagnostic page was
computing its own numbers rather than showing the engine's. Once the page
showed the engine's own workings — including the twelve actual phrases it
believed carried speech tags — the answer was immediate.

TWO SUPPORTING LESSONS, BOTH LEARNED THE HARD WAY:
· ONE FILE, NOT SEVERAL. A test page that loads its engine from a
  separate file fails silently when the two drift apart. An hour was lost
  to a new page sitting beside an old engine. Test pages now carry the
  engine inside them.
· A BUILD STAMP IN THE CORNER. "BUILD 12 · 28 AUG". Without it there is
  no way to tell which copy is open, and browsers save duplicates rather
  than overwriting.

--- THE SPECIFICATION, SORTED ---

A full punctuation specification was produced (via ChatGPT) and sorted
into three piles, kept at checker-spec-sorted.md:
  1. BUILD NOW — PASSAGE-LOCAL. Everything decidable from the passage,
     including the parser work. About 30 asserting rules, 9 queries, and
     the suppression list.
  2. BUILD LATER — MANUSCRIPT-AWARE. Essentially one thing wearing several
     hats: CONSISTENCY. Quotation style, dashes, ellipses, dates, house
     style, statistics, habits. All need the whole book.
  3. OUT OF SCOPE. Markdown, HTML, footnotes, bibliography, code modes,
     restrictive-vs-non-restrictive commas (undecidable locally).

NOTE: the specification assumed the checker would eventually see the whole
manuscript. It does not — it sees a pasted passage. A good deal of it is
not wrong, merely aimed at a different tool.
NOTE 17 SEPTEMBER: PILE TWO IS NOW A LIVE NEIGHBOUR. "Consistency across
the whole book" is the punctuation cousin of the continuity check. When
the continuity check is built, pile two should be looked at in the same
light — both need the whole book, both are consistency, both ping rather
than correct.

FOUR AMENDMENTS KEV MADE TO THE SORT, ALL CORRECT:
  · Sentence length removed entirely — belongs to a style tool.
  · Four or more dots moved out of near-certain errors (an ellipsis
    meeting a full stop is legitimate under some house styles).
  · Two hyphens moved out of near-certain errors (a long-standing
    plain-text convention, often deliberate).
  · Time and quantity possessives brought back into passage-local work —
    "two days' work" is decidable from the phrase alone.

--- STILL TO DO ON THE CHECKER ---
1. THE QUERIES (stage 1c) — nine rules that only ask: comma splice,
   action beat punctuated as a tag, speaker change without a paragraph
   break, question tag, vocative comma, colon with an incomplete unit,
   semicolon before a subordinating word, missing comma after a
   conjunctive adverb, four-or-more dots. NOT STARTED.
2. THE LEARNING LIST. Every accepted or hand-typed correction stores a
   pair — what was there, what replaced it — after A SINGLE USE. The
   writer's own correction then sits at the top of the drop-down. Where
   one slip has two answers (thier → their / there) BOTH ARE KEPT.
   Ordering by tally first; reading the sentence is a second phase.
3. SPELLING. The dictionary, on its own, so that if it breaks we know
   what broke. About a megabyte; fetched for testing, bundled for the
   pocket. The text still never leaves.
4. INTO INKYSWOT. The engine becomes a shared part in the corridor, then
   an attachment that can be given any writing area on any screen, then
   attached to ONE screen and lived with for a week before the rest.
   NOTE 1 SEPTEMBER: which screens can take painted marks is now partly
   known — the Plot Mapper can (contenteditable); Basics, the
   world-building screens and the Wheel's writing area cannot (plain
   inputs and textareas).
5. PARAGRAPHING GUIDANCE. Kev asked for it and it is teaching rather than
   checking. The one thing a checker can catch is two apparent speakers
   in one paragraph. THE RULE UNDERNEATH, worth carrying: A PARAGRAPH
   BELONGS TO ONE PERSON. Speech and action of the same person go
   together; the moment someone else's action joins their speech, the
   reader assumes it was them. Indent is a display choice, done by
   styling, NEVER by typed spaces (typed spaces would read to the checker
   as a spacing fault).

================================================================
*** THE PLOT MAPPER — LIVE (25 August 2026) ***
File: pockets/plot-mapper.html. Published to app.inkyswot.com.
================================================================

STEP ONE OF GOING LIVE IS DONE. The standalone code-plot-mapper-10.html
became a pocket, the corridor slot was added, the sidebar's DCW > Plot
Mapper points at it, and the header and word budget read the real project
rather than the Wind in the Willows demo.

IT SAVES. The document is written onto the project in localStorage
"is-projects" under plotMapper — parts, made, the budget, the indent and
details switches — with currentWords and lastEdited updated. Saving is
debounced and also fires on beforeunload. THE "NOTHING SAVES" ITEM FROM
15 AUGUST IS CLOSED.
NOTE 17 SEPTEMBER: IT STAYS IN THE BROWSER. Under the library-alone
decision the Plot Mapper does not move to Supabase. And its saves now go
through the save guard, so a failure would raise the red bar here too.

NOTE 1 SEPTEMBER: that plotMapper record is now doing a second job. It is
how the Basics screen knows whether a project has been to the Plot Mapper,
which decides the emphasis on its foot buttons. No new flag was added.

NOTE 16 SEPTEMBER: permanent IDs were added to chapters and scenes on
1 September so the Wheel can attach prose to a SCENE rather than a
position that shifts when content is rearranged. A paste handler was also
added, so text pasted from Word or a PDF arrives as plain ink in the
screen's own colour, paragraphs preserved and inline formatting stripped.
Kev put THE MAN WHO LEARNT TO FLY, book one of a series, into the Plot
Mapper on that day — THE FIRST REAL BOOK IN THE PLATFORM.

WHAT THE SCREEN DOES (unchanged from the 15 August build, confirmed live):
one continuous document, prose never boxed or retyped · F2 as the one key
· selections growing out to whole words · the dashed gold hairline break
with its pill in the left gutter and gold dot at the end · the gold dot's
menu (own word range, chapter↔scene, remove) · Also Called on cards with
suggested aliases, set-aside and recall · Indent and Details switches ·
the movable, resizable SECTION ? window · the cut-back header with
More/Less · the foot tally including how much is not yet divided.

ADA IS NOT CONNECTED TO THIS SCREEN. Prompt and Expand are built on every
chapter and scene line and on every card, but they are shown QUIET and
disabled, with a title saying why. A button that cannot work says so
rather than failing when pressed. WIRING THEM IS THE NEXT PIECE OF WORK
ON THIS SCREEN.

STILL TO DO ON THE PLOT MAPPER:
1. THE VANISHING TINTS. A mark is held as "characters 14 to 22 of this
   paragraph"; editing the words moves them. readBack() currently DROPS
   the marks on edit rather than following them. Unchanged since 15
   August, and still to be solved WITH step two, not after.
2. CARDS DO NOT REACH CHARACTERS. Making Mole does not put him anywhere.
   Step two, and the real work. THE WHEEL'S SCENE MENU DEPENDS ON THIS —
   until it is built, that menu is empty. NOTE 16 SEPTEMBER: THE IMPORT
   NEEDS THE SAME JOIN. NOTE 17 SEPTEMBER: AND SO NOW DOES THE CONTINUITY
   CHECK, which runs against the cards. Three things wait on this one
   join.
3. Ada's buttons.
4. THE CROSSING TO THE WHEEL. The Plot Mapper already carries "Edit in
   Basics →" at the top right of its header. That is the pattern; the
   crossing to the Wheel is the same idea in the same place, and the Wheel
   carries the matching one back. Job Three.

================================================================
*** THE ENCLOSURE — A REAL FAULT, FOUND AND FIXED (25 August 2026) ***
================================================================

WHAT HAPPENED. The Plot Mapper pocket was added, Stitch was pressed, and
the Enclosure PLACED 15 OF 16 POCKETS WITHOUT SAYING SO. The Plot Mapper
was silently skipped.

THE CAUSE. The Enclosure kept a HARD-CODED LIST of pockets, which had
never been updated to include the Plot Mapper. The corridor had the slot;
the Enclosure did not know the pocket existed.

THE MISDIAGNOSIS, WORTH RECORDING. Claude blamed the file upload first,
then GitHub's cache — twice wrong — before Kev cut through it and asked
for a plain explanation. THE IMMEDIATE FIX was to drop the Plot Mapper
into the already-stitched index.html by hand and publish, bypassing the
Enclosure. THEN the Enclosure was fixed properly.

THE FIX, AND IT IS THE IMPORTANT PART:
· THE ENCLOSURE NOW READS THE SLOTS FROM THE CORRIDOR ITSELF rather than
  from a maintained list. There is no longer a list to forget to update.
· IT REPORTS "PLACED N OF N POCKETS" AT THE END OF EVERY STITCH, so a
  silent miss is impossible.
· Tested against three deliberate scenarios before deploying: all pockets
  present, one missing, and a corridor with no slots at all.
· The Split side was left untouched.

THIS IS THE PATTERN TO COPY. When a tool can fail quietly, make it count
what it did and say so. The same thinking later produced the checker's
"Checked 47,074 words, found nothing" — because zero findings and a pass
that never ran look identical otherwise. AND ON 1 SEPTEMBER the same
thinking was turned toward the writer: an unreported save is a silent
success, and looks exactly like no save at all.
AND ON 16 SEPTEMBER THE SAME FAULT WAS FOUND IN THE CORRIDOR ITSELF —
saveProjects writing to localStorage with no check. THREE TIMES. IT IS THE
HOUSE FAULT. *** THE THIRD WAS FIXED 17 SEPTEMBER with the save guard. ***
Worth a deliberate sweep for a fourth rather than waiting to stumble on it.

================================================================
*** THE DESK — CONCEIVED AND SETTLED IN SHAPE (25 August 2026) ***
NOT BUILT. This is the fullest write-up; read it before reopening
anything about it.
================================================================

WHAT IT IS. Faders that combine to produce a version of a passage at a
chosen prose intensity, shown as A STACK OF WINDOWS, one per version, with
THE WRITER'S ORIGINAL PERMANENTLY AT THE FOOT.

THE MODEL IS A SYNTH, NOT A MIXING DESK — SETTLED BY TESTING
Tested live on a passage from Kev's story "Revenge of an Ordinary Man".
The controls GENERATE rather than balance existing material, which is
what a synth does and a mixing desk does not.
THE CONSEQUENCE THAT MATTERS: a paragraph with no dread in it is no longer
a limitation. IT IS A SOURCE WAITING FOR A SETTING. A desk can only bring
up what is already in the take; a synth makes the sound from the setting.

AND THE FINDING FROM THE TEST: RAISING INTENSITY REQUIRES COMPRESSION AND
DIRECTNESS, NOT ADDITION. Claude's early attempts were too cautious and
too wordy. One version Kev called "different", which confirmed the axis is
real.

THE ENVELOPE — THE BIT WORTH STEALING WHOLESALE
Attack, decay, sustain, release. NOT INTENSITY — SHAPE OVER TIME. A scene
where the anger arrives instantly and stays is a different scene from one
where it creeps in and gives way at the end. NO FADER ON A MIXING DESK
DOES THAT, and it is exactly what a scene needs.

THE OPEN QUESTION THE ENVELOPE RAISES, AND IT IS THE BIG ONE:
IS THE DESK ONE INSTRUMENT PER SCENE, OR IS THE WHOLE BOOK THE
INSTRUMENT? A synth patch holds across a performance. If the same settings
ran across every scene, that is not a mixing tool any more — THAT IS THE
VOICE OF THE BOOK. Where do the settings live: the scene, or the
manuscript? NOT ANSWERED.

THE LADDER, AND WHY THIS IS AN INSTRUMENT RATHER THAN A MENU
The writer's hand goes into the middle of the ladder and THE LADDER
RESHAPES TO FIT. The collaboration stops being turn-based — it is not
"Ada proposes, writer disposes". Both are working the same material, and
THE WRITER'S EDIT IS THE FIXED POINT THAT EVERYTHING ELSE MUST
ACCOMMODATE.

THE BASE MIX BUTTON
Every desk has one. PRESS AND HOLD: all faders drop, every window
collapses, and there is the original prose alone on screen. Let go and the
mix returns.
HELD, NOT TOGGLED. You GLANCE at the bare truth — you do not travel to it
and have to find your way back. The mix is where you work; your own words
are what you check yourself against.
AND THIS DOES SOMETHING PROAUTHORISM NEEDS: at any moment, one button
shows exactly how far the work has drifted. Not a warning. Just the raw
take, available whenever it is wanted.

PLUG-INS — LATER, VERSION THREE
Modules that change VOICE AND REGISTER, not intensity. Shakespeare.
Wordsworth. The angry young men. Street. Hard-boiled. Fairy tale.
· Plug-ins have THEIR OWN LEVELS, like the faders. A touch of Shakespeare
  is a cadence; all of it is pastiche.
· Plug-ins COMBINE with each other and with the faders. The useful
  settings will be a little of one under a lot of another — voices that do
  not exist as a named style because nobody has put them together.
· GENERIC AND HISTORICAL NAMES ONLY. Never a living writer. Nobody says
  JK Rowling. SETTLED AND NOT TO BE REOPENED.

THE ARCHITECTURE UNDERNEATH
Everything on the desk is HOW MUCH, and everything COMBINES. One shape
doing every job. Faders are how much of a FEELING; plug-ins are how much
of a VOICE.

--- THE PROAUTHORISM ARGUMENT — SETTLED, DO NOT RELITIGATE ---

Claude's first objection was that a fader asking Ada to rewrite a scene
darker breaks Proauthorism, because Ada would be writing prose.

THAT OBJECTION WAS WRONG AND WAS WITHDRAWN. Kev pointed out that they have
written together before — THE YULETIDE PROMISE, a full screenplay, where
Claude wrote text and Kev cut it, redirected it and threw scenes out. That
is a work with his name on it and he would defend it in a room.
PROAUTHORISM WAS NEVER "THE AI MUST NOT PRODUCE SENTENCES". It is declared
collaboration where the writer's voice stays primary.

TWO FURTHER THINGS SETTLED IT:
1. WHAT A DESK ACTUALLY DOES. It does not ask for a new take. It decides
   what you hear from the take you have.
2. THE WINDOWS. The original is always on screen, at the foot, permanent.
   The writer is choosing between VISIBLE ALTERNATIVES, not approving a
   replacement they can no longer compare against.

IF A NEW SESSION RAISES THE SAME OBJECTION, THIS IS THE ANSWER.

--- STILL OPEN ON THE DESK ---
· HOW MANY FADERS, AND WHAT ARE THEY CALLED? "Any number of faders" was
  enthusiasm. TWENTY FADERS IS A COCKPIT, AND A COCKPIT IS A SCREEN NOBODY
  OPENS. Likely four or five.
· Where the settings live: the scene, or the manuscript (the envelope
  question above).

================================================================
*** THE EVENT PLANNER / MURDER PLANNER — DESIGNED (26 August 2026) ***
NOT BUILT. NOT IN THE FLOW. An extension, reached from the right-hand
Site Map menu rather than the left working menu.
================================================================

ZERO HOUR IS THE ONE FIXED POINT — the moment the event occurs. Every
other moment is an OFFSET from it (minus forty minutes, plus two hours).

OFFSETS ARE THE TRUTH; CLOCK TIME IS A DERIVED COAT PLACED ON TOP. A real
clock time may be PINNED to zero hour and everything else derived from
it. Multiple pins are supported. THE ENGINE FLAGS CONFLICTS BETWEEN PINS
AND OFFSETS RATHER THAN SILENTLY RESOLVING THEM. Kev's own correction: a
fixed time can always be changed, and the engine adjusts everything else
accordingly.

THE BOARD BEGINS WITH TWO CHARACTERS: a victim (whose track ends at zero
hour) and a killer (whose track crosses it). More are added from the
manuscript's existing cast.

THE BOARD CARRIES PEOPLE ONLY. Locations, objects, weapons and context
live behind pop-ups drawn from the corridor's existing system — nothing
is ever entered twice.

THE VISUAL, after the first mockup was rejected as "too clunky": dark
background, hairline character tracks, slim bars for presence, labels
floating above bars, a faint gold vertical line for zero hour. A DROP LINE
falls from a top timeline THROUGH an event box reading "Bill kills Bob"
and continues down through all character tracks — the event is a single
continuous vertical axis, not a separate element.

TWO PHASES. Phase one: plan the TRUE event, what actually happened, with
no thought for the reader. Phase two: CONCEALMENT AND MISDIRECTION —
explicitly deferred.

OPEN: whether the zero hour drop line stays fixed at the centre of the
screen or moves with the timeline as the writer pans. Kev sees the board
as "more dynamic" than static draggable bars, so the interaction model is
still open. HOW IT REACHES THE MAIN WORK SCREEN IS DELIBERATELY PARKED —
Kev: "until we get more of the platform built I can't tell you how it will
all eventually hang together."

================================================================
*** THE MYSTERY PLOTTER — "WHO WAS WHERE" · GRID BUILT (25 August) ***
Working file: code-mystery-grid.html. NEVER REVIEWED.
================================================================

THE INSIGHT IT TURNS ON. A mystery has TWO TIMELINES, and every good one
is the friction between them.
· THE TRUTH — what actually happened, in order, from the killer's point
  of view.
· WHAT THE READER IS SHOWN — a different order, with pieces missing.
THE WRITER HOLDS BOTH IN THEIR HEAD AT ONCE, AND THAT IS THE GENUINELY
HARD PART. Not the murder. THE DOUBLE BOOKKEEPING. So the tool holds both
and shows where they contradict each other.

THE TRUTH TIMELINE. Who was where, when, and who saw whom. NOT METHOD —
positions and knowledge. A grid: people down one side, time across the
top. THIS IS THE PART THAT WAS BUILT.

THE SHOWN TIMELINE. The order the reader meets things in, chapter by
chapter. Because it comes from the same store, the tool knows the truth
behind every revelation. NOT BUILT.

WHAT IT TELLS YOU — the point of the whole thing:
· Which characters were unaccounted for at the time of death? THAT IS
  YOUR SUSPECT POOL, AND IT IS ARITHMETIC, NOT INTUITION.
· This alibi depends on Character B — and B is lying about something else.
  Does that hold?
· Nobody could have known about the letter by Chapter 9, but the detective
  refers to it in Chapter 8.
· Three suspects have alibis that all rest on the same witness.
· THE READER HAS EVERYTHING THEY NEED BY CHAPTER 12 AND THE REVEAL ISN'T
  UNTIL 20. That last one is the whole game. Fair play means the reader
  COULD have solved it. Too early and it is obvious; too late and it is a
  cheat. Nothing else tells a writer where that line is — they find out
  from a review.
NOTE 17 SEPTEMBER: "WHO KNOWS ABOUT A THING, AND FROM WHEN" is now a
field in factual-layer.md, on Relationships and on Events. It is the same
fact the mystery plotter's third question turns on. TWO TOOLS, ONE FACT.

WHERE IT LIVES. Not a new store. Characters, Locations and Events are
already there. This is a screen that READS THEM AND CROSS-REFERENCES.
That is what makes it a plug-in rather than a new platform.

WHAT IT NEVER HOLDS — AND THIS IS A LINE, NOT A LIMITATION.
METHOD. It does not care how anyone died, only who was where and who knew
what. Claude drew the distinction explicitly: a PUZZLE-CONSTRUCTION TOOL,
never a how-to-commit-a-murder tool. Realistic method is not what makes a
mystery good — Christie's murders are mostly implausible; what works is
THE STRUCTURE OF THE CONCEALMENT, not the chemistry. THE CONSTRAINT IS
WHAT KEEPS IT A PLOTTING TOOL RATHER THAN A MANUAL.

TIME ACROSS THE TOP IS CLOCK TIME, and Claude chose it rather than scenes
because it is the one that produces real answers — "who has no alibi at
9pm" is arithmetic. THE COLUMN HEADINGS ARE TYPEABLE, so a writer who
prefers "After dinner" to "9pm" can have it.

IT WAS BUILT ON A DAY KEV WAS UNWELL (a horsefly bite and a hospital
visit) and asked for it anyway — "yes TODAY as I am going mad with
bordom". It has not been looked at since.

RELATIONSHIP TO THE EVENT PLANNER, WHICH CAME THE NEXT DAY: they are two
approaches to the same problem and were designed a day apart. The Event
Planner's zero-hour offsets are a sharper model of the same truth
timeline. LOOK AT BOTH TOGETHER BEFORE BUILDING MORE ON EITHER — they may
be one tool.

================================================================
*** THE FLOW REVIEW (31 August 2026) — AND A CORRECTION ***
================================================================

KEV'S FLOW, IN HIS OWN ORDER:
  1. Basics (reached through New / Load Project)
  2. Plot Mapper
  3. Wheel / Manuscript
  4. Publishing preparation (Platform/KDP · Book size · Page layout ·
     Cover creator)
  5. Publish

THE ONE CAVEAT HE ADDED, AND IT MATTERS: the writer must be able to move
BACK AND FORTH between the Plot Mapper and the Wheel. Basics and
Publishing are one-way gates at either end; THE PLOT MAPPER AND THE WHEEL
ARE A PAIR.

WHERE THE FLOW STANDS AT 17 SEPTEMBER:
  1. BASICS — live, points forward, saves honestly, boxes line up.
  2. PLOT MAPPER — live, and it saves. Holds one real book.
  3. WHEEL / MANUSCRIPT — still not in the platform. Read and assessed
     1 September; the conversion is BEHIND THE LIBRARY AND THE CHECK.
  4. PUBLISHING PREPARATION — Coming Soon, none of the four built.
  5. PUBLISH — Coming Soon.

THE WORLD-BUILDING SCREENS ARE NOT MISSING FROM THE FLOW. They are
pockets used when needed, and the Wheel carries them in its side menu.
Claude raised this as a gap and was wrong.

A CORRECTION WORTH KEEPING. Claude read chapters.html and treatment.html
being stitched into index.html with no menu item as a REACHABILITY FAULT,
and proposed a check to catch orphaned screens. IT WAS DELIBERATE — the
11 August sidebar rebuild dropped them on purpose, left the pockets in the
repo, and guarded showScreen so the removed nav ids no longer throw. Kev
said plainly "I don't think anything is unreachable" and he was right.
ABSENCE WAS READ AS ACCIDENT. If a reachability check is ever built it
must know the difference between an orphan and a deliberate removal.

CLAUDE ALSO DIAGNOSED THE MENU TWICE FROM SCREENSHOTS AND WAS WRONG BOTH
TIMES, because the screenshots were of two different screens and neither
was the source. THE FILE IS THE TRUTH. And index.html is the OUTPUT —
corridor.html is where the menu lives and where a menu fix belongs.

A THIRD CORRECTION, 16 SEPTEMBER, THE SAME FAULT AGAIN. Claude stated
that the Cast and World screens had not been brought across into the
rebuild and that an import would have nowhere to land. WRONG. Characters
is a real, working screen with a list, an + Add button and a record in it;
so are Relationships, Factions, Language, Locations, Buildings, Objects
and Rules & Lore. All sixteen pockets are in the repository and stitched.
CLAUDE ASSERTED THE STATE OF THE PLATFORM FROM MEMORY INSTEAD OF ASKING
FOR ONE CLICK. The one click settled it in seconds.

================================================================
*** BASICS (OVERVIEW) — GENRE RANGES, THE THREE GUIDES, AND NOW THE
*** WAY FORWARD · LIVE
Published 12 August 2026. Foot rebuilt 1 September 2026. Saved line made
honest and paired boxes aligned 17 September 2026.
File: pockets/project-overview.html
================================================================

THE SAVE ROW LIVES IN THE POCKET, NOT THE CORRIDOR. Established
1 September by reading both files. The corridor holds only the slot and
the shared functions the buttons call — autoSave, saveProjectHeader,
showScreen, getProjects/saveProjects. It looks from the outside as though
the corridor owns this screen, because autoSave reaches into it by element
name (ph-format, ph-audience, ph-outline and the hidden stubs). It does
not. SO THE FOOT WAS A ONE-FILE CHANGE with no corridor edit.

--- THE FOOT OF THE SCREEN, REBUILT 1 SEPTEMBER ---

IT USED TO BE A DEAD END. "Save Overview", "Back to Projects", and a tick.
Pressing Save flashed the tick and left you sitting there. Nothing pointed
forward, so the writer's journey stopped at step one.

IT IS NOW THREE BUTTONS OF ONE FIXED WIDTH:
  SAVE · PLOT MAPPER → · BACK TO PROJECTS
All three always present, all three saving. The middle one goes forward;
the third goes back; the first stays.

THE WORDING WAS DECIDED BY THE WIDTH, NOT THE OTHER WAY ROUND. Kev: "I am
finding it hard to reconcile three buttons of different sizes." Three
buttons at the width of "Save and go to the Plot Mapper" will not fit an
800px column — it comes to well over a thousand pixels with the gaps. So
the wording came down to fit the set. THE ARROW MATCHES "Edit in Basics →"
already on the Plot Mapper's header, which is the crossing Job Three will
build in both directions — one shape, learned once.

FIRST VISIT ONLY, the Plot Mapper button is the filled one so a new
writer's eye lands on the way forward; afterwards both sit outlined as
equals. A project has been to the Plot Mapper if it carries a plotMapper
record. NO NEW FLAG WAS ADDED. Only the fill changes — nothing appears or
disappears, because a control that quietly behaves differently on hidden
state is what makes a platform feel unpredictable.
OPEN: whether "equal" should mean both outlined (as built) or both filled.
Two solid gold buttons side by side was judged loud. Not ruled on.

--- THE STANDING SAVED LINE ---

THE SCREEN HAD BEEN SAVING ON EVERY KEYSTROKE SINCE 12 AUGUST AND HAD
NEVER SAID SO. The flashing tick was the cause, not the cure — appearing
only when Save was pressed, it implied the other buttons did not save.
SINCE 1 SEPTEMBER: Back to Projects saves before it leaves, and a standing
line beneath the row reads "Saved · 14:32" in gold, present all the time.
SINCE 17 SEPTEMBER: IT REPORTS SUCCESS, NOT ATTEMPT. It reads the save
guard's flag first; on a failed save it reads "NOT SAVED — see the
warning at the top of the screen" in the danger red and claims no time.
The uncomfortable note of 16 September — that the line could lie — IS
CLOSED.

--- PAIRED BOXES LINE UP — 17 SEPTEMBER ---

Author and Status, and Start Date and Classification, now sit level. Each
half of a field-row is a column with its box pushed to the foot, so a
taller label above one of them cannot drag it out of line. Found by Kev
on the live screen. See THE SILENT SAVE section for the full account.

--- THE REST OF THE SCREEN, UNCHANGED ---

THE GENRE DROPDOWN carries each format's INDUSTRY WORD-COUNT RANGE,
labelled "TYPICAL LENGTH:" in small mono caps with the figure in gold. The
chosen range stays visible in the closed field. The writer sees what they
are signing up for AT THE MOMENT OF CHOOSING. Formats that need page
layout not yet built are greyed, with a hover note saying so.

Every genre carries THREE things: its range (wc), its words-per-chapter
(per), and ITS OWN SENTENCE WORDING (says) — so the steer reads "Most
adventures land…", "Most memoirs land…" and is never grammatically wrong.
Roughly forty entries. PAGES ARE NOT USED — "there are so many page
sizes."

THE WORD COUNT SECTION is THREE LINKED GUIDES: Words (a range), Chapters
(a range), Words per chapter. All drawn from the genre, all editable, all
gold while they are the platform's suggestion, with a ↺ to restore. CHANGE
ONE AND THE OTHERS FOLLOW. Beneath them one italic line: "Most adventures
land somewhere in this range — it's a guide, not a rule." LAND was chosen
deliberately: where books tend to end up, not where this one must.

RANGES THROUGHOUT — never a single target. The Plot Mapper's budget
divides the book's range across the chapters to give each its own range.

CURRENT AND REMAINING WERE REMOVED but survive as HIDDEN STUBS because the
corridor's autoSave still refers to them by name (as do ph-format,
ph-audience, ph-outline). THIS CAUSED A REAL BUG: autoSave stops dead at
the first missing element, silently preventing the steer sentence
updating. The pocket now updates its own display BEFORE calling autoSave,
and wraps corridor calls in try/catch.

WHERE THE DATA LIVES: wordRange, chapterRange, perChapter and guidesEdited
on the project in localStorage "is-projects"; window.IS_GENRE_WC and
window.IS_GENRE_INFO exposed for other screens.

NEW PROJECT POP-UP: Title and Author only. Genre removed — it duplicated
the proper dropdown and taught the writer nothing.

STILL ODD, AND NOTED: the screen's own title reads "Overview" while the
sidebar calls it Basics. Two names for one screen, live today. Part of the
unresolved Basics / Overview / Front Matter question — but the MISMATCH
is separate from the naming question: whatever it is called, it should be
called one thing. A SMALL FIX WORTH DOING.

================================================================
*** THE SIDEBAR — LIVE (11 August 2026) ***
File: corridor.html. Confirmed against the live file 17 September.
================================================================

AS BUILT IN THE LIVE CORRIDOR:
  NAVIGATE  My Projects · The Press
  PROJECT   Basics, then
    STORY    Plot Threads · Subplots · Themes & Motifs · Events & Timeline
    PEOPLE   Characters · Relationships · Factions & Orgs · Language &
             Dialogue
    WORLD    Locations · Buildings · Objects & Artefacts · Rules & Lore
    LIBRARY  Research & Reference · Notes · Images · Sandbox
    DCW      Plot Mapper · Manuscript · Publish
  HELP      Tutorial · Manual · FAQs · What's New
  TRASH

ELEVEN ITEMS POINT AT COMING SOON: The Press, Research & Reference, Notes,
Images, Sandbox, Manuscript, Publish, and the four Help items.

THE DUPLICATE "PLOT MAPPING" UNDER NAVIGATE WAS DELETED on 1 September.
CLOSED.

FOR JOB TWO, TWO CORRIDOR CHANGES ARE NEEDED AND NO MORE: nav-manuscript
currently calls showScreen('coming-soon','Manuscript') and must point at
the new pocket, and THERE IS NO POCKET:manuscript SLOT — one must be
added. Both confirmed by reading the live file.
AND FOR THE LIBRARY, THE SAME TWO: nav-research must point at a new
pocket, and a POCKET:research slot must be added.

SYNOPSIS HAS GONE FROM STORY (15 August) — it was this screen under
another name, and it is now DCW > Plot Mapper.

CHAPTERS AND THE TREATMENT were dropped from the sidebar DELIBERATELY.
Their pockets remain in the repo untouched; only the way in has gone.
showScreen was guarded so the removed nav ids no longer throw.

"BASICS" vs "OVERVIEW" IS UNRESOLVED. FRONT MATTER is the genuinely
literary option. LEFT AS BASICS DELIBERATELY, to be settled in the theatre
pass.

SANDBOX should move from Library to DCW. Not yet done. ONE LINE.
GROUP HEADINGS SHOULD BECOME LIVE ROOMS. Five to build. Not started.

================================================================
*** THE REPOSITORY, AS IT STANDS ***
================================================================
PitchDarkPress/inkyswot-rebuild (private):
  corridor.html · index.html (the stitched output) · README.md
  pockets/ — buildings · cast · chapters · events · factions · language ·
    locations · objects · plot-mapper · plotthreads · project-overview ·
    relationships · rules · subplots · themes · treatment
  test/
INDEX.HTML IS THE OUTPUT, NOT A SOURCE. Never edit it as though it were.
NO manuscript POCKET YET. NO research POCKET YET.
LAST STITCH, 17 SEPTEMBER: corridor.html 147,527 characters, index.html
347,456 characters, 16 of 16 pockets placed.

THE CORRIDOR'S SCRIPT NOW ENDS WITH THREE BOLTED-ON BLOCKS, in this
order: SPELL CHECK, READ ALOUD, THE SAVE GUARD. Each is self-contained and
each reaches back to improve something already in the file. THAT IS THE
CORRIDOR'S PATTERN FOR A SMALL, SAFE CHANGE, and it is the right route
whenever a whole-file rewrite of the corridor would be riskier than the
fault being fixed.

================================================================
*** SPELL CHECK — FIXED PLATFORM-WIDE · LIVE (11 August 2026) ***
================================================================

enableSpellCheck ran once on load and missed any field created later.
Rewritten to use the SAME MUTATIONOBSERVER PATTERN the Read-aloud block
already used, catching input[type="text"] and textarea whenever they
appear, marking each data-spellReady="1".

NOTE: this catches inputs and textareas. The Plot Mapper uses
contenteditable divs, which the selector does NOT cover — they set
spellcheck themselves. If a future screen uses contenteditable, widen the
corridor selector. THE WHEEL'S WRITING AREA IS A TEXTAREA, so it is
covered as things stand.

*** THE GRAMMARLY TRAP — READ BEFORE CHASING A SPELL-CHECK FAULT ***
Testing took an hour longer than it should because Grammarly was masking
the browser's own red underlines with its own. It had to be REMOVED AND
THE PC RESTARTED — closing the tab was not enough. Chrome's own
spell-check must also be on: chrome://settings/languages, BASIC (not
Enhanced — Enhanced sends typed text to Google), English (United Kingdom)
ticked. Grammarly often turns Chrome's spell-check off when it installs
and does not turn it back on when removed.

*** ENCLOSURE WARNING ***
NEVER press "ADD SPELL CHECK TO CORRIDOR". That button still sits in the
Enclosure below Publish. It was how the original code was installed, and
pressing it now would push an OLDER version back into the corridor,
undoing this fix — AND, SINCE 17 SEPTEMBER, POSSIBLY TAKING THE SAVE
GUARD WITH IT.

*** THE PUBLISHING RULE ***
WAIT A FULL MINUTE between Stitch and Publish. Publishing twenty seconds
after Stitch reads the PREVIOUS index.html and silently deploys stale
code. Stitch's character count and Publish's character count MUST MATCH
before a hard refresh is trusted. HELD TO TWICE ON 17 SEPTEMBER: 345,951
and 347,456, both matching.

================================================================
*** THE THREE BIG IDEAS — PARKED, NOT ABANDONED ***
A FOURTH now joins them, and it is closer to the others than it looks —
see the checker above and the continuity library in future.md. A project
that knows its own proper nouns serves the spell checker, the language
creator, the continuity guard AND the checker's learning list alike.
FOUR FEATURES, ONE WELL.
AND A FIFTH ROAD TO THE SAME WELL, 16 SEPTEMBER: THE IMPORT. A book read
for its characters and locations is a project's proper nouns arriving in
one go. NOTE 17 SEPTEMBER: THE FACTUAL LAYER'S CANONICAL NAME FIELD IS
THE WELL, WRITTEN DOWN. One spelling per character, per place.
================================================================

1. INKYSWOT'S OWN SPELL CHECKER
Browser spell-check can only be reached by right-clicking exactly on the
underlined word — no suggestion panel, because a page can see a word is
marked but cannot read Chrome's suggestions or open its menu. And the
dictionary belongs to the browser, not the book: every character name is
flagged forever. For a dyslexic writer, constant false flags on your own
proper nouns train you to ignore the underlines entirely.

OURS: a personal dictionary that lives WITH THE PROJECT. A free British
English word list plus Typo.js for suggestions.
NOTE (28 August): THE HARD PART IS NOW SOLVED. The overlay technique
described here has been superseded by the CSS Custom Highlight API, built
and working in the checker. Nothing is inserted into the text. The
click-to-correct panel is built. THE SPELL CHECKER IS NOW MOSTLY THE
DICTIONARY PLUS WORK ALREADY DONE.

2. THE LANGUAGE CREATOR
A language that HOLDS UP UNDER SCRUTINY: consistent sounds, plausible
names, a few dozen recurring words, a grammar that never contradicts
itself. An afternoon, if the tool is right. The writer chooses a character
for the tongue; the tool fixes an alphabet and rules about which sounds
may sit together, then generates place names, personal names and words for
the twenty things every invented culture needs. All obeying the same
rules, so IT SOUNDS LIKE ONE LANGUAGE. Everything lands in a LEXICON.
AND THE JOIN: THE LEXICON IS THE PERSONAL DICTIONARY.

3. INVENTED SPEECH IN THE MANUSCRIPT — THE FOOTNOTE MECHANISM
The writer types the line IN PLAIN ENGLISH, highlights it, marks it as
that language. The manuscript shows the invented tongue and THE ENGLISH
DROPS TO A FOOTNOTE.
· THE ENGLISH IS THE MASTER. Revise it and the invented version
  regenerates.
· IT CAN BE SWITCHED OFF at any point.
· IT NEEDS GRAMMAR, NOT JUST WORDS. Word order, plurals and tenses must
  be fixed when the language is made.
WHY FOOTNOTES: subtitles work because they are in the same frame; a
glossary at the back asks the reader to leave the book. Readers have known
the convention for four hundred years. In a digital edition it becomes
tap-to-reveal.

4. THE BUSINESS THOUGHT — LANGUAGE PACKS
Build the engine once, sell the languages forever.

================================================================
*** THE LIBRARY — THE SHAPE IS NOW DECIDED (16–17 September 2026) ***
================================================================

*** IT IS SERVER-SIDE, AND IT IS THE ONLY THING THAT IS. Decided
16 September; scope fixed 17 September. See the Supabase section. Kev:
"Two books is going to be too limiting. When we talk about a library it
has to be just that." And: "we move as little as possible." ***

THE SHELF'S SHAPE IS NOT DECIDED. Claude has proposed one — see the
Supabase section — but Kev: "I have no idea how things will work on
Supabase and until then I can't nail things down."

AND IT IS WHERE THE IMPORT LIVES — Kev's reasoning, and it is the right
one: the shelf will hold more than his own previous books, and the moment
it does, it is a reference collection.

SETTLED PREVIOUSLY, AND UNCHANGED: folders are FIXED and
platform-provided, NO "NEW FOLDER" BUTTON — the writer never makes a
filing decision, so there is nothing to tidy. Sub-folders mirror the
sidebar sections. An entry is filed in a sub-folder AND may optionally
NAME the location or character it is about, so it appears on that record's
screen too. Sandbox is not Library.

THE ROOM DESIGN FROM REBUILD-5, DRAWN AND AGREED BUT NEVER BUILT: click
Library and the room shows three rows — Research & Reference, Notes,
Images — each with an arrow running rightwards to its folders, and those
folders opening in turn. Not a tree down the left with a panel beside it.
A ROW PER SECTION, GROWING RIGHTWARDS.

REJECTED: shelves of book spines; a filing drawer of hanging files; a tree
of coloured pills. Then a folder icon and a stack of three folders seen
front-on. Then: "forget it and we will just carry on."

THE INSIGHT WORTH KEEPING is Kev's own: "Damn we already have it." Every
screen is already list-on-the-left, detail-on-the-right. Never followed to
its end, and it should be.

THE OLD RESEARCH & REFERENCE SCREEN, FOR THE RECORD. It was built in the
old single-file index.html — list on the left, a form on the right with
Title and Type, web search attached. THAT BUILD IS THE ONE THE REBUILD
REPLACED. There is no pockets/research.html. The nav item points at Coming
Soon. THIS IS A NEW POCKET FROM SCRATCH, NOT A REPAIR.

THE CONTINUITY LIBRARY belongs here. NOTE 17 SEPTEMBER: IT IS NOW BEING
BUILT — it is what the import became once it was reshaped into a check.

THE IMAGES ROOM HAS A NEW REASON TO EXIST. On the evening of 16 September
Kev returned to the illustration library — chapter initials and
ornaments — and took it further. See future.md. The file store will hold
the images, so the room is no longer blocked on where they would live.

================================================================
*** THE THEATRE PASS — DEFERRED DELIBERATELY ***
================================================================
"We are going to do a theatre pass at the end so we can mess about with
syntax then." Nothing decorative should be built before it.
THE BEST SINGLE MOMENT FOR THEATRE IS A BREAK ARRIVING IN THE PLOT
MAPPER — the rule drawing itself across, the prose settling into its new
place. One well-made moment there beats a dozen small flourishes.
GOLD MARKS ANYTHING ALIVE AND RESPONDING. NEVER DECORATIVE.

================================================================
*** CONCEPTS — BUILT & WORKING (14 July 2026) ***
Working file: concepts-canvas.html.
================================================================

CONCEPTS — a writer's private store for FUTURE-story ideas, separate from
any one project, living ON THE MY PROJECTS SCREEN. A concept is a
pre-project.

THREE STAGES: GENRE FOLDER → STORY TITLE → MAIN STORY CARD (a canvas). No
more levels. Genre folders named from the real GENRE LIST, made via a
+ FOLDER button bottom-right. Story sub-folders open OUT TO THE SIDE on a
dotted connector. Story titles are PLAIN BARS.

THE MAIN STORY CARD IS A RESIZABLE CANVAS holding small header-band idea
cards. ADD IDEA opens a GROUPED DROPDOWN of the platform's real side-menu
list; a card drops onto the canvas, named and COLOURED BY FAMILY. Because
these are the platform's REAL categories, a card jotted in a Concept LATER
INTEGRATES into the main platform.

GENRE FOLDER COLOUR: a repeating palette of the six track colours,
changeable per folder.

STILL TO DO: the story-naming step; wire Prompt/Expand; PERSIST
everything; a gold-rendering niggle unresolved.

OUTSTANDING SINCE 13 AUGUST: Concepts still uses the OLD Cast / World /
Plot grouping. Bring it into line with the sixteen sections when next
touched.

================================================================
*** MY PROJECTS CARD — STATIC STILL AGREED (1 September 2026) ***
NOT BUILT INTO THE LIVE SCREEN.
================================================================
Three underlined link-style doors at the foot of every card — BASICS ·
PLOT MAPPER · MANUSCRIPT. A bin icon in the top corner replacing the old
Trash pill. Cards of equal height with the strap line as the flexible row.
STEEL BLUE #7a9bd0 as the hover colour on active doors.

================================================================
*** HOUSE STYLE — LOCKED ***
================================================================
#0a0806 near-black · #0f0d0a background · #c9923a gold · #e8b060 bright
gold. Crimson Pro (body) · JetBrains Mono (labels and interface) ·
Playfair Display (wordmark and titles). Muted danger red #c43a2a for
overruns and warnings — THEY INFORM, THEY NEVER BLOCK THE WRITER.
Light/dark toggle platform-wide.
GOLD MARKS ANYTHING ALIVE AND RESPONDING. NEVER DECORATIVE.
Track colour families: People #cf7f57 · World #5fa898 · Story #c9923a ·
Library #9a8f72.
Steel blue #7a9bd0 — hover on the My Projects card doors (1 September).

FROM 15 AUGUST:
- A CONTROL THAT CHANGES ITS WORDING MUST NOT CHANGE ITS SIZE.
- A CONTROL'S SIZE MUST NOT DEPEND ON WHAT IS BESIDE IT.
- OPENING SOMETHING MUST NOT PUSH WHAT IS ABOVE IT.
- MARKS ARE DASHED LINES BENEATH, NEVER TINTED WORDS.
- EVERY SCREEN CARRIES A "SECTION ?" PILL at the TOP RIGHT.
THE CORRIDOR HAS STILL NOT BEEN SWEPT for the sizing rules.

FROM 28 AUGUST (from the checker):
- A TEST OR DIAGNOSTIC PAGE CARRIES A BUILD STAMP IN ITS TOP CORNER.
- A DIAGNOSTIC PAGE SHOWS THE ENGINE'S OWN WORKINGS, never its own
  calculation of what it thinks the engine did.
- A PROGRESS BAR IS HELD BACK a quarter of a second and only shown if the
  work is still running.

FROM 1 SEPTEMBER (from the Basics foot):
- A ROW OF CONTROLS DOING THE SAME KIND OF JOB IS ONE SIZE THROUGHOUT,
  sized to the longest — AND THE WIDTH DECIDES THE WORDING.
- A SAVE THAT HAPPENS CONTINUOUSLY MUST BE REPORTED CONTINUOUSLY. A
  confirmation that only appears on a button press teaches the writer that
  the other buttons do not save.
- EVERY DOOR OFF A SCREEN SAVES BEFORE IT OPENS, backwards as well as
  forwards.

FROM 16 SEPTEMBER:
- A SAVE IS ONLY REPORTED WHEN IT HAS ACTUALLY SUCCEEDED. Reporting an
  attempt is worse than reporting nothing, because the writer then trusts
  it. Wrapping a save in nothing and announcing it is how a platform lies.
  BUILT 17 SEPTEMBER.
- NOTHING THE PLATFORM FINDS LANDS IN THE WRITER'S WORK UNTIL THE WRITER
  HAS SEEN IT AND SAID SO. The muster, not the silent fill.

FROM 17 SEPTEMBER:
- TWO BOXES SIDE BY SIDE LINE UP, WHATEVER THEIR LABELS DO. The box is
  what the eye follows, so the box wins. Each half of a row is a column
  with its box pushed to the foot.
- A FAILURE WARNING IS LOUD, STANDING, AND NEVER BLOCKS. A red bar
  across the top that stays until the fault clears, and the writer can go
  on working beneath it. (As built in the save guard — the existing
  "inform, never block" rule applied.)

================================================================
*** SUGGESTED ORDER OF WORK — REORDERED 17 SEPTEMBER ***
Proposed, not ruled. USE WINS OVER THIS LIST WHEREVER THEY DISAGREE.
================================================================
DONE 17 SEPTEMBER: THE SILENT SAVE. The save guard in the corridor and
the honest saved line on Basics, both live.

0. *** THE SHELF. *** Supabase, THE LIBRARY ALONE (Kev's decision).
   ITS SHAPE IS NOT DECIDED — build something small, see how Supabase
   actually behaves, and decide from that. INFRASTRUCTURE, NOT A POCKET.
1. THE LIBRARY ROOM AND THE WAY IN — pockets/research.html, a corridor
   slot, nav-research repointed. A file picker, plain text first.
2. THE CHAPTER SPLIT — find the headings. CHECK FIRST whether the
   checker's parser (stage 3, which already classifies chapter titles)
   does most of it already.
3. *** THE FACTUAL LAYER ON THE CARDS. *** Moved up from seventh: the
   check cannot work without it. THREE QUESTIONS IN factual-layer.md
   WAIT FOR KEV FIRST — the Notes field, which wins when facts and prose
   disagree, and how many fields show at once.
4. THE READ, THE MUSTER AND THE LANDING — book one into the cards, once.
5. THE CHECK — book two tested against the cards, pinging with the
   chapter reference.
6. JOB TWO — THE WHEEL INTO THE PLATFORM. Settle the writing surface
   during the conversion: both the checker and the continuity check want
   painted marks, and a textarea cannot take them.
7. JOB THREE — THE CROSSING, both ways.
8. STEP TWO OF THE PLOT MAPPER — the cards writing into the shared store,
   and the vanishing tints with it. Note that items 3 to 5 approach the
   same store from the other end.
9. Ada's buttons on the Plot Mapper.
10. THE CHECKER — the queries, the learning list, spelling, into the
    platform.
11. The Library rooms, the five group headings, and the theatre pass.
12. THE CONDENSING PASS on these files. Its own session.

SMALL NIGGLES, TO DO WHEN THE CORRIDOR OR THE POCKET IS NEXT OPEN:
the Basics / Overview title mismatch; Sandbox moving to DCW; both-outlined
or both-filled on the Basics foot.

Kev's own words, still true: "We will have to make and remake this page
until it is right." Expect several passes. That is the plan, not a failure
of it.

AND KEV'S ONE FROM 16 SEPTEMBER, WHICH CHANGED THE DIRECTION OF THE
WHOLE PROJECT: "we are building something based on theory. I think that
now is the time to start using it and see where that takes the build."
THE BUILD LIST NOW COMES FROM USE, NOT FROM THIS FILE. Where the two
disagree, USE WINS. IT WAS TESTED FOR THE FIRST TIME ON 17 SEPTEMBER —
the box alignment came from Kev looking at the screen, not from any list.

AND KEV'S ONE FROM 17 SEPTEMBER, WHICH IS THE SAME THOUGHT FROM THE OTHER
SIDE: "we can't really progress the platform until we can start adding my
work to a database." THE NIGGLES ARE COSMETIC; THE STORE IS WHAT
EVERYTHING ELSE WAITS ON.