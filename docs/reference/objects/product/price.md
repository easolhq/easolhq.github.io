---
layout: default
title: Price
parent: Product
grand_parent: Objects
---

This object represents a price of a variant or extra. When using a `price` object you have access to the following attributes:

# price.fractional

The amount for this occupancy represented in the sub-unit of the current user's currency.
e.g. considering the amount $19.50, it will return 1950.

# price.per_person_fractional

The amount per-person represented in the sub-unit of the current user's currency.
e.g. considering a price of $20 with an occupancy of 2, it will return 10.

# price.occupancy

The occupancy associated with this price, i.e. if the variant is purchased with this occupancy, this is what the price will be.

# price.price _(deprecated)_

The amount for this occupancy represented in the sub-unit of the current user's currency.
e.g. considering the amount $19.50, it will return 1950.

> **Deprecated**
>
> Use `price.fractional` instead.
