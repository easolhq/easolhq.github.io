---
layout: default
title: Variant
parent: Product
has_children: true
---

When using a `variant` object you have access to the following attributes:<br>
*Note:* this defines a common interface shared between
[Experience Variant]({% link docs/reference/objects/product/variant/experience_variant/index.md %}) and
[Accommodation Variant]({% link docs/reference/objects/product/variant/accommodation_variant/index.md %}).

# variant.deposit_amount

Returns a humanized price for the variants deposit amount, if deposit's are not set on the variant this will just return `variant.price` e.g. `$250 Per Person`

# variant.has_infinite_stock

Returns true if the variant has infinite stock

# variant.id

Returns a unique id for the variant

# variant.image

Returns the variants [image]({% link docs/reference/objects/image.md %}) it it has one associated

# variant.initial_stock

Returns the initial stock for the variant, if the variant has infinite inventory this will return `nil`

# variant.max_occupancy

Returns the maximum number of guests for this variant.

# variant.min_occupancy

Returns the minimum number of guests for this variant.

# variant.name

Returns the variants name

# variant.price

Returns the variants cheapest price per unit e.g. `$124 Per Room` or `$124 Per Person`

# variant.promotion

Returns the variants current active [promotion]({% link docs/reference/objects/product/promotion.md %}) if there is one

# variant.remaining_stock

Returns the remaining stock for the variant, if the variant has infinite inventory this will return `nil`

# variant.segment_name

If the variant belongs to a segment this will return the segment name

# variant.sold_out

Returns true if the variant is sold out

# variant.tagline

Returns the variants tagline

# variant.type

Returns the type of this variant, one of `"experience_variant"` or `"accommodation_variant"`.
Check what other methods you can call on this drop according to their type,
[Experience Variant]({% link docs/reference/objects/product/variant/experience_variant/index.md %}),
[Accommodation Variant]({% link docs/reference/objects/product/variant/accommodation_variant/index.md %}).
