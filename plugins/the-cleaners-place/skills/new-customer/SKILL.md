---
name: new-customer
description: "Onboard a new customer in The Cleaners Place from first contact to first clean: create the customer and property, send a quote or book the job, set up recurring service. Use when the user mentions a new lead, a new customer, or wants to quote or book someone."
---

# New customer to first clean (owner / manager)

1. **Avoid duplicates.** `search_clients` by name, email and phone first. If there is a likely match, show it and ask whether to use it.
2. **Customer and property.** `create_client` (it also reports `possibleDuplicates`), then `create_property` with the address and any access notes the user gives you. Do not invent details; ask for what is missing (address and a way to contact them are the minimum).
3. **Price it.** `list_services` for service types, add-ons and price tiers. Match the request to a service and quote from the real price list.
4. **Choose a path** with the user:
   - **Quote first:** `create_estimate`, show it, then `send_estimate` (emails the customer: confirmation required). When they accept, `convert_estimate_to_job`.
   - **Book directly:** `find_available_slots` for the date, then `create_job` (assign a cleaner with `assign_job` if the user names one).
   - **Recurring:** `create_subscription` (weekly / biweekly / monthly) with start date, price and crew. `get_subscription` to confirm the next visits.
5. Offer to `send_client_portal_link` so the customer can see their bookings (emails them: confirmation required).

Summarize what now exists (customer, property, job/quote/subscription with dates and prices) and what you did not do.
