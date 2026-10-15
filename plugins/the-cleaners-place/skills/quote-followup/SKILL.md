---
name: quote-followup
description: "Follow up on quotes that have not been answered in The Cleaners Place: find sent estimates, see who has looked at them, re-send, and book or close them. Use when the user asks about open quotes, estimates waiting for an answer, or how to win more jobs."
---

# Quote follow-up (owner / manager)

Unanswered quotes are the cheapest revenue to recover.

1. `list_estimates` with `status: sent` and `olderThanDays: 3`. Note which have been viewed (`viewed`) and which have not, and the total value waiting.
2. For each worth chasing, `get_estimate` (scope, price, valid-until, customer contact). Sort the list: viewed but unanswered first (they are interested), then high value.
3. Suggest an action per quote and let the user choose:
   - **Not viewed:** `send_estimate` re-sends the email (asks for confirmation; it emails the customer).
   - **Viewed, no answer:** draft a short, friendly follow-up message for the owner to send themselves (call, text or email). Offer a small incentive only if the user suggests one.
   - **Customer said yes by phone or text:** `accept_estimate` records it and books the job (confirmation required; the preview says what is created).
   - **Customer said no:** `decline_estimate`, or `delete_estimate` for a stale one.
   - **Accepted but not booked:** `convert_estimate_to_job`, then offer `find_available_slots` and `assign_job`.
4. Finish with a tally: quotes sent, re-sent, booked, closed, and the value still open.

Never accept or decline for a customer without the user saying the customer told them so.
