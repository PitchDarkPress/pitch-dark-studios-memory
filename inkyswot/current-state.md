File: inkyswot/current-state.md

================================================================
*** THE PLOT MAPPER — WHAT WAS THE SYNOPSIS SCREEN (15 August 2026) ***
Working file: code-plot-mapper-10.html (standalone, not yet a pocket).
This SUPERSEDES the old Synopsis block and the "which plot mapper"
open decision, both of which have been removed from this file.
================================================================

*** THE DECISION OF THE SESSION ***

THE SYNOPSIS SCREEN IS NOW THE PLOT MAPPER. Not a screen that feeds one —
it IS the Plot Mapper. The writer writes the story down in one piece,
breaks it into chapters and scenes, and names the people, places and
things inside it. That is plot mapping.

AND IT IS THE ONLY ONE. Kev: "This is the only one we will be putting
live." The rotated board, the corkboard, the vertical DCW and the
horizontal work area are all OUT as candidates. The comparison we set out
to make was settled by building the better thing instead.

The name is now free of the rotated board. If that board is ever revived
it needs a different name — it cannot be called Plot Mapper.

*** HOW WE GOT THERE (worth keeping, because the reasoning matters) ***

Sara (writer, Kev's wife) was shown the Synopsis and said: "Do I have to
use it?" That was taken seriously. The reading: the screen asked the
writer to do admin — chop the prose up, tag the names — and gave nothing
back, because everything it produced was for a screen somewhere else.

Kev's answer was to make it the Plot Mapper. The breaking-up is no longer
work done for another screen; it is the thing itself. Kev's later view:
"What Sara said was wrong. This page works." Both are true — her reaction
was right about what she was shown, and what she was shown has changed.

A morning was spent instead trying to rescue the rotated board (files
code-board-rotated-6 to -11: scene summary line rendered, fine-line
divider, delicacy pass, titles into the margin, cards made in their cell).
It was ABANDONED. Kev: "None of this is working for me. Somewhere we have
lost the magic." Every step that morning had been a subtraction, and the
board was being judged empty. Those files exist but are not the way.

*** WHAT THE SCREEN DOES NOW ***

- ONE CONTINUOUS DOCUMENT. Prose is never boxed, moved or retyped.
  The insight it was built on, from 12 August, still holds: "when writing
  your idea for a story, a synopsis, you just write stuff down and then
  sort it out later."
- F2 IS THE ONE KEY. Bare cursor -> Chapter break (1) or Scene break (2).
  A phrase highlighted -> the SIXTEEN sections of the sidebar, four
  columns, headed and coloured by family, each with a single letter shown
  in bright white. Highlighting alone summons nothing.
  Letters: Story T U M E · People C R F D · World L B O W · Library G N I S.
- CATCHING PART OF A WORD IS ENOUGH. The selection grows out to whole
  words: "oa" gives Toad; a drag from inside "Mr." into "Toad" gives
  "Mr. Toad"; a trailing comma is dropped; "Mr." keeps its full stop.
  Kev: "a tired writer would get pissed off damn quick."
- THE BREAK is a dashed gold hairline with its "Ch. 1" pill out in a left
  gutter and a gold dot at the far end — Kev's own sketch, and the same
  mark a board would use. Scene breaks are the same in pale stone.
  A break never falls mid-word. Removing one stitches the prose back
  together. An empty run trapped between two breaks is dropped.
- THE GOLD DOT opens: own word range, change chapter to scene or back,
  remove the break.
- PROMPT / EXPAND sit ON THE LINE, right-hand end, before the dot, on
  every chapter and every scene — matching where Ada's buttons sit on
  other screens. They READ THE WRITING BENEATH THEM: with words there,
  both are live and say "312 words here already — Ada works from them";
  with nothing there, Expand goes quiet. The two buttons that used to sit
  at the foot of the page are GONE.
- AI ON/OFF in the header is live. Off removes Ada from every line and
  every card.
- CARDS carry ALSO CALLED — Mr. Toad is also Toad. The platform proposes
  the obvious ones (drops a title, drops a surname); a rejected name goes
  quiet but is reachable behind a "2 set aside" line; typing a rejected
  name in adds it normally. Rejection belongs to that card only.
- INDENT (first lines set in, flush after a break) and DETAILS (dashed
  lines under anything recorded, in its family's colour — the word itself
  is never tinted).
- SECTION ? at the top right opens a MOVABLE, RESIZABLE window: twelve
  lines, a gold label and one plain sentence each. No scrim — the page
  stays live so it can be read while working.
- THE HEADER was cut to title, strapline, word budget and Edit in Basics.
  A MORE / LESS button under the budget unfolds Genre, Classification,
  Status and Author beneath it. They are shown, not editable — Basics is
  the one door.
- THE FOOT tallies: words, chapters, scenes, how many things made, and
  HOW MUCH IS NOT YET DIVIDED.

*** THE BUG THAT COST AN AFTERNOON — READ THIS ***

The undo store was declared as "var history = []". The browser has
already claimed that name for its own back-and-forward list, and a var at
the top level of a script does NOT override it. Every call to snapshot()
hit history.push and threw.

snapshot() is the FIRST line of every action that changes the document,
so breaks, cards and break-removal all died silently at step one. It
looked like a broken F2, then a broken menu, then a broken mouse. It was
none of those.

NEVER NAME A VARIABLE history, name, location, status, top, self or
parent — the window already owns them all.

It was found only by building a version that PRINTED WHAT IT WAS DOING to
a line on the page. WHEN A FAULT SURVIVES ONE FIX, STOP GUESSING AND MAKE
THE SCREEN SAY WHAT IT DID.

*** HOW THE WRITING IS HELD ***

  { kind:'chapter', title, budget }
  { kind:'scene',   title }
  { kind:'prose',   paras:[ {text, marks} ] }

A run of prose is A LIST OF PARAGRAPHS, not one long string. A break is
"this paragraph, this point in it" — no counting across the document,
nothing to drift. Word counts are the words between one break and the
next. Chapter marks carry an optional own budget.

*** WHY THIS SHAPE — THE WHEEL ***

The Wheel (the writing view) is ONE FULL PAGE PER SCENE, each carrying:
the chapter heading, the scene number, the scene title, and THE SCENE'S
SUMMARY TEXT above the writing area. That summary is the line the writer
works FROM, and it is exactly what the splitting produces.

The Wheel's scene menu (Characters, Objects, Themes, Tension) is
populated by the naming done here: a scene knows Mole is in it because
Mole was made a character while writing that passage.

TEST FOR ANY PLOT MAPPER: can it produce chapter, scene number, title and
summary? If not, it is not a Plot Mapper, whatever else it does well.

*** STILL TO DO ***

1. NOTHING SAVES. Refresh and it is gone.
2. TINTS VANISH WHEN THE PROSE IS EDITED. A mark is held as "characters
   14 to 22 of this paragraph" and editing moves the words. THIS IS NOT
   FIXED BY GOING LIVE — it must be solved WHILE building saving, since
   both need the platform to follow a phrase as text moves. Do it after
   and the store is built twice.
3. CARDS DO NOT REACH CHARACTERS. Making Mole does not put him anywhere.
   Step two, and the real work.
4. The header facts and the budget are still the Wind in the Willows
   demo's, hard-coded.

*** NEXT SESSION — STEP ONE OF GOING LIVE ***
Turn code-plot-mapper-10.html into pockets/plot-mapper.html, add the
corridor slot, point the sidebar's DCW > Plot Mapper at it, make the
header and budget read the real project. THE CURRENT CORRIDOR MUST BE
PASTED IN — build from the file, never from a reconstruction.

================================================================
*** PLOT MAPPING — THE OPEN DECISION IS CLOSED (15 August 2026) ***
================================================================

THE CANDIDATES ARE OUT. The corkboard, the rotated board
(code-board-rotated-5.html), the vertical DCW and the horizontal work
area are no longer in the running.

WHAT THE ROTATED BOARD TAUGHT US, KEPT:
- The four requirements test still stands (chapter, scene number, title,
  summary). The rotated board was the only candidate whose design
  accounted for all four — and its summary line was styled but never
  rendered, so in truth it had three.
- The compass rose, the arrival state (reading chapterRange from
  localStorage "is-projects"), the take-6 header-band card, the
  drag-to-reorder tracks and the snap-to-grid machinery all still exist
  in that file if ever wanted.
- code-board-rotated-6 to -11 were a failed rescue attempt on 15 August.
  Do not build on them.

IF A BOARD IS EVER REVIVED IT NEEDS A DIFFERENT NAME.

================================================================
*** BASICS (OVERVIEW) — GENRE RANGES & THE THREE GUIDES · LIVE ***
Published 12 August 2026. File: pockets/project-overview.html
================================================================

THE GENRE DROPDOWN now carries each format's INDUSTRY WORD-COUNT RANGE,
labelled "TYPICAL LENGTH:" in small mono caps with the figure in gold. The
chosen range stays visible in the closed field. Kev's reasoning: the writer
sees what they are signing up for AT THE MOMENT OF CHOOSING.

Every genre carries THREE things: its range (wc), its words-per-chapter (per),
and ITS OWN SENTENCE WORDING (says) — so the steer reads "Most adventures
land...", "Most non-fiction lands...", "Most memoirs land..." and is never
grammatically wrong. Roughly forty entries, each written once. PAGES ARE NOT
USED — Kev: "there are so many page sizes."

THE WORD COUNT SECTION was rebuilt. It used to be four boxes (Target,
Chapters, Current, Remaining) with two blocks of explanation. It is now THREE
LINKED GUIDES: Words (a range), Chapters (a range), Words per chapter. All
drawn from the genre, all editable, all gold while they are the platform's
suggestion, with a ↺ to restore. CHANGE ONE AND THE OTHERS FOLLOW.

Beneath them, ONE italic line: "Most adventures land somewhere in this range —
it's a guide, not a rule." The word LAND was chosen deliberately: it describes
where books tend to end up, not where this one must.

RANGES THROUGHOUT — never a single target, because the Overview gives ranges
and the two must never disagree. The Plot Mapper's budget divides the book's
range across the chapters to give each its own range.

CURRENT AND REMAINING WERE REMOVED — they are facts about progress and belong
where the writing is. They survive as HIDDEN STUBS because the corridor's
autoSave still refers to them by name (as do ph-format, ph-audience,
ph-outline). THIS CAUSED A REAL BUG: autoSave stops dead at the first missing
element, which silently prevented the steer sentence updating. The pocket now
updates its own display BEFORE calling autoSave, and wraps corridor calls in
try/catch.

WHERE THE DATA LIVES: the Overview writes wordRange, chapterRange, perChapter
and guidesEdited onto the project in localStorage key "is-projects", and
exposes window.IS_GENRE_WC and window.IS_GENRE_INFO for other screens.

THE GENRE FIELD was restyled to match the other inputs (it had been using a
darker fallback colour and standing out from the row), and its chevron
enlarged to 18px, turning gold on hover.

NEW PROJECT POP-UP: Genre removed (it duplicated the proper dropdown and
taught the writer nothing). AUTHOR NAME(S) takes its place and carries through
to the Overview. Title and Author only.

================================================================
*** THE SIDEBAR — REBUILT · LIVE (11 August 2026) ***
File: corridor.html
================================================================

BASICS, then:
  STORY    Plot Threads · Subplots · Themes & Motifs · Events & Timeline
  PEOPLE   Characters · Relationships · Factions & Orgs · Language & Dialogue
  WORLD    Locations · Buildings · Objects & Artefacts · Rules & Lore
  LIBRARY  Research & Reference · Notes · Images · Sandbox
  DCW      Plot Mapper · Manuscript · Publish

SYNOPSIS HAS GONE FROM STORY (15 August) — it was this screen under another
name, and it is now DCW > Plot Mapper.

Images, Manuscript and Publish point at Coming Soon. Chapters and The
Treatment were dropped from the sidebar — their pockets remain in the repo
untouched, only the way in has gone. showScreen was guarded so the removed nav
ids no longer throw.

"BASICS" vs "OVERVIEW" IS UNRESOLVED. Overview is the better of the two for a
writing platform (it means the view over the whole thing; Basics sounds like a
form at a garage). FRONT MATTER is the genuinely literary option — it is what
publishing calls everything before the story starts. LEFT AS BASICS
DELIBERATELY, to be settled in the theatre pass.

SANDBOX should move from Library to DCW — it is drafting without commitment,
not gathered material. Not yet done.

GROUP HEADINGS SHOULD BECOME LIVE ROOMS. Agreed logical: if Library is
clickable, all five must be. Each room is a view of what is inside it. Five
rooms to build. Not started.

================================================================
*** SPELL CHECK — FIXED PLATFORM-WIDE · LIVE (11 August 2026) ***
File: corridor.html
================================================================

enableSpellCheck ran once on load, so it missed any field created later.
Rewritten to use the SAME MUTATIONOBSERVER PATTERN the Read-aloud block
already used. It now catches input[type="text"] and textarea whenever they
appear, platform-wide, marking each field data-spellReady="1" so nothing is
done twice.

NOTE: this catches inputs and textareas. The Plot Mapper uses contenteditable
divs, which the selector does NOT cover — they set spellcheck themselves. If a
future screen uses contenteditable, widen the corridor selector.

*** THE GRAMMARLY TRAP — READ THIS BEFORE CHASING A SPELL-CHECK FAULT ***
Testing took an hour longer than it should have because Grammarly was masking
the browser's own red underlines with its own. It had to be REMOVED AND THE PC
RESTARTED — closing the tab was not enough. Chrome's own spell-check must also
be on: chrome://settings/languages, BASIC (not Enhanced — Enhanced sends typed
text to Google), English (United Kingdom) ticked. Grammarly often turns
Chrome's spell-check off when it installs and does not turn it back on when
removed.

*** ENCLOSURE WARNING ***
NEVER press "ADD SPELL CHECK TO CORRIDOR". That button still sits in the
Enclosure below Publish. It was how the original code was installed, and
pressing it now would push an OLDER version back into the corridor, undoing
this fix.

*** THE PUBLISHING RULE ***
WAIT A FULL MINUTE between pressing Stitch and pressing Publish. Pressing
Publish twenty seconds after Stitch reads the PREVIOUS index.html and silently
deploys stale code. Pressing Publish again after a pause fixes it. Stitch's
character count and Publish's character count MUST MATCH before a hard refresh
is trusted.

================================================================
*** THE TWO BIG IDEAS — PARKED, NOT ABANDONED ***
These are the two things in the project nobody else is offering, and they are
the same idea seen from two ends. A THIRD now joins them — the continuity
library in future.md. A project that knows its own proper nouns serves the
spell checker, the language creator and the continuity guard alike. Three
features, one well.
================================================================

1. INKYSWOT'S OWN SPELL CHECKER
Browser spell-check can only be reached by right-clicking exactly on the
underlined word — no suggestion panel, because a page can see a word is marked
but cannot read Chrome's suggestions or open its menu. And the dictionary
belongs to the browser, not the book: every character name is flagged forever.
For a dyslexic writer, constant false flags on your own proper nouns train you
to ignore the underlines entirely, which defeats the purpose.

OURS: a personal dictionary that lives WITH THE PROJECT. Built from a free
British English word list plus Typo.js for suggestions (the easy part), an
overlay technique to draw the underlines — an invisible copy of the text
behind the box, kept in step as the writer types and scrolls (the hard part,
and it must be done ONCE, CAREFULLY, IN THE CORRIDOR so every field inherits
it) — and a proper click-to-correct panel in the house style. A session or two
of focused work. A genuine selling point: dyslexia-friendly in a way the
browser is not.

2. THE LANGUAGE CREATOR
Tolkien spent forty years because the languages WERE the point. Nobody else
wants that. What a writer needs is a language that HOLDS UP UNDER SCRUTINY:
consistent sounds, plausible names, a few dozen recurring words, a grammar
that never contradicts itself. That is an afternoon, if the tool is right.

The writer chooses a character for the tongue — harsh and consonantal, or
liquid and vowel-heavy. The tool fixes an alphabet and rules about which
sounds may sit together, then generates place names, personal names, and words
for the twenty things every invented culture needs. All obeying the same
rules, so IT SOUNDS LIKE ONE LANGUAGE — which is the entire trick. Everything
lands in a LEXICON.

AND HERE IS THE JOIN: THE LEXICON IS THE PERSONAL DICTIONARY. Invented words
stop being flagged because the platform knows they are real in this book. The
two ideas are one idea.

Proauthorism holds: Ada proposes the sound-world, the writer approves or
overrules, every word stays theirs to change.

3. INVENTED SPEECH IN THE MANUSCRIPT — THE FOOTNOTE MECHANISM
Kev's own design, and it is the right way round. The writer types the line IN
PLAIN ENGLISH, in their own voice and rhythm. They highlight it and mark it as
that language. The line in the manuscript becomes the invented tongue, and THE
ENGLISH DROPS TO A FOOTNOTE as the translation.

- THE ENGLISH IS THE MASTER. Revise it and the invented version regenerates.
- IT CAN BE SWITCHED OFF — the passage renders as plain English at any point.
  The invented layer is a setting, not a commitment.
- IT NEEDS GRAMMAR, NOT JUST WORDS. Word-for-word substitution gives you
  English wearing a hat. Word order, plurals and tenses must be fixed when the
  language is made. That is the real work.

WHY FOOTNOTES: subtitles work because they are in the same frame. A glossary
at the back is not — it asks the reader to leave the book. The old scholarly
convention does exactly what film subtitles do: a rule across the page, notes
beneath in smaller type, keyed by number. Readers have known how to use it for
four hundred years. The mark is made in the Plot Mapper AND the manuscript,
and the footnote is never written by hand, so it cannot drift out of step.

IN THE PRESS this becomes a typesetting problem: footnotes must fall on the
page their marker falls on, which means page-breaking solves for both at once.
It is why word processors do footnotes badly and typesetters charge for them.
WORTH BEING GOOD AT. In a digital edition it becomes tap-to-reveal —
subtitles at the reader's discretion, which print cannot do.

4. THE BUSINESS THOUGHT — LANGUAGE PACKS
Kev, last thing at night: "Language packs. Fully formed languages for sale."
Build the engine once, sell the languages forever. Each pack is a small,
finished thing a writer can drop in and use the same evening — sounds,
grammar, lexicon, names. It fits the Pitch Dark model (subscription, nibs,
PAYG bundles) and is a genuine reason to choose InkySwot over anything else.

================================================================
*** THE LIBRARY — DESIGNED, UNRESOLVED ***
================================================================

WHAT IS SETTLED
- FOLDERS ARE FIXED AND PLATFORM-PROVIDED. NO "NEW FOLDER" BUTTON. This is
  what stops research becoming a drawer full of paper — the writer never makes
  a filing decision, so there is nothing to tidy.
- SUB-FOLDERS MIRROR THE SIDEBAR SECTIONS (World holds Locations, Buildings,
  Objects, Rules & Lore; and so on).
- AN ENTRY IS FILED IN A SUB-FOLDER **AND** MAY OPTIONALLY NAME the specific
  location or character it is about — so a note on Ravensworth's cellars sits
  in World > Buildings and ALSO appears on Ravensworth's own screen. Kev:
  "you are going to have to, somehow, do BOTH." Both, and it is one act: file
  it, then optionally attach it.
- SANDBOX IS NOT LIBRARY (see sidebar note above).

WHAT WAS REJECTED (all "a bit boring" or wrong)
Shelves of book spines; a filing drawer of hanging files with staggered tabs;
a tree of coloured pills opening rightwards. Kev then showed a folder ICON
(closed, and open with papers standing out of it) and a STACK OF THREE FOLDERS
SEEN FRONT-ON, stepped, as the arrangement. Then: "forget it and we will just
carry on."

THE INSIGHT WORTH KEEPING
Mid-conversation Kev realised: "Damn we already have it." Every screen in the
platform is already list-on-the-left, detail-on-the-right. The Library may not
need a new metaphor at all — just the platform behaving consistently. That
line of thought was not followed to its end.

THE CONTINUITY LIBRARY (15 August, in future.md) belongs here when it is
built: uploading a finished book as a source the whole project reads from.

================================================================
*** THE THEATRE PASS — DEFERRED DELIBERATELY ***
================================================================

Kev: "we are going to do a theatre pass at the end so we can mess about with
syntax then." Nothing decorative should be built before it.

FROM THE EARLIER BRIEF, the board's failings: cards APPEAR rather than arrive;
pinning should feel like coming home; snap-to-grid should be the showpiece;
adding a scene jolts everything below; the board is inert at rest.

THE BEST SINGLE MOMENT FOR THEATRE IS A BREAK ARRIVING IN THE PLOT MAPPER —
the rule drawing itself across, the prose settling into its new place. One
well-made moment there would do more than a dozen small flourishes elsewhere.

REMEMBER: gold marks anything alive and responding. Never decorative.

================================================================
*** CONCEPTS — THE IDEAS SYSTEM · BUILT & WORKING (14 July 2026) ***
Working file: concepts-canvas.html.
================================================================

WHAT IT IS
CONCEPTS — a writer's private store for FUTURE-story ideas, separate from any
one project. It lives ON THE MY PROJECTS SCREEN, not in its own pocket: the
screen splits, My Projects on the left (unchanged), the Ideas/Concepts area
on the right. A concept is a pre-project — a seed that may one day become one
of the books on the shelf. (The name CONCEPTS is held LIGHTLY.)

THE STRUCTURE — THREE STAGES (locked, matches Kev's map)
GENRE FOLDER -> STORY TITLE -> MAIN STORY CARD (a canvas). No more levels.
- GENRE FOLDER: a narrow bar. Named from the real GENRE LIST (the same list
  as the Overview screen's custom dropdown). Made via a + FOLDER button,
  bottom-right of the Ideas area (mirrors + NEW PROJECT bottom-left).
- Click a genre folder: its STORY SUB-FOLDERS open OUT TO THE SIDE, joined by
  a dotted connector line. Stories are added by the folder's OWN +. Story
  titles are PLAIN BARS, not header-band cards.
- Click a STORY TITLE: its MAIN STORY CARD opens as an almost-full-screen
  POP-UP on a dimmed backdrop. Title in the top bar, with the close x.

THE MAIN STORY CARD = A RESIZABLE CANVAS (the heart of it)
- Not a title-and-body page. A CANVAS holding small header-band idea cards —
  the board idiom scaled down and living inside a story.
- ADD IDEA opens a GROUPED DROPDOWN of the platform's real side-menu list.
  Pick a category -> a HEADER-BAND CARD drops onto the canvas, named and
  COLOURED BY FAMILY. Each has a "Write your idea..." body that auto-grows.
- WHY IT MATTERS: because these are the platform's REAL categories, a card
  jotted in a Concept LATER INTEGRATES into the main platform when the idea
  grows into a project.
- Cards DRAG FREELY. The WHOLE POP-UP is RESIZABLE, opening large (~94vw x
  90vh); drag the bottom-right corner to adjust.
- PROMPT and EXPAND float up the right edge, gold. Placeholders — to wire to
  the corridor's aiAutofill / aiExpand helpers.

GENRE FOLDER COLOUR (locked)
- Default = a REPEATING PALETTE of the SIX TRACK COLOURS. New folder takes the
  next colour; loops after six. The writer CAN CHANGE any folder's colour via
  a small colour dot opening a six-swatch picker.

THE EMPTY-CARD IDIOM (settled, kept)
- An empty/unfiled card is a DASHED OUTLINE only — tab band and body both a
  soft pencil-grey stroke on the black. It earns its colour by being filled.
  (The Plot Mapper's Also-called suggestions use the same idiom.)

STILL TO DO
- Build the actual story-naming step (+ New story and folder + are demos).
- Wire Prompt / Expand to the real Ada helpers.
- PERSIST — folders, stories, cards and card positions into the database, and
  integrate the cards into the main platform entities when a concept becomes
  a project.
- A gold-rendering niggle on Prompt/Expand on Kev's screen was NOT resolved.

NOTE (13 August, still outstanding): the Concepts side-menu list uses the OLD
grouping (Cast / World / Plot). The sidebar is now STORY / PEOPLE / WORLD /
LIBRARY / DCW, and the Plot Mapper's section menu uses the new list of
sixteen. Concepts should be brought into line when next touched.

BANKED FOR future.md: (a) richer CHARACTER fields; (b) ADA AS
CONTINUITY-GUARD — now folded into the continuity library entry.

----------------------------------------------------------------
*** SUPERSEDED — the 13 July "Ideas Box / filing-box" design ***
The filing-box metaphor was ABANDONED: it chased theatre over usability. The
header-band CARD idiom and the DASHED-empty state survived from that thinking;
everything else about the box is dropped. Do not rebuild the box.
----------------------------------------------------------------

================================================================
*** HOUSE STYLE — LOCKED ***
================================================================
#0a0806 near-black · #0f0d0a background · #c9923a gold · #e8b060 bright gold.
Crimson Pro (body) · JetBrains Mono (labels and interface) · Playfair Display
(wordmark and titles). Muted danger red #c43a2a for overruns and warnings —
THEY INFORM, THEY NEVER BLOCK THE WRITER. Light/dark toggle platform-wide.
GOLD MARKS ANYTHING ALIVE AND RESPONDING. NEVER DECORATIVE.
Track colour families: People #cf7f57 · World #5fa898 · Story #c9923a ·
Library #9a8f72.

ADDED 15 AUGUST:
- A CONTROL THAT CHANGES ITS WORDING MUST NOT CHANGE ITS SIZE. Fixed width
  sized to the longest state, text centred. TO BE SWEPT ACROSS THE CORRIDOR
  when it is next in hand.
- A CONTROL'S SIZE MUST NOT DEPEND ON WHAT IS BESIDE IT.
- OPENING SOMETHING MUST NOT PUSH WHAT IS ABOVE IT.
- MARKS ARE DASHED LINES BENEATH, NEVER TINTED WORDS. Colour is by FAMILY,
  not by section — four colours read at a glance, sixteen do not.
- EVERY SCREEN CARRIES A "SECTION ?" PILL at the TOP RIGHT of its header,
  opening a movable, resizable window. No scrim. One line per thing.

================================================================
*** SUGGESTED ORDER OF WORK ***
================================================================
1. MAKE THE PLOT MAPPER LIVE — step one: pockets/plot-mapper.html, the
   corridor slot, the sidebar link, the header and budget reading the real
   project. THE CURRENT CORRIDOR MUST BE PASTED IN.
2. STEP TWO — the cards writing into the same store Characters, Locations and
   the rest read from. This is the real work, and the continuity library in
   future.md depends on it. SOLVE THE VANISHING TINTS AS PART OF THIS, not
   after.
3. Then the Library, then the five rooms, then the theatre pass.

Kev's own words, still true: "We will have to make and remake this page until
it is right." Expect several passes. That is the plan, not a failure of it.