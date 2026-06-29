# Navis Sideralis — Current State

*Overwrite each session. A snapshot of where the game is right now.*
*Last updated: 29 June 2026*

---

## What this is
A hobby text-adventure game — a break project, separate from InkySwot.
An escape-the-room game set aboard an ancient alien ship, 4I/SIDERA
("Navis Sideralis"), that has drifted through space for aeons.

## Where we've got to
The whole design is roughed out and the big decisions are locked (see
locked-decisions.md). In short:
- Seven decks, one map per deck, you only see the deck you're on.
- Grid map that reveals itself square by square and stays revealed.
- Arrow-key movement, turn-based: you move, aliens step toward you, redraw.
- "?" on each square opens the room as theatre plus an info panel.
- Radar senses three decks (yours, above, below) but seeing isn't reaching.
- Five-person away team, chosen at the start, each with one ability, no doubling up.
- Everyone can die; five deaths = game over; nobody gets stronger; humans can always
  win the slow hard way.
- Optional carried AI: can't be stabbed, but radiation/EMP make it slower, never dead.
- Puzzles have two states only — lights on (right specialist) or lights off (wrong
  person) — same puzzle, different help.

## Nothing is built yet
This is all design. No code exists. The agreed first build, when the time comes, is
the smallest core that proves the spine: the start square on a deck grid, arrow-key
movement revealing new squares, and the turn heartbeat running. Radar, "?" rooms,
team and puzzles all come after that core moves correctly.

## Next time — the obvious next piece of thinking
The list of five crew abilities (job titles still in pencil). Everything it has to
satisfy is already locked, so it should be a clean session.

## Open threads
- Exact five abilities, and whether any role titles change.
- Whether the 5-item carry limit stays at five.
- A leftover from an early mock-up: "connections, not compass directions" — probably
  moot now there are real decks and a grid, but noted.
