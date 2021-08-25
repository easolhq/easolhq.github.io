---
layout: default
title: Variant
parent: Product
---

When using a `variant` object you have access to the following attributes
Can be accessed on a product like below

# variant.deposit_amount

Returns a humanized price for the variants deposit amount, if deposit's are not set on the variant this will just return `variant.price` e.g. `$250 Per Person`

# variant.id

Returns a unique id for the variant

# variant.image

Returns the variants [image]({% link docs/reference/objects/image.md %}) it it has one associated

# variant.minimum_nights

If the variant is for an accommodation this will return the minimum number of nights the variant can be booked for

# variant.name

Returns the variants name

# variant.price

Returns the variants cheapest price per unit e.g. `$124 Per Room` or `$124 Per Person`

# variant.promotion

Returns the variants current active [promotion]({% link docs/reference/objects/product/promotion.md %}) if there is one

# variant.remaining_stock

Returns the remaining stock for the variants if the variant has infinite inventory this will return `INFINITE_STOCK`

# variant.segment_name

If the variant belongs to a segment this will return the segment name

# variant.sold_out

Returns true if the variant is sold out

# variant.tagline

Returns the variants tagline

