# InkySwot — Security
*Last updated: 19 May 2026*

---

## PRINCIPLE

Security is not an afterthought. It is built in from the
start. Every layer is considered before it is needed.
This file grows as InkySwot grows. Real threats inform
real responses. What we learn here informs every other
Pitch Dark Studios platform that follows.

---

## THREAT LEVEL 1 — IMMEDIATE (Pre-Launch)

### Spam Account Creation
The most immediate threat. Bad actors creating hundreds
of accounts to abuse the free AI prompt allowance.

FIRST LINE DEFENCES — LOCKED:
- Email verification code: unique, 20 min expiry,
  max 3 requests, 3 failures = account lock + spam flag
- Free tier: 20 AI calls per day only
- Store: £1.99 per publication on free accounts
- Paid: 2 free Store publications per week, £1.99 after

BEHAVIOUR PATTERN RECOGNITION:
Over time we will learn to recognise abuse patterns.
Flag and log accounts that show:
- Multiple projects created in rapid succession
- AI prompt limit hit every single day from day one
- No actual writing — only AI generate button use
- Multiple accounts from the same IP address
- Accounts created in bursts (many in short time window)
- Free tier accounts hitting Store limits repeatedly
- Accounts from known VPN or proxy IP addresses

Ada monitors and flags suspicious behaviour quietly.
She does not accuse — she flags for review.

### IP Tracking and Location Detection
Every account signup logs IP address and location.
Platform: IPinfo.io — country, city, organisation,
VPN and proxy detection.
Alternative: Cloudflare (if adopted for DDoS protection —
gives location data automatically, no extra integration).

VPN/proxy use at signup = automatic flag for review.
Not a block — a flag. Legitimate users use VPNs.
But it is a signal worth noting.

Multiple accounts from same IP = automatic flag.

### API Key Security
claude-haiku-4-5-20251001 API key: Vercel Environment
Variables ONLY. Never in GitHub. Never in client code.
All AI calls routed through server-side proxy.
Key: inkyswot-app-2

### Prompt Counter Security
Steps 5-7 in the build list address this directly:
- Step 5: Lifetime flag server-side in Supabase
- Step 6: F12 blocker — prevents localStorage manipulation
- Step 7: Prompt counter moves to Supabase server-side
Non-negotiable before launch.

---

## THREAT LEVEL 2 — AT LAUNCH

### Payment Fraud
Stripe handles card fraud detection automatically.
Additional measures:
- One account per payment method where possible
- Flag accounts that upgrade then immediately hit
  Store limits aggressively
- Monitor for chargebacks — pattern of upgrade,
  abuse, chargeback is a known fraud pattern

### Content Abuse in the Store
Full anti-spam strategy needed before Store build.
First line locked — see locked-decisions.md.
Still needed:
- Automated content scanning
- Human review triggers
- Account suspension criteria
- Appeals process

### Account Takeover
- Strong password requirements at signup
- Email verification required
- Password reset via verified email only
- Rate limit login attempts
- Flag logins from new locations or devices

---

## THREAT LEVEL 3 — POST-LAUNCH

### DDoS Protection
Cloudflare — recommended. Free tier covers most threats.
Routes traffic through Cloudflare before it hits Vercel.
Automatic DDoS mitigation. Location data as bonus.
Decision: implement before launch or immediately after.

### Data Breach Prevention
- No sensitive data stored in localStorage
- All user data in Supabase — encrypted at rest
- GDPR compliant — see locked-decisions.md
- Data deletion within 30 days of request
- InkySwot never sells user data. Ever.
- Regular Supabase security audit post-launch

### Escalating Threats
As InkySwot grows it becomes a more attractive target.
Post-launch security review at:
- 1,000 users
- 10,000 users
- Each time a new major feature launches

---

## WHAT WE ARE WATCHING FOR

Patterns that suggest coordinated abuse:
- Sudden spike in signups from same region
- Multiple accounts with similar usernames
- Accounts that never interact with the writing tools
- Accounts that exist only to publish to the Store
- Referral abuse if a referral programme is introduced

---

## OPEN DECISIONS

- Cloudflare adoption: recommended pre-launch
- Full Store anti-spam strategy: needed before Step 15
- Content scanning tool: to be selected
- Human review process: to be designed
- Security audit schedule: to be set post-launch

---

## LESSONS TO CARRY FORWARD

This section grows as InkySwot goes live.
Real threats, real responses, real patterns.
Everything learned here informs the security approach
for every other Pitch Dark Studios platform.
