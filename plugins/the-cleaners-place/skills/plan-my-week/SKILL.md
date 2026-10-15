---
name: plan-my-week
description: Review and fix next week's schedule in The Cleaners Place: unassigned jobs, double bookings, time-off clashes, gaps, and route order. Use when the user wants to plan, tidy, or rebalance the schedule.
---

# Plan the week (owner / manager)

1. `get_schedule` for the range (default this week; ask if they mean next week). Read the `conflicts`: `double_booked`, `inside_blockout`, `assignee_on_time_off`, `closed_day`.
2. `list_jobs` with `unassigned: true` for the same range.
3. Present a short plan: what is fine, and a numbered list of problems with a proposed fix for each (who to assign, what to move).
4. Apply fixes only after the user agrees, one batch at a time:
   - `assign_job` / `unassign_job` to change crew.
   - `check_schedule_slot` before moving anything, then `reschedule_job`. If the user wants a new time, `find_available_slots` first.
   - For a day with several stops, `preview_route_optimization` shows the proposed order and drive time. Only if the user likes it, `apply_route_order`: this moves jobs and emails each affected customer their new time, so it asks for confirmation. Read the preview aloud before confirming.
5. After changes, re-run `get_schedule` and report what is now clean and what is left.

Never silently move a customer's visit. Rescheduling is the user's call; say which customers will be affected.
