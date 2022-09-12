---
layout: default
title: Product
parent: Objects
has_children: true
---

When using a `product` object you have access to the following attributes.

# product.accommodations

Returns an array of the products [accommodations]({% link docs/reference/objects/product/accommodation_merchandise.md %})

# product.address

Returns the product [address]({% link docs/reference/objects/product/address.md %})

# product.blog_post_section

Returns the blog post section]({% link docs/reference/objects/product/blog_post_section.md %})

# product.category

Returns the category the product belongs to

# product.country

Returns the name of the country the product is based in

# product.dates

Returns the products dates as a formatted string based on whether the event is multi day or not.
e.g `15 - 20 November 2019` or `15 November 2019`

# product.depart_on

If the product has fixed dates this returns the start date of the event as a timestamp, this can then be used in conjunction with liquids[ built in filters ](https://shopify.github.io/liquid/filters/date/)

# product.deposit.rate

Returns the deposit rate for the product

# product.deposit.enabled

Returns true if deposits are enabled for the product

# product.display_variant

Returns the products display variant if set in the admin

# product.duration

Returns the duration of the product including duration unit e.g. `5 nights`

# product.enquire_only

Returns true if the product has been marked as Enquiry Only within the product payment settings

# product.extras

Returns an array of the products [extras]({% link docs/reference/objects/product/extra.md %})

# product.facilities _(deprecated)_

Returns an array of the products facilities

> **Deprecated**
>
> Please use [`product.whats_included.included`]({% link docs/reference/objects/product/whats_included.md %}#whats_includedincluded)

# product.faqs

Returns an array of the products [faqs]({% link docs/reference/objects/product/faq.md %})

# product.featured_accommodations

Returns an array of the products [accommodations]({% link docs/reference/objects/product/accommodation_merchandise.md %}) which are flagged as featured

# product.featured_variant

Returns the "featured" [variant]({% link docs/reference/objects/product/variant/index.md %}). This will be the display variant for this product, otherwise the variant with the cheapest per-person price, factoring in any promotions.

# product.gallery

Returns an array of [image objects]({% link docs/reference/objects/image.md %}) for the products gallery

# product.has_infinite_stock

Returns true if the product has infinite stock

# product.hero_image

Returns the products hero [image]({% link docs/reference/objects/image.md %}

# product.has_active_promotion

Returns true if one of the [variants]({% link docs/reference/objects/product/variant/index.md %}) in the product has an active [promotion]{% link docs/reference/objects/product/promotion.md %})

# product.highlights

Returns an array of the products [highlights]({% link docs/reference/objects/product/highlight.md %})

# product.host _(deprecated)_

Returns the products [host](https://app.gitbook.com/@fixers/s/canvas-developer/~/edit/drafts/-Lqg456H1ILVvLu_Ti3G/objects/product/host)
Deprecated please use [`hosts`](https://app.gitbook.com/@fixers/s/canvas-developer/~/drafts/-Lqg456H1ILVvLu_Ti3G/primary/objects/product#product-hosts)

> **Deprecated**
>
> Use [`product.host_section`]({% link docs/reference/objects/product/index.md %}#producthost_section) instead.

# product.host_section

Returns the product [host section]({% link docs/reference/objects/product/host.md %})

# product.id

Returns the product id

# product.includes_accommodation

Returns a boolean indicating whether or not the product includes accommodation or is just a ticket

# product.min_price _(deprecated)_

Returns a humanized price for the products cheapest configuration e.g. `$1,027 Per Person` or `$150 Per Night`
This excludes Sold Out and Hidden variants.
 If the display variant is changed within the product this will be used instead of the cheapest variant

> **Deprecated**
>
> Prices should be retrieved from the product's variants instead. `product.featured_variant` can be used to get the "featured" variant.

# product.minimum_nights

If the product is an accommodation this will return the minimum number of nights the product can be booked for

# product.name

Returns the name of the product

# product.overview

Returns the overview of the product

# product.overview_image

Returns the products overview [image]({% link docs/reference/objects/image.md %})

# product.remaining_stock

Returns the sum of remaining stock for a products variants, if any of the products has infinite inventory this will return `nil`

# product.schedule _(deprecated)_

Returns an array of the products [schedule elements]({% link docs/reference/objects/product/schedule_element.md %})

> **Deprecated**
>
> Use [`product.schedule_section`]({% link docs/reference/objects/product/index.md %}#productschedule_section) instead.

# product.schedule_section

Returns the schedule of the product [schedule section]({% link docs/reference/objects/product/schedule.md %})

# product.series

If the product is in a series this will return a [series object]({% link docs/reference/objects/series.md %})

# product.shop_path

Returns the path for the product's cart shop page.

# product.shop_url

Returns the url for the product's cart shop page.

# product.sold_out

Returns true if the product is sold out

# product.subcategory

Returns the subcategory the product belongs to

# product.tagline

Returns the tagline of the product

# product.testimonials

Returns an array of the product's [testimonials]({% link docs/reference/objects/product/testimonial.md %})

# product.transfers

Returns an array of the product's [transfers]({% link docs/reference/objects/product/transfer.md %})

# product.trip_tips

Returns an array of the product's [trip tips]({% link docs/reference/objects/product/trip_tip.md %})
# product.type

Returns the type of this product, one of `"experience"` or `"accommodation"`.

# product.url

Returns the url for the product's page in the site

# product.useful_info

Returns the product's [useful info]({% link docs/reference/objects/product/useful_info.md %})

# product.variants

Returns an array of the product's [variants]({% link docs/reference/objects/product/variant/index.md %}).

# product.variant_modifiers

Returns an array of all the [modifiers]({% link docs/reference/objects/product/modifier.md %}) associated with this product through its variants.

# product.venue

Returns the products [venue]({% link docs/reference/objects/product/venue.md %})

# product.whats_included

Return the product [whats_included]({% link docs/reference/objects/product/whats_included.md %})


<!--

Methods not publicly documented:

- base_resource_url

-->
