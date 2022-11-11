---
layout: default
title: Price
parent: Product
grand_parent: Objects
---

# Price
{: .d-inline-block }
object
{: .label .fs-1 }

#### Attributes

## `price.fractional`
{: .d-inline-block }
number
{: .label .fs-1 }

The price for this occupancy represented in the sub-unit of the current customer's currency.
e.g. considering the amount $19.50, it will return 1950.

## `price.per_person_fractional`
{: .d-inline-block }
number
{: .label .fs-1 }

The price per person represented in the sub-unit of the current customer's currency.
e.g. considering a price of $20 with an occupancy of 2, it will return 10.

## `price.occupancy`
{: .d-inline-block }
number
{: .label .fs-1 }

The occupancy associated with this price, i.e. if the variant is purchased with this occupancy, this is what the price will be.

## `price.price`
{: .d-inline-block }
string
{: .label .fs-1 }
deprecated
{: .label .fs-1 .label-red .ml-0 .mt-0 }

The price for this occupancy represented in the sub-unit of the current customer's currency.
e.g. considering the amount $19.50, it will return 1950.

Deprecated, use `price.fractional` instead.
