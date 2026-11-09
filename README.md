# Golf Card Game Scorecard

A single-page, 4-player scorecard for the Golf card game. Bissy Apps.

## What it is

- One self-contained file, `index.html`. All CSS and JavaScript are inline.
- No build step, no dependencies, no backend.
- The only external request is Google Fonts (Fraunces and Inter). Without it, system fonts are used.
- Scores and player names are saved in the browser with `localStorage` (key `golf-scorecard-v1`).

## Features

- 4 editable player names
- 9 or 18 holes, with a Front 9 subtotal in 18-hole mode
- A ± button in each cell for negative scores (phone number pads have no minus key)
- Lowest score per hole highlighted, overall leader highlighted, 1st to 4th ranking
- Winner announced when every hole is filled
- New game button clears scores and keeps names
- Collapsible card-value reference for 6-card Golf

## Intended location

`bissyapps.com/apps/golf-scorecard/`, listed on the `bissyapps.com/apps` page next to the Hand and Foot and Phase 10 scorecards.

## Integration checklist

1. Place this folder where the other scorecards live, matching their folder and naming pattern.
2. Add a card or link for "Golf Scorecard" on the /apps page, using the same markup as the existing scorecard entries.
3. If the other scorecards share a site header, footer, back link, analytics snippet or favicon, add the same to `index.html`.
4. Keep the inline `<script>` intact. The table is built by JavaScript.
5. Test on a phone in Safari. Check that the ± button flips a score negative and totals update.
6. Deploy the same way the rest of bissyapps.com is deployed.

## Known limits

- Opening the file directly from the iPhone Files app shows a preview that does not run JavaScript, so the score grid won't appear there. Open it from the website in Safari instead.
- Scores are stored per browser and per device. They do not sync.
