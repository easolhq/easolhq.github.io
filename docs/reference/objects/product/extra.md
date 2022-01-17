---
layout: default
title: Extra
parent: Product
---

When using a `extra` object you have access to the following attributes

# extra.deposit_amount

Returns a humanized price for the extras deposit amount, if deposit's are not set on the extra this will just return `extra.price` e.g. `$250 Per Person`

# extra.has_infinite_stock

Returns true if the extra has infinite stock

# extra.id

Returns a unique id for the extra

# extra.image

Returns the extras [image]({% link docs/reference/objects/image.md %}) it it has one associated

# extra.initial_stock

Returns the initial stock for the extra, if the extra has infinite inventory this will return `nil`

# extra.name

Returns the extras name

# extra.price

Returns the extras price e.g. `$124 Per Person`

# extra.promotion

Returns the extras current active [promotion]({% link docs/reference/objects/product/promotion.md %}) if there is one

# extra.remaining_stock

Returns the remaining stock for the extra, if the extra has infinite inventory this will return `nil`

# extra.segment_name

If the extra belongs to a segment this will return the segment name

# extra.sold_out

Returns true if the extra is sold out

# extra.tagline

Returns the extras tagline