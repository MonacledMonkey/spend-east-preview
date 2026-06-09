# Spend East review evidence — current build with actual QR

Status: Current review screenshots and QR evidence are ready for Andy review. This file does not claim visual or deployment approval; explicit Andy approval after viewing the current artifacts remains required.

## Guardrails applied

- Onboarding-first flow restored in `mobile/App.js`.
- Direct-dashboard/static-preview assumption removed from `mobile/test/mobile-structure.test.js`.
- Review/no-deploy process documented in `docs/review-and-approval-process.md`.
- Repo instructions updated so screenshots must be attached or linked before approval/deploy.
- Screenshot capture script added: `scripts/capture_review_screenshots.mjs`.
- Static preview QR generation now uses the `qrcode` package to produce real PNG QR data URLs.
- `QrDisplay` renders the generated QR image directly rather than substituting a hand-built placeholder pattern.

## Verification run

- Mobile tests: `npm test` in `mobile` — 8 passed, 0 failed.
- Backend tests: `node --test --test-reporter=spec` in `backend` — 3 passed, 0 failed.
- Static export: `npx expo export -p web` in `mobile` — succeeded.
- Browser/mobile QA: Playwright Chromium, 390×844 mobile viewport, local static export at `http://127.0.0.1:4174/`.
- Visual QR check: `artifacts/screenshots/latest/06-qr-generated.png` shows a dense QR with finder markers, not the old placeholder pattern.

## Review screenshots

All screenshots are current mobile portrait captures from the built static export:

1. `artifacts/screenshots/latest/01-splash-or-onboarding-entry.png`
2. `artifacts/screenshots/latest/02-onboarding-step1.png`
3. `artifacts/screenshots/latest/03-onboarding-step2.png`
4. `artifacts/screenshots/latest/04-onboarding-final.png`
5. `artifacts/screenshots/latest/05-wallet-dashboard.png`
6. `artifacts/screenshots/latest/06-qr-generated.png`
7. `artifacts/screenshots/latest/07-payment-confirmed.png`

## Approval state

Visual/deployment approval pending. Andy must explicitly approve after viewing the current artifacts before release/deploy claims proceed.
