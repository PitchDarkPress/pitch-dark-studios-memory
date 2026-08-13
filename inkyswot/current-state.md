File: inkyswot/current-state.md

================================================================
*** THE SYNOPSIS SCREEN — REBUILT AS ONE DOCUMENT (12 August 2026) ***
Paste this block at the TOP of current-state.md. It supersedes nothing —
the Synopsis screen had not been written up before. Working file:
code-synopsis-flow-3.html (standalone, not yet a pocket).
================================================================

THE INSIGHT THAT CHANGED IT
Kev, mid-session: "when writing your idea for a story, a synopsis, you just
write stuff down and then sort it out later."

The old screen (code-synopsis-boxes.html) was a Whole Story box followed by
chapter boxes opening into scene boxes. It was WRONG because it asked the
writer to know their chapter breaks before they knew their story. It has been
replaced.

WHAT IT IS NOW
ONE CONTINUOUS DOCUMENT. The whole synopsis is a single flowing, editable
text. The prose is NEVER moved, boxed or retyped. Structure arrives as MARKS
WITHIN the flow — the writer draws lines through their own writing.

- F2 at the cursor opens a small two-option menu: Chapter break (1) or Scene
  break (2). NO HIGHLIGHTING NEEDED. A break never falls mid-word — if the
  caret is inside a word it steps back to the start of it.
- A CHAPTER BREAK renders as a rule across the page with "Ch. 1", an
  editable title, and its word count against its range.
- A SCENE BREAK is a lighter mark — rule, dot, optional title — the way a
  printed book marks one.
- Removing a break STITCHES the prose either side back together.
- HIGHLIGHTING A PHRASE opens a menu offering the platform's sections:
  Character (P), Location (L), Building (B), Object (O), Plot thread (T),
  Subplot (U), Theme (M), Event (E). Each has a single-key shortcut.
- Choosing one OPENS THAT CARD OVER THE WHOLE PAGE — the phrase already in
  as the name, the right fields for that section, a line showing the sentence
  it came from, Prompt and Expand, Save or Cancel.
- The made phrase is TINTED IN THE PROSE in its section's colour.
- CTRL+Z steps back through breaks, cards, marks and typing (typing grouped
  into bursts, so one undo does not remove a single letter).
- The foot tallies: words, chapters, scenes, cards made, and HOW MUCH IS NOT
  YET DIVIDED — which tells the writer how far through the splitting they are.

HOW IT IS HELD
An ordered list of parts: {kind:'chapter'|'scene'|'prose', ...}. Everything on
screen is drawn from that list. Word counts are simply the words falling
between one break and the next. Chapter marks carry an optional own budget.

WHY THIS SHAPE — THE WHEEL
The Wheel (the writing view) is ONE FULL PAGE PER SCENE, each carrying: the
chapter heading, the scene number, the scene title, and THE SCENE'S SUMMARY
TEXT sitting above the writing area. That summary is the line the writer works
FROM. It is exactly what the splitting produces — the passage marked off IS
the scene summary.

The Wheel's scene menu (Characters, Objects, Themes, Tension) is populated by
the tagging done here: a scene knows Mole is in it because Mole was made a
character while writing that passage.

TEST FOR ANY PLOT MAPPER: can it produce chapter, scene number, title and
summary? If not, it is not a Plot Mapper, whatever else it does well.

KNOWN LIMITATION
Editing a run of prose clears that run's tints — the marks are held as
character offsets and the text has moved. To be solved when persistence is
built.

STILL TO DO
Two steps, agreed: (1) turn it into pockets/synopsis.html, add the corridor
slot, switch the sidebar link from Coming Soon, make the header and budget
read the real project, save and reload the document; (2) make the cards
actually write into the same store Cast/Locations use, so making Mole puts him
in Characters. Step 2 is the real work.

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
and the two must never disagree. The Synopsis budget divides the book's range
across the chapters to give each its own range.

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
  STORY    Synopsis · Plot Threads · Subplots · Themes & Motifs · Events & Timeline
  PEOPLE   Characters · Relationships · Factions & Orgs · Language & Dialogue
  WORLD    Locations · Buildings · Objects & Artefacts · Rules & Lore
  LIBRARY  Research & Reference · Notes · Images · Sandbox
  DCW      Plot Mapper · Manuscript · Publish

Synopsis, Images, Manuscript and Publish point at Coming Soon. Chapters and
The Treatment were dropped from the sidebar — their pockets remain in the repo
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

enableSpellCheck ran once on load, so it missed any field created later (the
Synopsis boxes, for instance). Rewritten to use the SAME MUTATIONOBSERVER
PATTERN the Read-aloud block already used. It now catches input[type="text"]
and textarea whenever they appear, platform-wide, marking each field
data-spellReady="1" so nothing is done twice.

NOTE: this catches inputs and textareas. The new Synopsis uses contenteditable
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

*** THE PUBLISHING RULE — reinforced twice this session ***
WAIT A FULL MINUTE between pressing Stitch and pressing Publish. Pressing
Publish twenty seconds after Stitch reads the PREVIOUS index.html and silently
deploys stale code. Pressing Publish again after a pause fixes it. Stitch's
character count and Publish's character count MUST MATCH before a hard refresh
is trusted.

================================================================
*** PLOT MAPPING — SMALL CHANGES, AND AN OPEN DECISION ***
File: code-board-rotated-5.html (standalone, not yet a pocket)
================================================================

DONE THIS SESSION
- The "+ card" button in the bottom-right corner REMOVED (cards are to be made
  within the tracks). The card machinery itself untouched.
- "Time" in the spine head replaced with a COMPASS ROSE — drawn SVG, house
  gold, eight points, engraved shading (brighter on one facet of each point,
  dimmer on the other), no lettering, 42px. Standalone high-res copy exists as
  compass-rose.svg.
- Track dropdown reordered to STORY, PEOPLE, WORLD, LIBRARY, and the Story
  group matched to the sidebar: Synopsis, Plot Threads, Subplots, Themes &
  Motifs, Events & Timeline. This REMOVED Chapter & Scene Tracker and Dialogue
  from the dropdown — flagged, not yet decided.
- AN ARRIVAL STATE was added: the board reads the Overview's chapter range,
  takes the bottom of it, and lays that many chapters down the spine, each
  with Scene One already present, so the board NEVER OPENS EMPTY. Falls back
  to 25. It finds the project by reading localStorage "is-projects" directly
  and taking the most recently edited entry.
  KEV'S RESPONSE: "We are jumping ahead of ourselves. we need the synopsis
  page first." Built, but the ordering was wrong.

*** THE OPEN DECISION — WHICH PLOT MAPPER ***
Kev's proposal (13 August): put all the candidates live and see which works
best, possibly letting the writer choose between them.

The counsel given: BUILDING THEM LIVE TO COMPARE — YES, you cannot judge a
workstation from a screenshot. OFFERING THE CHOICE PERMANENTLY — be careful.
Every one kept is maintained forever, and they must all agree about the same
scenes. Two views of one story is a feature; two that drift apart is a bug
factory. A new writer asked which plot mapper they would like has been handed
indecision as a menu. If two do genuinely different jobs (mess-making versus
placing) keep both DELIBERATELY, not by default.

THE CANDIDATES
1. THE CORKBOARD — free-form. Double-click to drop a note, drag anywhere,
   pull threads between notes, chapter timeline along the bottom, Ada bubble,
   Transfer to InkySwot, section help panel, notes flip to private DARK
   THOUGHTS. Beautifully made. DOES NOT CREATE SCENES.
2. THE ROTATED BOARD — spine of chapters and scenes down the left, tracks as
   columns. DOES create scenes. Chosen as Plot Mapping in the earlier brief.
3. THE VERTICAL DCW (dcw-vertical-full.html) — and this one impressed.
   FORTY-FIVE-DEGREE TRACK HEADERS, so twenty tracks fit where the rotated
   board manages three. Small, flat, dense cards with the red full-stop for
   Dark Thoughts. TENSION, FEAR AND COMPASSION DRAWN AS CURVES running down
   the whole book rather than tracks of cards. Atmosphere, Weather and Time as
   their own columns. A RIGHT-HAND PANEL showing the selected character with
   their arc, relationships, which staves they appear in, and Ada's tools
   (Auto-fill, Image prompt, Check & improve).
4. A STILL PICTURE — fixed grid, no interaction. A look, not a tool.

KEV'S OBSERVATION: "I think we have lost a little of the DCW idea and with
that some of the theatre." He is right. The vertical DCW is what he means by a
workstation; the rotated board is its skeleton with most of the flesh missing.

================================================================
*** THE TWO BIG IDEAS — PARKED, NOT ABANDONED ***
These are the two things in the project nobody else is offering, and they are
the same idea seen from two ends.
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

================================================================
*** THE THEATRE PASS — DEFERRED DELIBERATELY ***
================================================================

Kev: "we are going to do a theatre pass at the end so we can mess about with
syntax then." Nothing decorative should be built before it.

FROM THE EARLIER BRIEF, the board's failings: cards APPEAR rather than arrive;
pinning should feel like coming home; snap-to-grid should be the showpiece
(twenty cards flying into formation); adding a scene jolts everything below;
the board is inert at rest.

SUGGESTED THIS SESSION: the best single moment for theatre is A BREAK ARRIVING
IN THE SYNOPSIS — the rule drawing itself across, the prose settling into its
new place. One well-made moment there would do more than a dozen small
flourishes elsewhere.

REMEMBER: gold marks anything alive and responding. Never decorative.

================================================================
*** CONCEPTS — THE IDEAS SYSTEM · BUILT & WORKING (14 July 2026) ***
This block is unchanged from its original entry. It REPLACES the old "Ideas
Database / Ideas Box" design block from 13 July — see the SUPERSEDED note at
the foot. Working file: concepts-canvas.html.
================================================================

WHAT IT IS
CONCEPTS — a writer's private store for FUTURE-story ideas, separate from any
one project. It lives ON THE MY PROJECTS SCREEN, not in its own pocket: the
screen splits, My Projects on the left (unchanged), the Ideas/Concepts area
on the right. A concept is a pre-project — a seed that may one day become one
of the books on the shelf. (The name CONCEPTS is held LIGHTLY — settled for
now, change later if a better one turns up. "Ideas" is the working heading on
screen in the prototype.)

THE STRUCTURE — THREE STAGES (locked, matches Kev's map)
GENRE FOLDER -> STORY TITLE -> MAIN STORY CARD (a canvas). No more levels.
- GENRE FOLDER: a narrow bar. Named from the real GENRE LIST (the same list
  as the Overview screen's custom dropdown — all ~50, twelve greyed "coming
  soon"). Made via a + FOLDER button, bottom-right of the Ideas area
  (mirrors + NEW PROJECT bottom-left). + FOLDER makes an EMPTY genre folder
  and nothing more.
- Click a genre folder: its STORY SUB-FOLDERS (story titles) open OUT TO THE
  SIDE (to the right), joined by a dotted connector line. Narrow genre bars
  stack tight; the opened stories float beside without adding row height.
  Stories are added by the folder's OWN + (and a "+ New story" line).
  Story titles are PLAIN BARS (just the title), not header-band cards.
- Click a STORY TITLE: its MAIN STORY CARD opens as an almost-full-screen
  POP-UP on a dimmed backdrop (modal). Title sits IN THE TOP BAR, with the
  close x. No category band in the head (that was removed — it belonged to
  earlier idea-card thinking).

THE MAIN STORY CARD = A RESIZABLE CANVAS (the heart of it)
- The story card is NOT a title-and-body page. It is a CANVAS that holds
  small header-band idea cards — a mini-board, the board idiom scaled down
  and living inside a story.
- ADD IDEA button (top bar) opens a GROUPED DROPDOWN = the platform's real
  side-menu list:
    Cast:  Characters, Relationships, Factions & Orgs, Language & Dialogue
    World: Locations, Buildings, Objects & Artefacts, Rules & Lore
    Plot:  Plot Threads, Subplots, Themes & Motifs, Events & Timeline
  Pick a category -> a HEADER-BAND CARD drops onto the canvas, named and
  COLOURED BY FAMILY (Cast = terracotta, World = teal, Plot = violet — deep
  muted tints from the platform palette). A glance tells you the kind by
  colour. Each card has a "Write your idea..." body that auto-grows, and a
  small x to remove.
- WHY IT MATTERS (the integration thread): because these are the platform's
  REAL side-menu categories, a card jotted in a Concept LATER INTEGRATES
  into the main platform when the idea grows into a project (a Location
  jotted here can carry through to the project's Locations).
- Cards DRAG FREELY around the canvas (grab the card, not the text).
- The WHOLE POP-UP is RESIZABLE (head + canvas + foot grow together — not
  the canvas alone). It opens LARGE by default (~94vw x 90vh) since it's a
  pop-up and has the room; drag the bottom-right corner to adjust.
- PROMPT and EXPAND buttons float up the right edge of the pop-up, gold,
  matching the Overview screen's Ada-assist buttons. Placeholders for now —
  to wire to the corridor's aiAutofill / aiExpand helpers when built for real.

GENRE FOLDER COLOUR (locked)
- Default = a REPEATING PALETTE of the SIX TRACK COLOURS (deep muted body
  tints, so folders sit calm in the dark, light text on deep bar). New folder
  takes the next colour; loops after six.
- The writer CAN CHANGE any folder's colour: a small colour dot on each bar
  opens a six-swatch picker (same six, same idiom as the note palette).

THE EMPTY-CARD IDIOM (settled, kept)
- An empty/unfiled card is a DASHED OUTLINE only (no fill) — tab band and
  body both just a soft pencil-grey stroke on the black. It earns its colour
  by being filled/filed. (Chosen over a grey fill — an empty idea is honestly
  empty.)

BUILT FROM THE TRUTH
- The header-band card was lifted from code-board-rotated.html (the take-6
  cards: .note-tab band + .note-card body + "Write your idea..." + Details).
- The genre list was read from project-overview.html (the real dropdown).
- The side-menu category list (Cast/World/Plot, 12 items) came from Kev.

STILL TO DO (next session)
- The "+ New story" and folder "+" are demo placeholders — build the actual
  story-naming step.
- Wire Prompt / Expand to the real Ada helpers (aiAutofill / aiExpand).
- PERSIST — folders, stories, cards, and card positions must save into the
  InkySwot database (and integrate the cards into the main platform entities
  when a concept becomes a project).
- Decide if a card, once dropped, needs anything beyond its body (kept
  deliberately just body for now — the seed end must not be forced).
- A gold-rendering niggle on Prompt/Expand on Kev's screen was NOT resolved
  (the icons were flat system glyphs; swapped to gold SVGs; Kev still saw no
  gold — likely browser/cache, left for later).

NOTE (added 13 August 2026): the Concepts side-menu list above uses the OLD
grouping (Cast / World / Plot). The sidebar has since been rebuilt as STORY /
PEOPLE / WORLD / LIBRARY / DCW, and the Synopsis screen's section menu uses
the new list. Concepts should be brought into line when it is next touched.

BANKED FOR future.md (from the dropped face-generator idea, still valid)
- (a) richer CHARACTER fields; (b) ADA AS CONTINUITY-GUARD ("written with
  long hair, but his record says short"). Banked, not started.

----------------------------------------------------------------
*** SUPERSEDED — the 13 July "Ideas Box / filing-box" design ***
The filing-box metaphor (face-on drawer, genre divider TABS across the top,
an Unfiled tab, cream front card, brass pull, four richness levels) was
ABANDONED. Reason: it chased theatre over usability. It was replaced by the
simple Concepts system above (folders on the My Projects screen). The
header-band CARD idiom and the DASHED-empty state survived from that
thinking; everything else about the box (drawer, tabs-as-furniture, folding
cards, the peeking-blank-card, richness levels) is dropped. Do not rebuild
the box.
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

================================================================
*** SUGGESTED ORDER OF WORK ***
================================================================
1. Gather and assess the plot-mapping candidates against the Wheel's four
   requirements (chapter, scene number, title, summary). DECIDE — do not ship
   a menu of them.
2. Make the Synopsis live, in the two steps above. It is the screen everything
   downstream depends on, and it produces the chapters the board is supposed
   to arrive holding.
3. Then the remaining Library sections, then the five rooms, then the theatre
   pass.

Kev's own words, still true: "We will have to make and remake this page until
it is right." Expect several passes. That is the plan, not a failure of it.