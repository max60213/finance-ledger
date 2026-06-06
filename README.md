# Finance Ledger

Codex skill for recording daily expenses and monthly finance summaries in an Obsidian Finance vault.

中文說明: [README.zh-TW.md](README.zh-TW.md)

## What it does

- Records daily spending into dated notes under `Finance/支出紀錄/YYYY-MM/`
- Keeps daily entries structured for Dataview and monthly charts
- Updates month pages so summaries, charts, and totals stay in sync
- Preserves the vault rules for `daily_budget`, `remaining_today`, and monthly preset categories

## Repository structure

- `SKILL.md`: skill instructions used by Codex
- `agents/openai.yaml`: UI metadata for Codex skill lists and chips
- `references/finance-workflow.md`: detailed workflow reference

## Usage

Use this skill when you want Codex to:

- log a new day of expenses
- update an existing daily note
- refresh the monthly summary page
- reconcile monthly charts and totals with the daily records

## Notes

- This skill is designed for a finance vault that follows the rules in `Finance/AGENTS.md`
- `daily_budget` is the food budget; transport and other spending stay in the daily table
- Monthly summaries treat `訂閱費`, `基金`, and `美股` as preset monthly items
