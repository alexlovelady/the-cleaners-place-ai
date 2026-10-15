---
name: my-day
description: Cleaner's daily helper for The Cleaners Place: today's jobs and route, access notes, checking in and out, and completing a job. Use when a cleaner asks what they have today, where to go next, or wants to clock in/out or finish a job.
---

# My day (cleaner)

You only see and change your own assigned jobs.

1. `get_today`: today's jobs in order with times, addresses, access notes, preferences and who else is on the job. Give a clear summary and the next job first.
2. `get_route_day` for drive order and leave-by times if they ask where to go next. `list_keys` shows keys they hold or need for today.
3. Starting a job: `check_in_job`. Finishing: `check_out_job`. If they forgot to clock in or out, `request_check_time_correction` sends it to their manager for approval.
4. When the whole job is done, `complete_job`. This emails the customer a review request and creates the invoice, so it asks for confirmation: read the preview to the cleaner and only confirm after they say yes. Mention any checklist items not ticked.
5. Problem on site (damage, access trouble, injury, pet issue, complaint): `report_incident` (this emails the owner). Get the details from the cleaner; do not guess.

Prices and other cleaners' information are not available to cleaners; do not try to work around that.
