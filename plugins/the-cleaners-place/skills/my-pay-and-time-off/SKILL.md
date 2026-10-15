---
name: my-pay-and-time-off
description: "Cleaner self-service for The Cleaners Place: expected pay and payout status, expenses, and requesting time off. Use when a cleaner asks about their pay, a missing payout, a reimbursement, or wants a day off."
---

# My pay, expenses and time off (cleaner)

- **Pay:** `my_pay` shows earnings so far this period, approved pay waiting to be paid, payouts in flight with the expected bank date, and whether any are late. If a payout looks late, say what the data shows and suggest contacting their manager; do not speculate.
- **Expenses to be reimbursed:** `my_expenses` for the log; `my_add_expense` to add one (amount, date, category, note). Receipt photos can't be attached here; tell them to add the receipt in the app.
- **Time off:** `my_time_off` for existing requests; `request_time_off` with start and end dates and an optional note; `cancel_my_time_off` to withdraw a pending one. Check `get_today` / `list_jobs` first so you can warn them about jobs on those dates.
- **Availability:** `my_availability` shows business hours and their approved time off.

- **Payout looks wrong or missing:** `report_pay_issue` sends the line to support with the details (it shows the exact message first). Say plainly that it goes to platform support.
- **Change how they are paid:** `set_my_payout_method` (confirmation required; it changes where their money goes). `refresh_my_payout_status` re-checks their Stripe setup.
- **Receipt for an expense:** `get_my_receipt_url` gives a private link that expires in minutes.

Everything here is about the signed-in person only.
