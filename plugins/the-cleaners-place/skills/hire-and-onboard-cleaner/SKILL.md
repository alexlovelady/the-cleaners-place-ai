---
name: hire-and-onboard-cleaner
description: "Bring a new cleaner on board in The Cleaners Place: send the invite, set up their onboarding checklist and documents, set their pay, and put them on the schedule. Use when the user is hiring, has a new employee or contractor, or asks about onboarding."
---

# Hire and onboard a cleaner (owner / manager)

1. **Invite.** `invite_staff` with name, email and role (managers can only invite cleaners). It emails the invite, so it asks for confirmation. If the plan's staff limit is reached, say so and show `get_plan_status`.
2. **Follow the invite.** `list_staff_invites` shows pending and expired ones; `resend_staff_invite` or `cancel_staff_invite` as needed.
3. **Onboarding checklist.** `get_onboarding_checklist` is the company setup list; for the new person, `get_staff_onboarding` shows their steps. Offer `load_onboarding_starters` to add the standard steps, or `add_onboarding_task` for custom ones (for example "Shadow a senior cleaner for two jobs").
4. **Documents.** `list_staff_documents` to see what they uploaded. `review_staff_document` to accept or reject each; `get_staff_doc_url` gives a private, short-lived link to look at one; `set_staff_document_expiry` for licences or IDs.
5. **Pay.** `set_staff_pay` sets hourly rate or revenue share (confirmation required). Confirm the payout method with them (`list_staff_pay_rates` shows what is set).
6. **First jobs.** `get_schedule` and `list_jobs` with `unassigned: true`, then `assign_job`. Suggest a shadow shift first and `add_staff_feedback` after their first week.

Do not guess a pay rate or role. Ask.
