File: inkyswot/press.md
Last updated: 29 May 2026

THE PRESS — FULL SPECIFICATION
This is a new specialist file.
Add to the specialist files list in current-state.md.

WHAT THE PRESS IS
The Press is where the writer goes when the book is done.
It is a separate section of InkySwot — distinct from the
writing workflow. The manuscript leaves the desk and goes to press.
It is not part of the project nav.
It has its own top-level section in the platform.
Entry point: the writer declares the book ready.
From that moment, The Press takes over.

THE PRESS IS NOT THE EXPORT SUITE
The Export Suite (Step 14) handles file export —
Word, PDF, JSON, EPUB, AI platform formats.
That is for working writers sharing and backing up their work.
The Press is for publication. The end of the writing journey.
The beginning of the reader's journey.
These are two different things and must never be conflated.

FORMAT CHOICES
When the writer enters The Press they choose their format:
Paperback
Hardback
Ebook
Audiobook — future. See AUDIOBOOK section below.

Each format has a completely different workflow.
Different cover requirements.
Different interior layout requirements.
Different platform requirements.
Different metadata requirements.
The Press handles all of them.

DESTINATION PLATFORMS
After choosing format the writer chooses their destination:

PRINT (Paperback / Hardback):
Amazon KDP — dominant. Most writers start here.
IngramSpark — professional grade. Wider distribution.
Lulu — popular with independents and small press.
Barnes & Noble Press — US focused.
Other — manual spec entry for platforms not listed.

EBOOK:
Amazon KDP — Kindle format.
Draft2Digital — aggregates to multiple platforms
(Apple Books, Kobo, Barnes & Noble, libraries, and more).
Kobo Writing Life — direct Kobo submission.
Apple Books for Authors — direct Apple submission.
Smashwords (via Draft2Digital) — wide distribution.
Other — manual spec entry.

BOTH (Print + Ebook simultaneously):
The Press can prepare both formats at the same time.
Different files. Different specs. One workflow.

THE PLATFORM REQUIREMENTS DATABASE
This is the operational heart of The Press.
Every destination platform has its own requirements.
These change. Platforms update their specs without warning.
InkySwot maintains a live requirements database
for every supported platform.

What is stored per platform:
Accepted file formats (PDF, EPUB, MOBI, DOCX etc.)
Page size options (6x9, 5.5x8.5, A5, etc.)
Margin requirements (inside / outside / top / bottom)
Bleed settings (with bleed / without bleed)
Cover dimensions (calculated from page count and page size)
Spine width calculation formula (pages x paper thickness)
Cover file format requirements
Cover colour space (RGB / CMYK)
Image resolution requirements (300 DPI minimum for print)
ISBN requirements (mandatory / optional / provided by platform)
Metadata requirements (title / author / description / categories /
keywords / language / publication date / BISAC codes)
Front matter requirements (what must appear and in what order)
Back matter requirements
Content guidelines and restrictions
Upload process specifics
Review timelines
Royalty structures (for reference — not financial advice)

THE MAINTENANCE COMMITMENT
Platform requirements change. This is non-negotiable.
InkySwot must monitor and update the requirements database
whenever a platform changes its specs.
This is an ongoing operational commitment — not a one-time build.

How it works:
Each platform entry has a last verified date.
Pitch Dark Press monitors platform announcements and
update notifications.
When a platform changes its requirements InkySwot updates
the database immediately.
Writers using The Press are always working to current specs.

Alert system:
If a platform changes its requirements after a writer
has begun their Press workflow, InkySwot alerts them.
The workflow pauses. The writer is shown what changed.
They confirm and continue with the updated specs.
No writer uploads a file to a stale specification.

Validation layer:
Before any file is generated, InkySwot validates the
manuscript against the destination platform's current
requirements.
Word count within acceptable range.
Images at correct resolution.
Fonts embedded correctly.
No disallowed content flagged.
Front and back matter complete.
Metadata complete.
Cover dimensions correct.
The writer sees a checklist. Green lights only before export.

THE COVER CREATOR
The cover is made of three elements:
Front cover / Back cover / Spine.

The spine problem — solved:
The spine width varies with page count.
Traditional cover design tools require the designer
to recalculate and rebuild the spine every time
the page count changes.
InkySwot solves this with the Fixed Spine System.

Fixed Spine System:
The spine is built at maximum width — oversized.
The front and back covers slide over it,
masking whatever width is not needed.
As page count changes, the covers move in or out.
The spine never changes. Only what is visible of it does.
Spine content — title, author, publisher logo —
sits in the centre of the spine and is always visible
regardless of page count.
No recalculating. No reformatting. No rebuilding.

Cover Creator interface:
Three-panel canvas — front cover / spine / back cover.
Drag and drop elements.
Image upload with crop and position tools.
Text layers — title, author, series, tagline, blurb snippet.
Font selector — Google Fonts API.
Colour tools.
Barcode / ISBN placement (auto-positioned to platform spec).
Real-time spine width adjustment as page count changes.
Cover preview — flat and wrapped (3D book view).
Export to platform-correct specifications automatically.

THE BOOK LAYOUT TOOL
The writer sees their book as a physical object on screen.
An open book. Blank at first. Flippable page by page.

What it shows:
Left page and right page — correct recto/verso positioning.
The spine.
Every page in sequence — front matter, chapters,
back matter — in the correct physical position.
Page numbers where they belong.
Chapter headings where they fall.
Images in position, with correct bleed and margins shown.
The exact print area — what will and won't be trimmed.

What the writer can do:
Flip through the book like a real book.
Drop content onto pages — text blocks, images, headings.
Move and resize elements.
See immediately how a change affects surrounding pages.
See where chapter one actually falls on the physical page.
See whether the spine content is visible at this page count.
Zoom in to check detail. Zoom out to see the whole spread.

Why this matters:
With KDP and other POD platforms the writer currently
cannot see how the book will look until after uploading.
Errors — wrong margins, images too close to the trim,
spine content cut off — are only discovered after the fact.
The Book Layout Tool eliminates this entirely.
What the writer sees on screen is what prints.

FRONT AND BACK MATTER ASSEMBLY
The Press assembles front and back matter automatically
from the project database.

Front matter (in correct order for chosen platform):
Half title page
Series page (if applicable)
Title page — title, author, publisher, year
Copyright page — auto-generated from project metadata
Dedication — from Overview or entered in The Press
Epigraph (optional)
Table of contents — auto-generated from Chapters
Foreword / Preface (optional — writer adds)
Acknowledgements (optional — writer adds)

Back matter (in correct order for chosen platform):
Author biography — from author profile or written by Ada
Also by this author — from other InkySwot projects
Bibliography / References (if applicable)
Index (future — complex to automate)
Colophon (optional)

Ada's role in front and back matter:
Ada writes first drafts of:
Back cover blurb — drawn from synopsis, genre, tone, characters.
Author biography — drawn from author profile.
Acknowledgements — prompted, writer adds names.
The writer reviews, refines, and makes it their own.

METADATA
Every platform requires metadata at submission.
InkySwot collects and stores metadata from the project:
Title / Subtitle / Series / Series number
Author / Co-author / Editor / Illustrator
Publisher (Pitch Dark Press or writer's own imprint)
Publication date
Language
ISBN (writer's own or platform-provided)
BISAC category codes (up to 3 — selected from list)
Keywords (up to 7 for KDP — guided entry)
Description / blurb (from Ada or writer)
Age / content rating
Price (per platform — writer sets)
Territory rights (worldwide or restricted)

InkySwot pre-fills everything it knows.
The writer completes what remains.
The Press validates before export.

EBOOK SPECIFICS
EPUB format — universal standard.
MOBI — Kindle legacy (KDP now prefers EPUB).
Reflowable text — correct for most ebooks.
Fixed layout — for illustrated books, children's books,
graphic novels, cookbooks. Different spec entirely.
InkySwot detects format type from manuscript format
chosen at project setup and handles accordingly.
Cover image — separate high-res JPEG for ebook platforms.
Table of contents — linked, navigable.
Fonts — embedded or system fonts per platform requirement.
Metadata embedded in file — not just submitted separately.

AUDIOBOOK — FUTURE
Audiobook is a separate format with a completely different
workflow. Not on the current build list.
When built it will include:
AI voice selection — character voices, narrator voice.
Human voice option — recording guidance and file format spec.
Chapter by chapter audio assembly.
Cover — square format (different from print and ebook).
Submission to ACX (Audible), Findaway Voices, Author's Republic.
Full spec to be written when revenue supports the build.

WHAT THE PRESS IS NOT
Not a design agency. Not a vanity press.
Not a guarantee of publication success.
Not financial or legal advice.
The Guide (honest, platform-agnostic publishing guidance)
remains a separate feature within The Press — see below.

THE GUIDE
Honest, platform-agnostic publishing guidance.
Not a sales tool. Not affiliated with any platform.
Covers:
What POD publishing actually costs.
What royalties actually look like.
What distribution actually means.
What ISBN ownership means and why it matters.
How to choose between KDP and IngramSpark.
What to expect from the review process.
Common mistakes and how to avoid them.
Written by Kev. Updated as the industry changes.

BUILD POSITION
The Press is a new step in the build order.
Currently the Publishing Suite is Step 15.
The Press replaces and significantly expands Step 15.
Exact position in build order to be confirmed.
Needs Export Suite (Step 14) in place first.
Needs Cover Creator — complex, may need its own sub-step.
Needs Book Layout Tool — complex, may need its own sub-step.
Platform requirements database — operational from day one.
The Guide — can be written in parallel with build.
Full build timeline to be assessed before Step 14 begins.

OPEN DECISIONS
Build order position — to be confirmed.
Cover Creator sub-step — to be assessed.
Book Layout Tool sub-step — to be assessed.
Fixed list of supported platforms at launch — to be confirmed.
ISBN guidance — does InkySwot help writers obtain ISBNs?
Price setting guidance — how much help does InkySwot give?
Audiobook timeline — post-launch, when revenue supports it.
Index automation — complex, post-launch consideration.