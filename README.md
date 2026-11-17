# Weekly Program Report Builder

One locked report template for paid-media programs, instead of a new report (or a new reporting agent) per program. Upload an Ads Manager CSV export and it renders the same report every time: same sections, same order, same metrics.

## Set the site live (so you can open it from a link)

1. On GitHub, open this repo → **Settings** → **Pages**.
2. Under "Build and deployment", set **Source** to **Deploy from a branch**.
3. Set **Branch** to **main** and the folder to **/ (root)**, then **Save**.
4. Wait a minute or two, then open: https://athyyna.github.io/automated-dashboard-builder-media-reports/

## Download the HTML (to use it offline or send it to someone)

- From this repo: open `index.html` → **Raw** → right-click → **Save As** (or Ctrl/Cmd+S).
- Or: the green **Code** button → **Download ZIP**, unzip, and open `index.html`.
- Or ask me in chat and I'll send you the file.

## How to use

1. Open `index.html` in a browser (double-click it — nothing is installed, nothing leaves your browser).
2. Upload your Ads Manager `.csv` / `.tsv` export, or paste it in. A weekly breakdown is fine: one row per ad per week is aggregated by ad before anything is ranked.
3. Optional: program name, objective (sets the hero metric only), date range.
4. Check the report, tick the QA checklist, then export.

## What the report contains

- **TLDR — top 3**, computed from the data: (1) spend and main KPIs, (2) top 3 performers (top ad set by spend, highest-CTR ad, biggest asset), (3) up to 3 watch-outs, good and bad (low-CTR big spender, mixed result types, cheapest-CPC ad set, zero-delivery weeks, spend concentration). With no target in the file it states the result plainly — it never invents a pass/fail.
- **KPI tiles** — same 8, same order, every program: Spend, Impressions, Reach, CPM, CTR, CPC, Results, CPA.
- **Hero metric** for the chosen objective (e.g. Link clicks for Traffic).
- **Top 5 ads by spend** (weekly rows aggregated by ad).
- **Charts** — spend by ad set (bars), and a scatter of every ad: impressions on a log scale vs CTR, bubble size = spend, colour = ad set.
- **QA checklist** — nothing is sent anywhere; you QA before anything goes out.

## How the data is read

- Currency is read from the Amount spent header (USD, SGD…).
- Period is campaign-to-date as exported (earliest Reporting starts to latest Reporting ends) — never an assumed 7-day slice.
- Reach is labelled a sum across ads and weeks, not unique people.
- Results are split by what they actually are (Result indicator). If Results mixes different actions, CPA is hidden rather than shown blended.
- An Ads Manager Total row is ignored so totals can't double-count.

## Exports

- **Download report (.html)** — a standalone copy of the finished report.
- **Download data (.csv)** — TLDR, totals, top 5 ads, ad sets.
- **Copy for Google Sheets** — the same tables as tab-separated values to paste in. A standalone file can't save directly into Google Sheets, so CSV import / paste is the route.
- **Print / Save as PDF** — opens the report in a real browser tab and prints from there.

If a button does nothing, the file is being viewed inside a preview pane that blocks downloads and printing — use **Open report in new tab** and print or save from your browser instead.

## Version

v2.6 — locked template. Built and tested against a real Ads Manager export (music activation, Traffic, 1 Sep–8 Nov 2026: $359.0K spend, 1.11B impressions, $0.32 CPM, 8,791,391 link clicks at 0.79% CTR / $0.04 CPC).
