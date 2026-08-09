# Investment Tracker

Personal portfolio tracker — Bundesschatz, crypto, and stocks — with live pricing and cross-device sync.

**Live app**: https://smaurer2-a11y.github.io/investment-tracker/
**GitHub repo**: https://github.com/smaurer2-a11y/investment-tracker
**Firebase project**: `invest-5c80f` ([console.firebase.google.com](https://console.firebase.google.com))

## What's in this folder

- `index.html` — the entire app (single file: markup, styles, script, Firebase sync)
- This is a git repo, pushed to GitHub, deployed via GitHub Pages on every push to `main`

## Companion project

**`Purchase Logger Claude`** (sibling folder on the Desktop) — where you log new stock/crypto purchases by pasting a screenshot into a Claude chat. Holds the Firebase service account credential; kept separate from this repo on purpose so the credential never touches a public git history. See its own README for usage.

## How data works

- Bundesschatz and the iShares ETF / LVMH: manually entered values
- Crypto (8 coins) and 5 US-listed stocks (MSFT, NVDA, PLTR, CVX, COIN): you enter **quantity held**, the app fetches live prices (CoinGecko for crypto, Finnhub + a live EUR/USD rate for stocks) and computes value automatically — refreshes on load, on demand, and every 5 minutes
- Everything syncs across devices via Firebase (sign in with Google in the app's sync bar) — without signing in, data just stays local to that one browser

## Making changes

Open a Claude Code session in this folder and describe what you want changed. The whole app is the one `index.html` file. To deploy: commit and push to `main` — GitHub Pages picks it up automatically (usually under a minute; if it seems stuck, `gh api -X POST repos/smaurer2-a11y/investment-tracker/pages/builds` forces a rebuild).
