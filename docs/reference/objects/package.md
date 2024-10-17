---
layout: default
title: Package
parent: Objects
---

# Package
{: .d-inline-block }
object
{: .label .fs-1 }

The package object represents a package, which is a collection of items that can be purchased together.

<br>

#### Attributes

## `package.id`
{: .d-inline-block }
string
{: .label .fs-1 }
The unique id of the package.

## `package.name`
{: .d-inline-block }
string
{: .label .fs-1 }

The name of the package.

## `package.tagline`
{: .d-inline-block }
string
{: .label .fs-1 }

The tagline of the package.

## `package.type`
{: .d-inline-block }
string
{: .label .fs-1 }

Will always return "`package`".

## `package.price_fractional`
{: .d-inline-block }
number
{: .label .fs-1 }

The total price for the package represented in the sub-unit of the current
customer's currency. e.g. considering the amount $19.50, it will return 1950.

## `package.requires_date`
{: .d-inline-block }
boolean
{: .label .fs-1 }

Whether the package requires a date to be selected when adding to the cart.
A date field with the name `package[start_date]` will be required when adding
the package to the cart, optionally with a `package[start_time]` field matching
the format `HH:MM` can be added to the form.

## `package.price_per_person_fractional`
{: .d-inline-block }
number
{: .label .fs-1 }

The price per person for the package represented in the sub-unit of the current
customer's currency. e.g. considering the amount $19.50, it will return 1950.

## `package.image`
{: .d-inline-block }
[Image]({% link docs/reference/objects/image.md %})
{: .label .fs-1 }

The package's image.

## `package.items`
{: .d-inline-block }
[Package Item]({% link docs/reference/objects/package/item.md %})
{: .label .fs-1 }

The included items in the package.

## `package.off_sale`
{: .d-inline-block }
boolean
{: .label .fs-1 }

Whether the package is off sale.

## `package.off_sale_copy`
{: .d-inline-block }
string
{: .label .fs-1 }

The copy to display when the package is off sale.

## `package.payment_plan`
{: .d-inline-block }
[Payment Plan]({% link docs/reference/objects/product/variant/payment_plan.md %})
{: .label .fs-1 }

If the package is custom priced and has a payment plan associated with it, this will return that payment plan. The payment plan won’t be returned if the instalment schedule cannot be completed before the start date of the package.

## `package.state`
{: .d-inline-block }
string
{: .label .fs-1 }

The state of the package. Can be one of:
- draft
- selling
- off_sale

## `package.steps`
{: .d-inline-block }
[Package Step]({% link docs/reference/objects/package/step.md %})
{: .label .fs-1 }

The booking journey steps available for a package.

## `package.booking_fee_rate`
{: .d-inline-block }
number
{: .label .fs-1 }

The package's booking fee rate as a decimal between 0 and 1.

## `package.total_booking_fee`
{: .d-inline-block }
number
{: .label .fs-1 }

The package's total booking fee represented in the sub-unit of the current customer’s currency.
e.g. considering the amount $19.50, it will return 1950.
