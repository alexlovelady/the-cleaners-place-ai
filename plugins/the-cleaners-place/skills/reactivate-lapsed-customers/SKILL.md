---
name: reactivate-lapsed-customers
description: "Win back customers who have not been cleaned for a while in The Cleaners Place: find lapsed and at-risk customers and propose a deep clean, a new quote, or a fresh recurring schedule. Use when the user wants more repeat business, asks who has stopped booking, or is worried about churn."
---

# Reactivate lapsed customers (owner / manager)

1. `search_clients` with `lastCleanedBefore` set to about 60 days ago (ask the user what counts as lapsed; 45 to 90 days is typical). Also run `get_retention_report` for the at-risk list and lifetime value, and `list_subscriptions` with `paused: true` for holds that may have run out.
2. Rank by value: lifetime value first, then how long since the last clean. Show 10 at most, with last clean date, average ticket and recurring status.
3. For the ones the user picks, `get_client` for history and notes, then propose one next step each:
   - **Gone quiet, no recurring:** `suggest_deep_clean` emails them a deep-clean suggestion (confirmation required: read the preview aloud, it shows the recipient and the exact text).
   - **Wants a price:** `create_estimate`, then `send_estimate`.
   - **Ready to book:** `find_available_slots`, `create_job`, or `create_subscription` for a recurring schedule.
4. For personal outreach, draft the text for the owner to send themselves.

Customers who opted out of email are skipped by the sender; say so if the preview shows no email will be sent. Never send to several customers on one yes: confirm each.
