---
layout: default
title: Package Price
parent: Objects
---

# Package Price
{: .d-inline-block }
object
{: .label .fs-1 }

#### Attributes

## `price.fractional`

{: .d-inline-block }
number
{: .label .fs-1 }

The total price of a package for a specified adult count represented in the sub-unit of the current customer's currency.
e.g. considering the amount $19.50, it will return 1950.

## `price.per_person_fractional`

{: .d-inline-block }
number
{: .label .fs-1 }
The per-person price for a package based on the specified adult count represented in the sub-unit of the current customer's currency.
e.g. considering the amount a total amount of $30.00 and an adult count of 3, it will return 1000.
