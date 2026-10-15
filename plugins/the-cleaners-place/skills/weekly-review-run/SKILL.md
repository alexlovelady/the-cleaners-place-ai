---
name: weekly-review-run
description: "Run the weekly review-request round in The Cleaners Place: find customers with a recently completed job who have not been asked, ask them one by one, and see what came back. Use when the user wants more Google reviews or asks to request reviews."
---

# Weekly review run (owner / manager)

1. `list_review_candidates` for the last 7 to 14 days. These are completed jobs with a customer email, no review request sent yet, no review, and no opt-out.
2. Show who is on the list: customer, date, service, and the cleaner. Skip anyone with a known complaint (check `list_incidents` and the customer's notes via `get_client`).
3. For each customer the user approves, `request_review` (it emails the customer, so it asks for confirmation: read the preview aloud). One confirmation per customer.
4. `list_reviews` to see what came back recently: average rating, any low scores, and private feedback. For a low score, offer the `handle-incident-or-complaint` workflow.
5. If the company has no Google review link yet, mention that `update_business_settings` can set `googleReviewUrl`.

Ask only customers who had a good visit. Never write or edit a review for a customer.
