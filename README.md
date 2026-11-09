# Golf Card Game Scorecard

A single-page, 4-player scorecard for the Golf card game. Bissy Apps.

## What it is

- One self-contained file, `index.html`. All CSS and JavaScript are inline.
- No build step, no dependencies, no backend.
- No external requests. Fraunces and Inter are self-hosted in `fonts/` because bissyapps.com's Content Security Policy blocks Google Fonts.
- Scores and player names are saved in the browser with `localStorage` (key `golf-scorecard-v1`).

## Features

- 4 editable player names
- 9 or 18 holes, with a Front 9 subtotal in 18-hole mode
- A ± button in each cell for negative scores (phone number pads have no minus key)
- Lowest score per hole highlighted, overall leader highlighted, 1st to 4th ranking
- Winner announced when every hole is filled
- New game button clears scores and keeps names
- Collapsible card-value reference for 6-card Golf

## Deploy

The live app is at **https://bissyapps.com/apps/golf-scorecard**, served the same way as the Phase 10 and Hand & Foot scorecards:

- This repo is connected to the Vercel project `golf-scorecard` (its domain has the `-ochre` suffix because `golf-scorecard.vercel.app` belongs to someone else). Every push to `main` deploys it to https://golf-scorecard-ochre.vercel.app.
- bissyapps.com (the `BissyApps-v1` Next.js site) has a rewrite in its `next.config.ts` that serves `/apps/golf-scorecard` from this project.
- There is no build step. `vercel.json` serves the files at `/apps/golf-scorecard/` on this project's own domain and redirects `/` to it. Asset URLs in `index.html` and `manifest.webmanifest` use that path.

## Run it locally

Open `index.html` in a browser for a quick look (fonts and favicon won't load from a file URL). To test with the real paths, run `npx vercel dev` and open http://localhost:3000/apps/golf-scorecard.

## Known limits

- Opening the file directly from the iPhone Files app shows a preview that does not run JavaScript, so the score grid won't appear there. Open it from the website in Safari instead.
- Scores are stored per browser and per device. They do not sync.
