---
layout: default
title: Availability day
parent: Accommodation variant
grand_parent: Variant
---

# Availability day

{: .d-inline-block }
object
{: .label .fs-1 }

#### Attributes

## `availability_day.available`

{: .d-inline-block }
boolean
{: .label .fs-1 }

If the accommodation is marked as available for the date.

Additionally, when using "Resources" as the stock strategy, it will also check if there are available resources for the date and if the available resources have enough capacity to accommodate the mininum occupancy.

## `availability_day.date`

{: .d-inline-block }
timestamp
{: .label .fs-1 }

The date as a timestamp. This can then be used in conjunction with Liquid's [built-in filters](https://shopify.github.io/liquid/filters/date/).

## `availability_day.prices`

{: .d-inline-block }
array of [Price]({% link docs/reference/objects/product/price.md %})s
{: .label .fs-1 }

An array of [Price]({% link docs/reference/objects/product/price.md %}) objects for the date.

## `availability_day.remaining_stock`
{: .d-inline-block }
number
{: .label .fs-1 }

The remaining stock for the accommodation day if variant uses inventory per night stock strategy.

Otherwise this will return `nil`.
