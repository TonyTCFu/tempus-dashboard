# MEMORY.md

Tempus AI (NASDAQ: TEM) tracking dashboard. Static single page served by
GitHub Pages. This repo is independent of `spacex-dashboard`; keep the two
separate (own quote.json, own workflow, own public link).

## Deployment
- Public link: https://tonytcfu.github.io/tempus-dashboard/
- Source: `index.html` at the `main` branch root, generated from the
  `tempus-ai-dashboard` web artifact (re-export on data updates; do not hand-edit).
- GitHub Pages setting: Deploy from a branch / main / /(root).

## Quote snapshot
- `quote.json` at repo root; refreshed by `.github/workflows/quote.yml`
  (cron `*/15 13-21 * * 1-5` UTC = NYSE 09:30-17:00 ET Mon-Fri, plus manual dispatch).
- Source: Nasdaq official API (`api.nasdaq.com/api/quote/TEM/info`), real-time.
- Page fallback chain: quote.json -> Nasdaq direct -> Yahoo Finance -> Stooq (tem.us).
- Format: {"symbol":"TEM","price":..,"netChange":..,"pctChange":..,"prevClose":..,
  "quoteTime":"YYYY-MM-DD HH:MM","status":"intraday|postmarket|close","source":"Nasdaq"}.

## Data baseline
- Price/financials/short/analyst snapshot: 2026-09-30 close ($81.90, -0.82%).
- Q2 2026 earnings (2026-07-30): revenue $382.5M (+22%), first GAAP profit $5.6M,
  FY guide $1.59-1.60B revenue / ~$65M adj. EBITDA.
- Short interest (FINRA 2026-09-15): 28.06M shares, 20.53% of float, 5.2 days to cover.
- Analyst consensus: Hold, avg target ~$69.3 (Oct 2026).
