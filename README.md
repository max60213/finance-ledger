# Finance Ledger

AI agent skill for recording daily expenses and monthly finance summaries in an Obsidian Finance vault.

Traditional Chinese README: [README.zh-TW.md](README.zh-TW.md)

## What it does

- Records daily spending into monthly dated notes under the vault's expense-records folder
- Keeps daily entries structured for Dataview and monthly charts
- Updates month pages so summaries, charts, and totals stay in sync
- Preserves the vault rules for `daily_budget`, `remaining_today`, and monthly preset categories

## Example outputs

<table>
  <tr>
    <td>
      <img src="assets/monthly-summary-overview-clean.jpg" alt="Monthly summary overview" />
    </td>
    <td>
      <img src="assets/monthly-summary-chart-clean.jpg" alt="Monthly summary charts" />
    </td>
  </tr>
</table>

## Repository structure

- `SKILL.md`: skill instructions used by AI agents
- `agents/openai.yaml`: UI metadata for skill lists and chips
- `references/finance-workflow.md`: detailed workflow reference

## Usage

Use this skill when you want an AI agent to:

- log a new day of expenses
- update an existing daily note
- refresh the monthly summary page
- reconcile monthly charts and totals with the daily records

## Notes

- This skill is designed for a finance vault that follows the rules in `Finance/AGENTS.md`
- `daily_budget` is the food budget; transport and other spending stay in the daily table
- Monthly summaries treat subscription and investment as preset monthly items
