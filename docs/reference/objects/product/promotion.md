---
layout: default
title: Promotion
parent: Product
grand_parent: Objects
---

When using a `promotion` object you have access to the following attributes

# promotion.active

Returns true if the promotion is currently active.

# promotion.category

Returns one of the following categories `Early release`, `Special offer` or `Last minute` if the promotion is categorised.

# promotion.dates

Returns the dates the promotion is active for as a humanized string e.g. `7 - 14 August 2019`.

# promotion.discount_amount _(deprecated)_

Returns the discount the promotion will apply, if the promotion represents a percentage discount this will be formatted as `25%` if it is a monetary discount this will be as `$25.00`.

> **Deprecated**
 >
 > This is deprecated. Use `promotion.discount_amount_fractional` or `promotion.discount_percentage` instead. `promotion.is_discount_percentage` can be used to determine which method to use.

# promotion.discount_amount_fractional

Returns the discount the promotion will apply when it's a monetary amount e.g. `1250` when the promotion is `$12.50`.
It will return `nil` if the promotion is a percentage discount.

# promotion.discount_is_percentage

Returns true if this promotion is a percentage discount.

# promotion.discount_percentage

The percentage discount for this promotion as a number e.g. `30`.
It will return `nil` if the promotion is a monetary amount.

# promotion.ends_on

Returns the date the promotion will end on as a timestamp, this can then be used in conjunction with liquids[ built in filters ](https://shopify.github.io/liquid/filters/date/).
It will return `nil` if the promotion doesn't have an end date.

# promotion.name

Returns the name of the promotion.

# promotion.starts_on

Returns the date the promotion will start on as a timestamp, this can then be used in conjunction with liquids[ built in filters ](https://shopify.github.io/liquid/filters/date/).

# promotion.tagline

Returns the tagline for the promotion.
