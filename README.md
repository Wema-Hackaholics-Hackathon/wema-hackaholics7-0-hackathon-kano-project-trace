# Wema MarketFlow

**Hackathon:** Wema Hackaholics 7.0 — Kano  
**Team:** Trace  
**Track:** Financial Inclusion (Open Banking as supporting intelligence layer)

---

## Team Members

- Yoosuph (`ylawan658@gmail.com`)
- [Name 2]
- [Name 3]
- [Name 4]
- [Name 5]

*Replace remaining placeholders with full team member names before final submission.*

---

## 🚀 Live Demo

*   **Live Application:** https://wema-marketflow-yoosuph.netlify.app  
*   **Source (full project):** https://github.com/Yoosuph/wema-marketflow  
*   **Backend API:** Local / demo only for now (Netlify serves the frontend in **preview mode** with seeded demo data; no live bank money)  
*   **Recorded Demo:** [Link to your Loom walkthrough — pending]

Netlify admin: https://app.netlify.com/projects/wema-marketflow-yoosuph

---

## 🎯 The Problem

> How might we help cash-heavy micro-retailers turn irregular earnings into verified restock orders on Wema—without another wallet, POS fleet, or unaffordable loan?

Cash-heavy traders restock in lump sums but earn in small, irregular increments. Formal accounts often do not capture real commercial activity, while self-reported sales are easy to fabricate. Feature-phone users also cannot depend on smartphone-only products.

---

## ✨ Our Solution

**Wema MarketFlow** is a Wema-owned **restock rail** for micro-retailers (starting with community pharmacies / licensed PPMVs).

It is **not** a new wallet, marketplace, inventory suite, or generic cash loan. It orchestrates:

1. An optional **restock pocket** funded from qualifying Wema business receipts  
2. Orders from an **approved supplier catalogue**  
3. Funding via account balance, pocket, or **agent cash-in** (pending until Wema confirms)  
4. Dispatch + merchant delivery confirmation + Wema verification → a **three-proof trade record**  
5. After repeat verified trade, a small **supplier-paid inventory top-up** with disclosed cost  
6. Repayment only from **qualifying business receipts** under a separate mandate  
7. Optional **read-only Open Banking** consent for affordability comparison (never debit authority)

Every bank-core, identity, bureau, NIBSS, supplier, and production Open Banking connection in this submission is a **simulated demo adapter**. No real money moves.

---

## 🛠️ Tech Stack

*   **Frontend:** React 18, TypeScript, Vite  
*   **Backend:** FastAPI, Pydantic 2, async SQLAlchemy  
*   **Database:** SQLite (demo)  
*   **Tooling:** Make, pytest, end-to-end API smoke script  
*   **Deployment:** Netlify (frontend SPA) — https://wema-marketflow-yoosuph.netlify.app  
*   **AI/APIs:** No LLM credit decisions; Open Banking is optional read-only sandbox  

---

## ⚙️ How to Set Up and Run Locally

### Prerequisites

* Python 3.11+ (Conda base env is fine)  
* Node.js 20+ and `pnpm`  
* Git  

### 1. Clone the full project

This Classroom repo holds the submission README. Full application source:

```bash
git clone https://github.com/Yoosuph/wema-marketflow.git
cd wema-marketflow
```

### 2. Install dependencies

```bash
make install
```

This installs backend Python requirements and frontend packages.

### 3. Start the API

```bash
make backend-dev
```

* API: `http://127.0.0.1:8000`  
* OpenAPI docs: `http://127.0.0.1:8000/docs`  

Equivalent command:

```bash
cd backend && python -m uvicorn app.main:app --reload --port 8000
```

### 4. Start the frontend (second terminal)

```bash
make frontend-dev
```

* App: `http://127.0.0.1:5173`

### 5. Demo reset

Use **Reset demo** in the app menu, or:

```bash
curl -X POST http://127.0.0.1:8000/api/v1/demo/reset
```

### 6. Verify (optional)

```bash
make test
make build
./scripts/smoke_api.py
```

`smoke_api.py` expects the API to be running on `127.0.0.1:8000`.

---

## Demo Safety

* All merchants, suppliers, stock, receipts, accounts, and identity data are **fictional**  
* Eligibility is deterministic and bounded by explicit affordability caps  
* No LLM approves credit or moves money  
* Open Banking consent is **read-only** and never authorizes repayment or debit  
* Production Wema authentication, core settlement, and bureau adapters remain explicit pilot dependencies  
* The public Netlify site runs in **preview mode** (seeded demo data); it does not connect to production banking systems  

---

## Links

| Resource | URL |
|---|---|
| Live demo | https://wema-marketflow-yoosuph.netlify.app |
| Full source | https://github.com/Yoosuph/wema-marketflow |
| Classroom submission | https://github.com/Wema-Hackaholics-Hackathon/wema-hackaholics7-0-hackathon-kano-project-trace |

---

## Repository note

This GitHub Classroom repository is the **submission remote** for team **Trace**. The complete MarketFlow application lives at [Yoosuph/wema-marketflow](https://github.com/Yoosuph/wema-marketflow) and is deployed on Netlify.
