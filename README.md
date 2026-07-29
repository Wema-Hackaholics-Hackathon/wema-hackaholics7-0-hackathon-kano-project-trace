# Trace

**Hackathon:** Wema Hackaholics 7.0 — Kano
**Team:** Trace
**Track:** Financial Inclusion

---

## Team Members

- Yoosuph (`ylawan658@gmail.com`)
- Munir Kabir Ammani (`ammanikabir2@gmail.com`)
- Muhammad Musa Odaudu ( `maqitsolutions@gmail.com`)
- [Name 4]
- [Name 5]

*Replace remaining placeholders with full team member names before final submission.*

---

## 🚀 Live Demo

* **Live prototype:** https://wema-trace.vercel.app/
* **Source:** https://github.com/MKAmmani/trace
* **Recorded demo:** https://www.youtube.com/shorts/w1IhpzbmEu8

The live link is a **static, front-end-only prototype**. There is no backend, no database, and no live connection to any bank system. Everything described below runs entirely in the browser.

---

## 🎯 The Problem

> Small business owners in Nigeria — cash-heavy micro-retailers like a neighbourhood pharmacy or provisions store — do real, honest business every day, but almost none of that activity is verifiable to a bank. Self-reported sales figures are easy to fabricate, so banks can't safely extend credit, and merchants stay locked out of formal financing regardless of how well their business is actually doing.

This is a Financial Inclusion problem, not an Open Banking one: the barrier isn't lack of a bank account, it's the lack of *independently verifiable* proof of activity.

---

## ✨ Our Solution

**Trace** turns a merchant's everyday sales into proof a bank can trust, and lets that proof stand behind a generic loan application.

1. **Sign up** — enter an existing Wema account number, which pulls back (simulated) KYC details already on file — name, phone, BVN and NIN verification status — so the merchant never re-enters identity information. A short business-details step (business name, trade type, city) follows.
2. **Sign in** — for returning users, the same credentials as the existing Wema mobile app.
3. **Log a sale** — when a payment lands, the merchant logs what was sold and confirms it took place.
4. **Independent confirmation** — the customer who paid is asked to confirm the sale independently, either by tapping a WhatsApp message or by dialing a short USSD code sent via SMS (no smartphone or data required). A confirmed sale counts fully toward the merchant's **Trace score**; an unconfirmed one counts for much less.
5. **Trace score** — built from confirmed sales, the number of distinct customers who confirmed them, and months of trading history. Nothing about the score is a black box — a full breakdown is visible on the merchant's own dashboard.
6. **Loan application** — a generic application (amount requested, purpose: restocking, equipment, expansion, or working capital) is submitted alongside the Trace score for Wema to review. It is not an instant, automatic approval — it's framed as a real application pending a human decision, matching how lending actually works.
7. **Bank view** — a separate credit-officer-facing screen shows the same data with an explicit "could this be faked?" section: how many distinct customers confirmed sales, what share of sales were independently confirmed rather than self-reported, and that confirmations arrive from the customer's own phone number rather than something the merchant can generate.

---

## 🛠️ Tech Stack — what this actually is

This is intentionally a **single static HTML file** — no framework, no build step, no backend, no database.

* **Frontend:** Vanilla HTML, CSS, and JavaScript in one file
* **State:** This is just a working prototype that shows exactly how the solution will really works.
* **Backend:** None. There is no server, no API, and no database.
* **Deployment:** Static hosting on Vercel — https://wema-trace.vercel.app/

There is no LLM involved anywhere in the scoring or credit logic; the score is a deterministic formula over locally-held demo data.

---

## ⚙️ How to Run Locally

Because it's a single static file, there is no install step and no dependencies.

### Option 1 — open directly
Download the HTML file and open it in a browser.

### Option 2 — serve it locally (recommended, avoids browser file:// restrictions)




There is no reset endpoint or database to seed — using the in-app **"Fast-forward 6 months"** demo button reseeds a sample sales history, and reloading the page clears everything back to a blank slate.

---

## Demo Safety — what is simulated and what is real

Being direct about this, since it matters for judging:

* **All merchants, customers, and transaction data are fictional**, generated within the app for demonstration.
* **Account number verification is a mocked lookup** against a small hard-coded set of demo profiles — it does not call Wema's real core banking system. Any 10-digit number will resolve to one of a few demo identities.
* **Login accepts any non-empty phone/username and password** — there is no real authentication server.
* **WhatsApp confirmation uses a real `wa.me` deep link** (so it does open WhatsApp with a pre-filled message), but the "customer's phone" screen inside the demo itself is a simulated view, not an actual second device or account.
* **USSD confirmation is illustrative only** — the on-screen `*945*55*XXXX#` dial prompt is a mockup; dialing it on a real phone would not reach any live system.
* **The loan approval step includes a "Demo: Wema approves" button** so the full application-to-approval loop can be shown live in a pitch. In a real product this would be a human loan officer's decision, not an instant in-app action.
* **No real money moves anywhere in this prototype.** There is no connection to Wema's production banking systems, NIBSS, or any live payment rail.

---

## Links

| Resource | URL |
|---|---|
| Live prototype | https://wema-trace.vercel.app/ |
| Source | https://github.com/MKAmmani/trace |
| Recorded demo | https://www.youtube.com/shorts/w1IhpzbmEu8 |

---

## Repository note

*[Add a note here linking this submission repository to the full project source, if they live in different places — matching however your team's Classroom/hosting setup is actually structured.]*
