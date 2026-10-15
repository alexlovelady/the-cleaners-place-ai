---
name: recurring-schedule-health-check
description: "Check the health of recurring customers in The Cleaners Place: schedules with no crew, holds that have ended, upcoming gaps, rotation focus, and visits at risk. Use when the user asks if recurring jobs are in order or wants a tidy-up of repeat customers."
---

# Recurring schedule health check (owner / manager)

1. `list_subscriptions` (active), then `list_subscriptions` with `paused: true` for vacation holds. Flag holds that have ended or end soon: the schedule resumes by itself, but confirm the customer expects that.
2. `list_jobs` with `unassigned: true` for the next 2 to 3 weeks and filter to recurring visits: a recurring customer with no crew is the most common gap. Offer `assign_job` for each, or `update_subscription` to set a default crew so future visits are covered.
3. `get_schedule` for conflicts (`double_booked`, `assignee_on_time_off`) on recurring visits.
4. `get_rotation_plan` for this week's rotating focus task and who is exempt.
5. For each problem propose a fix, apply only after a yes. For absences use `skip_subscription_visit` or `pause_subscription` (both cancel visits, so they ask for confirmation; read the preview). `cancel_subscription` ends a schedule and also asks first.
6. Finish with a short list: healthy, fixed, and still needs a decision.
