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
3. Create or update `Finance/Expense Records/YYYY-MM/YYYY-MM-DD.md` for the daily record; update the existing note if that date already exists. Translate the path names to match the user's language and existing vault structure when writing files.
4. Keep daily spending in a `## Daily Expenses` table, not in properties. Translate the heading to match the user's language when writing notes.
5. Keep `daily_budget` as the food budget; record transport and other spending separately.
6. Update `total_spent`, `remaining_today`, and `status` to match the daily note. If the day only contains food spending, keep the visible summary focused on food-related lines and omit transport and total-spend lines. Do not repeat the unchanged `daily_budget` in the visible summary; only mention it when the user changes the food budget that day.
7. Add daily food difference and cumulative monthly food difference to a `## Daily Summary` section. Translate the heading to match the user's language when writing notes.
8. If the user provides a photo, copy it into the monthly `assets/` folder and embed it with an Obsidian wikilink.
9. Update `Finance/Expense Records/YYYY-MM/YYYY-MM.md` so the month page stays in sync, and keep the monthly actual-spending pie chart filled to 100% by adding a `Remaining` slice where `Remaining = monthly income - actual spending`. Translate the path names to match the user's language and existing vault structure when writing files.
10. Treat `Subscription` and `Investment` as preset monthly items that start as already spent/invested in monthly summaries. Translate those labels to match the user's language or the vault's existing language when writing notes.
11. Keep category names stable and prefer the vault's existing categories by default: `Food`, `Transport`, `Other`, plus `Subscription` and `Investment` when summarizing a month. Translate labels to match the user's language or the vault's existing language when writing notes.
12. If the user asks to persist the change, commit and push only the Finance files that changed.

## Guardrails

- Keep file paths and names in `YYYY-MM/YYYY-MM-DD.md` format.
- Do not add an H1 title to daily notes; Obsidian already uses the file name as the visible page title.
- Do not leave a blank line after the frontmatter in daily notes; start the body immediately with `## Daily Expenses` or the localized equivalent.
- Do not repeat `month` in daily note frontmatter; derive the month from `date` when needed.
- Do not move daily spending into properties.
- Do not invent new category names unless the user explicitly asks for a change.
- Preserve existing Dataview / Obsidian chart structure when updating month pages.
- Keep the Finance vault aligned with `Finance/AGENTS.md` if it exists in the workspace.
