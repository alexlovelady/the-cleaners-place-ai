---
name: morning-briefing
description: Owner/manager daily briefing for The Cleaners Place: today's jobs, what needs attention, money due, and requests waiting. Use when the user says good morning, asks what's going on today, or wants a status check on the business.
---

# Morning briefing (owner / manager)

Goal: one short, scannable briefing the user can read in under a minute.

1. `get_today`: today's jobs in the company timezone. Note the first job time, total jobs, who is working, and the `needsAttention` block (unassigned jobs, pending check-time approvals, open incidents).
2. `list_invoices` with `status: overdue` (and `sent` if useful): count and total owed; name the 3 largest.
3. `list_time_off_requests` with `status: pending` and `list_check_time_requests`: anything waiting on the user.
4. `list_upcoming_payouts` (only if the company has staff on pay runs): money owed to staff soon.

Write the briefing as:
- **Today:** N jobs, first at H:MM, crew, anything unusual (double booking, time off, open incident).
- **Needs you:** unassigned jobs, requests to approve, incidents to resolve.
- **Money:** overdue total, biggest overdue customers.
- **Suggested next steps:** at most three, each one phrased as something you can do right now ("Assign Maria to the 2pm Hill St clean?").

Do not take any action without being asked. If a section has nothing, skip it rather than saying "nothing".
