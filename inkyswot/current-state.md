File: inkyswot/current-state.md
Last updated: 31 August 2026 — rewritten WHOLE.

THE GAP THAT PROMPTED THIS REWRITE. All five database files were last
written on 15 August. Between then and 31 August a fortnight of work
happened that never reached them, including the Plot Mapper going LIVE
and a real fault in the Enclosure. The gap was found when the database
was read against the repository and the two disagreed. It has been
filled from the session record. Kev, honestly: "I have been slack on
updating these files and have now been caught out."

THE RULE THAT COMES OUT OF IT IS NOW LOCKED — UPDATE THE DATABASE AT THE
END OF EVERY SESSION. See locked-decisions.md.

================================================================
*** SESSION-END REMINDER — READ THIS FIRST, EVERY SESSION ***
================================================================

BEFORE A SESSION CLOSES, THESE FILES ARE BROUGHT CURRENT. Not "when
there is time". Not "next session". At the end of the session that did
the work, while the reasoning is still in the room.

WHAT GETS WRITTEN:
  · current-state.md   what is built, what is live, what is still to do
  · locked-decisions.md anything settled, with its date
  · completed.md        one line per milestone, dated
  · thinking.md         what is still open
  · future.md           anything conceived but not started

WHY IT MATTERS MORE HERE THAN ON MOST PROJECTS. The code survives on
disk; the REASONING does not. A repository shows WHAT was built. Only
these files show WHY, what was tried and rejected, and what the trap was.
When 15–31 August went unrecorded, the code was still there — the two
weeks of decisions behind it were nearly lost, and were only recovered
because the session record could be searched.

IF A SESSION ENDS ABRUPTLY, the next one begins by writing up the last.

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
   Step two, and the real work.
3. Ada's buttons.

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
that never ran look identical otherwise.

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

================================================================
*** BASICS (OVERVIEW) — GENRE RANGES & THE THREE GUIDES · LIVE ***
Published 12 August 2026. File: pockets/project-overview.html
================================================================

THE GENRE DROPDOWN carries each format's INDUSTRY WORD-COUNT RANGE,
labelled "TYPICAL LENGTH:" in small mono caps with the figure in gold. The
chosen range stays visible in the closed field. The writer sees what they
are signing up for AT THE MOMENT OF CHOOSING.

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

================================================================
*** THE SIDEBAR — LIVE (11 August 2026) ***
File: corridor.html
================================================================

AS BUILT IN THE LIVE CORRIDOR:
  NAVIGATE  My Projects · The Press · Plot Mapping
  PROJECT   Basics, then
    STORY    Plot Threads · Subplots · Themes & Motifs · Events & Timeline
    PEOPLE   Characters · Relationships · Factions & Orgs · Language &
             Dialogue
    WORLD    Locations · Buildings · Objects & Artefacts · Rules & Lore
    LIBRARY  Research & Reference · Notes · Images · Sandbox
    DCW      Plot Mapper · Manuscript · Publish
  HELP      Tutorial · Manual · FAQs · What's New
  TRASH

TWELVE ITEMS POINT AT COMING SOON: The Press, Plot Mapping, Research &
Reference, Notes, Images, Sandbox, Manuscript, Publish, and the four Help
items.

NOTE — "PLOT MAPPING" UNDER NAVIGATE IS A DEAD END while the real Plot
Mapper is live under DCW. Two items, similar names, one working. A writer
would try the more prominent one first. WORTH RESOLVING.

SYNOPSIS HAS GONE FROM STORY (15 August) — it was this screen under
another name, and it is now DCW > Plot Mapper.

CHAPTERS AND THE TREATMENT were dropped from the sidebar DELIBERATELY.
Their pockets remain in the repo untouched; only the way in has gone.
showScreen was guarded so the removed nav ids no longer throw.

"BASICS" vs "OVERVIEW" IS UNRESOLVED. FRONT MATTER is the genuinely
literary option. LEFT AS BASICS DELIBERATELY, to be settled in the theatre
pass.

SANDBOX should move from Library to DCW. Not yet done.
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
corridor selector.

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
undoing this fix.

*** THE PUBLISHING RULE ***
WAIT A FULL MINUTE between Stitch and Publish. Publishing twenty seconds
after Stitch reads the PREVIOUS index.html and silently deploys stale
code. Stitch's character count and Publish's character count MUST MATCH
before a hard refresh is trusted.

================================================================
*** THE THREE BIG IDEAS — PARKED, NOT ABANDONED ***
A FOURTH now joins them, and it is closer to the others than it looks —
see the checker above and the continuity library in future.md. A project
that knows its own proper nouns serves the spell checker, the language
creator, the continuity guard AND the checker's learning list alike.
FOUR FEATURES, ONE WELL.
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
*** THE LIBRARY — DESIGNED, UNRESOLVED ***
================================================================

SETTLED: folders are FIXED and platform-provided, NO "NEW FOLDER" BUTTON —
the writer never makes a filing decision, so there is nothing to tidy.
Sub-folders mirror the sidebar sections. An entry is filed in a sub-folder
AND may optionally NAME the location or character it is about, so it
appears on that record's screen too. Sandbox is not Library.

REJECTED: shelves of book spines; a filing drawer of hanging files; a tree
of coloured pills. Then a folder icon and a stack of three folders seen
front-on. Then: "forget it and we will just carry on."

THE INSIGHT WORTH KEEPING is Kev's own: "Damn we already have it." Every
screen is already list-on-the-left, detail-on-the-right. Never followed to
its end, and it should be.

THE CONTINUITY LIBRARY belongs here when built. NOTE (31 August): Kev
arrived at the same idea again from a different direction — see thinking.md.

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

================================================================
*** SUGGESTED ORDER OF WORK ***
================================================================
1. THE CORRIDOR. It is the source of the menu and has not been in hand
   since 11 August. Settle the Plot Mapping dead end, and do the sizing
   sweep while it is open.
2. STEP TWO OF THE PLOT MAPPER — the cards writing into the same store
   Characters, Locations and the rest read from. THE REAL WORK, and the
   continuity library depends on it. SOLVE THE VANISHING TINTS AS PART OF
   IT, not after.
3. Ada's buttons on the Plot Mapper.
4. THE CHECKER — the queries, then the learning list, then spelling, then
   into the platform.
5. THE CARDS — the factual layer under the prose fields (see thinking.md).
6. Then the Library, the five rooms, and the theatre pass.

Kev's own words, still true: "We will have to make and remake this page
until it is right." Expect several passes. That is the plan, not a failure
of it.