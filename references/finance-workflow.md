# Finance Workflow Reference

## Scope

Use this reference for Obsidian finance records in `Finance/`.

## Core paths

- `Finance/Budget.md`: source of monthly budget allocations
- `Finance/Expense Records/Expense Records.md`: entry page for expense records
- `Finance/Expense Records/YYYY-MM/YYYY-MM.md`: monthly summary page
- `Finance/Expense Records/YYYY-MM/YYYY-MM-DD.md`: daily expense page

If the user's vault uses another language or an existing folder layout, follow that structure instead of forcing these English names.

## Daily page shape

Use frontmatter fields:

```yaml
date: 2026-06-02
month: 2026-06
daily_budget: 400
total_spent: 265
remaining_today: 135
status: within_budget
```

Use a `## Daily Expenses` table with columns:

| Category | Item | Amount | Notes |
| --- | --- | ---: | --- |

Rules:

- `daily_budget` is the food budget only.
- Put transport and other costs in the table, not in properties.
- Keep `remaining_today = daily_budget - food spending`.
- Allow `remaining_today` to be negative.
- Add `Daily Food Balance` and `Monthly Cumulative Food Balance` in `## Daily Summary`, and do not repeat `Daily Food Balance` in the visible summary text.
- Compute `Daily Food Balance = daily_budget - daily food spending`.
- Compute `Monthly Cumulative Food Balance = day-of-month * daily_budget - cumulative monthly food spending through that day`.
- Do not add an H1 title to the daily note; the file name already serves as the visible page title in Obsidian.
- Keep the visible `Daily Summary` concise: if the day only contains food spending, omit transport and total-spend lines; if there are transport or other non-food items, list them explicitly and include `total_spent`. Do not repeat the unchanged `daily_budget`; only mention it when the user explicitly changes the food budget that day.

Translate headings and labels to match the user's language when writing notes.

## Monthly page shape

Monthly pages should contain:

- a monthly overview with record count, total spending, average daily spending, and month balance
- a food cumulative progress chart comparing cumulative budget and actual cumulative food spending, followed by the signed difference `cumulative budget - actual cumulative food spending`
- a pie chart for actual monthly spending plus a `Remaining` slice so the chart totals 100%, where `Remaining = monthly income - actual monthly spending`
- a bar chart comparing planned vs actual spending
- a comparison table with planned amount, actual amount, balance, usage rate, and verdict
- month-end review prompts
- the daily table at the bottom

The daily table should show `Date`, `Food`, `Transport`, `Investment`, `Other`, `Daily Balance`, and `Cumulative Balance`.

## Category handling

Use stable categories and aliases:

- `Food`
- `Transport`
- `Other`
- `Subscription`
- `Investment`

Monthly summaries should treat these as preset:

- `Subscription`
- `Investment`

These categories start the month as already fully spent/invested and should not be re-accumulated from daily pages.

If the user's vault or request is in another language, translate the labels to match that language while preserving the same underlying category meaning.

## Photo attachments

When the user provides a receipt photo or meal photo, copy it into the monthly `assets/` folder and embed it with a wikilink in the related daily note.

## Monthly editing rule

When a daily page changes, update the matching monthly page so charts and totals stay in sync.
