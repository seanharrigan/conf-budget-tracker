# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project

**Conference Per Diem Meal Tracker** — a single-page, single-file HTML app (`index.html`) Sean uses to log meals against a daily per-diem while on conference trips. No build, no deps, no backend. Open the file in a browser.

## Adding a meal

Primary workflow is the in-page **+ Add Meal** form, which persists entries to `localStorage` under `ottawa-cadth-2026-meals` (scoped per browser). Editing source directly only affects users who have no localStorage entry yet — existing users already have their own state.

Data schema (same for `SEED` in source and the stored array):

```js
{ day: "Tue Apr 21", mealType: "Breakfast", location: "…", cost: 13.60 }
```

- `day` must exactly match one of the `key` values in the `DAYS` array — per-day budget filtering uses string equality.
- `mealType` is `Breakfast` | `Lunch` | `Dinner` | `Snack` (case matters: the badge class is `'meal-' + mealType.toLowerCase()`).
- `cost` is a number in CAD (column header is "Cost (CAD)"; do not mix currencies silently).
- Totals, budget bars, and warn/over colors (olive → orange at 80% → red at 100%) are derived — never hand-edit the summary stats.

If the user asks you to add a receipt, prefer telling them to use the form. Only edit `SEED` when they want the change baked into the source (e.g. a canonical starter entry).

## Current trip config

- **Trip:** CADTH, Ottawa, 2026
- **Dates:** Tue Apr 21 – Fri Apr 24, 2026
- **Per diem:** $95 CAD/day → $380 total
- Edit `BUDGET` and `DAYS` at the top of the `<script>` to change these.

## Git workflow

- Active branch: `claude/add-claude-documentation-9G0jy`. Commit each receipt and push (`git push -u origin <branch>`).
- Do not open a PR unless explicitly asked.
