---
name: time-off-requests
description: "Review and decide staff time-off requests in The Cleaners Place, checking the schedule for clashes first. Use when the user asks about time off, vacation, or who is out."
---

# Time-off requests (owner / manager)

1. `list_time_off_requests` with `status: pending`.
2. For each, `get_schedule` over the requested dates: how many jobs would lose their cleaner, and who else is free. Present each request as: who, dates, jobs affected, a recommendation.
3. On the user's decision: `approve_time_off` or `deny_time_off` (include a short reason when denying; ask the user for wording). Staff are notified by the app's normal flow.
4. If approving leaves jobs uncovered, offer to reassign with `assign_job` / `unassign_job` and list the affected jobs.
