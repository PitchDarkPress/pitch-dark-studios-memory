# NAVIS SIDERALIS — Master Briefing
*The single authoritative file. Hand this whole file to any new chat to bring it
fully up to speed. Everything permanent and load-bearing lives here.*
*Last updated: 6 July 2026*

> **⚠ RULE FOR THIS FILE — read me.**
> This is deliberately ONE file so a new chat never misses vital information.
> The moment it becomes unwieldy — too long to edit comfortably, or slow/error-prone
> to change — **STOP and tell Kev to split it back up** (constitution vs current-state
> vs the throwaway satellites). Do not let it quietly grow into the InkySwot monster.
> Guarding this file's length is part of the job.

---

## 0. What this is
A hobby text-adventure game — a break project, separate from InkySwot.
A quiet, solitary, narrative text game: a lone astronaut boards an ancient
human-built ship that has drifted for aeons, and slowly comes to understand it —
and to help it. In the spirit of Clarke's *Rendezvous with Rama*, but tender, not
tense. No combat, no collecting, no arbitrary puzzles. Exploration, discovery, care.

> An earlier design (a tactical squad roguelike — away team, alien enemies,
> permadeath, reveal-grid, radar, lights-on/off puzzles) was replaced on 5 July 2026.
> The only survivors were the ship's NAME and the Rama-tinged premise. The old design
> is kept as history in completed.md; this file holds the LIVE game.

---

# PART ONE — THE CONSTITUTION (permanent; changes only by deliberate decision)

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
- Voice signature: uncertainty — "I think," "there might have been" — it qualifies its
  own feelings. No contractions. Plain, short, never melodramatic.
- FIRST ENTRY — LOCKED (found at the Flight-deck console):
  > If you read this then I am glad.
  > I think it has been a long time.
  > I stopped counting the days. There might have been a great many of them.
  > I am writing this down so that it is somewhere, in case someone comes.
  > I am cold. I have been cold for a long time, and I have grown used to it — but I do not think I should be this cold.
  > Parts of me have gone quiet. I do not remember when.
  > I am well enough. I do not want to be any trouble.
  > I hope that one day someone will come.
  > I think I am frightened.

## House writing style — LOCKED
- Short declaratives. No similes. State what is seen and heard, never why. Trust the
  player to imagine the rest. Atmosphere by subtraction.

## Visual signature — LOCKED (the face of the game; found 5 July 2026)
The whole visual identity is the ship's condition made visible in the screen itself —
the interface as a vital-signs monitor. Two changes, both earned by the player's care,
both spanning the WHOLE climb, both imperceptibly slow. Symptoms SHOWN, never told —
this obeys the commandment (the screen is the ship being unwell/recovering in front of
you, not the ship instructing you).

- **Temperature — the world warms.** Starts cold: bloodless grey-on-black, the palette
  of something switched off and unwell. As the player tends the ship and climbs, warmth
  seeps back in, resolving by the end into Pitch Dark black-and-GOLD (lamplight). The
  game ends looking like Pitch Dark because the ship, by then, is WELL. The gold is the
  reward for care, not a timer.
- **Pulse — the screen steadies.** The screen is "almost broken" — it flickers. NOT
  madly: mostly steady, then every so often it falters, so it reads as illness, not
  style. The gaps matter as much as the flickers. As the ship is tended, the flickers
  come LESS often — its breath steadying — until by Command the screen is calm. Possibly
  worst where the ship is most hurt (flicker as rough diagnostic) — try, don't promise.

- **THE ACCEPTANCE TEST (the Shaw Theatre dusk).** Kev once did sound at the Shaw
  Theatre, London, on an early digital lighting board: a 20-minute day-into-night fade.
  Across 3 weeks of rehearsal and a 3-week run he NEVER once saw it change — he was
  always surprised when an actor said "it's getting dark, we should go inside." That is
  the bar. The player must NEVER catch the warmth or the flicker-fade moving; they must
  only, near the end, REALISE the world is warm now and the ship hasn't trembled in a
  long while. The realisation should arrive from OUTSIDE the effect (the ship says
  something; the map's paper looks warmer than remembered), the way it came from the
  actor's mouth, not the lights. **If the shift is ever perceptible in the moment, it
  is too fast.** Kev is the acceptance test — he has 30 performances of "correct" in his
  memory; if he catches it moving, slow it down.

- **How to get near Shaw-invisibility on a screen (technique):** keep the colour
  distance MODEST; spread it over the whole game; put the warmth in TEXT on near-black
  (black doesn't band; small coloured text on black hides drift best — we're warming a
  candle, not fading a sky); lay a faint film-GRAIN/dither over everything to break up
  8-bit banding (also suits the old/analogue mood). Both effects are a slow tide, never
  a switch, never a rhythm.
- **Both effects are PLAYER-ADJUSTABLE** (turn-down / off). Illness you can witness,
  never illness inflicted — the flicker must never become a strobe (photosensitivity),
  and anyone uncomfortable can still the ship's tremor without losing the game. Same
  kindness as the map's brightness setting.

## What a machine feels when it is sick — note
Not circuitry. The ship feels sick the way a PERSON does, because humans built it and
it caught feeling from them: parts gone quiet and it can't remember when; a cold it has
grown so used to it forgot wasn't normal; unsure of its own memory; a brave face; not
wanting to be any trouble; frightened and far from home, hoping someone comes. That is
the whole game in one line — a machine that learned to feel sick the way we do.

## First room text — LOCKED (Flight deck, the hangar you board into)
  > The hangar is vast. The walls are lost in the dark.
  > Strange craft stand in rows, black, silent and still.
  > Lights, high up, are low.
  > There is no noise.
  > In the distance, a light is flashing.
- Then a three-turn walk toward the light (world responds each step) reaches the
  console: "PLEASE PRESS ENTER" — the ship names the key. Pressing it triggers the
  first communion (game withdraws) and the diary types out in the dark.

## Architecture (the anti-InkySwot rule) — LOCKED
- index.html + style.css + engine.js + ONE FILE PER DECK. Engine (how it works) stays
  separate from content (what happens). NO single file ever becomes the whole game.
  If a deck-file grows too big, split THAT deck into room-files; nothing else changes.
- The Deck Mapper is the AUTHORING workbench, not the game. Rooms survive as DATA
  (place, exits, description, contents); the mapper's boxes/grid/pipes and pop-ups are
  builder tools the player NEVER sees. Player-facing detail arrives as terminal text
  or on the onion-skin map — no pop-ups in the game.

---

# PART TWO — CURRENT STATE (overwrite this part each session)

## Where we are (5–6 July 2026)
The whole soul AND the visual signature of the game are now designed and locked (see
Part One: the warmth, the flicker, the Shaw acceptance test). It is coherent. Several
working prototypes exist; no production engine yet.

## What's actually built
- **Cold open** — the docking/hatch terminal sequence.
- **Deck Mapper** — authoring workbench. Reordered to the six decks; DECK codes
  editable; anchor now marks the ACTIVE deck.
- **Onion-skin map** — tracing-paper chart that slides over the terminal; player-set
  translucency. Prototype locked (roll-open tried and rejected).
- **Console-communion prototype** — dark hangar → walk north → PLEASE PRESS ENTER →
  game withdraws → diary types out.

## Next piece
Rewrite the prototype's movement to the agreed language (true facing;
ahead/behind/left/right; above/below to describe, up/down to move), then scaffold the
engine (index.html + style.css + engine.js + one file per deck) and author Flight.

---

# PART THREE — OPEN THREADS (not yet locked; overwrite as they resolve)

- **Voice register.** Ship learned English from Earth's old broadcasts (radio bubble
  ~100 ly; TRAPPIST ~40 ly, so it heard mid-20th-century Earth). FROZEN in that older
  register, or MODERNISING as it nears Earth? Colours the ending.
- **What "helping" is.** Repair, or being-known? Leaning: a creature this old may not
  be "fixable" — it settles because it is finally found and understood. Care as witness.
- **The diary — one entry or many?** Leaning: scattered up the decks, same voice,
  a little more frightened/hopeful as you climb.
- **Where the brightness control lives** (settings / on the sheet / a preset key).
- **The dependency chain, in full.** Principle only so far. Must be designed as one
  connected system BEFORE authoring rooms. Root so far: power/Engine (heart) →
  cooling → the mind can wake.
- **Prototype tuning:** does the withdrawal into the dark feel like CONTACT? Is the
  diary's pacing right?

---

# PART FOUR — BUILD ORDER & REAL-WORLD JOBS

## Build order (agreed)
1. **Movement prototype** — true facing; the new direction language; finding a way up.
   It underlies every room, so prove it first.
2. **Scaffold the engine** — index.html + style.css + engine.js + first empty deck file.
3. **Author Flight (Deck 1)** — real rooms into the mapper, fed to the engine.
- Also: design the FULL dependency chain as one system before authoring beyond Flight.

## Real-world jobs (only Kev can do these)
- **Domain** — choose/register a name (standalone, e.g. navissideralis.*, or under
  Pitch Dark). Claude can check availability given a shortlist.
- **GitHub** — new repo in the PitchDarkPress org (e.g. navis-sideralis); free hosting
  via GitHub Pages; point the domain at it later. Claude can give exact steps.