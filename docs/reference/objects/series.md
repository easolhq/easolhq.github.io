---
layout: default
title: Series
parent: Objects
---

# Series
{: .d-inline-block }
object
{: .label .fs-1 }

#### Attributes

## `series.countries`
{: .d-inline-block }
array of strings
{: .label .fs-1 }

An array of the countries of all upcoming products in the series.

## `series.departure_months`
{: .d-inline-block }
array of strings
{: .label .fs-1 }

An array of the departure months of all upcoming products in the series.

## `series.featured_variant`
{: .d-inline-block }
[Variant]({% link docs/reference/objects/product/variant/index.md %})
{: .label .fs-1 }

The display [variant]({% link docs/reference/objects/product/variant/index.md %}) if set or the cheapest variant in the series.

## `series.first_upcoming`
{: .d-inline-block }
[Product]({% link docs/reference/objects/product/index.md %})
{: .label .fs-1 }

The first upcoming [product]({% link docs/reference/objects/product/index.md %}) in the series.

## `series.first_upcoming_including_ongoing`
{: .d-inline-block }
[Product]({% link docs/reference/objects/product/index.md %})
{: .label .fs-1 }

The first upcoming [product]({% link docs/reference/objects/product/index.md %}) in the series, including any product that is taking place currently.

## `series.humanized_display_amount`
{: .d-inline-block }
string
{: .label .fs-1 }
deprecated
{: .label .fs-1 .label-red .ml-0 .mt-0 }

A humanized display amount e.g. `$120.00`.

This method is deprecated in favour of retrieving the value from the [variant price]({% link docs/reference/objects/product/variant/index.md %}#variantprice) instead.

## `series.id`
{: .d-inline-block }
string
{: .label .fs-1 }

The unique identifier for the series.

## `series.name`
{: .d-inline-block }
string
{: .label .fs-1 }

The name of the series.

## `series.products`
{: .d-inline-block }
array of [Product]({% link docs/reference/objects/product/index.md %})s
{: .label .fs-1 }

An array of published [products]({% link docs/reference/objects/product/index.md %}) in the series, both past and future.

## `series.slug`
{: .d-inline-block }
string
{: .label .fs-1 }

The unique slug used in a series url i.e. `domain.com/experiences/:series_slug/:date`.

## `series.upcoming_products`
{: .d-inline-block }
array of [Product]({% link docs/reference/objects/product/index.md %})s
{: .label .fs-1 }

An array of published [products]({% link docs/reference/objects/product/index.md %}) in the series which are upcoming.

## `series.upcoming_products_including_ongoing`
{: .d-inline-block }
array of [Product]({% link docs/reference/objects/product/index.md %})s
{: .label .fs-1 }

An array of published [products]({% link docs/reference/objects/product/index.md %}) in the series which are taking place currently or are upcoming.

