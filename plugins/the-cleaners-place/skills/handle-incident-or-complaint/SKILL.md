---
name: handle-incident-or-complaint
description: "Handle a damage report, accident, or customer complaint in The Cleaners Place from first report to resolution: pull up the job and history, record what happened, coach the team, follow up, and route refund requests to support. Use when something went wrong on a job."
---

# Handle an incident or complaint (owner / manager)

1. **Find it.** `list_incidents` for open ones, or start from the job: `get_job` (who was there, times, checklist, notes) and `get_client` (history, notes, preferences).
2. **Understand it.** `get_incident` for the details, category and whether the customer was told. Summarize what happened and what is still unknown. Ask the user questions rather than assuming fault.
3. **Record it.** `report_incident` if it was not logged yet, and `add_client_note` or `add_job_note` for context (these append; they never overwrite).
4. **Make it right.** Suggest options and let the user choose: a redo visit (`create_job`, linked to the same client and property), a goodwill adjustment on the next invoice (`create_invoice` or `update_invoice` for a draft), or a call from the owner. Draft any customer message for the owner to send.
5. **Team.** If a cleaner needs coaching, `add_staff_feedback` (private unless the user chooses to share it).
6. **Close it.** `resolve_incident` with a short resolution note. `reopen_incident` if it comes back.
7. **Refunds.** Refunds are not done through the assistant. If the customer is owed money back, use `submit_feedback` to send the request to support: it shows the exact message for the user to approve first.

Be factual and kind in anything written about a cleaner or a customer.
