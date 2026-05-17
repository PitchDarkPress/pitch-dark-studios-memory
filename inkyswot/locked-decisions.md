# InkySwot — Locked Decisions
*Last updated: 14 May 2026*

These decisions are final. Do not revisit, suggest alternatives,
or work around them unless Kev explicitly asks you to, or unless
it seems genuinely wise to flag something.

---

## IDENTITY & BRANDING

Name: InkySwot (capital I, capital S. Always.)
Tagline: Publish and be prepared.
App hero text: PUBLISH AND BE DAMNED (no full stop)
Landing line: The world's first Digital Creative Workstation
for writers (no full stop)
Owned term: DCW — Digital Creative Workstation.
Said as three letters: D.C.W.
Sidebar label: DCW
Screen label: Digital Creative Workstation
Newsletter: The InkySwot Bugle
AI position: AI welcome. AI optional. Always writer-led.

---

## COLOURS

#0f0d0a / #18120d / #221a14
Ink: #e8e0d0 / #b0a090 / #706050
Gold: #c9923a / #e8b060
Rule: #221709 / #352815
Light: #fafaf8 / #1a1410 / #b07820

---

## FONTS

Playfair Display 900
Crimson Pro 300/400/600
JetBrains Mono 300/400/500
All Google Fonts.

---

## PRICING

One tier. No feature gates. No second class writers.

Monthly: £7.95 / 150 prompts per day / everything included
Annual: £79.50 / two months free / same everything
Top-up: £1.99 for 500 prompts / available, never pushed
Lifetime: by invitation / Kev, Sara, early testers / everything forever

Free tier: 1 project / localStorage / 20 AI calls per day /
JSON export / £1.99 per Store publication

Ada's contextual observations are FREE — do not count against
prompt allowance. Ada conversational responses count.

Lifetime members: infinity symbol in header instead of number.
Server-side flag: is_lifetime: true in Supabase.
Must be before F12 blocker.

Prompt top-up economics: 150/day is generous — most writers use
10-20. Top-up at £1.99/500 gives good margin at Haiku pricing.
Micro-transactions below £1.99 do not work with Stripe fees.

---

## TECHNICAL

URL: inkyswot-app.vercel.app
Production: app.inkyswot.com (DNS pending UK Cheapest)
Repo: github.com/PitchDarkPress/inkyswot-app
Vercel Hobby — auto-deploys on push to main.
Single HTML file.
API: claude-haiku-4-5-20251001
Key: inkyswot-app-2 — Vercel Environment Variables ONLY.
NEVER IN GITHUB.

---

## BUILD RULES

Fix before moving on. No snag lists. No deferred problems.
No patches on patches. One step at a time.
Explain before doing. Wait for confirmation.
Persistent bugs: rebuild from scratch. Never overwhelm.

---

## FORMAT LIST

Novel / Short Story / Novella / Flash Fiction / Screenplay /
Teleplay / Radio Drama / Audio Drama / Stage Play / Picture Book /
Children's Book / Graphic Novel / Poetry Collection / Non-Fiction /
Memoir / Essay Collection / Literary Journal / Cookbook / Other

---

## GENRE

Three fields: primary genre + two sub-genres.
All three feed AI context.
Not a dropdown. Not a tag cloud.

---

## SIGNUP & VERIFICATION

Email + password (no card) → Email verification →
Platform code (unique, 20 min, max 3 requests,
3 failures = account lock + spam flag).
Ada handles messaging.

---

## SPAM PREVENTION

Free: £1.99 per publication (transparent).
Paid: 2 free per week, £1.99 additional.
Verification code = second filter.

---

## DATA IMPORT & MIGRATION

Phase 1: .docx / .pdf / .txt / .fountain in New Project modal.
Smart Entity Assignment. Sandbox workaround for migrants.
Phase 2: Scrivener .scriv. Roadmap in What's New.

---

## FORMAT CONVERSION

Export Suite. Both directions.
'InkySwot has done the heavy lifting — the craft is still yours.'

---

## FONT MANAGEMENT

Publishing Suite / Templates. Google Fonts API.
Fontsquirrel / Font Library supplementary.
Licensing disclaimer included.

---

## REMOVED — NOT BEING BUILT

Cover thumbnail on Overview — removed.
AI-generated cover concepts — removed until post-launch revenue
justifies image generation API cost.

---

## INFRASTRUCTURE & COSTS

Vercel Hobby (free)
Supabase (free dev → Pro ~£20/month at launch)
claude-haiku-4-5-20251001
Resend: Step 9
Stripe: Step 8
ElevenLabs API: pre-launch
Launch cost: ~£20/month

---

## LEGAL & GDPR

Privacy Policy / Terms / Cookie Policy / Acceptable Use —
all required before email capture.
Data deletion: 30 days.
Free tier: local only.
InkySwot never sells user data. Ever.

---

## OPEN DECISIONS — NOT YET LOCKED

These must be resolved before the relevant build step:
- Writing panel tagline (undecided)
- Chapters screen spec (superseded — new spec needed)
- Export Suite full spec (needed before Step 14)
- Manuscript storage 5MB decision
- Sandbox v4.0 position
- Proauthorism credit in app (undecided)
- Beta programme structure (undecided)
- Store full anti-spam strategy (needed before Step 15)
- Six user flow gaps (resolve in Step 2)
- Ada voice — Sara Martin will NOT be voicing Ada.
  Alternative to be decided.