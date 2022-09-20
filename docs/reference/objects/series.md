---
layout: default
title: Series
parent: Objects
---

When using a `series` object you have access to the following attributes
Can be accessed on a product like below

# series.countries

Returns an array of the countries of all upcoming products in the series

# series.departure_months

Returns an array of the departure months of all upcoming products in the series

# series.featured_variant

Returns the display [variant]({% link docs/reference/objects/product/variant/index.md %}) if set or defaults to the cheapest in the series.

# series.first_upcoming

Returns the first upcoming [product]({% link docs/reference/objects/product/index.md %}) in the series

# series.first_upcoming_including_ongoing

Returns the first upcoming [product]({% link docs/reference/objects/product/index.md %}) in the series, including any product that is taking place currently.

# series.humanized_display_amount _(deprecated)_

Returns a humanized display amount e.g. `$120.00`.

> ** Deprecated **
>
> This method is deprecated in favour of retrieving the value from the variant price instead.
>
> {% raw %}
> ```liquid
> {{variant.price | money}}
> ```
> {% endraw %}

# series.id

Returns a unique identifier for the series

# series.name

Returns the name of the series

# series.products

Returns an array of published [products]({% link docs/reference/objects/product/index.md %}) in the series, both past and future

# series.slug

Returns the unique slug used in a series url i.e. `domain.com/experiences/:series_slug/:date`

# series.upcoming_products

Returns an array of published [products]({% link docs/reference/objects/product/index.md %}) in the series which are upcoming

# series.upcoming_products_including_ongoing

Returns an array of published [products]({% link docs/reference/objects/product/index.md %}) in the series which are taking place currently or are upcoming.

