File: inkyswot/future.md
Last updated: 8 June 2026

FUTURE IDEAS — NOT LOCKED — TO DISCUSS
These are logged future possibilities, not on the current build list.
Nothing here is a commitment. Revisit when revenue supports it.

ADA — FUTURE CAPABILITIES
Full voice interaction — conversational speech input/output
beyond current Read Aloud.
Braille support.
Multi-voice/actor audiobook production.
Radio play production with multiple cast voices.
AI voice profiles for characters.

PLATFORM — FUTURE FEATURES
Six-tone time-of-day theme system — designed, not yet built.
Scrivener .scriv importer — Phase 2 priority.
World Anvil JSON import.
AI inference from imported manuscript — platform reads manuscript
and pre-fills setup fields. Revisit when revenue supports it.
Collaborative editing with live cursors (Google Slides-style).

SMART ENTITY ASSIGNMENT / HOT-KEY TAGGING — the writing-as-spine idea
(expanded 8 June; STILL ROUGH, NOT LOCKED — needs its own clean spec,
on a fresh head, before any of it is built. Build the live-keyboard
parts static-first; never spec moving behaviour by description alone.)
The original seed: highlight any word, assign it as Character / Location
/ etc, dropping you into the relevant screen. The 8 June thinking grew
that into a fuller shape:
- THE SPINE IS A LOOSE, REORDERABLE TIMELINE OF EVENTS — you write the
  things that HAPPEN ("A man goes to work"). As you write, the
  people/places/things you mention ("the man — Kev", "the work — the
  office") are caught and FILED to the right-side menu as entities to
  reference later. The database fills ITSELF from the writing — no blank
  forms first.
- THE HOT-KEY MECHANISM (clearest part):
  · Write freely. Hit a HOT KEY — it grabs the LAST WORD.
  · BACK-ARROW extends the highlight word-by-word (forward-arrow pulls
    back if you overshoot) for multi-word names ("the Manor House").
    [LIVE-KEYBOARD MECHANISM — needs a selection mode + an Escape route;
    build static-first.]
  · A menu offers the TYPE (Character / Location / Event …); pick one →
    a list of existing records of that type (Kev / Sara / Claude …) +
    "New: …". Pick a record, or New to seed a fresh one filed to the
    side menu.
  · A record is a THING, not a string: one CANONICAL name + ALIASES. The
    word you tagged ("the Manor") becomes an alias pointing at the record
    (Manor House). This unties cross-tagging (Manor House / the Manor /
    the House = one record).
  · DIAL: the system must ERR TOWARD ASKING (writer-triggered, accurate,
    never mis-files) over guessing (smooth but wrong). Auto-detecting
    aliases is dangerous — suggest, never decide.
- A known entity carries a QUIET MARK in the prose so the writer knows
  there are details behind it (a faint section-colour tint and/or a
  small mark; must NOT rely on colour alone; must stay calm on the page).
  Open: always-visible vs reveal-on-hover.
- BRIEF: "intuitive and unobtrusive", and forgiving for a dyslexic
  writer — never make spelling/precision the price of being understood.
  Ada-assisted offer when AI is on; one-tap manual when off. Both.

ONION-SKIN / LAYERED WRITING SURFACE — (8 June, ROUGH, NOT LOCKED)
One surface built up in passes, same notes throughout: a loose mind-map
of events → add a TIMELINE overlay (reorder chronologically) → add a
CHAPTERS overlay → add a SCENES overlay. NB the conceptual knot: it is a
FUNNEL not even layers — wide/loose at the top (all ideas), narrowing to
events → chapters → scenes at the spine; characters/locations don't
vanish, they become things events reach into (the pop-up). Open: how this
surface meets the WHEEL (the WP is already the wheel); whether SYNOPSIS
is this surface at a looser zoom. Closely tied to the hot-key tagging
idea above — likely one design, not two.

SYNOPSIS → WP TRANSITION — (8 June, ROUGH, NOT LOCKED)
"Convert when happy" — the arrow from the Synopsis/Plot-Mapping stage to
Chapters/Scenes. The fork: a one-time POUR (loose notes become
chapters/scenes; the corkboard's job is done) vs a LIVING LINK (one set
of data, two views, change-one-changes-the-other). "Nothing entered
twice" leans to the living link. Unsettled.

MANUSCRIPT VIEW — TOGGLE (8 June; a WRITER COMFORT, agreed in principle)
A toggle in the WP that strips the chrome (running heads, stave
headings) so the writer can read the book as a continuous manuscript.
NB: a comfort, NOT a security feature — it deliberately makes the text
easier to read whole (and on-screen text can't be protected in a browser
anyway). Display-level only (hide chrome / butt sheets up); TRUE flowing
pagination remains the bigger deferred build.

Emotional Map as literal map — the DCW Emotional Map curve
expands into a full cartographic view of a character's emotional
journey through the story. High ground for intensity. Low ground
for numbness. Rivers for flow. Storms for crisis.
The word Map was chosen with this in mind.
Not on the current build list. This is the destination the word
points toward.

Write Screen Customisation Remote — the main writing area
must be fully customisable by the writer. Background colour,
text colour, font, size. Critical accessibility feature —
dyslexic writers in particular benefit from non-white backgrounds
(blue screen / white text as one proven example).
Controls delivered via a floating remote control — styled like
a TV remote. Moveable. Theatrical. Adds to the InkySwot theatre.
Full detail to be worked out by Kev. Not on current build list.

Stickies — floating post-it style notes for capturing quick
thoughts without breaking writing flow. Colour customisable
by the writer. Moveable. Persistent until dismissed.
The writer comes back to them when ready.
Distinct from the Index Card system — Stickies are unstructured,
instant, and disposable. Index Cards are structured and connect
to the database. Not on current build list.

Two pre-filled demo books — fully-populated, every-section-complete
demo PROJECTS of "A Christmas Carol" and "The Wind in the Willows",
so a new user can land inside a finished world and see at a glance how
InkySwot works. An empty app never explains a world-building tool; a
finished one explains itself — click any character, location, scene;
turn the wheel through real scenes; open one and read it.
Both books are out of copyright (Dickens 1843; Grahame 1908), so the
text and characters are free to use. A demo = a normal project,
pre-filled.
UPDATED 8 June 2026 (this OVERRIDES the earlier "ideally read-only"):
the demos are FULLY EDITABLE — let the new user PLAY; the more they
poke, add and change, the more comfortable they get and the more it
feels like theirs. Pristine state is protected by a RESET ("reset
demo"), not a lock; and a SAVE-AS-YOUR-OWN-COPY lets them keep what they
made (working assumption: save = save as a copy → the demo stays a demo,
their version becomes a new project in My Projects).
Build "A Christmas Carol" first as the template (its bones are already
in the wheel mockup), then "The Wind in the Willows" to the same pattern.
DEPENDS ON: the app shell and the sections being final — the demo must
mirror the real thing exactly, so build it AFTER Step 1 (fill the
database once). Open question for build time: whether the in-scene prose
is written/adapted by Kev or sample-generated.
Confirmed feasible 4 June 2026. Editable/reset/save decided 8 June 2026.
Not scheduled. Not a lock.

PLATFORM — FUTURE PRODUCTS
Newspaper / magazine platform — separate product.
Rights marketplace — writers sell and license rights.
InkySwot for screenwriters — dedicated mode.
Educational version — universities and writing schools.
Partnership with writing communities — NaNoWriMo etc.

================================================================
CONSIDERED AND DROPPED (kept so it is not re-proposed)
================================================================
MAPS & GEOGRAPHY — a line-glyph "SimCity"-style stamp composer (drag
1×1 snap-together pen-and-ink tiles to build a map), a separate
world-map tile set, and era-grouped building elevations. Explored at
length 8 June 2026, then DROPPED: a map/picture maker pulls against what
InkySwot IS — a writing platform, assisted not generative. It makes
pictures, not a better book. Charming, but not right here. NOT to be
revisited. (Generation prompts and tile lists were drafted in chat; not
retained as build targets.)