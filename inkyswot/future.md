File: inkyswot/future.md
Last updated: 31 August 2026 — rewritten clean. The CONTINUITY LIBRARY
entry from 15 August has been REACHED AGAIN from a different direction and
is now much better specified. The SPELL CHECKER entry has changed
substantially: its hard part is solved. THE DESK and THE EVENT PLANNER
have moved out of here into current-state.md, being designed rather than
merely imagined.

FUTURE IDEAS — NOT LOCKED — TO DISCUSS
Logged possibilities, not on the current build list. Nothing here is a
commitment. Revisit when revenue supports it.

REMINDER: THIS FILE IS UPDATED AT THE END OF EVERY SESSION, along with the
other four. See the lock in locked-decisions.md.

================================================================
THE CONTINUITY LIBRARY — upload a finished book
Conceived 15 August 2026. REACHED AGAIN INDEPENDENTLY 31 August 2026,
from the humaniser conversation. NOT STARTED. Needs step two to exist.
================================================================

KEV'S ORIGINAL FRAMING (15 August): "I have written a book and want to
write another one, a sequel. It would be nice to have an area where I
could upload the 1st book so the system could help with continuity. Not
only in terms of style but correct names, places, events and so on."

KEV'S SHARPER FRAMING (31 August), arrived at from the opposite end —
having started from a "humaniser" for AI prose and worked backwards:
"It's not so much the writing style I want studied but inconsistencies in
the writing. EG: Bill has dark hair in book one and I give him blond in
another."

THAT SECOND FRAMING IS THE BETTER ONE AND SHOULD GOVERN THE BUILD. The
same idea arrived at twice, two weeks apart, from different directions —
which is about as strong a signal as a solo project gets.

WHERE IT BELONGS: THE LIBRARY, not the Plot Mapper. It is a SOURCE the
whole project reads from, not a screen the writer works on.

IT IS TWO THINGS WEARING ONE COAT.

1. CONTINUITY — THE STRONG ONE, AND NOW THE STRONGER OF THE TWO.
   Upload the first book and the platform reads it into the project's own
   records: Ravensworth is a house with a cellar, Nell has short hair by
   chapter nine, the funeral was in March.
   WHY IT IS THE STRONG ONE: FACT CONSISTENCY IS HARD, NOT FUZZY. Bill
   has dark hair or he doesn't. When the tool says his hair changed it is
   right or wrong, and the writer can check in a second. Style
   consistency can only ever say "this doesn't sound like you."
   It is also the kind of mistake that genuinely gets through — nobody
   re-reads book one to check a hair colour before writing book three.
   THIS IS NOT A CHAT WITH A DOCUMENT. It is exactly the job the Plot
   Mapper's cards already do — writing into Characters, Locations,
   Events — run from a finished manuscript instead of a synopsis. WHICH
   MEANS IT IS DOWNSTREAM OF STEP TWO, not a separate build.
   AN INCOMPLETE BOOK IS FINE FOR THIS. For style an unfinished draft is
   a problem; for facts it is not. A half-written book contributes the
   facts it contains.
   And it delivers ADA AS CONTINUITY-GUARD: "written with long hair, but
   his record says short." She invents nothing. She holds the writer to
   what they already wrote. This is also the CONFLICT DETECTION half of
   the Chapters spec.

2. STYLE — THE WEAKER ONE, AND TO BE HANDLED WITH CARE.
   THE VERSION THAT WORKS: style used to CHECK, never to produce. Ada
   noticing this chapter runs long-sentenced where the first book was
   clipped.
   AND THE TRAP, NAMED 31 AUGUST: a tool that measures a writer against
   their own past work REWARDS CONSISTENCY. Pushed too hard it becomes a
   machine for stopping a writer developing. VOLUNTARY AND OCCASIONAL,
   NEVER ALWAYS ON.

THE LOCAL VERSION AND THE WIDE VERSION (31 August).
· LOCAL leans on what the platform already knows. If Bill's card says
  dark hair, the tool scans the manuscript for other hair statements near
  his name and flags disagreements. Narrow, honest, and it uses the
  world-building the writer already does. IT DEPENDS ON THE CARDS
  CARRYING FACTS — see thinking.md.
· WIDE reads the prose and works out the facts itself. Needs a model,
  which means sending text away. A deliberate choice, never a default.

THE LEGAL NOTE THE PLATFORM SHOULD CARRY
The Wind in the Willows is out of copyright, so a sequel to it is the
writer's to publish. A sequel to a book still in copyright can be written
privately but NOT published without the estate's permission. Worth saying
at the point of upload — a writer could put six months into one without
realising.

THE MACHINERY IS SHARED. FOUR separate items need the same thing — a way
to take an uploaded manuscript and read it: this, the SERIES BIBLE IMPORT
for Research & Reference (raised 25 August), the PUBLIC PRESS, and the
post-launch AI INFERENCE FROM AN IMPORTED MANUSCRIPT. Build one and the
others are nearly free.
THE OPEN QUESTION ACROSS ALL FOUR: whether the writer confirms extracted
data before it lands in Characters, or whether it lands and is corrected.

================================================================
THE SERIES BIBLE IMPORT — teaching Ada your own voice
Raised 25 August 2026. NOT BUILT. Deserves its own session.
================================================================

WHAT IT IS. The writer uploads THEIR OWN FINISHED BOOKS into Research &
Reference, and the platform reads them — both for continuity (names,
places, events) and as a reference for the writer's own voice.

WHY IT IS THE STRONGEST PROAUTHORIST THING ON THE PLATFORM, and it should
be named as such: IT IS THE WRITER TEACHING ADA THEIR OWN VOICE FROM THEIR
OWN BOOKS. That is not the AI imposing a style. It is the exact opposite.

THE BOUNDARY, AND IT NEEDS DECIDING BEFORE IT IS BUILT RATHER THAN AFTER.
The writer's own books — absolutely. SOMEONE ELSE'S BOOKS UPLOADED IN
ORDER TO WRITE LIKE THEM IS A DIFFERENT THING ENTIRELY. Take a position on
it before somebody does it.

A HARD LIMIT WORTH KNOWING NOW. Ada cannot read a whole novel every time
Prompt is pressed. STYLE REFERENCE HAS TO BE A DISTILLED THING — a sense
of the writer's sentences, their rhythms, how they handle dialogue — NOT
THE BOOK ITSELF. Whatever is built must produce that distillation once and
carry it, rather than re-reading.

THE OPEN QUESTION THAT DECIDES THE SHAPE: when a book goes in, DOES THE
WRITER CONFIRM WHAT GETS EXTRACTED BEFORE IT LANDS IN CHARACTERS — OR DOES
IT JUST APPEAR? The same question governs the continuity library, the
public Press and the post-launch import inference, and it should be
answered once for all four.

================================================================
THE STYLE METER — new, 31 August 2026. NOT STARTED.
================================================================

FROM KEV'S HUMANISER IDEA. On a drum machine a humanise control shifts
each hit a few milliseconds off the grid so it stops sounding like a
machine. Kev asked whether the same could be built for AI writing.

HIS OWN DIAGNOSIS IS THE USEFUL PART, AND IT IS MORE PRECISE THAN THE
ANALOGY: "The problem with AI generated content is that it falls back on
the same type of sentence." NOT LENGTH — CONSTRUCTION.

WHERE THE ANALOGY BREAKS. A humanise knob works because the notes are
already right and the only fault is exactness. Prose evenness is a
SYMPTOM of how the text was made, not a layer on top. Randomising
sentence lengths produces prose irregular in the WRONG places, which
reads as odd rather than alive — the same reason a badly set humanise
knob makes a drummer sound drunk.

ONE SET OF MEASUREMENTS, TWO TOOLS:
  1. A METER that marks where the writer's OWN prose has flattened. Not
     correcting; marking, the way the checker marks punctuation.
  2. THE SAME MEASUREMENTS applied to generated text before it goes near
     the manuscript.
BOTH ARE LEGITIMATE HERE because the collaboration is declared either
way. Kev: "even if it were possible to hide the AI generated text I would
still be open about how it was constructed." THE DECLARATION IS THE
POINT; THE DISGUISE NEVER WAS.

WHAT TO MEASURE — all countable from the passage with the checker's
parser: sentence OPENINGS (subject, participle, subordinate clause);
sentence SHAPES (simple, compound, complex, fragment); LENGTHS and
whether they vary or hover; REPEATED CONSTRUCTIONS, the same frame
recurring within a few paragraphs.

WHAT IT CANNOT DO. Judge whether a departure is bad. A scene written
differently because the scene needed it is invisible to arithmetic. IT
CAN ONLY EVER SAY "THIS DOESN'T SOUND LIKE YOU", never "this is wrong".

THIS IS THE STYLE / READABILITY TOOL the checker's specification sort
deliberately kept OUT of the punctuation checker. Sentence length was
removed from the punctuation rules on 28 August and belongs here.

================================================================
DELIVERED OR SUBSTANTIALLY CHANGED SINCE THIS FILE WAS LAST WRITTEN
================================================================

INKYSWOT'S OWN SPELL CHECKER — THE HARD PART IS NOW SOLVED (28 August)
The entry as written on 15 August described the overlay technique — "an
invisible copy of the text behind the box, kept in step as the writer
types and scrolls" — as the hard part, and said it must be done ONCE,
CAREFULLY, IN THE CORRIDOR.
THAT IS NO LONGER THE PLAN AND NO LONGER NECESSARY. The checker uses the
CSS CUSTOM HIGHLIGHT API: ranges are handed to the browser and it paints
them. NOTHING IS INSERTED INTO THE TEXT — no mirror, no wrappers, no
markup. It is built, working, and tested on a 47,000-word manuscript. The
click-to-correct panel in the house style is also built.
WHAT REMAINS OF THE SPELL CHECKER: the dictionary itself (a free British
English word list plus Typo.js for suggestions), and the personal
dictionary that lives WITH THE PROJECT so a character's name is never
flagged again. The reason it matters is unchanged and worth restating:
for a dyslexic writer, constant false flags on your own proper nouns
train you to ignore the underlines entirely, which defeats the purpose.

SMART ENTITY ASSIGNMENT / HOT-KEY TAGGING — LARGELY BUILT (15 August)
The 8 June seed was: highlight a word, hit a key, assign it as Character /
Location / etc. That is now the Plot Mapper's F2.
WHAT WAS BUILT, against what was specced:
  · Write freely, then a hot key catches the phrase — YES, F2.
  · Extending a partial catch — YES, and better than specced: the
    selection GROWS OUT TO WHOLE WORDS by itself. No selection mode, no
    escape route, nothing to learn.
  · A menu offering the TYPE — YES, all sixteen sections in four columns.
  · A record is a THING, not a string: one CANONICAL name + ALIASES —
    YES. This is ALSO CALLED.
  · ERR TOWARD ASKING, never guessing — YES, and further than specced:
    suggested aliases appear as faint dashed pills the writer accepts or
    sets aside, and a rejected one goes quiet without being lost.
  · A QUIET MARK in the prose — YES, a dashed line beneath in family
    colour, with a Details switch. Does not rely on colour alone.
WHAT IS NOT BUILT YET:
  · Picking an EXISTING record from a list. F2 always makes a new card.
  · The database filling ITSELF as you write.
  · Ada-assisted offers when AI is on. (Ada is not connected to that
    screen at all — see thinking.md.)
All three need the entity store — step two.

STICKIES — BUILT as THE QUICK-NOTE (17 June 2026). A locked, built
component awaiting wiring.

MANUSCRIPT VIEW TOGGLE — LOCKED (8 June 2026).

THE ONION-SKIN / LAYERED WRITING SURFACE — RESOLVED into THE MIXDOWN.

SYNOPSIS → WP TRANSITION — RESOLVED as the LIVING LINK, not a one-time
pour. "Nothing entered twice" won.

DEMO BOOKS — decided and in use. Still open: whether the in-scene prose
is written by Kev or sample-generated.

THE DESK — MOVED OUT OF THIS FILE (25 August). It is designed and settled
in shape, not merely imagined. Full write-up in current-state.md.

THE EVENT PLANNER / MURDER PLANNER — MOVED OUT OF THIS FILE (26 August).
Designed. Full write-up in current-state.md.

================================================================
STILL FUTURE — NOT STARTED
================================================================

ADA — FUTURE CAPABILITIES
Full voice interaction — conversational speech in and out, beyond the
current Read Aloud. Braille support. Multi-voice audiobook production.
Radio play production with multiple cast voices. AI voice profiles for
characters.

PLATFORM — FUTURE FEATURES
Six-tone time-of-day theme system — designed, not built.
Scrivener .scriv importer — Phase 2 priority.
World Anvil JSON import.
AI inference from an imported manuscript — pre-filling setup fields. See
the shared machinery note above.
Collaborative editing with live cursors.

EMOTIONAL MAP AS A LITERAL MAP
The DCW Emotional Map curve expands into a cartographic view of a
character's emotional journey: high ground for intensity, low ground for
numbness, rivers for flow, storms for crisis. The word Map was chosen with
this in mind.

WRITE SCREEN CUSTOMISATION REMOTE
The writing area fully customisable — background colour, text colour,
font, size. A critical accessibility feature: dyslexic writers in
particular benefit from non-white backgrounds. Delivered via a floating
remote control, styled like a TV remote. Moveable. Theatrical.

RICHER CHARACTER FIELDS — banked from the dropped face-generator idea.
NOTE (31 August): THIS HAS COME BACK AS A LIVE JOB, from a different
direction. The cards need a FACTUAL LAYER beneath their prose fields for
the continuity check to work at all. See thinking.md — it is no longer a
future nicety.

PLATFORM — FUTURE PRODUCTS
Newspaper / magazine platform — separate product.
Rights marketplace — writers sell and license rights.
InkySwot for screenwriters — a dedicated mode.
Educational version — universities and writing schools.
Partnership with writing communities.
LANGUAGE PACKS — build the engine once, sell the languages forever. Each
pack a small, finished thing a writer can drop in and use the same
evening: sounds, grammar, lexicon, names. Fits the Pitch Dark model
(subscription, nibs, PAYG bundles).

================================================================
THE BIG IDEAS — the ones nobody else is offering
(full write-ups in current-state.md)
================================================================
1. INKYSWOT'S OWN SPELL CHECKER — a personal dictionary that lives WITH
   THE PROJECT, so a character's name is never flagged again. Genuinely
   dyslexia-friendly in a way the browser is not. THE HARD PART IS NOW
   BUILT.
2. THE LANGUAGE CREATOR — a language that holds up under scrutiny in an
   afternoon, not forty years. THE LEXICON IS THE PERSONAL DICTIONARY, so
   this and the spell checker are one idea. With the footnote mechanism
   for invented speech, and LANGUAGE PACKS as a product.
3. THE CONTINUITY LIBRARY — above.
4. THE CHECKER — a punctuation checker whose text never leaves the
   machine. Built to Build 12; see current-state.md. It belongs on this
   list because "your manuscript never leaves your computer" is a claim
   Grammarly structurally cannot make.

ALL FOUR DRAW FROM THE SAME WELL: A PROJECT THAT KNOWS ITS OWN PROPER
NOUNS. The spell checker needs it. The language creator fills it. The
continuity library reads it. The checker's learning list is the same
shape — the writer's own corrections, remembered against this project.
WHICHEVER IS BUILT FIRST SHOULD BUILD THAT WELL PROPERLY.

================================================================
CONSIDERED AND DROPPED (kept so it is not re-proposed)
================================================================
MAPS & GEOGRAPHY — a line-glyph "SimCity"-style stamp composer, a
world-map tile set, era-grouped building elevations. Explored at length
8 June 2026, then DROPPED: a map maker pulls against what InkySwot IS — a
writing platform, assisted not generative. It makes pictures, not a better
book. Charming, but not right here. NOT to be revisited.

THE FACE GENERATOR — dropped. Two things were banked from it and both
survive: richer character fields (now a live job — see above), and Ada as
continuity-guard (now part of the continuity library).

A HUMANISER THAT DISGUISES MACHINE PROSE — considered 31 August and
turned round rather than dropped. The measurements are worth having; the
purpose was not. It became THE STYLE METER above. Kev's own position
settled it: he would declare the collaboration either way, so there was
never anything to disguise.