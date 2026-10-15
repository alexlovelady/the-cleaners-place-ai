---
name: end-of-day-wrap-up
description: "Close out the day in The Cleaners Place: jobs that were not completed, clock times to fix, incidents, invoices created, and tomorrow's schedule. Use when the user says wrap up, end of day, or asks what is left to do today."
---

# End-of-day wrap-up (owner / manager)

1. `get_today`: which jobs are completed, in progress, or still scheduled. Anything not completed needs a decision.
2. For each unfinished job offer one fix: `complete_job` (emails the customer a review request and creates the draft invoice, so it asks for confirmation), `reschedule_job`, `cancel_job`, or `set_job_status` for a no-show.
3. `list_check_time_requests` for corrections waiting on approval (`approve_check_time_request` / `reject_check_time_request`). If a clock time was missed entirely, `set_job_check_times` backfills it (asks first and shows the pay impact).
4. `list_incidents` for anything opened today.
5. `list_invoices` with `status: draft` for invoices created today that still need to be sent (`send_invoice` asks for confirmation).
6. `get_schedule` for tomorrow: unassigned jobs, conflicts, anyone on time off.

Summarize in three lines: done, still open, and what needs doing first thing tomorrow.
