# CricFAN

Files:
- index.html
- styles.css
- index.js

## Run
Open `index.html` in a modern browser, or serve the folder over HTTPS/local web server for best API compatibility.

## Real score API
Tap the gear icon, select a provider, and enter your own API key.
- API-Cricket: uses the documented `get_livescore` endpoint.
- Cricket Database API: uses `/v1/live?state=all&international=true`.
- Custom JSON endpoint: accepts a JSON endpoint you control.

API provider plans, CORS policies, and response schemas vary. The app intentionally displays an error instead of fabricated scores when it cannot load actual data. Provider results may not include yesterday's matches or full scorecards in the same endpoint; the API plan/endpoints may need adjustment.
Polling is attempted every 1 second. Providers may update less frequently and can rate-limit frequent requests. A production release should proxy requests through a backend and cache data to protect API keys and avoid rate limits.

The manual scorer is separate from official scores and includes run buttons, wide, no-ball, wicket, undo, batter and bowler tables, overs and run rate. It is a starter scorekeeper; advanced dismissal types, extras, strike logic for all edge cases, and persistent score storage should be added before official scoring use.
