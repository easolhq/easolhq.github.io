---
layout: default
title: Promotion
parent: Product
grand_parent: Objects
---

# Promotion
{: .d-inline-block }
object
{: .label .fs-1 }

#### Attributes

## `promotion.active`
{: .d-inline-block }
boolean
{: .label .fs-1 }

Returns `true` if a promotion is currently active.

## `promotion.category`
{: .d-inline-block }
string
{: .label .fs-1 }

Returns one of the following categories `Early release`, `Special offer` or `Last minute` if the promotion is categorised.

## `promotion.dates`
{: .d-inline-block }
string
{: .label .fs-1 }

Returns the dates the promotion is active for as a humanized string e.g. `7 - 14 August 2019`.

## `promotion.discount_amount`
{: .d-inline-block }
string
{: .label .fs-1 }

Returns the discount the promotion will apply, if the promotion represents a percentage discount this will be formatted as `25%` if it is a monetary discount this will be as `$25.00`.

Deprecated, use `promotion.discount_amount_fractional` or `promotion.discount_percentage` instead. `promotion.is_discount_percentage` can be used to determine which method to use.

## `promotion.discount_amount_fractional`
{: .d-inline-block }
number
{: .label .fs-1 }

Returns the discount the promotion will apply when it's a monetary amount e.g. `1250` when the promotion is `$12.50`.
It will return `nil` if the promotion is a percentage discount.

## `promotion.discount_is_percentage`
{: .d-inline-block }
boolean
{: .label .fs-1 }

Returns `true` if this promotion is a percentage discount.

## `promotion.discount_percentage`
{: .d-inline-block }
number
{: .label .fs-1 }

The percentage discount for this promotion as a number e.g. `30`.
It will return `nil` if the promotion is a monetary amount.

## `promotion.ends_on`
{: .d-inline-block }
timestamp
{: .label .fs-1 }

Returns the date the promotion will end as a timestamp, this can then be used in conjunction with liquids[ built-in filters ](https://shopify.github.io/liquid/filters/date/).
It will return `nil` if the promotion doesn't have an end date.

## `promotion.name`
{: .d-inline-block }
string
{: .label .fs-1 }

Returns the name of the promotion.

## `promotion.starts_on`
{: .d-inline-block }
timestamp
{: .label .fs-1 }

Returns the date the promotion will start as a timestamp, this can then be used in conjunction with liquids[ built-in filters ](https://shopify.github.io/liquid/filters/date/).

## `promotion.tagline`
{: .d-inline-block }
string
{: .label .fs-1 }

Returns the tagline for the promotion.
