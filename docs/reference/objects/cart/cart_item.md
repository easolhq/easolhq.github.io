---
layout: default
title: Cart item
parent: Cart
---

# Cart item
{: .d-inline-block }
object
{: .label .fs-1 }

#### Attributes

## `item.adult_count`
{: .d-inline-block }
number
{: .label .fs-1 }

The number of guests selected for the variant.

## `item.end_on`
{: .d-inline-block }
timestamp
{: .label .fs-1 }

The end date of the product associated with the cart item.

## `item.id`
{: .d-inline-block }
string
{: .label .fs-1 }

A unique ID for the cart item.

## `item.quantity`
{: .d-inline-block }
number
{: .label .fs-1 }

The quantity selected on the cart item.

## `item.price`
{: .d-inline-block }
number
{: .label .fs-1 }

The price of the cart item _not_ including any modifier selections and _not_ including any price reductions. This is returned as a fractional in the sub-unit of the current customer's currency.

## `item.product`
{: .d-inline-block }
[Product]({% link docs/reference/objects/product/index.md %})
{: .label .fs-1 }

The [product]({% link docs/reference/objects/product/index.md %}) associated with the cart item.

## `item.selections`
{: .d-inline-block }
array of [Modifier selection]({% link docs/reference/objects/cart/modifier_selection.md %})s
{: .label .fs-1 }

The [modifier selections]({% link docs/reference/objects/cart/modifier_selection.md %}) made on the cart item.

## `item.start_on`
{: .d-inline-block }
timestamp
{: .label .fs-1 }

The start date of the product associated with the cart item.

## `item.sub_items`
{: .d-inline-block }
array of [Cart item]({% link docs/reference/objects/cart/cart_item.md %})s
{: .label .fs-1 }

The related sub-items for a [Cart item]({% link docs/reference/objects/cart/cart_item.md %}). Currently these are available for cart items that are for a custom-priced package, and the sub-items are all other line items that are part of its package booking.

## `item.subtotal`
{: .d-inline-block }
number
{: .label .fs-1 }

The price of the cart item, including the total price of all modifier selections and _not_ including any price reductions. This is returned as a fractional in the sub-unit of the current customer's currency.

## `item.total`
{: .d-inline-block }
number
{: .label .fs-1 }

The total cost of the item, including the total price of all modifier selections and after all price reductions and fees have been applied. This is returned as a fractional in the sub-unit of the current customer's currency.

## `item.total_deposit`
{: .d-inline-block }
number
{: .label .fs-1 }

The minimum amount to be paid for the item at checkout. If no deposit is enabled this will return the `total`, otherwise it will return the `total` multiplied by the deposit rate. This is returned as a fractional in the sub-unit of the current customer's currency.

## `item.total_fee`
{: .d-inline-block }
number
{: .label .fs-1 }

The booking fee amount for the item returned as a fractional in the sub-unit of the current customer's currency.

## `item.total_guests`
{: .d-inline-block }
number
{: .label .fs-1 }

The total number of guests on the cart item, i.e. `quantity` multiplied by `adult_count`.

## `item.total_modifications_amount`
{: .d-inline-block }
number
{: .label .fs-1 }

The total of all the modifier selections made on the cart item. This is returned as a fractional in the sub-unit of the current customer's currency.

## `item.total_package_upgrade_amount`
{: .d-inline-block }
number
{: .label .fs-1 }

The total of all the package upgrades associated with the cart item. This is returned as a fractional in the sub-unit of the current customer's currency.

## `item.variant`
{: .d-inline-block }
[Variant]({% link docs/reference/objects/product/variant/index.md %})
{: .label .fs-1 }

The [variant]({% link docs/reference/objects/product/variant/index.md %}) associated with the cart item.

## `item.variant_name`
{: .d-inline-block }
string
{: .label .fs-1 }

The name of the variant associated with the cart item.
