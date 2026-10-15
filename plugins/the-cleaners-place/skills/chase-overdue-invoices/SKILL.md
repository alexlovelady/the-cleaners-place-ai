---
name: chase-overdue-invoices
description: "Collect overdue payments in The Cleaners Place: review overdue invoices, decide per customer whether to re-send, charge the card on file, or send a card-setup link. Use when the user asks about unpaid or overdue invoices or wants to get paid."
---

# Chase overdue invoices (owner / manager)

1. `list_invoices` with `status: overdue`, oldest first (use `olderThanDays` for age buckets such as 30, 60 and 90 days). Show a compact table: customer, invoice number, amount, days overdue, whether autopay/card is on file.
2. For any the user wants to dig into, `get_invoice` (autopay attempts, last decline reason, payment link status).
3. Suggest an action per invoice and let the user choose:
   - **Card on file, autopay failed:** explain the last decline reason; options are wait for the automatic retry, or `charge_invoice_now`.
   - **No card on file:** `send_invoice` re-sends the invoice email; `email_card_setup_link` asks the customer to save a card.
   - **Paid outside the app (cash/cheque):** `update_invoice_status` to `paid`. This only records it and does not touch Stripe.
   - **Write off:** `update_invoice_status` to `void`.
4. `charge_invoice_now`, `send_invoice` (which can also charge an autopay customer), `email_card_setup_link` and `update_invoice_status` all require confirmation. Read the preview to the user exactly as returned: it states the amount, the card, and who is emailed. Only call again with the token after a clear yes.

Charging a card (including a send that will also charge) returns an approval link: the user opens it and clicks Approve in The Cleaners Place before you can continue. Never batch-confirm several money actions at once: confirm each invoice separately. Never invent a refund path: refunds are handled by contacting support.
