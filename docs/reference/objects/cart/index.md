---
layout: default
title: Cart
parent: Objects
---

# Cart
{: .d-inline-block }
object
{: .label .fs-1 }

#### Attributes

## `cart.items`
{: .d-inline-block }
array of [Cart item]({% link docs/reference/objects/cart/cart_item.md %})s
{: .label .fs-1 }

An array of [cart items]({% link docs/reference/objects/cart/cart_item.md %}) associated with the cart.

## `cart.currency`
{: .d-inline-block }
string
{: .label .fs-1 }

The currency code associated with the cart.

## `cart.custom_data`
{: .d-inline-block }
array of [Custom Data]({% link docs/reference/objects/cart/custom_data.md %})
{: .label .fs-1 }

An array of [custom data]({% link docs/reference/objects/cart/custom_data.md %}) that the creator has chosen to be visible. For use in recommendation templates where the cart is the booking.

## `cart.subtotal`
{: .d-inline-block }
number
{: .label .fs-1 }

The amount of the cart _before_ any price reductions have been applied. This is returned as a fractional in the sub-unit of the current customer's currency.

## `cart.total`
{: .d-inline-block }
number
{: .label .fs-1 }

The amount of the cart after all price reductions have been applied. This is returned as a fractional in the sub-unit of the current customer's currency.

## `cart.total_fee`
{: .d-inline-block }
number
{: .label .fs-1 }

The booking fee amount returned as a fractional in the sub-unit of the current customer's currency.

## `cart.total_price_reduction`
{: .d-inline-block }
number
{: .label .fs-1 }

The total amount of all price reductions from promotions or vouchers. This is returned as a fractional in the sub-unit of the current customer's currency.

## `cart.total_deposit`
{: .d-inline-block }
number
{: .label .fs-1 }

The minimum payment possible at checkout if choosing to pay with a deposit. This will be zero if a deposit is not enabled for any of the products in the cart. This is returned as a fractional in the sub-unit of the current customer's currency.

## `cart.start_on`
{: .d-inline-block }
timestamp
{: .label .fs-1 }

The earliest start on from all the cart's line items. Returns `nil` if the cart doesn't have any line items.

## `cart.end_on`
{: .d-inline-block }
timestamp
{: .label .fs-1 }

The latest end on from all the cart's line items. Returns `nil` if the cart doesn't have any line items.

## `cart.first_instalment_amount`
{: .d-inline-block }
number
{: .label .fs-1 }

The amount due for the cart on a payment plan. Returns zero if no payment plan is enabled. This is returned as a fractional in the sub-unit of the current customer's currency.
