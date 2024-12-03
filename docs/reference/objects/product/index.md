---
layout: default
title: Product
parent: Objects
has_children: true
---

# Product
{: .d-inline-block }
object
{: .label .fs-1 }

#### Attributes

## `product.accommodations`
{: .d-inline-block }
array of [accommodation merchandise]({% link docs/reference/objects/product/accommodation_merchandise.md %})
{: .label .fs-1 }

An array of the product's [accommodation merchandise fields]({% link docs/reference/objects/product/accommodation_merchandise.md %}).

## `product.address`
{: .d-inline-block }
[address]({% link docs/reference/objects/product/address.md %})
{: .label .fs-1 }

The product [address]({% link docs/reference/objects/product/address.md %}).

## `product.blog_post_section`
{: .d-inline-block }
[blog post section]({% link docs/reference/objects/product/blog_post_section.md %})
{: .label .fs-1 }

The [blog post section]({% link docs/reference/objects/product/blog_post_section.md %}).

## `product.category`
{: .d-inline-block }
string
{: .label .fs-1 }

The category the product belongs to.

## `product.company`
{: .d-inline-block }
[Company]({% link docs/reference/objects/company.md %})
{: .label .fs-1 }

The company the product is associated with.

## `product.country`
{: .d-inline-block }
string
{: .label .fs-1 }

The name of the country the product is based in.

## `product.dates`
{: .d-inline-block }
string
{: .label .fs-1 }

The dates of the product as a formatted string.
e.g. `15 November 2024` for an experience with a duration of less than or equal to one day.
e.g. `15 - 20 November 2024` for an experience with a duration of more than one day.
If a product is an experience with multiple slots, this returns the range based on the depature dates, and does not account for the experience duration.
e.g. `November 2024` for an experience with multiple departure dates in the same month.
e.g. `November 2024 - January 2025` for an experience with multiple departure dates over more than one month.

## `product.depart_on`
{: .d-inline-block }
timestamp
{: .label .fs-1 }

- If the product has a fixed date this returns the start date of the event as a timestamp, this can then be used in conjunction with Liquid's [built-in filters](https://shopify.github.io/liquid/filters/date/).
- If the product is an experience with multiple slots, this returns the start date of the next upcoming or ongoing slot if there is one, or the start date of the most recent slot if all slots are in the past.

## `product.deposit`
{: .d-inline-block }
[deposit]({% link docs/reference/objects/product/deposit.md %})
{: .label .fs-1 }

The product [deposit]({% link docs/reference/objects/product/deposit.md %}).

## `product.display_variant`
{: .d-inline-block }
[Variant]({% link docs/reference/objects/product/variant/index.md %})
{: .label .fs-1 }

The products display variant if set in the admin.

## `product.duration`
{: .d-inline-block }
string
{: .label .fs-1 }

The duration of the product including duration unit e.g. `5 nights`.

## `product.enquire_only`
{: .d-inline-block }
boolean
{: .label .fs-1 }

Returns `true` if the product has been marked as Enquiry Only within the product payment settings

## `product.extras`
{: .d-inline-block }
array of [Extra]({% link docs/reference/objects/product/extra.md %})s
{: .label .fs-1 }

An array of the product's [extras]({% link docs/reference/objects/product/extra.md %})

## `product.facilities`
{: .d-inline-block }
array of strings
{: .label .fs-1 }
deprecated
{: .label .fs-1 .label-red .ml-0 .mt-0 }

An array of the product's facilities.

Deprecated, replaced with [`product.whats_included.included`]({% link docs/reference/objects/product/whats_included.md %}#whats_includedincluded).

## `product.faqs`
{: .d-inline-block }
array of [Faq]({% link docs/reference/objects/product/faq.md %})s
{: .label .fs-1 }

An array of the product's [faqs]({% link docs/reference/objects/product/faq.md %}).

## `product.featured_accommodations`
{: .d-inline-block }
array of [accommodation merchandise]({% link docs/reference/objects/product/accommodation_merchandise.md %})
{: .label .fs-1 }

An array of the products [accommodations]({% link docs/reference/objects/product/accommodation_merchandise.md %}) which are flagged as featured.

## `product.featured_variant`
{: .d-inline-block }
[Variant]({% link docs/reference/objects/product/variant/index.md %})
{: .label .fs-1 }

The "featured" [variant]({% link docs/reference/objects/product/variant/index.md %}). This will be the display variant for this product or if none has been set, the variant with the cheapest per-person price, factoring in any promotions.
If the product is an experience with multiple slots, this returns the display or cheapest variant across all upcoming slots.

## `product.gallery`
{: .d-inline-block }
array of [Image]({% link docs/reference/objects/image.md %})s
{: .label .fs-1 }

An array of [Image]({% link docs/reference/objects/image.md %}) objects for the products gallery.

## `product.has_infinite_stock`
{: .d-inline-block }
boolean
{: .label .fs-1 }
deprecated
{: .label .fs-1 .label-red .ml-0 .mt-0 }

Returns `true` if any variant on the product has infinite stock.
If a product is an experience with multiple slots, this returns `true` if any variant on any upcoming date has infinite stock.

Deprecated. Not being maintained as it's no longer used in Easol themes.

## `product.hero_image`
{: .d-inline-block }
[Image]({% link docs/reference/objects/image.md %})
{: .label .fs-1 }

The products hero [image]({% link docs/reference/objects/image.md %}).

## `product.has_active_promotion`
{: .d-inline-block }
boolean
{: .label .fs-1 }
deprecated
{: .label .fs-1 .label-red .ml-0 .mt-0 }

Returns `true` if one of the [variants]({% link docs/reference/objects/product/variant/index.md %}) in the product has an active [promotion]({% link docs/reference/objects/product/promotion.md %}).

Deprecated. Not being maintained as it's no longer used in Easol themes.

## `product.highlights`
{: .d-inline-block }
array of [highlight]({% link docs/reference/objects/product/highlight.md %})s
{: .label .fs-1 }

An array of the product's [highlights]({% link docs/reference/objects/product/highlight.md %}).

## `product.host`
{: .d-inline-block }
[Host]({% link docs/reference/objects/product/host.md %})
{: .label .fs-1 }
deprecated
{: .label .fs-1 .label-red .ml-0 .mt-0 }

The first product [host]({% link docs/reference/objects/product/host.md %}).

Deprecated, use [`product.host_section`]({% link docs/reference/objects/product/index.md %}#producthost_section) instead.

## `product.host_section`
{: .d-inline-block }
[Host section]({% link docs/reference/objects/product/host_section.md %})
{: .label .fs-1 }

The product [host section]({% link docs/reference/objects/product/host_section.md %}).

## `product.id`
{: .d-inline-block }
string
{: .label .fs-1 }

The product id.

## `product.includes_accommodation`
{: .d-inline-block }
boolean
{: .label .fs-1 }

Returns a boolean indicating whether or not the product includes accommodation or is just a ticket.

## `product.is_multi_slot_experience`
{: .d-inline-block }
boolean
{: .label .fs-1 }

Returns a boolean indicating whether or not the product is an experience with
multiple slots.

## `product.min_price`
{: .d-inline-block }
boolean
{: .label .fs-1 }
deprecated
{: .label .fs-1 .label-red .ml-0 .mt-0 }

Returns a humanized price for the product's cheapest configuration e.g. `$1,027 Per Person` or `$150 Per Night`.
This excludes Sold Out and Hidden variants.
If the display variant is changed within the product this will be used instead of the cheapest variant.

Deprecated, prices should be retrieved from the product's variants instead. `product.featured_variant` can be used to get the "featured" variant.

## `product.minimum_nights`
{: .d-inline-block }
number
{: .label .fs-1 }

If the product is an accommodation this will return the minimum number of nights the product can be booked for.

## `product.name`
{: .d-inline-block }
string
{: .label .fs-1 }

The name of the product.

## `product.overview`
{: .d-inline-block }
string
{: .label .fs-1 }

The overview of the product.

## `product.overview_image`
{: .d-inline-block }
[Image]({% link docs/reference/objects/image.md %})
{: .label .fs-1 }

The products overview [image]({% link docs/reference/objects/image.md %}).

## `product.remaining_stock`
{: .d-inline-block }
number
{: .label .fs-1 }

The sum of remaining stock for a product's variants. If any variants are manually marked as 'Sold Out', they will contribute 0 towards this value. If any of the variants have infinite stock this will return `nil`.
If the product is an experience with multiple slots, this returns the sum total of remaining stock for all variants across all upcoming slots.

## `product.schedule`
{: .d-inline-block }
array of [Schedule element]({% link docs/reference/objects/product/schedule_element.md %})s
{: .label .fs-1 }
deprecated
{: .label .fs-1 .label-red .ml-0 .mt-0 }

An array of the product's [schedule elements]({% link docs/reference/objects/product/schedule_element.md %}).

Deprecated, use [`product.schedule_section`]({% link docs/reference/objects/product/index.md %}#productschedule_section) instead.

## `product.schedule_section`
{: .d-inline-block }
[Schedule section]({% link docs/reference/objects/product/schedule_section.md %})
{: .label .fs-1 }

The product's [schedule section]({% link docs/reference/objects/product/schedule_section.md %}).

## `product.series`
{: .d-inline-block }
[Series]({% link docs/reference/objects/series.md %})
{: .label .fs-1 }

If the product is in a series this will return a [Series]({% link docs/reference/objects/series.md %}) object.

## `product.shop_path`
{: .d-inline-block }
string
{: .label .fs-1 }
deprecated
{: .label .fs-1 .label-red .ml-0 .mt-0 }

The path for the product's cart shop page.

Deprecated, please use [shop_url]({% link docs/reference/objects/product/index.md %}#shop_url)instead.

## `product.shop_url`
{: .d-inline-block }
string
{: .label .fs-1 }

The url for the product's cart shop page.

## `product.sold_out`
{: .d-inline-block }
boolean
{: .label .fs-1 }

Returns `true` if all of the product's variants are sold out.

A variant is sold out if all stock is sold, it has been manually marked as 'Sold Out', or all [slots]({% link docs/reference/objects/product/experience_slot.md %}) are in the past.

## `product.subcategory`
{: .d-inline-block }
string
{: .label .fs-1 }

The subcategory the product belongs to.

## `product.tagline`
{: .d-inline-block }
string
{: .label .fs-1 }

The tagline of the product.

## `product.testimonials`
{: .d-inline-block }
array of [Testimonial]({% link docs/reference/objects/product/testimonial.md %})s
{: .label .fs-1 }

An array of the product's [testimonials]({% link docs/reference/objects/product/testimonial.md %}).

## `product.transfers`
{: .d-inline-block }
array of [transfer]({% link docs/reference/objects/product/transfer.md %})s
{: .label .fs-1 }
deprecated
{: .label .fs-1 .label-red .ml-0 .mt-0 }

An array of the product's [transfers]({% link docs/reference/objects/product/transfer.md %}).

Deprecated, the product admin no longer contains transfer settings. Extras should be used instead.

## `product.trip_tips`
{: .d-inline-block }
array of [Trip tip]({% link docs/reference/objects/product/trip_tip.md %})s
{: .label .fs-1 }

An array of the product's [trip tips]({% link docs/reference/objects/product/trip_tip.md %}).

## `product.type`
{: .d-inline-block }
string
{: .label .fs-1 }

The type of this product, one of `"experience"` or `"accommodation"`.

## `product.upcoming_or_recent_slot`
{: .d-inline-block }
[experience slot]({% link docs/reference/objects/product/experience_slot.md %})
{: .label .fs-1 }

The product's next upcoming or ongoing [experience slot]({% link docs/reference/objects/product/experience_slot.md %}) if there are any.
If all dates are in the past, this returns the most recent date.

## `product.url`
{: .d-inline-block }
string
{: .label .fs-1 }

The url for the product's page on the site.

## `product.useful_info`
{: .d-inline-block }
[Useful info]({% link docs/reference/objects/product/useful_info.md %})
{: .label .fs-1 }

The product's [useful info]({% link docs/reference/objects/product/useful_info.md %}).

## `product.variants`
{: .d-inline-block }
array of [variant]({% link docs/reference/objects/product/variant/index.md %})s
{: .label .fs-1 }

An array of the product's [variants]({% link docs/reference/objects/product/variant/index.md %}).

## `product.variant_modifiers`
{: .d-inline-block }
array of [modifier]({% link docs/reference/objects/product/modifier.md %})s
{: .label .fs-1 }
deprecated
{: .label .fs-1 .label-red .ml-0 .mt-0 }

An array of [modifiers]({% link docs/reference/objects/product/modifier.md %}) associated with this product.
Deprecated, modifiers should be accessed through each [variant modifier group]({% link docs/reference/objects/product/variant/index.md %}#variantmodifier_groups) or [extra modifier group]({% link docs/reference/objects/product/extra.md %}#extramodifier_groups).

## `product.venue`
{: .d-inline-block }
[Venue]({% link docs/reference/objects/product/venue.md %})
{: .label .fs-1 }

The product's [venue]({% link docs/reference/objects/product/venue.md %}).

## `product.whats_included`
{: .d-inline-block }
[what's included]({% link docs/reference/objects/product/whats_included.md %})
{: .label .fs-1 }

The product's [`what's included`]({% link docs/reference/objects/product/whats_included.md %}).

<!--

Methods not publicly documented:

- base_resource_url

-->
