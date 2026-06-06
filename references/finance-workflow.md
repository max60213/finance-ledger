# Finance Workflow Reference

## Scope

Use this reference for Obsidian finance records in `Finance/`.

## Core paths

- `Finance/財務模擬.md`: source of planned monthly allocations
- `Finance/支出紀錄/支出紀錄.md`: entry page for expense records
- `Finance/支出紀錄/YYYY-MM/YYYY-MM.md`: monthly summary page
- `Finance/支出紀錄/YYYY-MM/YYYY-MM-DD.md`: daily expense page

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

Use a `## 今日支出` table with columns:

| 類別 | 項目 | 金額 | 備註 |
| --- | --- | ---: | --- |

Rules:

- `daily_budget` is the food budget only.
- Put transport and other costs in the table, not in properties.
- Keep `remaining_today = daily_budget - 飲食支出`.
- Allow `remaining_today` to be negative.
- Add `今日飲食差額` and `本月飲食累積差額` in `## 今日結算`, and do not repeat `今日飲食剩餘` in the visible summary text.
- Compute `今日飲食差額 = daily_budget - daily food spending`.
- Compute `本月飲食累積差額 = day-of-month * daily_budget - cumulative monthly food spending through that day`.

## Monthly page shape

Monthly pages should contain:

- a monthly overview with record count, total spending, average daily spending, and month balance
- a food cumulative progress chart comparing ideal cumulative budget and actual cumulative food spending, followed by the signed difference `ideal cumulative budget - actual cumulative food spending`
- a pie chart for actual monthly spending
- a bar chart comparing planned vs actual spending
- a comparison table with planned amount, actual amount, balance, usage rate, and verdict
- month-end review prompts
- the daily table at the bottom

The daily table should show `日期`, `飲食`, `交通`, `其他`, `今日差額`, and `累積差額`.

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
