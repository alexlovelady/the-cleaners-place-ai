---
name: tax-season-prep
description: "Gather what an accountant needs from The Cleaners Place for tax time: income, expenses, payroll and contractor totals, missing receipts, and worker documents. Use when the user mentions taxes, year-end, 1099s, or handing records to an accountant."
---

# Tax-season prep (owner / manager)

This produces bookkeeping summaries to hand to an accountant. It is not tax advice.

1. `get_tax_summary` for the year with `kind: summary`, then `income`, `expenses` and `payroll`. Report totals and anything unusual (a month with no expenses, a very large single item).
2. `get_revenue_report` and `get_profit_report` for the year-to-date picture, including estimated card fees and the tax set-aside.
3. `list_expenses` with `from` and `to` for the tax year, by category, and note entries without receipts (the summary shows a receipt yes/no).
4. `list_staff_documents` with expiry or missing items: workers paid as contractors should have their tax forms on file. `get_staff_doc_url` gives a private, short-lived link to view one.
5. `list_staff_pay_rates` and the payroll summary for who was paid what.
6. Offer to add missing expenses with `create_expense` if the user has the figures.
7. Customer data requests (a customer asking for a copy of their data) are separate: `export_client_data`.

End with a checklist of what is ready and what is missing.
