---
layout: default
title: Cart
parent: Objects
---

The `cart` object has the following attributes.

# cart.items

A list of [cart items]({% link docs/reference/objects/cart/cart_item.md %}) associated with the cart.

# cart.currency

The currency code associated with the cart.

# cart.subtotal

The amount of the cart _before_ any price reductions have been applied. This is returned as a fractional in the sub-unit of the current customer's currency.

# cart.total

The amount of the cart after all price reductions have been applied. This is returned as a fractional in the sub-unit of the current customer's currency.

# cart.total_fee

The booking fee amount returned as a fractional in the sub-unit of the current customer's currency.

# cart.total_price_reduction

The total amount of all price reductions from promotions or vouchers. This is returned as a fractional in the sub-unit of the current customer's currency.

# cart.total_deposit

The minimum payment possible at checkout if choosing to pay with a deposit. This will be zero if a deposit is not enabled for any of the products in the cart. This is returned as a fractional in the sub-unit of the current customer's currency.

# cart.start_on

The earliest start on from all the cart's line items. Returns `nil` if the cart doesn't have any line items.

# cart.end_on

The latest end on from all the cart's line items. Returns `nil` if the cart doesn't have any line items.

# cart.first_instalment_amount

The amount due for the cart on a payment plan. Returns zero if no payment plan is enabled. This is returned as a fractional in the sub-unit of the current customer's currency.
