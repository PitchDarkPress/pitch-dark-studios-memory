# Navis Sideralis — Current State
*Overwrite each session. A snapshot of where the game is right now.*
*Last updated: 5 July 2026*

---

## What this is
A hobby text-adventure game — a break project, separate from InkySwot.
A quiet, solitary, narrative game about a lone astronaut who boards an ancient
human-built ship, Navis Sideralis, and slowly comes to understand it — and to
help it. Not combat, not collecting, not arbitrary puzzles. Exploration, discovery,
care.

## The heart of it (settled today)
The ship is ours — built by humans millennia ago to carry humanity from a dying
Earth. Its people were long ago settled on New Earth (TRAPPIST-1e). The empty ships
became sentient. One, Navis Sideralis, fell ill and came *home* — to Old Earth — the
way a frightened child goes home, because home is where safety is. Earth knows
nothing; it sends one ordinary person to look at an "object." That person is the
player — and, though neither they nor Earth know it, the one who finally came when
the ship called.

The ship is a puppy-whale: vast, gentle, frightened, innocent, overjoyed to be met.
The player is its doctor/physio, not its mechanic. The ending leans hopeful: it came
home, and someone was there.

## Structure
Six decks, built bottom-up (the way the player climbs), viewed top-down in our notes:
- Deck 6 · Command — *What really happened?*
- Deck 5 · Computer — *What does the ship remember?*
- Deck 4 · General Quarters — *Who were they?*
- Deck 3 · Engine — *How does this thing work?*
- Deck 2 · Storage — *What did they bring / leave behind?*
- Deck 1 · Flight — *Where am I?* ← we build here first (the prologue/docking deck)

## What's actually built
- **Cold open** — the docking/hatch terminal sequence (earlier).
- **Deck Mapper** — the authoring workbench (not the game). Reordered to the six decks;
  DECK codes editable; anchor now marks the active deck.
- **Onion-skin map** — hand-drawn tracing-paper chart that slides over the terminal;
  player-set translucency; a record you consult, never a controller. Prototype locked.
- **Console-communion prototype** — dark hangar, walk north, PLEASE PRESS ENTER, the
  game withdraws, and the ship's first diary entry types out in the dark.
- **The ship's first diary entry** — written and locked (ends "I think I am frightened.").

## Next time — the obvious next piece
Rewrite the prototype's movement to the agreed language (true facing;
ahead/behind/left/right; above/below to describe, up/down to move), then scaffold the
engine (index.html + style.css + engine.js + one file per deck) and author Flight.

## Open threads
See thinking.md — voice register (frozen-old vs modernising), whether "helping" is
repair or being-known, one diary entry or scattered per deck, where the brightness
control lives.