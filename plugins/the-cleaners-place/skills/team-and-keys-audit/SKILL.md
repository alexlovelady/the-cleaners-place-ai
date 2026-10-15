---
name: team-and-keys-audit
description: "Audit people and access in The Cleaners Place: expiring staff documents, unfinished onboarding, keys and lockbox access, and open incidents. Use when the user asks about compliance, who is missing paperwork, or where the keys are."
---

# Team and keys audit (owner / manager)

1. **Documents.** `list_staff_documents` with `expiringWithinDays: 30`, plus anything rejected or missing. `set_staff_document_expiry` to correct a date; `review_staff_document` to accept or reject.
2. **Onboarding.** `get_staff_onboarding` with no staff id shows progress for everyone; list who is stuck and on which step.
3. **Keys.** `list_keys`: who holds each key, what is checked out, and keys with no recent activity. `check_in_key` and `check_out_key` record a handover; `set_key_status` marks a key lost or returned.
4. **Open incidents.** `list_incidents` for anything unresolved, especially key or access related.
5. **Time off and gaps.** `list_time_off_requests` with `status: pending`.

Present a short exceptions list (who, what, by when) and offer a fix for each. Reading a document file uses `get_staff_doc_url`, which is private and expires in minutes.
