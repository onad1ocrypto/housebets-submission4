# Housebets — Sportsbook UI (Submission 3)

**Live demo:** https://housebets-sportsbook-v3.vercel.app

A single-page sportsbook interface for Housebets, laid out as a three-column
desktop book: a permanent sport navigation sidebar, a fixture list, and a bet
slip that is always on screen.

No framework, no build step.

---

## What makes this one different

Submissions 1 and 2 use a horizontal top bar with the bet slip sliding in from
the side. This entry changes the structure instead of the colour scheme:

| | Submissions 1 & 2 | Submission 3 |
|---|---|---|
| Navigation | horizontal sport tabs | **sidebar, always visible** |
| Bet slip | slides in on demand | **permanent third column** |
| Sports | football only | **8 sports, 35 fixtures** |
| Palette | near-black / lime | **blue-grey steel** |

## Palette

| Role | Value |
|---|---|
| Page | `#141519` |
| Bar & sidebar | `#1D1E22` |
| Card | `#25262B` |
| Card alt | `#1A1B1F` |
| Tiles | `#26272C` / `#2C2D33` / `#34353D` |
| Ink | `#EDEFF2` / `#B4B7BE` / `#9A9DA6` / `#8A8D96` |
| Price (brand cyan) | `#3ED0DA` |

Prices and primary actions stay cyan — the official Housebets brand accent —
so the brand identity is unchanged across all three entries. The steel grey is
decorative and limited to surfaces, borders and highlights.

## Sports

Eight sports, each with its own competitions and fixtures:

| Sport | Competitions | Fixtures |
|---|---|---|
| Football | Premier League, Champions League, LaLiga, Serie A, Bundesliga | 13 |
| Basketball | NBA | 4 |
| Baseball | MLB | 3 |
| American Football | NFL | 3 |
| Tennis | ATP Tour | 3 |
| Esports | LoL EMEA | 3 |
| Volleyball | FIVB Nations | 3 |
| Rugby | Autumn Nations | 3 |

Sidebar counts are derived from the fixture list at load time, so a number on
screen can never drift from what the page actually lists.

## Features

- **Sidebar navigation** — Home, Live Betting with a live count, eight sports
  with fixture counts, then Favourites, Active Bets, Settled and Logout.
- **Permanent bet slip** — Straight bet / Parlay bet, total stake, total
  payout, and a full-width Submit All Bet action.
- **Match pages** — market tabs (Popular, Goals, Halves, Handicaps,
  Goalscorers, Corners & cards), 48 markets and 117 outcomes on football.
- **Live odds drift** — prices move, and the direction of the move is shown.
- **Generated crests** — teams without an artwork file get a shield drawn from
  their own colours, so every club in every sport has a crest.
- **Responsive** — below 860px the sidebar collapses and the bet slip becomes a
  bottom sheet.

## Accessibility

- Every text element passes WCAG AA (4.5:1, or 3:1 for large text), measured
  across three routes at two viewport widths.
- Two contrast defects were found and fixed during the build: the sidebar
  count badges (4.07:1) and the active count badge (4.49:1).
- All animation is disabled under `prefers-reduced-motion`.

## Running it locally

No install, no build:

```sh
python3 -m http.server 8000
```

Then open http://localhost:8000

## Structure

```
index.html
assets/
  app.css      styles
  app.js       rendering, state, routing
  data.js      sports, teams, fixtures, markets
  brand/       official Housebets lockup and icons
  crests/      football club crests
  icons/       sport icons
  posters/     hero posters
```

## Tech

Vanilla HTML, CSS and JavaScript. No framework, no bundler, no dependencies.
Deployed on Vercel.
