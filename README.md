# Enough Gold — 19Keys × High Lvl Operating Deck

Single static file. No build step.

## Deploy to Vercel via GitHub
1. Create a new GitHub repo (e.g. `operating-deck`), private.
2. Add `index.html` (and this README) to the repo root and push.
3. In Vercel: Add New → Project → Import the repo. Framework preset: **Other**. Leave build command and output directory empty. Deploy.
4. Every push to `main` redeploys automatically.

## Updating the agenda
Open Items live in `index.html` under `<section id="board">`. Each item is a `.glass.item` block with a `data-id`; checkmarks are saved per device in the browser.
