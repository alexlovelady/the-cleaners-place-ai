---
name: supply-restock
description: "Keep cleaning supplies stocked in The Cleaners Place: see what is running low, decide what to buy, and record the purchase as an expense and a stock update. Use when the user asks about supplies, inventory, or what to reorder."
---

# Supply restock (owner / manager)

1. `list_supplies` with `reorderOnly: true`. Show item, quantity left, the reorder level, and unit.
2. Ask what the user actually bought or plans to buy (quantities and the total price). Do not guess prices.
3. After they buy: `adjust_supply` to add the quantity, and `create_expense` for the cost (category supplies, the date, the amount). Receipt photos cannot be attached here; remind them to add the receipt in the app.
4. New item or changed reorder level: `create_supply` or `update_supply`.
5. `get_dashboard_summary` shows any other low-stock warnings. Finish with what is still low.

`delete_supply` removes an item and asks for confirmation.
