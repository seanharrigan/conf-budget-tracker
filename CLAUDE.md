# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project

**Conference Per Diem Meal Tracker** — a single-page, single-file HTML app (`index.html`) Sean uses to log meals against a daily per-diem while on conference trips. No build, no deps, no backend. Open the file in a browser.

## Adding a meal (primary workflow)

When the user sends a receipt, append one object to the `meals` array inside the `<script>` block at the bottom of `index.html`. Schema:

```js
{ day: "Tue Apr 21", mealType: "Breakfast", location: "…", cost: 13.60 }
```

- `day` must exactly match one of the `key` values in the `DAYS` array above it — day filtering for the per-day budget strip keys off string equality.
- `mealType` is `Breakfast` | `Lunch` | `Dinner` | `Snack` (case matters for the badge CSS: the template does `'meal-' + mealType.toLowerCase()`).
- `cost` is a number in CAD (the column header says "Cost (CAD)"; don't silently mix currencies).
- Totals, budget bars, and warn/over colors (olive → orange at 80% → red at 100%) are all derived — don't hand-edit the summary stats.

## Current trip config

- **Trip:** CADTH, Ottawa, 2026
- **Dates:** Tue Apr 21 – Fri Apr 24, 2026
- **Per diem:** $95 CAD/day → $380 total
- Edit `BUDGET` and `DAYS` at the top of the `<script>` to change these.

## Git workflow

- Active branch: `claude/add-claude-documentation-9G0jy`. Commit each receipt and push (`git push -u origin <branch>`).
- Do not open a PR unless explicitly asked.
