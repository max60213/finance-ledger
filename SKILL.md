---
name: finance-ledger
description: Record daily expenses, attach receipt photos, and update monthly finance summaries in an Obsidian Finance vault. Use when the user asks to log spending, reconcile daily entries, update monthly totals/charts/tables, or maintain the Finance folder structure and monthly presets.
---

# Finance Ledger

## Overview

Use this skill to keep the Finance vault consistent when recording daily expenses and monthly summaries. Follow the vault rules, keep entries structured, and update the monthly page whenever a daily page changes.

## Workflow

1. Read [`references/finance-workflow.md`](references/finance-workflow.md) before editing files.
2. Determine the target date and month from the user's message or the current date.
3. Create or update `Finance/支出紀錄/YYYY-MM/YYYY-MM-DD.md` for the daily record; update the existing note if that date already exists.
4. Keep daily spending in a `## 今日支出` table, not in properties.
5. Keep `daily_budget` as the food budget; record transport and other spending separately.
6. Update `total_spent`, `remaining_today`, and `status` to match the daily note.
7. Add daily food difference and cumulative monthly food difference to `## 今日結算`.
8. If the user provides a photo, copy it into the monthly `assets/` folder and embed it with an Obsidian wikilink.
9. Update `Finance/支出紀錄/YYYY-MM/YYYY-MM.md` so the month page stays in sync.
10. Treat `訂閱費` and `投資` as preset monthly items that start as already spent/invested in monthly summaries.
11. Keep category names stable and prefer the vault's existing categories: `飲食`, `交通`, `其他`, plus the finance simulation categories when summarizing a month.
12. If the user asks to persist the change, commit and push only the Finance files that changed.

## Guardrails

- Keep file paths and names in `YYYY-MM/YYYY-MM-DD.md` format.
- Do not move daily spending into properties.
- Do not invent new category names unless the user explicitly asks for a change.
- Preserve existing Dataview / Obsidian chart structure when updating month pages.
- Keep the Finance vault aligned with `Finance/AGENTS.md` if it exists in the workspace.
