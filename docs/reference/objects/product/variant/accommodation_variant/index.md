---
layout: default
title: Accommodation variant
parent: Variant
grand_parent: Product
has_children: true
---

# Accommodation variant
{: .d-inline-block }
object
{: .label .fs-1 }

The `accommodation_variant` object will inherit all attributes defined on
the [Variant]({% link docs/reference/objects/product/variant/index.md %}) object, plus
it has access to the following attributes.

<br>

#### Attributes

## `accommodation_variant.minimum_nights`
{: .d-inline-block }
number
{: .label .fs-1 }

Returns the minimum number of nights the variant can be booked for.

## `accommodation_variant.min_price_of_stay_fractional`
{: .d-inline-block }
number
{: .label .fs-1 }

The minimum price of stay represented as a sub-unit of the current customer's currency.
If present, the customer will be charged at least this amount, regardless of how many
nights they book the accommodation for.

## `accommodation_variant.type`
{: .d-inline-block }
string
{: .label .fs-1 }

Will return `accommodation_variant`.
