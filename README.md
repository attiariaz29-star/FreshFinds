# FreshFind — Fresh All Along

A farmers' market discovery and fresh-produce guide platform.
**Find Fresh. Find Local. Find Your Market.**

> This is a discovery guide, NOT an e-commerce site — no cart, no checkout, no payments.

## Run it

No build step, no backend. Either:

1. **Double-click `index.html`** — works straight from the file system
   (data falls back to the embedded copy in `js/data.js`), or
2. **Serve the folder** and open `http://localhost:8000`, e.g.
   `npx serve .` — the app then loads the live JSON files from `data/`.

## Stack (per spec)

- HTML5 + CSS3 + JavaScript
- Bootstrap 5 (layout, navbar, modals styling, utilities)
- React 18 (UMD, no-JSX `createElement` so it runs without a build step)
- Local JSON data — no backend, no database, no auth

## Structure

```text
freshfind/
  index.html          # app shell (React root, fonts, CDN links)
  css/style.css       # premium fresh/natural theme, responsive
  js/data.js          # embedded copy of all data (file:// fallback)
  js/app.js           # entire React app (search, modals, bookmarks, chatbot…)
  data/
    markets.json      # 12 markets (areas, schedules, coords, produce…)
    produce.json      # 16 produce guides (season, price, nutrition…)
    seasonal.json     # 12 months of seasonal picks + tips
    chatbot.json      # rule-based intents, keywords, responses
```

## Features

- **Home**: responsive navbar, hero with live search, stats, featured markets, how-it-works
- **Market directory**: text search (name/area/produce), area/day/produce filters,
  sort (Recommended, A–Z, Top rated, Closest, Next open), **Open Right Now** toggle,
  result counts, loading skeletons, empty states, reset
- **Market details modal**: schedule table with today highlighted, live status,
  produce tags, info, embedded map + directions, prev/next navigation
- **Open/Closed status**: computed live in JS from each market's days + hours
- **Geolocation**: "Use my location" → haversine distances + closest-first sort
- **Produce guide**: search, category chips, "in season now" toggle, "where to find"
- **Seasonal**: 12 month pills, current-month highlight, picks + tip
- **Bookmarks**: markets + produce tabs, temporary personal notes (Save Note),
  export to JSON file, copy summary, clear all — persisted in `localStorage`
- **Rule-based chatbot**: floating launcher, keyword intents from `chatbot.json`,
  quick replies, typing indicator, dynamic open-now counts
- **Every button works**: search/clear, filters/reset, sort, details, bookmarks,
  notes, export/copy, chat send/close, nav scroll, directions, newsletter validation,
  back-to-top, toasts for all feedback
- **Responsive**: 4 cards/row (desktop) → 2 (tablet) → 1 (mobile), no horizontal overflow
