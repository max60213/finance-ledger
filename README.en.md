# Finance Ledger

Finance Ledger is an AI agent skill for recording daily expenses, tracking budgets, and maintaining monthly financial summaries in an Obsidian Finance vault.

Traditional Chinese: [README.md](README.md)

## Features

- Record daily expenses through natural-language or spoken descriptions
- Organize daily notes into monthly folders instead of one growing file
- Store expenses in structured tables for Dataview queries and charts
- Refresh monthly summaries, tables, and charts whenever an expense changes
- Compare planned budgets with actual spending and track balances over time
- Preserve the user's existing vault structure, language, and category conventions

## Expense categories

Users can define categories that match their financial plan, such as:

- Food
- Subscription
- Transport
- Investment
- Savings
- Other

These names are examples rather than fixed requirements. The AI agent should prefer categories and language already used in the vault, while allowing users to add or adjust categories when needed.

## Usage

A user can describe daily spending directly to an AI agent:

> I spent 180 on lunch and 63 on a train ticket today.

The AI agent records the expenses in the daily note, classifies them as food and transport, and recalculates the daily total, budget difference, and cumulative monthly results.

Each month has a summary page. Whenever a daily expense is added or changed, the monthly table, category charts, and budget comparison update accordingly, making it easier to track both daily and monthly spending.

## Example outputs

<table>
  <tr>
    <td width="50%">
      <img src="assets/monthly-summary-overview-clean.jpg" alt="Monthly expense overview" />
    </td>
    <td width="50%">
      <img src="assets/monthly-summary-chart-clean.jpg" alt="Monthly expense charts" />
    </td>
  </tr>
</table>

## Repository structure

- `SKILL.md`: primary skill instructions for AI agents
- `agents/openai.yaml`: metadata used by skill lists and interfaces
- `references/finance-workflow.md`: detailed bookkeeping workflow and data structure
- `assets/`: example images used by the README

## Notes

- Category labels default to English, but notes should follow the user's language and existing vault conventions.
- Detailed budget rules should come from `Finance/AGENTS.md` or an equivalent rules file in the user's vault.
- Transport and other non-food expenses can be tracked separately without reducing the daily food budget.
