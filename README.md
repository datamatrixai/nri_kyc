# NRI KYC Onboarding – Clickable Prototype

Demo of an AI-assisted NRI onboarding flow: **Case → Documents → AI Verification → RM Sign-off + Audit Trail**.
Single static file (`index.html`), no build step, no backend. Extraction is **simulated** with sample data; nothing is uploaded anywhere.

## Run locally
Open `index.html` in any browser.

## Deploy on GitHub Pages
1. Create a new GitHub repo (e.g. `nri-kyc-prototype`).
2. Upload `index.html` and `README.md` to the repo root (Add file → Upload files), or:
   ```bash
   git init && git add . && git commit -m "NRI KYC prototype"
   git branch -M main
   git remote add origin https://github.com/<your-username>/nri-kyc-prototype.git
   git push -u origin main
   ```
3. Repo **Settings → Pages → Build and deployment**: Source = *Deploy from a branch*, Branch = `main` / `(root)` → Save.
4. Share the link: `https://<your-username>.github.io/nri-kyc-prototype/`

## Demo script (3 minutes)
1. Load **clean sample** → run verification → all checks pass → RM approves.
2. Load **case with issues** → shows name mismatch, near-expiry passport, invalid PAN, stale address proof, US-person indicia → approval blocked.
3. Export the **audit trail JSON**.

## Path to production
Replace the simulated `run()` with API calls to self-hosted Document AI (India-hosted), add real OCR/face-match, rules engine, and core-banking/PMS connectors.
