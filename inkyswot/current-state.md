File: inkyswot/current-state.md

File: inkyswot/current-state.md
================================================================
*** THE OVERVIEW SCREEN — REBUILT & LIVE (13 July 2026) ***
(paste-in section — newest at the top; everything below untouched)
================================================================
WHAT HAPPENED: a full BUILD session on the OVERVIEW screen (the
project-overview pocket). Every change below is DONE, SIGNED OFF, and
LIVE at app.inkyswot.com. Kev drove most of the Stitch/Publish himself.

THE JOURNEY — CONFIRMED (the writer's path, start to finish)
This was settled plainly this session so board/wheel work has a spine:
  1. NEW PROJECT — title + genre, Save. (Fine as is.)
  2. OVERVIEW — the screen we just rebuilt. Writer fills it, Save Overview.
  3. THE SYNOPSIS BOARD (the rotated board, code-board-rotated.html) —
     the WIDE end of the funnel. Tracks as columns, cards, spine of
     chapters/scenes. Where the writer builds the shape and fills fields.
     Chapters are created here, each with its NUMBER.
  4. THE GATHERED, ACTIVE SYNOPSIS — what the writer types on the board
     BECOMES written synopsis at three grains: SCENE synopsis, CHAPTER
     synopsis, and an OVERALL synopsis GATHERED from below. ACTIVE:
     change anything at any level and it flows through the whole, live,
     never a frozen copy. The CHAPTER NUMBERS are the shared address that
     keeps board and page pointing at the same chapter — so a chapter
     created on the board already exists on the page with its synopsis in.
  5. THE WHEEL / THE PAGE (the wheel file) — the CLOSE end. Page centre,
     scene menu left, wheel right. Where the book is written scene by scene.
  RUNNING UNDER ALL: the LEFT MENU + the IN-PAGE LIST stay live — create
  or add an entity and it appears in BOTH at once, each opening as a pop-up.
- THE BUTTON that turns the board INTO the wheel view (Kev's "SOMEHOW at
  the click of a button") IS the KEYSTONE / funnel data model. Same beast
  as always: one record must carry board position + timeline order +
  chapter/scene home at once. Still the next real build (see NEXT).
- STILL OPEN from this walk-through: when the board becomes the wheel, can
  the writer FLIP BACK to the board (mixdown never destroys tracks), or is
  it a one-way move? (My steer: flip-back, per the mixdown. Not confirmed.)
- KEV'S GOAL, stated plainly and to hold to: something so intuitive a
  writer thinks "why aren't all writing platforms like this?" The whole
  promise lives on ONE feeling — the writer types in one place and TRUSTS
  it has flowed everywhere, without checking. The day they stop checking
  is the day it feels like magic. Death by a thousand small frictions is
  the enemy. Build smallest honest picture first, judge with the eyes.

OVERVIEW — WHAT WE CHANGED (all live)
- STRAP LINE: was a multi-line textarea with Prompt + Expand. Now a
  SINGLE-LINE box, Expand removed, Prompt kept. PLUS a HOVER-SCROLL: when
  the text is longer than the box, hovering the field gently drifts it so
  the hidden end slides into view, pauses at the end, drifts back, and
  SETTLES to the start when the mouse leaves. Holds DEAD STILL while the
  field is focused (so it never fights editing). Gentle, not a ticker
  whizz (SPEED 34px/s, PAUSE_ENDS 700ms, no pause on the FIRST move).
  Reason it was needed: Ada's Prompt drops in a long line whose end was
  hidden in a fixed single-line box.
- COVER & OUTLINE GROUP: REMOVED WHOLE — both the cover upload and the
  Outline textarea. (Cover returns in the PUBLISH section later.)
- FORMAT dropdown: REMOVED (Genre covers it). The only Format items Genre
  lacked (Screenplay, Poetry Collection) folded into Genre.
- TARGET AUDIENCE: REMOVED (Classification covers who it is for).
  Classification now sits alone on its row.
- WORD COUNT GROUP — now has the CLEVER STEERS (see next section).
- GENRE — now a CUSTOM InkySwot dropdown (see COMING-SOON PATTERN).

THE CLEVER WORD COUNT STEERS (Overview, live)
Both TARGET and CHAPTERS boxes guide the writer, genre-driven, overridable.
- TARGET box: type-a-number box that AUTO-COMMAS as you type (80000 -> 
  80,000). It is a TEXT box (not number) so commas can show; the maths
  reads digits only. Under it, a caption: "A novel runs ~=80,000 words"
  then a second plain line "You can change this to suit your needs".
- CHAPTERS box: shows a SUGGESTED number, worked from the target words
  divided by a genre-appropriate words-per-chapter. If no target yet, a
  genre FALLBACK number. The suggestion sits in GOLD; type your own and it
  turns to plain INK and a small reset arrow (rotate) appears to bring the
  suggestion back. Caption under it: "<n> chapters suits <target> words"
  (or "<n> chapters is typical for a <genre>") then the same "You can
  change this to suit your needs" line.
- CAPTIONS: kept genuinely READABLE (16-17px, near-full ink, upright — NOT
  faint italic). This mattered: Kev is on 28-inch screens and small grey
  italic was unreadable. Readable beats quiet here. Steer line forced to
  ONE line (white-space:nowrap).
- THE HONEST FIGURES (industry norms, checked, reusable):
  words-per-chapter: Novel 3000, Novella 2500, Children's 1500, Non-Fiction
  4500, Crime/Thriller 2000, Fantasy 4000, Sci-Fi 4000, Romance 2500,
  Literary 4000, Historical 3500, Horror 3000, default 3000.
  typical whole-book words: Novel 80k, Novella 35k, Children's 10k,
  Non-Fiction 90k, Crime/Thriller 85k, Fantasy 100k, Sci-Fi 100k, Romance
  80k, Literary 90k, Historical 95k, Horror 85k, default 80k.
  fallback chapters (no target): Novel 25, Novella 12, Children's 10,
  Non-Fiction 15, Crime/Thriller 35, Fantasy 30, Sci-Fi 30, Romance 28,
  Literary 22, Historical 24, Horror 28, default 25.
  RULE OF THUMB behind it: chapters ~= target words / 3000 is a decent
  default across most genres.

THE COMING-SOON DROPDOWN PATTERN (Overview Genre — a REUSABLE idiom)
A plain browser <select> CANNOT grey options elegantly, show a note on
hover, or hold custom behaviour. So the Genre field is a CUSTOM InkySwot-
BUILT dropdown. Pattern, worth reusing wherever formats/features arrive in
stages:
- The FULL list lives in one place; each entry carries a quiet "coming:true"
  flag for anything not yet deliverable. Ready ones show in full ink and
  pick normally; "coming" ones are GREYED and cannot be picked.
- NO marker/text/icon on the greyed rows — the list stays THIN and elegant.
- On HOVER of a greyed row, a small gold-edged POINTER-NOTE pops up beside
  it: "COMING SOON" (mono, gold) + an italic line "<Format> formatting is
  on its way." The note CENTRES itself on the row and its little arrow
  points dead at the row. Fades when the mouse leaves. Clicking a greyed
  row does nothing.
- The dropdown's scrollbar is restyled dark-and-gold (the default XP-look
  bar was wrong).
- WHY GREYED not hidden (Kev's call): the writer sees the full ambition,
  knows nothing's forgotten, but is never let through a door not built yet.
- The CLOCK as a "we're working on this" glyph was considered and dropped
  for the list (keep it thin) — but noted as InkySwot's vocabulary: a
  STILL clock = "coming", a SPINNING clock = "working". Kept for elsewhere.
- GENRES currently flagged "coming" (need specialised page formatting not
  yet built): Audio Drama, Audiobook, Comic Script, Game Script, Graphic
  Novel, Picture Book, Poetry, Poetry Collection, Radio Drama, Screenplay,
  Stage Play, Teleplay. Flip a flag OFF as each format's layout is built.

HOW THE POCKET IS WIRED (so it survives future edits)
- The pocket keeps the corridor's helpers UNTOUCHED: autoSave,
  saveProjectHeader, aiAutofill, aiExpand all still called exactly as
  before. The custom Genre value is written into a HIDDEN input #ph-genre
  (with onchange="autoSave()") so saving works as it always did.
- The NEW parts (custom dropdown, coming-note, word-count steers, strap
  hover-scroll) travel INSIDE the pocket — their own <style> and <script>
  at the foot of the pocket file, scoped with #screen-project-overview and
  using the corridor's colour VARIABLES (var(--gold) etc). Nothing new was
  added to the corridor.
- The floating COMING-SOON note div lives just OUTSIDE the screen div
  (it is position:fixed).

PUBLISH TIMING — A LESSON LEARNED THIS SESSION (important)
- First publish attempt FAILED silently: Stitch wrote the new file
  (254,657 chars) but PUBLISH read the OLD one (252,709) — it grabbed the
  stale stitched file because Publish was clicked before Stitch had fully
  settled. The strap-scroll never reached live.
- THE FIX / THE HABIT: after Stitch, WATCH THE CHARACTER COUNTS. The
  "Wrote index.html (N chars)" from Stitch and the "Read index.html (N
  chars)" from Publish MUST MATCH. If Publish shows the old number, STOP,
  re-Stitch, and Publish again — do not refresh and chase ghosts. Second
  run matched (254,657 both) and it went live correctly.

================================================================
*** THE POCKET-SPLIT REBUILD + THE ENCLOSURE — LIVE (July 2026) ***
(everything below here is the earlier file, untouched)
================================================================
WHAT CHANGED SINCE 17 JUNE: the app is no longer one giant index.html.
It has been carved into a CORRIDOR + POCKETS, stitched back together by a
purpose-built tool called the ENCLOSURE, and the whole rebuild is now the
LIVE app at app.inkyswot.com. This section records that work so a fresh
chat starts already knowing it. NB: this concerns the app's STRUCTURE and
BUILD PLUMBING, not the DCW/mixdown design thinking below — that all still
stands.

THE NEW REPO
- PitchDarkPress/inkyswot-rebuild (PRIVATE) — the home of the rebuild.
  Branch: main. Separate from the live app repo.
- The LIVE app repo is still PitchDarkPress/inkyswot-app — Vercel watches
  it and publishes to app.inkyswot.com on a push to main (a minute or two,
  then hard-refresh Ctrl+Shift+R).

THE ARCHITECTURE — CORRIDOR + POCKETS
- CORRIDOR (corridor.html in inkyswot-rebuild) = the shared shell: header,
  sidebar, ALL the CSS, ALL the shared JavaScript, and empty labelled slots
  where each screen drops in. The slot marker is a comment: <!-- POCKET:id -->
- POCKETS (pockets/ folder) = one HTML file per content screen. Fifteen of
  them: project-overview, events, treatment, chapters, cast, relationships,
  factions, language, locations, buildings, objects, rules, subplots,
  themes, plotthreads. Edit a screen here, on its own, in a short file.
- Three small shared screens STAY in the corridor (not pocketed): projects
  (home), trash, coming-soon.
- IMPORTANT: pockets currently hold each screen's HTML ONLY. The shared
  JavaScript stays whole in the corridor — it was deliberately NOT split,
  to avoid shredding the working script. Splitting the script is a possible
  future job, its own careful task, not yet done.
  (NB 13 July: the Overview pocket now ALSO carries its OWN small style +
  script block for its new custom parts — scoped, using corridor vars. This
  is a fine pattern for screen-specific behaviour; the SHARED script still
  stays whole in the corridor.)
- index.html (in inkyswot-rebuild) = the finished, stitched platform,
  written by the enclosure. This is what gets published to live.

THE ENCLOSURE — THE BUILD TOOL (installed, working)
- Lives in the memory database at core/enclosure.html (next to the bench),
  reachable from a menu button in the admin panel (sits beside CODE VIEW).
- Built like the bench: one HTML page, the GitHub token, the GitHub API.
  Same token as the database — it reaches all the repos.
- WHAT IT DOES (its buttons, top to bottom):
  · IMPORT & SPLIT — paste an index.html, it carves it into corridor +
    pockets and writes them to inkyswot-rebuild. (One-time; already done.)
  · STITCH — reads corridor + all pockets, joins them, writes a fresh
    index.html into inkyswot-rebuild. Run after every pocket edit.
  · PUBLISH TO LIVE — copies the stitched index.html from inkyswot-rebuild
    into inkyswot-app, where Vercel publishes it to app.inkyswot.com.
  · FIX USED BUTTON COLOUR — a corridor CSS tweak (see features below).
  · ENABLE SPELL CHECK — a corridor tweak (see features below).
  · ADD READ ALOUD TO EVERY FIELD — a corridor tweak (see features below).
  · INSTALL TO DATABASE — writes the enclosure's own current source into
    core/enclosure.html. Press after any change to the enclosure itself.
- The enclosure's writeFile RETRIES on a stale-sha conflict (handles two
  writes landing close together). Commit messages are sanitised to plain
  ASCII (a fancy em-dash once broke a request). Tokens are cleaned of
  hidden characters on save/read (a hidden char in the token once broke
  every request — the classic gotcha).

THE BUILD RHYTHM (the new way of working — SETTLED)
  edit a pocket  →  STITCH  →  PUBLISH TO LIVE  →  Vercel publishes  →
  hard-refresh (Ctrl+Shift+R) to see it.
- If the enclosure ITSELF is changed, add one step first: INSTALL TO
  DATABASE, so the menu copy is current.
- WATCH THE CHARACTER COUNTS (13 July lesson): Stitch's "Wrote (N chars)"
  and Publish's "Read (N chars)" MUST MATCH, or Publish grabbed a stale
  file — re-Stitch and Publish again.
- THE LAST-MILE LESSON (learned the hard way): a change is not truly live
  until it has gone corridor → stitch → publish → Vercel rebuild → browser
  cache cleared. When something "didn't work", CHECK THE ACTUAL FILE ON
  GITHUB (open inkyswot-app/index.html, Ctrl+F the rule) to see the truth
  rather than guess. That is where a lost change shows up.

PLATFORM FEATURES ADDED VIA CORRIDOR CHANGES — LIVE
- SPELL CHECK across every written field (browser spell-check switched on
  platform-wide). NB the browser's OWN spell-check must also be on in the
  user's browser settings, or no squiggles show — that half is per-machine
  and cannot be forced from code. British English follows the browser.
- READ ALOUD on EVERY written field — the big boxes AND the short one-line
  fields (Title, Author, etc.). Dropdowns deliberately left alone. Runs
  immediately and watches for fields that appear later.
- USED BUTTON COLOUR fixed — a used Prompt/Expand button now looks
  identical to a fresh one (full gold), keeping only the ↺ redo arrow, so
  it no longer looks disabled. (Was greyed via --ink3; now --gold.)

PROMPT / EXPAND — A NOTE (not a bug)
- The AI buttons only reach the AI from the REAL live site (the Vercel
  proxy trusts app.inkyswot.com, not a downloaded file). So a downloaded
  index.html shows Prompt/Expand "failing" — that is expected, not broken.
  On the live site they work. The daily-20 Prompt count resets at midnight;
  a manual reset line for the console:
  localStorage.setItem('is-ai-calls', JSON.stringify({date:new Date().toDateString(),count:0}))

LOOSE ENDS (noted, none urgent)
- The old test/ folder in inkyswot-rebuild is harmless clutter — delete
  from GitHub whenever.
- PUBLIC vs PRIVATE for the memory database is still its own decision.
  GitHub Pages may now work on private free repos — would need testing
  (flip private, check the bench/enclosure still open, flip back if not).
  GitHub Pro is about $4/month if a paid route were ever wanted.

WHAT THIS MEANS FOR THE DESIGN WORK BELOW
- All the DCW / mixdown / wheel / quick-note / menu-spine thinking below
  STILL STANDS. The pocket split does not change any of it — it just makes
  the app easier to edit (each screen its own file) and gives a clean
  path to publish. When the design work resumes, the new screens/changes
  are made as POCKET edits, then stitched and published.

================================================================
(original current-state.md continues below, unchanged)
================================================================

Last updated: 17 June 2026 (chat / BUILD session — THE QUICK-NOTE (pinned
post-it) BUILT as a standalone component and signed off: amber scrap, a
two-state thumbtack pin (gold OUTLINE when loose → the SAME shape filled
with colour when pinned), a colour popup using the six track colours,
pin-drag moves the note, pinned scraps anchor to the scene and scroll with
it; saved to the DB as inkyswot-code-quick-note.html.md. STILL TO DO: make
notes PERSIST + a "SEE ALL" button + the across-all-screens wiring. Images
DROPPED from notes — they live in Research. Admin-panel gotcha found and
fixed: a file saved at the repo ROOT saves fine but does NOT show in the
menu — give it the division folder.)

WHO YOU ARE WORKING WITH
Kevin Martin (Kev). Writer, former professional actor and voice artist.
Based in Devon, England.
Runs Pitch Dark Press — one-person independent publishing imprint.
Works with his wife Sara, also a writer.
Has dyslexia — one step at a time always. Never overwhelm.
Never give multiple instructions at once.
Mid-to-late sixties. Anthropic Max plan subscriber.
Coined Proauthorism — transparent, declared human-AI creative
collaboration. Website: proauthorist.com.

HOW TO WORK WITH KEV
One step at a time. Always. Never multiple instructions at once.
Explain before doing. Wait for confirmation before proceeding.
"n", "next", "y", or "done" = confirmed, proceed.
Never assume a step is complete — wait for Kev to confirm.
Show changes locally before uploading to GitHub.
Persistent bugs — rebuild from scratch. Never patch on patch.
British English. Witty and direct. Match his register.
Never rush. Kev may be slow at some steps — this is fine.
Do NOT use multiple-choice button lists to ask questions — plain
questions only. A single plain either/or in prose is fine; never a
stacked list of options.
KEEP IT SIMPLE — when Kev says he doesn't understand, STOP, drop the
jargon and the long lists, and say it in plain words, one thing at a
time. Do not dump a big banked list on him; hold it yourself.
InkySwot = always capital I and capital S.
PUBLISH AND BE DAMNED — no full stop. Ever.
If a decision is in the files, do not revisit it unless Kev asks.
GitHub organisation: PitchDarkPress.
At the start of any build session, ask Kev to paste in the current
code before any work begins. THE CODE IS THE TRUTH.
Update the files at the end of a session. Rebuild clean — never patch
on patch. The .md is the single source of truth; the code is the truth
above it. When updating a file, rewrite the WHOLE file clean.
WHEN DESIGNING A LIVE MECHANISM (motion, scroll, interaction, drag,
keyboard behaviour): build a small STATIC mockup FIRST, agree the still
picture, THEN add the movement. Designing moving behaviour in words
wastes time (learned hard on the wheel). Ask for a screenshot/sketch.
WORK FROM THE IMAGE / THE CODE — NOT FROM A GUESS (hard lesson, 9 June).
When Kev gives a screenshot, that image IS the template — match it, do
not reinterpret it. When changing a built file, work from the pasted
code, never a reconstruction of it from memory or a screenshot. SMALL
CHANGES MEAN SMALL CHANGES — change only the one thing asked, touch
nothing else.
DISPLAY FREEZE: if edits stop showing, do a CLEAN REBUILD in a fresh
artifact rather than editing on.
LONG-THREAD DRIFT: a long, winding conversation degrades reliability —
start a fresh chat (with the .md files pasted) for a new build session
rather than carrying a tired thread on.

================================================================
THE MODEL — INKYSWOT *IS* THE DCW (settled 4 June 2026)
================================================================
- InkySwot IS THE DCW — the whole instrument. Every section already
  built (Characters, Locations, Events, etc.) is part of it. The
  database IS the bones of the story.
- THE TREATMENT / THE DCW is the database switched on — assembled into a
  readable, writable whole. A plotline is a VIEW of data that already
  exists, not a new thing to author.

================================================================
*** THE BIG TURN — THE DCW IS ONE BODY OF DATA / A MIXDOWN ***
(settled 16 June 2026 — supersedes "three views" framing)
================================================================
KEV'S INSIGHT, stated plainly: "It is just one thing." The DCW is NOT
three separate screens you move between. It is ONE body of material seen
through OVERLAYS — and it behaves like a MIXDOWN in music.

THE FUNNEL, END TO END (both ends now seen on real screens):
- SANDBOX — the raw, no-order end. Brainstorming. You drop ideas in
  (places, characters, events, objects) and toss them about until they
  coalesce into a semblance of a story. WIDE end of the funnel.
- SYNOPSIS — the SAME material with an overlay that fixes it into an
  ORDERED timeline; then a SECOND overlay drops CHAPTERS and SCENES onto
  it.
- THE MANUSCRIPT (renamed from "Writing Panel", 16 June) — the SAME
  material again, with the writing surface revealed, where the writer
  completes the book. CLOSE end of the funnel (one scene).

WHY BACK-AND-FORTH IS FREE — THE MIXDOWN:
- Like multitrack music: the tracks underneath never go away; a mixdown
  RENDERS them together but does not destroy them. Going back is free
  because nothing was ever converted — it was the same data wearing a
  different coat all along.
- Things drop into FIXED PLACES (a home/slot) but can STILL be moved
  from place to place. Loose AND structured at once.
- When you MIX DOWN, only certain things stay VISIBLE in the centre (the
  spine / the EVENTS — the through-line), and the rest (Characters,
  Locations, Objects, Themes, Tension — the "reach-into" tracks) drop to
  a LIST DOWN THE SIDE. They don't vanish; they move to the margin. That
  side-list IS the WP SCENE MENU already built into the wheel file.
- THE BOARD (code-board-look.html) is the WIDE end — all six tracks as
  columns, everything visible. THE WHEEL + PAGE is the CLOSE end — spine
  as the page, reach-into tracks as the side list. SAME DATA, two coats.

THE HARD KERNEL — THE KEYSTONE (NOT yet solved; the next real build):
- The whole thing only works if each overlay's structure — the ordering,
  the timeline position, the chapter/scene home — is STORED ON THE
  SHARED DATA itself, not held inside a view. In music terms: the
  structure lives in the MIX INSTRUCTIONS that sit alongside the tracks,
  not in the tracks.
- THE QUESTION TO ANSWER (still-picture first, fresh chat): how does ONE
  record carry its board position, its timeline order, AND its
  chapter/scene home all at once, so the overlays just read and write the
  same thing? This is the SAME beast as the long-standing DATABASE
  REORGANISATION question.
- OPEN within this: is each level's ordering a SEPARATE set of mix
  instructions (Sandbox can stay jumbled while Synopsis holds the tidy
  order), or does ordering in one level flow down and change the others?
- (13 July) The BOARD->WHEEL button, the CHAPTER NUMBERS as shared address,
  and the GATHERED ACTIVE SYNOPSIS all hang off THIS keystone. See the
  OVERVIEW REBUILD section at the top for the confirmed journey.

THE SPINE — A TIMELINE OF EVENTS
Three tiers: CHAPTER → SCENE → EVENT. Only EVENTS sit on the line and
become prose — only events HAPPEN. Characters, Locations, Objects, etc.
do not happen; they are REACHED INTO by the events that use them.

"FILL IN THE BLANKS"
The Treatment assembles the SUBSTANCE from the database and leaves the
writer the blanks: the prose only they can write. Assembled, the
sections ARE the draft; the writing is the last layer.

================================================================
THE QUICK-NOTE — PINNED POST-IT, BUILT (component, 17 June 2026)
================================================================
The PINNED POST-IT idea (raised 16 June) is now a WORKING, APPROVED
standalone component, signed off by Kev. Saved to the DB as
inkyswot/inkyswot-code-quick-note.html.md. NOT yet wired into the
platform — it is a finished part waiting to be dropped in.

WHAT IT IS (settled this session):
- A small AMBER PAPER SCRAP — warm amber on the dark workspace, so it
  reads instantly as a SCRAP (a thought, NOT filed story data). Built as
  the scruffy cousin of the entity POP-UP idiom: drag by its top strip,
  ✕ to delete (top-right), cascades when there is more than one, click a
  scrap to raise it to the front.
- Square-ish and upright. AUTO-GROWS as you type — the paper deepens, so
  there is never a scrollbar. The folded bottom-right corner is a real
  RESIZE handle (drag it).
- IT IS NOT STORY DATA: never a character / event / scene, never becomes
  prose, never mixes down. The writer talking to themselves ("fix this",
  "Marley too early?", "check the date").

THE LIFE OF A SCRAP — three exits:
- SUMMON from anywhere → jot → then one of:
  · KEEP (Enter) — files it away. In the platform this hands the text to
    the Notes pad via an optional hook (window.QuickNoteOnKeep).
  · BIN (esc, or the ✕) — gone.
  · PIN — sticks it down; it stays until deleted.

THE PIN — a two-state thumbtack (much-iterated; Kev happy):
- LOOSE: a small GOLD OUTLINE thumbtack, centred on the top of the note.
- PINNED: the SAME thumbtack SHAPE, FILLED with a colour, in the SAME
  spot — clicking swaps outline → filled IN PLACE (no jump). The note
  also gains a faint gold ring, so "pinned" reads at a glance.
- A CLEAN CLICK on the pin toggles pinned/loose. A PRESS-AND-DRAG on the
  very same pin MOVES the note — so a pinned scrap is still freely
  movable (grab the pin, or the top strip).
- PINNED = ANCHORED TO THE SCENE: a pinned scrap drops into the scrolling
  page and SCROLLS WITH IT (content-anchored, not floating on the glass).
  Loose scraps float over the view.

THE PIN-HEAD COLOUR — assignable, per note (new this session):
- When you pin, a small COLOUR POPUP opens just below the pin. Pick a
  colour and it applies and the popup closes (clicking away also closes
  it). Each scrap remembers its own head colour.
- The palette is THE SIX TRACK COLOURS (Events gold, Locations teal,
  Characters terracotta, Objects steel blue, Themes violet, Tension red),
  default Tension red — so a pin's colour can MEAN something later rather
  than being random decoration.
- To recolour later you re-pin (the popup is tied to the pinning action).
  A "recolour without unpinning" gesture is a possible future tweak — not
  built.

HOW THE COMPONENT IS WIRED (for the integration step):
- HOST = a layer fixed in the viewport — loose scraps float here.
- STAGE = the scrolling scene/page — pinned scraps anchor here.
- window.QuickNoteOnKeep(text) = optional hook; in the platform it files
  a kept scrap into the Notes pad.
- summonNote() = call it from the summon key / a button / the ELSRA keypad.
- The file ships with a DEMO HARNESS (dark backdrop + ＋ button + N key),
  clearly marked to DELETE on integration; the STYLES and SCRIPT blocks
  are marked to lift whole.

STILL TO DO (also noted as a comment in the code):
1. PERSIST — scraps must STAY where dropped and survive a refresh. In the
   standalone file that means browser memory; in the platform they should
   save into the InkySwot DATABASE like everything else. NOT built.
2. SEE ALL — one button that shows EVERY scrap at once, wherever each is
   pinned. UNDECIDED: a panel that LISTS them, or GATHER the actual notes
   onto the screen. NOT built. (Persistence comes first — you cannot
   gather what was never saved.)
3. ACROSS ALL SCREENS — the founding requirement. This is the integration
   job: HOST becomes one app-level overlay above EVERY screen; the summon
   moves to app level (the keypad). Needs the live platform shell pasted.

STILL OPEN (carried from 16 June): does a PINNED note travel BETWEEN views
(pinned to the THING — e.g. a scene — so it rides the funnel) or live only
in the view it was stuck in (pinned to the VIEW)? The component anchors a
pinned scrap to the scene/page and scrolls with it; whether it CROSSES the
funnel is still undecided.

DROPPED this session: notes do NOT hold images. Images live in the
RESEARCH section.

LINEAGE: the grown-up form of the old "Stickies" toy / Map Plotter
corkboard. Stickies remains NOT a menu destination; its DNA lives here and
in the board.

================================================================
THE SIX TRACK COLOURS — SETTLED (9 June 2026)
================================================================
One decision, used wherever the entity categories appear. All six pull
clearly apart; a dyslexic reader must tell them at a glance, so no two
muddy neighbours.
  EVENTS      gold        #c9923a
  LOCATIONS   teal        #5fa898
  CHARACTERS  terracotta  #cf7f57
  OBJECTS     steel blue  #7a9bd0
  THEMES      violet      #a07d9a
  TENSION     red         #c45b48
NB: this REVISES the older locked section colours (Character #cba36a,
Event #b08a6a). Characters is now terracotta; Events takes the gold.
Locations teal unchanged. Applied to the WP scene menu (live in the
wheel file), and now ALSO to the QUICK-NOTE pin-head palette (17 June).
Chapter #9a8fb0.

================================================================
THE PAGE + THE WHEEL — AS BUILT (4 June settled; 6–7 June refined)
================================================================
Full spec in dcw.md. The heart of the writing experience.

THE PAGE — one scene per full US-Letter sheet (816×1056px); always full
height; stave heading on every page; running head top-right; scene
heading; the event(s) with "— click to write this scene —"; writing
surface hidden until Writing Mode.

THE WHEEL — a single hairline gold RAIL in the channel right of the
page; TWO-LINE kicker labels (gold mono "STAVE ONE — SCENE ONE" + scene
title); window of NINE each side; straight belt (BOW=0); ring + dot +
leader centre mark; hover lights node only; eased motion (rate 0.072,
TIGHT=46, GAP=64); 0.35s smoothed hand-off.

THE PAGE LANDING — ONE SHARED READING LINE (page-top bug fixed 7 June).
Page and wheel share one reading line ~28px below the header
(READ_PAD=28). Clicking a label (or opening a scene) lands the scene's
TOP on the line (rollToTop). The wheel reads "where you are" from the
same line. SMALL OPEN TWEAK: live label flips ~halfway down a tall page;
biasing it later is an easy future tweak.

WRITING MODE shows ONLY the live scene; other pages hidden. "‹ overview"
returns to the Treatment.

================================================================
THE RIGHT-HAND ROADMAP — TO BE REMOVED; THE WHEEL STAYS (16 June 2026)
================================================================
The current live wheel file (see FILES — the real file is now
wheel-with-roadmap (7).html) carries a scrolling ROADMAP down the RIGHT
side — a list of every scene (Stave One Scene One, Fred's Visit, …).
- DECISION: the right-hand ROADMAP GOES. It duplicates the WHEEL — both
  tell you "where you are" and move you between scenes. One mover, not two.
- THE WHEEL STAYS, on the right, in its place.
- RESTING SHAPE of the close view: LEFT reach-into list (Characters,
  Objects, Themes, Tension) · the PAGE in the centre · the WHEEL on the
  right.
- This is a SMALL SURGICAL build for a fresh chat: remove the roadmap
  from the pasted wheel file, wheel untouched, small-change-means-small.

================================================================
THE CHAPTER (STAVE) PAGE — A SYNOPSIS PAGE OF ITS OWN (built 11 June 2026)
================================================================
THE GAP FOUND: the synopsis only existed at SCENE level. The CHAPTER had
no synopsis of its own — leaving the chapter-level + Prompt nothing to
act on.

THE FIX: a CHAPTER gets its own full page, SAME FORMAT FAMILY as a scene
page, sitting BEFORE that stave's first scene. The spine reads: Stave One
page → its scenes → Stave Two page → its scenes, etc.

THE STAVE PAGE LAYOUT (agreed against Kev's image, 11 June):
- Full US-Letter sheet, page shadow — a scene page's twin.
- Running head top-right ("A Christmas Carol by Charles Dickens"), alone.
- The stave TITLE shown large (Crimson Pro ~30px, weight 600) — this IS
  the heading; NO duplicate mono stave line above it.
- A small mono line under the title, on the rule: "STAVE ONE · 5 SCENES".
- A centred mono section label on/under the rule: "CHAPTER SYNOPSIS".
- The SYNOPSIS BLOCK — identical grammar to a scene's .event block, then
  the italic invitation "— click to write this synopsis —".
- A hidden writing surface beneath; the chapter synopsis is editable.
STILL PICTURE only (standalone artifact). NOT YET folded into the wheel
file; the wheel will also need a label for the stave page (not yet done).

================================================================
THE WP AI PROMPT — PROMPT + EXPAND ON THE PAGE (settled 11 June 2026)
================================================================
The writer-facing Ada buttons (gold "+ Prompt" / "⟳ Expand").

WHAT IT DOES — AND ITS LIMIT (assisted-not-generative guard):
- SCOPED to expand the SYNOPSIS of the scene or chapter — NOT the prose.
  Expanding the synopsis thickens the PLAN; the blank the writer fills
  stays blank. Ada makes the brief richer, never finishes the work.
- Scales with the spine: a chapter + Prompt expands the CHAPTER synopsis;
  a scene + Prompt expands THAT scene's synopsis. (Why the chapter
  synopsis had to exist first.)
- HOW "stop AI writing the whole thing" is guaranteed: (a) scoped buttons
  — no "write everything" door; (b) hidden system prompt is OURS,
  forbidding prose, server-side (Steps 5–7); (c) output lands by CHOICE.

THE LOOK — PAGE FURNITURE, NOT DARK-UI CHROME (settled 11 June):
On the cream sheet, drawn in the PAGE'S OWN palette — page ink (#221a14),
page rule (#ded6c6), page-mute grey (#8a7d68). NO gold loudness at rest.
- CHOSEN TREATMENT ("A"): an OUTLINE PAIR. Thin page-rule border, page-ink
  text, transparent inside. EXPAND carries a faint grey WASH
  (rgba(138,125,104,.14)) as the weightier of the two; PROMPT stays open
  paper. HOVER: border + text wake to GOLD.
PLACEMENT (from Kev's image): TOP-RIGHT of the page, level with the large
title, tucked under the running head.
NOT YET folded into the wheel file.

================================================================
THE WP SCENE MENU — LEFT OF THE PAGE (built 9 June 2026)
================================================================
The home for the four reach-into tracks. In the dark channel LEFT of the
WP, MIRRORING the wheel on the right — the workspace reads as one
instrument, the same gold rail-and-ring furniture both sides.
- WHAT IT IS: "what this scene reaches into" — the Characters, Objects,
  Themes and Tension of the scene in front of you. Tied to the PAGE; it
  changes scene to scene.
- THIS IS THE MIXED-DOWN SIDE LIST (see THE MIXDOWN): the reach-into
  tracks that collapse out of the board's columns into the margin.
- LOOK: right-aligned list. Coloured group headers (Characters terracotta,
  Objects steel blue, Themes violet, Tension red), names in plain ink
  beneath. Thin vertical gold RAIL, gold RING (17px) on the rail, short
  gold LEADER pointing INWARD.
- CLICKABLE: a name opens that entity's draggable POP-UP RECORD with copy
  buttons.
- TENSION — A METER (settled 9 June; NOT YET BUILT). A SEGMENTED BAR METER
  — segments GREEN → AMBER → RED, lighting to the scene's level, the
  PERCENTAGE beneath (e.g. 55%). Can run PAST 100 into red. A light-up
  SWEEP between scenes wanted (car-dial wake) — build static-first.
  (Currently shows a plain "55%" placeholder in the wheel file.)

================================================================
THE MENU SPINE — GROWN (16 June 2026)
================================================================
Kev grew the menu beyond the bare nav to a full spine: a Landing page,
then a Home page, then the project nav. NOTE: this is a SPINE, not the
finished map — Kev flagged there is still "loads missing". Wording on a
few items is LEANING, not locked (see OPEN DECISIONS).

THE LANDING PAGE (before login)
- Sign in
- Sign up

THE HOME PAGE (after login — the launchpad)
- New Project
- Load Project
- Demos
   - A Christmas Carol
   - The Wind in the Willows
- The Press

THE PROJECT NAV (the in-app left menu)
- PROJECTS
   - New Project
   - Load Project
   - Demo
      - A Christmas Carol
      - The Wind in the Willows
- DCW
   - Sandbox        (moved here — head of the funnel)
   - Synopsis
   - Chapters
   - Scenes
   - Manuscript     (was "Writing Panel")
   - The Press       (its second home; sub-items TBD — "other stuff")
- WORLD BUILDING
   - Cast
      - Characters
      - Relationships
      - Language & Dialogue
      - Factions & Organisations
   - World
      - Locations
      - Buildings
      - Objects & Artefacts
      - Rules & Lore
- NOTES
   - Snippets        (was "Library" — Snippets = bits of script/text YOU
                      wrote and saved for later; replaces the vague
                      "Library" wrapper)
   - Research        (was "Research & Reference" — material brought in
                      from OUTSIDE the story; ALSO now the home for any
                      IMAGES — they are NOT held on notes, 17 June)
- HELP
   - Tutorials
   - Manual
   - FAQs
   - What's New
- Trash
   - View Trash
   - Empty Trash

NOTES ON THE MENU SPINE:
- SANDBOX now lives at the HEAD of DCW (not under NOTES). It is the loose
  entry point that feeds the DCW; head of DCW = where the funnel begins.
- THE PRESS lives in TWO homes: on the HOME page, and nested under DCW.
  Its DCW sub-items are not yet defined ("other stuff" placeholders).
- NOTES = Snippets + Research. "Library" dropped (too vague — Snippets
  names the actual contents, so a writer never hesitates "mine vs found").
- STICKIES (Notes & Scratchpad) — DELIBERATELY DROPPED from the menu (16
  June). It is NOT a menu destination; it is the PINNED-NOTE layer, now
  BUILT as the QUICK-NOTE component (see that section).
- SYNOPSIS under DCW IS the former "Plot Mapping" (same thing; name
  dropped, confirmed 14 June).
- FACTIONS & ORGANISATIONS — written in FULL. Never "Orgs".
- STRUCK FROM THE NAV earlier (hidden, not deleted as screens): Plot
  Threads, Subplots, Themes & Motifs.

ENTRY (settled 8 June, standing):
- LANDING PAGE (before login): Sign In / Sign Up. Its own screen.
- After sign in/up the writer lands on the HOME page (launchpad).
- OVERVIEW: RESOLVED 13 July — OVERVIEW STAYS, and is GROWING. It is no
  longer in doubt. See the OVERVIEW REBUILD section at the top: it is now
  a rich screen and is set to become the HOME OF THE GATHERED SYNOPSIS
  (overall + chapter synopsis land here). The separate ROUTING question
  (does login land on Overview or Home) is still open, but Overview as a
  SCREEN is confirmed and invested in. (Was titled "BASIS" in old
  index.html; that rename/fate now settled as OVERVIEW, alive.)

LAUNCHPAD ICONS — SETTLED (8 June 2026)
Clean single-weight gold line art, stroke="currentColor" (recolour with
Tone; no PNGs). Three drawn: Load Project — drawer chest; New Project —
typewriter; Demos — signpost. Stored with inkyswot/home-icons.svg.md.

================================================================
THE SITE MAP — TWO DIFFERENT THINGS; DON'T CONFUSE THEM
================================================================
1. THE STRUCTURAL SITE MAP (a PLAN, not a feature) — the complete tree of
   what InkySwot contains, the skeleton on paper, built to settle where
   everything lives. Kev asked for this 16 June ("we have to build a
   complete site map… so we stop messing"). NOT yet built — wants its own
   fresh chat with the core files. The MENU SPINE above is the start of it.
2. THE THEATRICAL SITE MAP (a FEATURE in the app) — the "where you are"
   delight: blocks of colour (the six track colours), strange lines, a
   "BOOM (ish)" flourish on navigate, meant to make the writer smile.
   PARKED (14 June) — likely wants its OWN PAGE; the 290px sidebar was too
   cramped. The calm FOUR-HEADING SIDEBAR map is the quiet stand-in.

THE CALM FOUR-HEADING SITE MAP — the SIDEBAR version (built, kept):
A calm SPINE of the FOUR HEADINGS, contents popping up on hover; spine on
the RIGHT, ring nodes, plain-text contents right-aligned, two lanes,
STATIC / hover-driven. NB the four headings should be kept in step with
the SETTLED nav — which has now GROWN (see THE MENU SPINE), so the
sidebar map will need updating when next touched.

================================================================
MANUSCRIPT VIEW — TOGGLE (writer comfort, agreed 8 June)
================================================================
A toggle in the WP to strip the chrome and read the book as a continuous
manuscript. Display-level only; TRUE flowing pagination remains a bigger
deferred build. (NB: "the Manuscript" is now also the NAME of the close /
writing view — see THE MIXDOWN. This toggle is a comfort view within it.)

================================================================
SECURITY — A NOTE FROM 8 June (resolves a WP worry)
================================================================
Full system in security.md (seven layers, locked 24 May; paid-only; API
key in Vercel env vars only; server-side prompt tracking Steps 5–7).
- Protecting on-screen TEXT from copying is NOT achievable in a browser.
  Do NOT harden the WP against text-lifting.
- THE REAL FARMING MOAT: paid-only + assisted-not-generative (InkySwot
  won't WRITE the book) + per-account rate limits.
- The WP + Prompt expands the SYNOPSIS, never prose (prose-forbidding
  prompt server-side).
- PRESS-AS-CLEAN-EXPORT is good commercial design, NOT a security feature.

OTHER STANDING SECTIONS (unchanged — abbreviated; see specialist files):
- IDENTITY & BRANDING, COLOURS, FONTS — Playfair 900 logo; Crimson Pro
  body; JetBrains Mono UI; dark palette #0f0d0a / ink #e8e0d0 / gold
  #c9923a–#e8b060. TRACK COLOURS per THE SIX TRACK COLOURS; Chapter
  #9a8fb0.
- PRICING — paid only; £9.95/mo, £99.50/yr; 14-day money back; £1
  publication fee.
- TECHNICAL — v4.7 pre-Step 1 rebuild; Autumn 2026 target; repo
  PitchDarkPress/inkyswot-app; Vercel Hobby; API claude-haiku-4-5; key in
  Vercel env vars only.
- THE PRESS (two doors), ADA (Step 12), MANUSCRIPT FORMAT / GROUPS / GENRE
  lists, LANDING + LOGIN pages — as previously logged.

================================================================
THE MEMORY DATABASE — HOUSEKEEPING (9 June; updated 17 June 2026)
================================================================
Pitch Dark Studios Memory (pitchdarkpress.github.io/pitch-dark-studios-
memory) holds files per DIVISION. Code files carry a "code-" prefix, e.g.
  inkyswot/code-readme.md            (index of the code files)
  inkyswot/code-treatment-wheel.html.md   (the WHEEL — live design source)
  inkyswot/code-board-look.html.md   (the board STILL PICTURE)
  inkyswot/code-site-map.html.md     (the SITE MAP)
  inkyswot/code-map-plotter.html.md  (old corkboard — SUPERSEDED history)
  inkyswot/home-icons.svg.md         (launchpad line icons)
  inkyswot/inkyswot-code-quick-note.html.md  (NEW 17 June — the QUICK-NOTE
                                     component; note this one carries the
                                     division at the FRONT of the name,
                                     fuller than the older "code-" prefix)

*** ADMIN-PANEL GOTCHA — FOUND & FIXED (17 June) ***
A file saved at the repo ROOT (a bare filename, no division folder in
front) SAVES fine but does NOT appear in the admin menu. The menu builder
(renderTree) buckets files by their top-level folder and deliberately
drops anything not inside one. THE FIX: always put the division folder in
front, e.g. "inkyswot/inkyswot-code-quick-note.html.md" — not just the
bare filename. (Any root copy made by mistake is hidden, not lost.)

STILL TO TEST: whether the InkySwot division can hold a .png / .jpg image
(now mainly for RESEARCH, since images are NOT held on notes).

FILES — InkySwot division of the memory database
current-state.md · locked-decisions.md · dcw.md (the three core .md).
*** FILE-OF-TRUTH NOTE (16 June): the LIVE wheel file is now
"wheel-with-roadmap (7).html" — it carries the SETTLED four-section nav,
the LEFT reach-into list, and the RIGHT-HAND ROADMAP (which is to be
REMOVED, wheel kept). An OLDER copy with a stub left-nav and an EMPTY
right sidebar was pasted earlier and is NOT the truth. Always ask Kev for
the current file at the start of a build. ***
*** THE OVERVIEW POCKET is now LIVE and RICH (13 July) — the current live
version is the project-overview pocket in inkyswot-rebuild. Always ask Kev
to paste the current pocket before editing it. ***
inkyswot/code-treatment-wheel.html.md — earlier live design source (the
older lineage; superseded by wheel-with-roadmap (7).html as the working
file). STILL NOT folded in anywhere: the chapter STAVE PAGE; the WP
Prompt/Expand buttons; the wheel's stave-page label; the Tension meter
(still a "55%" placeholder).
inkyswot/inkyswot-code-quick-note.html.md — the QUICK-NOTE component
(BUILT 17 June, signed off). Standalone; STYLES + SCRIPT blocks marked to
lift, plus a DEMO HARNESS marked to delete on integration. NOT yet wired
into index.html or the wheel.
inkyswot/code-site-map.html.md — the SITE MAP. The standalone four-heading
spine. NB the THEATRICAL "where you are" Site Map (blocks of colour, BOOM)
is the new intent and is PARKED (likely its own page) — not in any file.
inkyswot/code-board-look.html.md — the BOARD still picture = the WIDE end
of the funnel (all six tracks as columns). Now CONFIRMED as part of the
mixdown, not "under review". (NB the ROTATED board, code-board-rotated.html,
is the more advanced working board — the SYNOPSIS BOARD in the confirmed
journey.)
inkyswot/home-icons.svg.md — launchpad icons.
inkyswot/code-map-plotter.html.md — old Plot Mapping corkboard (grew from
the original "Stickies" toy). SUPERSEDED as a screen; its DNA feeds the
QUICK-NOTE and the Sandbox.
index.html — the app workspace.
login.html — login / sign up gate (stubbed).

WHAT IS BUILT AND WORKING
Landing page; login page (stubbed); My Projects / Trash / New Project
modal / OVERVIEW (REBUILT & LIVE 13 July — single-line strap with hover-
scroll; Cover & Outline group removed; Format + Target Audience removed;
clever Word Count steers; custom Genre dropdown with greyed coming-formats
+ hover COMING SOON note) / Characters / Relationships / Factions & Orgs /
Language & Dialogue / Locations / Buildings / Objects & Artefacts /
Rules & Lore / Plot Threads / Subplots / Themes & Motifs / Events &
Timeline / Chapters / The Treatment (placeholder shell) / AI Expand /
AI ON-OFF / Read Aloud / light-dark / voice selector. The WHEEL + WP +
LEFT SCENE MENU + SETTLED LEFT NAV + RIGHT-HAND ROADMAP live together in
the standalone mockup (wheel-with-roadmap (7).html), NOT yet in
index.html. The BOARD is a standalone still picture (the wide end); the
ROTATED board (code-board-rotated.html) is the advanced synopsis board.
The QUICK-NOTE component is built and signed off as a STANDALONE file —
NOT yet wired into the platform.

BUILD ORDER — CONFIRMED (unchanged)
Step 1 v4.0 App Shell Rebuild (NOT STARTED) · 2 Walk · 3 Sign-off Gate ·
4 Supabase · 5 Lifetime flag · 6 F12/Security · 7 Server prompt tracking
· 8 Stripe · 9 Resend · 10 Writing surface (WP + pop-ups + wheel + scene
menu) · 11 The Treatment (the wheel) · 12 Ada · 13 DCW (= the wheel) ·
14 Export Suite · 15 The Press · 16 Admin · 17 PWA · 18 Beta · 19 Launch.
DEMO BOOKS (Carol then Willows) — after Step 1 sections are final.

CURRENT STATUS & NEXT ACTIONS
v4.7 pre-Step 1 rebuild. Autumn 2026 target.
... [history through 14 June as previously logged] ...
16 June (chat / design session — NO CODE CHANGED): settled the DCW as ONE
  BODY OF DATA / a MIXDOWN (Sandbox → Synopsis (timeline + Chapters/Scenes
  overlays) → THE MANUSCRIPT, renamed from Writing Panel). Saw the funnel
  end-to-end on real screens: the BOARD is the wide end, the WHEEL+PAGE
  the close end, the left scene menu IS the mixed-down side list. Decided
  the RIGHT-HAND ROADMAP goes and the WHEEL stays. New idea: PINNED
  POST-IT NOTES — a layer above the data, content-anchored, never mixed
  down. Grew the MENU SPINE (Landing / Home / four-section nav; Sandbox to
  head of DCW; NOTES = Snippets + Research; Stickies parked; Press in two
  homes; Trash opens to View/Empty). Identified the real wheel file as
  wheel-with-roadmap (7).html (older pasted copy was stale).
17 June (chat / BUILD session — CODE BUILT): built THE QUICK-NOTE
  component (the pinned post-it) end to end and Kev signed it off. An
  amber scrap built as the pop-up's scruffy cousin (drag, ✕, cascade,
  raise-to-front); auto-grows with the text; folded-corner resize; summon
  → jot → keep / bin / pin. The PIN is a two-state thumbtack — gold
  OUTLINE when loose, the SAME shape FILLED with colour when pinned, swap
  in place, with a faint gold ring when pinned; a clean click toggles, a
  drag on the pin MOVES the note; a pinned scrap anchors to the scene and
  scrolls with it. The pin-HEAD colour is assignable via a small POPUP (the
  six track colours, default Tension red). Saved to the DB as
  inkyswot/inkyswot-code-quick-note.html.md. Images on notes DROPPED (they
  live in Research). Found & fixed an admin-panel gotcha: root-level files
  save but do not show in the menu — give the division folder. STILL TO
  DO: persistence + a "see all" button + the across-all-screens wiring.
13 July (chat / BUILD session — CODE BUILT & LIVE): rebuilt the OVERVIEW
  screen end to end and Kev signed it off on the live site. Confirmed the
  WRITER'S JOURNEY (New Project → Overview → Synopsis board → gathered
  active synopsis → Wheel/page), with CHAPTER NUMBERS as the shared
  address and the board->wheel button = the KEYSTONE. Overview changes,
  all live: strap line to single-line + HOVER-SCROLL; Cover & Outline
  group removed whole; Format + Target Audience removed; the CLEVER WORD
  COUNT STEERS (target auto-commas + genre word-count steer; chapters
  suggested from target/genre, overridable with reset arrow; readable
  captions for 28-inch screens; honest industry figures logged); the
  custom GENRE DROPDOWN with GREYED coming-formats + a hover COMING SOON
  pointer-note (a reusable pattern). Learned the PUBLISH TIMING lesson
  (watch Stitch/Publish char counts match, or Publish grabs a stale file).
  RESOLVED: Overview STAYS and is GROWING — it will become the home of the
  GATHERED SYNOPSIS (both an auto-gathered active synopsis AND a hand-typed
  one). current-state.md rewritten clean (this file).

NEXT (do in order, one at a time — START A FRESH CHAT for a build)
0. OVERVIEW GROWS: add the SYNOPSIS FIELDS to Overview — the OVERALL
   SYNOPSIS (BOTH a gathered, active one that fills itself from chapters/
   scenes below AND a hand-typed one the writer writes), plus chapter/
   scene synopsis plumbing. This ties into the KEYSTONE (the gathered/
   active flow needs the shared store). Kev has fresh ideas here — start
   there next.
1. SMALL SURGICAL BUILD: remove the RIGHT-HAND ROADMAP from the live wheel
   file (wheel-with-roadmap (7).html), WHEEL UNTOUCHED. Work from Kev's
   pasted file.
2. THE KEYSTONE: design the FUNNEL DATA MODEL (still-picture first) — how
   ONE record carries its board position + timeline order + chapter/scene
   home at once so the overlays/mixdown read and write the same thing.
   This is the spine of the whole platform. The board->wheel button, the
   chapter-number address, and the gathered active synopsis all hang here.
3. FOLD THE STAVE PAGE + WP PROMPT/EXPAND into the live wheel file. Then
   the wheel's stave-page label.
4. Build the TENSION SEGMENTED BAR METER + sweep (static-first) to replace
   the "55%" placeholder in the scene menu.
5. THE QUICK-NOTE — finish it: (a) PERSIST the scraps (browser memory in
   the standalone, the DATABASE in the platform); (b) the SEE-ALL button
   (decide first: a panel that lists them, or gather the notes onto the
   screen); (c) settle whether a pinned note CROSSES between views; then
   (d) WIRE IT ACROSS ALL SCREENS (HOST as an app-level overlay; summon on
   the keypad) — needs the live platform shell pasted.
6. THE THEATRICAL SITE MAP (when off hold): agree resting + exploded
   stills, then wire the BOOM — likely its OWN PAGE.
7. UPDATE locked-decisions.md and dcw.md to match (DCW = mixdown; Writing
   Panel = Manuscript; menu spine; roadmap out; the QUICK-NOTE settled
   spec; the confirmed JOURNEY; Overview stays & grows; the coming-soon
   dropdown pattern) — one file at a time.
8. Test whether the InkySwot division can hold a .png image (for Research).
9. (Carried app jobs) build the nav into index.html (to the new spine);
   build the home launchpad; begin Step 1.

OPEN DECISIONS — STILL TO SETTLE (one at a time)
1. THE KEYSTONE — the FUNNEL DATA MODEL (how one record holds all three
   structures at once). The big one; everything hangs on it.
2. PINNED NOTES — does a note cross BETWEEN views (pinned to the thing) or
   live in one view (pinned to the view)? (Component anchors to the scene
   and scrolls with it; crossing the funnel is still undecided.)
2b. QUICK-NOTE "SEE ALL" — does the button open a PANEL that LISTS every
   scrap, or GATHER the actual notes onto the screen? Undecided.
2c. QUICK-NOTE PERSISTENCE — browser memory (quick, standalone) vs the
   InkySwot DATABASE (proper, everywhere). The DB is the real home; the
   storage swaps over at integration.
3. MENU WORDING — final confirm "Snippets" replaces "Library"; "Research"
   vs "Research & Reference"; THE PRESS's DCW sub-items.
4. THE PRESS — what its two homes each hold; its DCW sub-items.
5. OVERVIEW ROUTING — Overview STAYS (resolved 13 July), but does LOGIN
   land on Overview or on HOME? The screen is confirmed; only the routing
   is open.
6. THE BOARD's exact role in the mixdown (it is the wide end — but does
   the writer build IN it, or is it a read view?).
7. STICKIES / NOTES & SCRATCHPAD — now answered by the QUICK-NOTE; any
   remaining "scratchpad" need to revisit.
8. THE THEATRICAL SITE MAP — its own page; what the BOOM is.
9. EVENT ORDER WITHIN A SCENE; multiple events per scene (list or collapse).
10. WHERE THE MOOD WORDS LIVE (Cold · Bleak · Biting). Parked.
11. TAG SET — Prose vs Action; Dialogue's place; Emotion tag vs Map.
12. CARRIED FEATURES' HOME — Emotional Maps, Ambient, the lift.
13. WHEEL LIVE-LABEL FLIP POINT — small tweak.
14. THE STAVE PAGE'S WHEEL LABEL — settle when folding the stave page in.
15. BOARD->WHEEL BUTTON — one-way move, or flip-back (mixdown never
    destroys tracks)? (Steer: flip-back. Not confirmed.)

================================================================
ROUGH — NOT SETTLED. Captured so it is not lost. Do NOT build from this.
Proper home: future.md.
================================================================
THE LAYERED / ONION-SKIN WRITING SURFACE + HOT-KEY TAGGING.
- Write the story as a LOOSE, REORDERABLE TIMELINE OF EVENTS.
- As you write, people/places/things are caught and FILED to the side
  menu as entities. The database fills ITSELF.
- A known entity carries a quiet MARK in the prose (NOT colour alone; calm
  for a dyslexic reader).
THE TAGGING MECHANISM:
- Write freely. Hit a HOT KEY — grabs the LAST WORD. BACK-ARROW extends
  word-by-word for multi-word names. [build static-first.]
- A menu offers the TYPE; pick one → existing records + "New: …".
- A record is a THING, not a string: one CANONICAL name + ALIASES.
- DIAL: "err toward asking" over "guessing". Suggest, never decide.
- Forgiving for a dyslexic writer — never make spelling the price.

================================================================
SUPERSEDED / DROPPED — KEPT AS HISTORY (do NOT build from any of this)
================================================================
- "THREE VIEWS OF ONE BODY OF DATA" as the framing — superseded 16 June by
  THE MIXDOWN (one body, overlays). The funnel idea survives; "three
  separate views" does not.
- "WRITING PANEL" as the name — renamed THE MANUSCRIPT, 16 June.
- THE RIGHT-HAND ROADMAP — to be removed (duplicates the wheel), 16 June.
- "LIBRARY" as a NOTES item — replaced by "Snippets", 16 June.
- IMAGES ON NOTES — dropped 17 June. A quick-note holds text only; images
  live in the RESEARCH section.
- THE ROUND GLOSSY RED PUSHPIN for the pinned note — superseded 17 June by
  the FILLED THUMBTACK that matches the gold outline shape (same shape,
  one outline, one filled).
- THE OVERVIEW "COVER & OUTLINE" GROUP — removed 13 July. Cover returns in
  the PUBLISH section; the Outline box is gone (the gathered synopsis will
  be the story-description home instead).
- FORMAT dropdown + TARGET AUDIENCE on Overview — removed 13 July (Genre
  and Classification cover them).
- THE CLOCK GLYPH ON GREYED FORMATS — dropped 13 July for the list (keep it
  thin); the coming-soon note is hover-only, no per-row marker. (Clock kept
  as vocabulary elsewhere: still = coming, spinning = working.)
- THE CALM FOUR-HEADING SITE MAP AS THE INTENDED MAP — superseded 14 June
  as the *whole* intent: now only the calm SIDEBAR version. The intended
  Site Map is THEATRICAL. The four-heading map is kept, not killed.
- THE 14-JUNE SIDEBAR CONSTELLATION TRIES — all PARKED; the theatrical map
  wants its own page.
- "PLOT MAPPING" as a name/item — dropped; it IS Synopsis.
- THE FIRST SITE MAP (11 June) — full branching TREE; superseded by the
  four-heading spine.
- THE "ROAD MAP" NAME — renamed to SITE MAP, 11 June.
- THE OLD GOLD CHARACTERS / BROWN EVENTS section colours — revised 9 June.
- TENSION as a VU NEEDLE / FLAT LINE-WITH-POINTER / plain "55%" text — all
  superseded by the segmented bar meter.
- MERGING the left scene menu INTO the wheel — rejected 9 June.
- SITE MAP BUTTON TREATMENTS B / C / D (WP Prompt/Expand) — "A" chosen.
- MAPS & GEOGRAPHY / "SimCity" stamp composer / tile sets — DROPPED 8 June.
- POP-UP RESTYLE to the "C / ticket" note — abandoned 8 June.
- Per-user NAV reordering — dropped 8 June.
- [Earlier superseded items — the shutter, the old vertical board, the
  fusion, the card model, the one-screen X-ray, the horizontal strip,
  rollToCentre, the single reused pop-up, etc. — as in dcw.md /
  locked-decisions.md history. Unchanged.]
RETAINED FROM HISTORY (still live): the QUIET NOTE grammar; Dark Thoughts
(private, never exported); the SECTION ? help pill; the SIX TRACK COLOURS;
carried features (Emotional Maps, Ambient, the lift) awaiting placement.