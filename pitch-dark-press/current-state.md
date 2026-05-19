# Pitch Dark Press — Current State
*Last updated: 19 May 2026*

---

## WHAT PITCH DARK PRESS IS

The Pitch Dark Studios publishing imprint.
Live and operational.
Publishes under the Proauthorist philosophy —
declared, as always.

Not a platform. An imprint. The distinction matters.
Pitch Dark Publishing is the platform that enables
others to do what Pitch Dark Press does.

---

## LIVE URLS

Main site: www.pitchdarkpress.com
GitHub repo: PitchDarkPress/pdp-site
GitHub Pages fallback: pitchdarkpress.github.io/pdp-site

---

## DOMAIN

Registrar: Namecheap
Account: TWOFINGERFILMS
Domains: pitchdarkpress.com and pitchdarkpress.co.uk
DNS switched from Wix to GitHub Pages — May 2026.
Wix subscription runs until December 18 2026 — cancel
when ready.

DNS records (Namecheap):
A Record @ → 185.199.108.153
A Record @ → 185.199.109.153
A Record @ → 185.199.110.153
A Record @ → 185.199.111.153
CNAME www → PitchDarkPress.github.io

---

## THE WEBSITE — PAGES

Home (index.html)
Manifesto text. Navigation to Manifest / Dispatches /
Connect. Amber LED pulses every 7 seconds bottom right.

Dispatches (dispatches.html)
Three tabbed FAQ sections: Doing It Yourself /
Pitch Dark Press / Proauthorism.
Managed via Dispatches Admin.

Connect (connect.html)
Contact form via Formspree.
Endpoint: https://formspree.io/f/xdablozg
Submissions to: kev@kevinmartinmedia.com
Free tier: 50 submissions per month.

Ecosystem (howto.html)
Proauthorism and InkySwot showcase page.

The Manifest (catalog/index.html)
Full book catalogue. Filter by status. Search.
Clickable hashtags. Links to individual book pages.

Book Detail (catalog/book.html)
Individual book page. Dynamic from books data array.

---

## ADMIN SYSTEMS

Gateway
URL: www.pitchdarkpress.com/gateway.html
Password: pitchdark2026
Access: invisible dot (.) in footer of every page —
click the dot after "Declared, as always."
The dot is the same colour as the background.

Control Page
URL: www.pitchdarkpress.com/control.html
Links to both admin panels.

Manifest Admin
URL: www.pitchdarkpress.com/catalog/admin.html
Manages all books. Add / edit / delete / cover upload.
Publishes direct to GitHub (pdp-site repository).
GitHub token stored in localStorage as pdp_gh_token.
Book data stored in localStorage.
ALWAYS hit Publish after changes — localStorage is not
permanent. Clearing browser history loses the token.

Dispatches Admin
URL: www.pitchdarkpress.com/dispatches-admin.html
Manages all FAQ content.
Publishes direct to GitHub (pdp-site repository).
FAQ data stored in localStorage as pdp_dispatches.
ALWAYS hit Publish after changes.

---

## DESIGN SYSTEM

Fonts: Cormorant Garamond (headings) /
Montserrat (body/UI). Both Google Fonts.
Base font size: 18px.

Colours:
Background: #0a0a0a
Text: #f0ece4
Accent/buttons: #607D1E (olive)
Dividers: #222
Muted text: #888
InkySwot accent: #c8a84b (gold)

Nav: Sticky top. Logo at 64px.
Links: Home / Dispatches / Manifest /
Proauthorism / Connect / Ecosystem.

---

## CONTACT

Formspree: formspree.io
Account: kev@kevinmartinmedia.com
Form: Pitch Dark Press Contact
Endpoint: https://formspree.io/f/xdablozg
Free tier: 50 submissions/month.

---

## THE MANIFEST — BOOK STATUSES

Published — live and available
Coming — confirmed, in production
Free — available to read free
Taking Shape — active work in progress
Emerging — early stage development
Smoke — just an idea

---

## CURRENT BOOKS

The Adventures of A. Rapscallion — Published
Closure Sufficient — Coming — Pitch Dark Collective
The Mystery of Gallows House — Coming
KEELER: credendum — Taking Shape — Pitch Dark Collective
The Winchester Geese — Emerging
Revenge of An Ordinary Man — Free
The Dead Broke Cookbook — Taking Shape —
Pitch Dark Collective
The Renting — Smoke

---

## THE ROOM

Three.js room. Spec locked. See room.md.

Hero: Victorian standing desk. Bare bulb above.
Printing press letter blocks on the desk. Chase set.
Corner: Simple printing press in the shadows.
Sound: Rhythmic thud and hiss of a press. Background.

---

## OUTSTANDING TASKS

- Set custom domain in GitHub Pages settings
- Tick Enforce HTTPS once available
- Point pitchdarkpress.co.uk to GitHub Pages
- Cancel Wix subscription (December 2026 deadline)
- Fix SSL on proauthorist.com (separate platform)
- Delete or archive old catalog repository
- Complete descriptions and covers for all 8 books
- Fix Rapscallion Amazon link (currently placeholder)
- Update any bookmarks pointing to old admin URL:
  pitchdarkpress.github.io/catalog/admin.html
  Correct URL: www.pitchdarkpress.com/catalog/admin.html
  Old catalog repository still exists but is retired.