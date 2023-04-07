---
layout: default
title: Experience Date
parent: Product
has_children: false
---

# Experience Date
{: .d-inline-block }
object
{: .label .fs-1 }

#### Attributes

## `experience_date.dates`
{: .d-inline-block }
string
{: .label .fs-1 }

The dates of the product as a formatted string.
e.g. `15 November 2024` for an experience with a duration of less than or equal to one day.
e.g. `15 - 20 November 2024` for an experience with a duration of more than one day.

## `experience_date.end_on`
{: .d-inline-block }
timestamp
{: .label .fs-1 }

This can then be used in conjunction with Liquid's [built-in filters](https://shopify.github.io/liquid/filters/date/).

## `experience_date.extras`
{: .d-inline-block }
array of [Extra]({% link docs/reference/objects/product/extra.md %})s
{: .label .fs-1 }

An array of the date's [extras]({% link docs/reference/objects/product/extra.md %})

## `experience_date.featured_variant`
{: .d-inline-block }
[Variant]({% link docs/reference/objects/product/variant/index.md %})
{: .label .fs-1 }

The "featured" [variant]({% link docs/reference/objects/product/variant/index.md %}). This will be the display variant for the date's product or if none has been set, the variant with the cheapest per-person price, factoring in any promotions.

## `experience_date.remaining_stock`
{: .d-inline-block }
number
{: .label .fs-1 }

The sum of remaining stock for a date's variants. If any of the variants have infinite stock this will return `nil`.

## `experience_date.shop_url`
{: .d-inline-block }
string
{: .label .fs-1 }

The url for the date's cart shop page.

## `experience_date.sold_out`
{: .d-inline-block }
boolean
{: .label .fs-1 }

Returns `true` if all stock for this date is sold out.

## `experience_date.start_on`
{: .d-inline-block }
timestamp
{: .label .fs-1 }

This can then be used in conjunction with Liquid's [built-in filters](https://shopify.github.io/liquid/filters/date/).

## `experience_date.variants`
{: .d-inline-block }
array of [variant]({% link docs/reference/objects/product/variant/index.md %})s
{: .label .fs-1 }

An array of the date's [variants]({% link docs/reference/objects/product/variant/index.md %}).
