File: inkyswot/future.md
Last updated: 16 September 2026 — rewritten clean. THE SERIES BIBLE IMPORT
HAS MOVED OUT OF THIS FILE: it is being built, as THE IMPORT, and its
write-up is in current-state.md. The CONTINUITY LIBRARY's open question is
answered. Several entries gain a note now that the platform has a real
file store behind it.

FUTURE IDEAS — NOT LOCKED — TO DISCUSS
Logged possibilities, not on the current build list. Nothing here is a
commitment. Revisit when revenue supports it.

REMINDER: THIS FILE IS UPDATED AT THE END OF EVERY SESSION, along with the
other four. See the lock in locked-decisions.md.

================================================================
THE CONTINUITY LIBRARY — upload a finished book
Conceived 15 August 2026. REACHED AGAIN INDEPENDENTLY 31 August 2026,
from the humaniser conversation. AND A THIRD TIME 16 SEPTEMBER, from the
import. NOT STARTED. Needs step two to exist.
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

AND ON 16 SEPTEMBER IT ARRIVED A THIRD TIME, no longer as an idea but as a
thing he actually wants to do this week: Rapscallion book one finished,
book two half written, and a request to put book one into the platform.
THE SAME IDEA REACHED THREE TIMES FROM THREE DIRECTIONS IN A MONTH is
about as strong a signal as a solo project gets. IT IS NO LONGER A FUTURE
IDEA IN ANY MEANINGFUL SENSE — the front half of it is being built. What
remains here is the CHECKING, which is the half that needs the factual
layer.

WHERE IT BELONGS: THE LIBRARY, not the Plot Mapper. CONFIRMED 16 SEPTEMBER
when the import's home was decided on exactly this reasoning. It is a
SOURCE the whole project reads from, not a screen the writer works on.

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
   facts it contains — WHICH IS PRECISELY KEV'S SITUATION WITH BOOK TWO.
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
NOTE 16 SEPTEMBER: THIS IS THE SAME DOOR AS THE BOUNDARY QUESTION. The
point of upload is where both belong: whose book is this, and what are you
intending to do with it. One quiet note at one moment, covering both.

THE MACHINERY IS SHARED. FOUR separate items need the same thing — a way
to take an uploaded manuscript and read it: this, the IMPORT (formerly the
series bible import — NOW BEING BUILT), the PUBLIC PRESS, and the
post-launch AI INFERENCE FROM AN IMPORTED MANUSCRIPT. Build one and the
others are nearly free.
*** AND THE FIRST OF THE FOUR IS NOW BEING BUILT. Whatever the import does
about file formats, chapter finding and reading a book in one pass, the
other three inherit. Build it as though all four depended on it, because
they do. ***
THE OPEN QUESTION THAT RAN ACROSS ALL FOUR IS NOW ANSWERED: THE WRITER
CONFIRMS. Nothing lands in Characters until it has been seen and ticked.
See the muster in current-state.md and the lock in locked-decisions.md.

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

A HARD LIMIT CARRIED OVER FROM THE SERIES BIBLE ENTRY, and it applies to
any style work: ADA CANNOT READ A WHOLE NOVEL EVERY TIME PROMPT IS
PRESSED. Style reference must be A DISTILLED THING — the sense of the
sentences, the rhythms, the handling of dialogue — produced once and
carried, never the book itself. THE IMPORT'S READ IS WHERE THAT
DISTILLATION WOULD BE MADE, if it is ever wanted.

================================================================
DELIVERED OR SUBSTANTIALLY CHANGED SINCE THIS FILE WAS LAST WRITTEN
================================================================

THE SERIES BIBLE IMPORT — MOVED OUT OF THIS FILE (16 September). It is
being built, as THE IMPORT, and it turned out to be a different thing from
what it had been called. Full write-up in current-state.md; six stages,
and the muster is the one that matters.
WHAT IT KEPT FROM THE ENTRY THAT USED TO SIT HERE: the framing worth
keeping, which is that it is THE WRITER TEACHING ADA THEIR OWN VOICE FROM
THEIR OWN BOOKS — not the AI imposing a style but the exact opposite, and
arguably the strongest Proauthorist thing on the platform.
WHAT REMAINS OPEN AND CAME WITH IT: THE BOUNDARY. The writer's own books,
yes. Someone else's uploaded in order to write like them is a different
thing entirely. Raised twice now and deliberately settled neither time.

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
NOTE 16 SEPTEMBER: THE IMPORT IS THE FASTEST ROUTE TO A FULL PERSONAL
DICTIONARY THERE HAS EVER BEEN. A book read for its characters and places
is a project's proper nouns arriving in one go, already spelled the way
the writer spells them.

SMART ENTITY ASSIGNMENT / HOT-KEY TAGGING — LARGELY BUILT (15 August)
The 8 June seed was: highlight a word, hit a key, assign it as Character /
Location / etc. That is now the Plot Mapper's F2.
WHAT WAS BUILT, against what was specced:
  · Write freely, then a hot key catches the phrase — YES, F2.
  · Extending a partial catch — YES, and better than specced: the
    selection GROWS OUT TO WHOLE WORDS by itself.
  · A menu offering the TYPE — YES, all sixteen sections in four columns.
  · A record is a THING, not a string: one CANONICAL name + ALIASES —
    YES. This is ALSO CALLED.
  · ERR TOWARD ASKING, never guessing — YES, and further than specced:
    suggested aliases appear as faint dashed pills the writer accepts or
    sets aside, and a rejected one goes quiet without being lost.
  · A QUIET MARK in the prose — YES, a dashed line beneath in family
    colour, with a Details switch.
WHAT IS NOT BUILT YET:
  · Picking an EXISTING record from a list. F2 always makes a new card.
  · The database filling ITSELF as you write.
  · Ada-assisted offers when AI is on.
All three need the entity store — step two.
NOTE 16 SEPTEMBER: "PICKING AN EXISTING RECORD" HAS JUST BECOME MORE
IMPORTANT. Once a book has been imported, a project already HAS a cast
before the writer types a word — so F2 making a new card every time would
start producing duplicates of characters that are already there.

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
NOTE 16 SEPTEMBER: THE AUDIO ONES NOW HAVE SOMEWHERE TO LIVE. Supabase's
file store holds any file — audio, video, images — so audiobook and radio
play output is no longer blocked on "where would it go". Only on being
built. WORTH CHECKING ON THE DAY: the maximum size for a single uploaded
file, which is generous but is the one limit a long audio file might meet.

PLATFORM — FUTURE FEATURES
Six-tone time-of-day theme system — designed, not built.
Scrivener .scriv importer — Phase 2 priority. NOTE: this is the same
family as the import. A .scriv file is a folder of text plus metadata, so
it is a WAY IN rather than a new machine — stage 2 of the import's six,
wearing a different coat.
World Anvil JSON import. Same note.
AI inference from an imported manuscript — pre-filling setup fields. See
the shared machinery note above.
Collaborative editing with live cursors. NOTE 16 SEPTEMBER: this was
impossible while everything lived in one browser. With a server behind the
platform it becomes merely hard. Not a reason to build it; a reason to
know it is no longer barred.

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
the continuity check to work at all.
NOTE (16 SEPTEMBER): AND NOW FROM A THIRD DIRECTION. The import needs
somewhere to put the facts it extracts, and long prose fields throw away
exactly the structure that made them worth extracting. THE FACTUAL LAYER
IS THE IMPORT'S TARGET. See thinking.md — it is well past being a future
nicety.

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
3. THE CONTINUITY LIBRARY — above. Its front half is being built.
4. THE CHECKER — a punctuation checker whose text never leaves the
   machine. Built to Build 12; see current-state.md. It belongs on this
   list because "your manuscript never leaves your computer" is a claim
   Grammarly structurally cannot make.
   NOTE 16 SEPTEMBER: MOVING THE PLATFORM'S STORE TO SUPABASE DOES NOT
   WEAKEN THIS, but it does make the wording matter. The claim is about
   the CHECKER — what it is handed is checked in the browser and goes
   nowhere. It is not a claim about where the manuscript is stored. KEEP
   THE TWO APART IN EVERY SENTENCE WRITTEN ABOUT IT, because blurring
   them would be easy and would cost more than it gained.

ALL FOUR DRAW FROM THE SAME WELL: A PROJECT THAT KNOWS ITS OWN PROPER
NOUNS. The spell checker needs it. The language creator fills it. The
continuity library reads it. The checker's learning list is the same
shape — the writer's own corrections, remembered against this project.
AND A FIFTH ROAD ARRIVED 16 SEPTEMBER: THE IMPORT FILLS THE WELL IN ONE
GO, from a book the writer has already written.
WHICHEVER IS BUILT FIRST SHOULD BUILD THAT WELL PROPERLY — and the import
now looks like being the one that does.

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

A SCHEDULED KEEP-ALIVE PING TO SUPABASE — considered 16 September and set
aside. Free projects pause after seven days of inactivity, and a timed
ping from Vercel would keep one awake. It cannot come from inside InkySwot
(the app only runs when a browser has it open, and the problem is
precisely the weeks when nobody opens it), and it works against the terms
of the free tier rather than within them. KEV'S ANSWER REPLACED IT: a
reminder to HIM to open the platform, which is real use and needs no
disguise. THE PRINCIPLE IS WORTH MORE THAN THE CASE — A NUDGE TO THE
WRITER, YES; A THING PRETENDING TO BE THE WRITER, NO.