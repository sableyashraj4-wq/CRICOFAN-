# CricFAN

Mobile-first cricket scores website using `index.html`, `styles.css`, and `index.js`.

## Real score data (no demo scores)
1. Sign up with CricketData / CricAPI: https://cricketdata.org/
2. Obtain your API key from the provider.
3. Open CricFAN and tap the gear (⚙).
4. Paste the key and choose a refresh interval.

The app calls the provider's `currentMatches` endpoint and attempts to retrieve recent matches from `matches`. API coverage, historical result availability, scorecard detail and update cadence depend on your account plan and provider response. The app deliberately shows no invented match data when the API returns nothing.

## Run
- Easiest: serve this folder using any static web server, or open `index.html` in a modern browser.
- Android: use a WebView wrapper or package it with a trusted web-to-app tool. Keep `index.html`, `styles.css`, and `index.js` together.
- Internet is required for Google Fonts and live API data.

## Important API-key security
This static frontend stores the key in the current browser's local storage and sends it to the provider API. Do not publish a build with your private key embedded in source code. For a public app, create a small backend proxy and store the key as a server-side environment variable.

## Refresh interval
The app can poll at 15, 30, or 60 seconds. A UI cannot guarantee new official scores every second: the provider controls update frequency, availability, and rate limits. Polling every second could exhaust a plan or be blocked.

## Manual scorer
Use “Add match” to create your own match and enter runs, wickets, wides, no-balls and byes. It calculates innings totals, overs, run rate, batter stats, and basic bowler figures. Manual scores are stored locally and are separate from official provider scores.

## Notes
- Home feed filters for international matches using the match type/series/team fields the API returns. Coverage and classification vary by provider.
- The National tab intentionally explains that domestic/national matches are not displayed in this international-only feed.
- The “Match details” button identifies the selected provider record; full provider scorecard endpoints can be added once your plan and endpoint schema are confirmed.
