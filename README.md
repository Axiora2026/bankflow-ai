# BankFlow AI

A competition prototype for transaction complaint routing and resolution. Created for David Mukwauri / Found3r.

## Run

Open `index.html`, or serve the folder with `python3 -m http.server 8080`.

## Demo walkthrough

1. Review the operations overview and open the case queue.
2. Open case BF-2026-0105 and review the transaction evidence.
3. Add an internal note, change its status, and save a public progress note.
4. In Customer portal, choose TXN-26005 (the initially resolved transaction), describe an issue and submit it.
5. Use the new case reference in Track a case.
6. View the updated analytics and audit log.

Open cases prevent duplicate complaints against the same transaction. Fraud-related wording routes cases to Fraud & Risk. Sensitive decisions remain with staff.

## GitHub Pages

Create a public repository named `bankflow-ai`, upload this folder's contents to its root, and use `main` as the default branch. In Settings → Pages, select **GitHub Actions**. The included workflow deploys the app. The expected address for Axiora2026 is `https://axiora2026.github.io/bankflow-ai/` after deployment succeeds.

Alternatively, use **Deploy from a branch**, `main` and `/ (root)`; the static files do not require a build step.

## Prototype boundaries

All customers and transactions are synthetic. USD is the sole currency in the sample dataset. Cases are saved in browser localStorage on one device and origin; staff and customer views are demo roles, not authenticated accounts. Classification is deterministic rules, not a trained AI model. SLA targets are illustrative, not bank policy. Status updates are displayed in the app; no email or SMS is sent. Logs are editable browser data, not an immutable audit trail. Do not enter real banking or personal data.

## 90-day pilot outline

- Days 1–30: validate one bank workflow, baseline metrics, access controls, retention and integration requirements.
- Days 31–60: implement authenticated backend, bank-approved read-only integration, encrypted persistence and server-side audit events; test with staff.
- Days 61–90: run a limited authorised pilot and measure resolution time, manual touches, SLA compliance, repeat contacts and routing accuracy.

A production system needs verified identities, server-side authorisation, case access controls, approved data handling, security testing and controlled integration before any real banking use. AI-assisted routing may be added only with validation, confidence thresholds and human oversight.

## Files

- `index.html`: shell and navigation
- `styles.css`: responsive interface
- `engine.js`: synthetic transaction data and routing rules
- `app.js`: cases, customer portal, tracking, analytics and audit history
- `.github/workflows/pages.yml`: static deployment
