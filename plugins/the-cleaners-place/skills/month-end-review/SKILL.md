---
name: month-end-review
description: "Month-end or quarter review for The Cleaners Place: revenue, profit, expenses, receivables, tax set-aside, and what to fix before closing the books. Use when the user asks how the business is doing, for reports, profit, or tax prep."
---

# Month-end review (owner / manager)

1. `get_revenue_report` and `get_profit_report` for the period. Report revenue, expenses by category, profit, estimated card fees and tax set-aside.
2. `get_profit_breakdown`: which customers and services have the worst margin after labor. Call out the bottom few honestly with a suggestion (raise price, change frequency, drop).
3. `list_expenses` for the month: check for obvious gaps (no supplies expense, a receipt-less large item). Offer `create_expense` for anything the user mentions.
4. `list_invoices` with `status: overdue` or `sent`: money still outstanding. Offer the `chase-overdue-invoices` workflow.
5. `get_retention_report`: customers at risk of leaving. Offer a follow-up list.
6. For taxes, `get_tax_summary` (`summary`, `income`, `expenses`, `payroll`). State clearly that these are bookkeeping summaries to hand to an accountant, not tax advice.

Finish with: three headline numbers, three things that look good, three things to fix. Do not change any data unless asked.
