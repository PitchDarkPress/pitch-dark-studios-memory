[README.md](https://github.com/user-attachments/files/27901319/README.md)
# Pitch Dark Studios — Memory

The central knowledge base for all Pitch Dark Studios operations.

## What this is

This is the persistent memory system for Pitch Dark Studios. It stores
project information, decisions, session notes, and current state for
every division — so that AI collaborators (Claude, ChatGPT) can be
briefed instantly at the start of any session without losing context.

## Starting a new chat session

Paste this as your first message in any new Claude chat:

"I am Kev, running Pitch Dark Studios. Our database is at
pitchdarkpress.github.io/pitch-dark-studios-memory — please read
the README and the Memories section, then we will work on [DIVISION]."

Replace [DIVISION] with the project you are working on.

## Giving AI their memory back

1. Open the admin panel at pitchdarkpress.github.io/pitch-dark-studios-memory
2. Click the division you are working on in the left panel
3. Click `current-state.md`
4. Click COPY FOR CLAUDE
5. Paste into your Claude chat

Also load `memories/current-state.md` for cross-project context.

## Saving a session note

At the end of each session Claude writes a session note.
1. Click SESSION NOTES tab in the right panel
2. Select the correct division
3. Paste the note Claude wrote
4. Click SAVE SESSION NOTE

## Structure

- `core/` — Locked decisions, branding, people
- `memories/` — Cross-project context and session memory
- `the-room/` — The Room interactive environment
- `proauthorist/` — Proauthorism philosophy and site
- `pitch-dark-press/` — Publishing imprint and books
- `inkyswot/` — Writing platform
- `pitch-dark-publishing/` — Digital publishing division
- `pitch-dark-broadcasting/` — Radio, television, recording
- `rd/` — Research and development

Each division contains:
- `current-state.md` — Where things are right now
- `future.md` — Ideas and plans not yet in development
- `sessions/` — Dated session notes written by AI collaborators

## Admin panel

Live at: pitchdarkpress.github.io/pitch-dark-studios-memory

The Chat with Claude tab lets you talk to Claude directly with database
context loaded automatically. Select a division, click Load, then ask anything.

## Purpose

This repository is the persistent memory layer for Pitch Dark Studios.
It is read and written by AI collaborators (currently Claude, later ChatGPT)
so that knowledge is never lost between sessions.

Human-readable at all times. Owned entirely by Pitch Dark Studios.
