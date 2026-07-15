# IntelliCite UI

Frontend for **IntelliCite**, an AI-assisted research companion that helps students and researchers search academic literature, judge which papers are actually worth reading, and generate citations — without manually screening dozens of results.

The backend lives in a companion repo: [intellicite-api](https://github.com/intisar-alosaimi/intellicite-api).

## The problem

Academic search engines return a pile of papers with no easy way to judge relevance, credibility, or citation quality without reading each one. IntelliCite lets a user search by topic and get back an AI-generated report explaining *why* each paper matches their query, plus automatic quality badges ("highly cited", "recent", "outdated"). A separate "Cite Check" tool takes a paper's DOI and a research question and tells the user whether that source is actually a good fit — or suggests it isn't.

## Features

- Landing page + authenticated search home for finding papers by topic
- AI-generated relevance reports and quality badges per result
- **Cite Check** flow for evaluating a specific paper against a research question
- Save/bookmark papers and revisit them later
- Search history view
- Citation generator (APA, MLA, etc.) via `citation-js`
- User profile, login/register with JWT-based auth
- Admin dashboard: user management and app settings, behind a protected admin route
- Bilingual UI (Arabic/English) via `react-i18next` with automatic language detection

## Tech stack

| | |
|---|---|
| Framework | React 19 + Vite |
| Routing | React Router 7 |
| Styling | Tailwind CSS 4, Radix UI primitives, PrimeReact |
| Animation | Framer Motion |
| Localization | i18next / react-i18next |
| Auth | `jwt-decode` (client-side token handling) |
| Citations | `citation-js` |
| HTTP | Axios |

## Getting started

```bash
git clone https://github.com/intisar-alosaimi/intellicite-ui.git
cd intellicite-ui
npm install
cp .env.example .env   # then point VITE_BASE_URL at a running intellicite-api instance
npm run dev
```

## Environment variables

| Variable | Purpose |
|---|---|
| `VITE_BASE_URL` | Base URL of the `intellicite-api` backend this UI talks to |

## What I'd improve

- Add a test suite — there currently isn't one
- Add loading/error states around API calls more consistently across pages
- Split the large `Router.jsx` route/layout logic into smaller pieces
- Add basic accessibility pass (focus states, ARIA labels) given the amount of custom UI
- Package name in `package.json` is still the generic `"frontend"` — worth renaming to `intellicite-ui`

## Design

Figma: [Final Tuwaiq Project](https://www.figma.com/design/AOBplsedeefft6SPW3KOt5/Final-Tuwaiq-Project)

## Team

Originally built by:

- **[عبدالرحمن الطامي](https://github.com/Iimvalue)**
- **[عائشة عبدالله](https://github.com/ENG-Aisha-Abdullah)**
- **[انتصار العصيمي](https://github.com/intisar-alosaimi)**
- **[طلال الشعبان](https://github.com/TalalAlrashedi)**
