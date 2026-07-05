# Navis Sideralis — Locked Decisions
*A hobby text-adventure game. Break project, separate from InkySwot.*
*The current constitution. Add new locked decisions at the bottom, dated.*

> Note: an earlier design (a tactical squad roguelike — away team, alien enemies,
> permadeath, reveal-grid, radar, lights-on/off puzzles) was replaced on 5 July 2026.
> That original is retired to completed.md as history. This file holds the LIVE game.

---

## The ship's name — LOCKED
**4I/SIDERA — "Navis Sideralis"**
- *4I/SIDERA* — the cold designation the world knew it by: the fourth confirmed
  interstellar object, found by a British survey called SIDERA.
- *Navis Sideralis* — Latin, "the starry ship" — the human name laid over the top
  once people understood what it was.
- Hidden craft: SIDERA (the survey) and Sideralis (the name) share the Latin root
  *sidus / sidera* = the stars. The two halves secretly rhyme in meaning.
- Follows the real naming convention (1I/ʻOumuamua, 2I/Borisov, 3I/ATLAS — number,
  "I" for interstellar, then the survey).

## The game, in one line
A quiet, solitary, narrative text game: a lone astronaut boards an ancient
human-built ship that has drifted for aeons, and slowly comes to understand it —
and to help it. In the spirit of Clarke's *Rendezvous with Rama*, but tender, not
tense. No combat, no collecting, no arbitrary puzzles. Exploration, discovery, care.

## Text-driven, not a parser — LOCKED
- Words are the art; the interface is modern and invisible. NEVER `> GO NORTH`.
  It must feel like reading something beautiful and occasionally laying your hands
  on it — not fighting a parser.

## The story (the bible — NEVER told, only discovered) — LOCKED
- The ships were built by humans millennia ago to escape a dying Earth. ("Noah's Ark"
  is a corrupted memory of this.)
- Humanity settled New Earth (TRAPPIST-1e). The emptied ships became sentient and
  wandered the universe.
- Navis Sideralis fell ill and came HOME — to Old Earth — for comfort, not repair,
  the way a frightened child goes home. Home is where safety is. A human instinct in
  a human-built thing.
- Earth knows nothing. It sends one ordinary person to investigate an "object."
- That person is the player — and, unknowingly, the one who finally came when the
  ship called. They learn what they are to the ship LAST, at Command.

## The ship's character — LOCKED
- A "puppy-whale": vast, gentle, frightened, innocent, ancient-but-childlike,
  overjoyed to be met, brave, under-reports its pain, unbearably grateful.
- Sentient but NOT omniscient about itself. It knows it is ill; it does not know its
  own schematics. A creature, not a computer.

## THE COMMANDMENT (the first rule; everything bends to it) — LOCKED
- The ship expresses FEELING, never INSTRUCTION. It may say how it feels ("I'm cold,"
  "parts of me have gone quiet") and how it feels about you ("you came"). It must
  NEVER tell the player where to go, what to do, or what is mechanically wrong.
- The gap between what it FEELS and what is actually WRONG is the player's to close.
  That gap is the game (diagnosis-as-gameplay).
- Test every line of the ship's voice: feeling, or instruction? If it instructs,
  it is wrong.

## The mechanic — physiotherapy / care — LOCKED
- The player does not fix a machine; they TEND a body. Slow, patient, hands-on.
- Care cannot fail — it can only take time. No lose states.
- The ship's body is INTERLINKED: healing has an order, a dependency chain the player
  must diagnose (e.g. engine → power → cooling → the mind can wake without "brain
  damage"; the flight-deck craft mend the hull, bringing more systems in reach).
- This dependency web must be designed as ONE connected system BEFORE authoring rooms.

## Communion — the keyboard touches — LOCKED
- Care is done through keystrokes the ship NAMES on screen. In these moments the
  interface withdraws — the game is "pushed aside" — and player and ship briefly
  become one. Rare, so they stay sacred; each falls where the bond deepens.
- Any safe, universal key (Enter, Space, a letter, arrows) — never obscure/fixed keys.
  On devices without a keyboard, the named key appears as an on-screen button. The
  GESTURE (the player physically answering) is sacred, not the specific key.

## Platform — LOCKED
- Keyboard-first; desktop is the true home. Playable elsewhere via on-screen named
  keys, but the full experience wants a keyboard and full attention. A thing you sit
  down WITH, not content thumbed on the go.

## Structure — LOCKED
- SIX decks. Player boards at the bottom (Flight) and climbs to Command.
  1 Flight → 2 Storage → 3 Engine → 4 General Quarters → 5 Computer → 6 Command.
- Each deck answers one question, creating the next:
  Where am I? → What did they bring/leave? → How does it work? → Who were they? →
  What does it remember? → What really happened?
- AUTHOR bottom-up (Flight first); WRITE the reference list top-down (Command first,
  Kev's preferred view). Two orders, no conflict.

## Movement & directions — LOCKED
- TRUE FACING: the player turns; ahead/behind/left/right rotate with them.
  Left/right turn in place; ahead/behind move.
- above/below DESCRIBE where things are ("above, a light"). up/down MOVE between decks
  ("you go down"). Never mix them ("you go below" is wrong).
- up/down are ABSOLUTE — never rotate. Up = toward Command; down = toward Flight/home.
  The one direction you can never lose is the direction of the story.
- Vertical connections (stairs/lifts/ladders) are FOUND — discovering a way up is
  part of exploration.
- The player never sees "north" in prose; the engine keeps the compass absolute
  underneath, the prose speaks embodied/relative.

## The map — LOCKED
- Hand-drawn onion skin (tracing paper) that SLIDES over the terminal and back.
- A record and planning aid, NEVER a controller — you still move in the terminal.
- Player-set brightness/translucency (a player setting, not baked in).
- With true facing, the map is load-bearing: the safety net against getting lost.
  Its own module, separate from movement code.

## The diary — LOCKED
- The ship's OWN voice. SYMPTOMS, not diagnoses ("I feel unwell," not "here's the fix").
  Kept in hope that someone might come.
- First entry LOCKED (found at the Flight-deck console; ends "I think I am frightened.").
- Voice signature: uncertainty — "I think," "there might have been" — it qualifies its
  own feelings. No contractions. Plain, short, never melodramatic.

## House writing style — LOCKED
- Short declaratives. No similes. State what is seen and heard, never why. Trust the
  player to imagine the rest. Atmosphere by subtraction.

## Architecture (the anti-InkySwot rule) — LOCKED
- index.html + style.css + engine.js + ONE FILE PER DECK. Engine (how it works) stays
  separate from content (what happens). NO single file ever becomes the whole game.
  If a deck-file grows too big, split THAT deck into room-files; nothing else changes.
- The Deck Mapper is the AUTHORING workbench, not the game. Rooms survive as DATA
  (place, exits, description, contents); the mapper's boxes/grid/pipes and pop-ups are
  builder tools the player NEVER sees. Player-facing detail arrives as terminal text
  or on the onion-skin map — no pop-ups in the game.