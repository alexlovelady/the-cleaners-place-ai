---
name: pay-day
description: "Run staff pay in The Cleaners Place: review or create a pay run, check hours and adjustments, finalize it, and pay staff through Stripe. Use when the user mentions pay run, payroll, paying the team, or payouts."
---

# Pay day (owner / manager)

Payouts move real money. Go slowly and confirm every step.

1. `list_pay_runs` to find the current/last run. If the user wants a new period, `create_pay_run` for that date range, then `get_pay_run` and walk through each person: hours, jobs, rate, base pay, adjustment, total.
2. Flag problems before anything is paid: staff with no pay rate (`list_staff_pay_rates`), missing check-in/out (`list_check_time_requests`), unusually high or low totals.
3. Fix with `set_pay_line_adjustment` (bonus, deduction, reimbursement) and `recompute_pay_run` if jobs changed. Changing someone's rate is `set_staff_pay` and needs confirmation.
4. When the numbers are right, `finalize_pay_run` (confirmation required).
5. To pay by Stripe: `pay_line_via_stripe` for each person who has payouts set up (confirmation required; the preview shows the recipient, amount and funding source). Paying many people means one confirmation per person. If a payout fails, `retry_stripe_payout` retries only the transfer and never charges the owner again. `list_upcoming_payouts` shows what is still owed.

- Paid in cash, Zelle or cheque rather than Stripe: once the run is finalized, `set_pay_line_paid` records the line as paid (confirmation required; it moves no money, so say that).
- Wrong dates: `update_pay_run_period` rebuilds the run for a new period (confirmation required; only if nothing has been paid yet; read the preview of what changes).
- A cleaner's Stripe setup looks stuck: `refresh_cleaner_payout_status` re-checks it.

Setting pay, finalizing a run and paying through Stripe each return an approval link as well as a preview: the user must open it and click Approve themselves before you can continue. Never pay a line the user has not explicitly approved. If the owner's funding source is not set up, explain that and stop.
