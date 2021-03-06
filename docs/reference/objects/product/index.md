---
layout: default
title: Product
parent: Objects
has_children: true
---

When using a `product` object you have access to the following attributes

# product.accommodations

Returns an array of the products [accommodations]({% link docs/reference/objects/product/accommodation.md %})

# product.address

Returns the product [address]({% link docs/reference/objects/product/address.md %})

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

# product.facilities 

Returns an array of the products facilities
_Deprecated please use _[`whats_included.included`]({% link docs/reference/objects/product/whats_included.md %}#whats_includedincluded)

# product.has_infinite_stock

Returns true if the product has infinite stock

# product.hero_image

Returns the products hero [image]({% link docs/reference/objects/image.md %})

# product.faqs

Returns an array of the products [faqs]({% link docs/reference/objects/product/faq.md %})

# product.featured_accommodations

Returns an array of the products [accommodations]({% link docs/reference/objects/product/accommodation.md %}) which are flagged as featured

# product.gallery

Returns an array of [image objects]({% link docs/reference/objects/image.md %}) for the products gallery

# product.has_active_promotion

Returns true if one of the [variants]({% link docs/reference/objects/product/variant.md %}) in the product has an active [promotion]{% link docs/reference/objects/product/promotion.md %})

# product.highlights

Returns an array of the products [highlights]({% link docs/reference/objects/product/highlight.md %})

# product.host [ Deprecated, see product.host_section ]

Returns the products [host](https://app.gitbook.com/@fixers/s/canvas-developer/~/edit/drafts/-Lqg456H1ILVvLu_Ti3G/objects/product/host)
Deprecated please use [`hosts`](https://app.gitbook.com/@fixers/s/canvas-developer/~/drafts/-Lqg456H1ILVvLu_Ti3G/primary/objects/product#product-hosts)

# product.host_section

Returns the product [host section]({% link docs/reference/objects/product/host.md %})

# product.id

Returns the product id

# product.includes_accommodation

Returns a boolean indicating whether or not the product includes accommodation or is just a ticket

# product.min_price

Returns a humanized price for the products cheapest configuration e.g. `$1,027 Per Person` or `$150 Per Night`
This excludes Sold Out and Hidden variants.
 If the display variant is changed within the product this will be used instead of the cheapest variant

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

# product.schedule [ Deprecated, see product.schedule_section ]

Returns an array of the products [schedule elements]({% link docs/reference/objects/product/schedule_element.md %})

# product.schedule_section

Returns the schedule of the product [schedule section]({% link docs/reference/objects/product/schedule.md %})

# product.series

If the product is in a series this will return a [series object]({% link docs/reference/objects/series.md %})

# product.shop_path

Returns the url for the product's cart shop page

# product.sold_out

Returns true if the product is sold out

# product.subcategory

Returns the subcategory the product belongs to

# product.tagline

Returns the tagline of the product

# product.testimonials

Returns an array of the products [testimonials]({% link docs/reference/objects/product/testimonial.md %})

# product.trip_tips

Returns an array of the products [trip tips]({% link docs/reference/objects/product/trip_tip.md %})

# product.url

Returns the url for the product's page in the site  

# product.useful_info

Returns the product's [useful info]({% link docs/reference/objects/product/useful_info.md %})

# product.variants

Returns an array of the products [variants]({% link docs/reference/objects/product/variant.md %}).

# product.venue

Returns the products [venue]({% link docs/reference/objects/product/venue.md %})

# product.whats_included

Return the product [whats_included]({% link docs/reference/objects/product/whats_included.md %})

