---
layout: default
title: Cart Item
parent: Cart
---

The `item` object has the following attributes.

# item.adult_count

The number of guests selected for the variant as an integer.

# item.end_on

The end date of the product associated with the cart item.

# item.id

A unique ID for the cart item.

# item.quantity

The quantity selected on the cart item as an integer.

# item.price

The price of the cart item _not_ including any modifier selections and _not_ including any price reductions. This is returned as a fractional in the sub-unit of the current user's currency.

# item.product

The [product]({% link docs/reference/objects/product/index.md %}) associated with the cart item.

# item.selections

A list of [modifier selections]({% link docs/reference/objects/cart/modifier_selection.md %}) made on the cart item.

# item.start_on

The start date of the product associated with the cart item.

# item.subtotal

The price of the cart item, including the total price of all modififer selections and _not_ including any price reductions. This is returned as a fractional in the sub-unit of the current user's currency.

# item.total

The total cost of the item, including the total price of all modififer selections and after all price reductions and fees have been applied. This is returned as a fractional in the sub-unit of the current user's currency.

# item.total_deposit

The minimum amount which must be paid for the item at checkout. If no deposit is enabled this will return the `total`, otherwise it will return the `total` multiplied by the deposit rate. This is returned as a fractional in the sub-unit of the current user's currency.

# item.total_fee

The booking fee amount for the item returned as a fractional in the sub-unit of the current user's currency.

# item.total_guests

The total number of guests on the cart item, i.e. `quantity` multiplied by `adult_count`.

# item.total_modifications_amount

The total of all the modifier selections made on the cart item. This is returned as a fractional in the sub-unit of the current user's currency.

# item.variant

The [variant]({% link docs/reference/objects/product/variant.md %}) associated with the cart item.

# item.variant_name

The name of the variant associated with the cart item.
