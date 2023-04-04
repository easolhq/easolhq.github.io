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

For recurring experiences each product drop is for a specific departure date. `product` defaults to the next upcoming date if there is one, or the first date if all dates are in the past.

#### Attributes

### Global

## `product.accommodations`
{: .d-inline-block }
array of [accommodation merchandise]({% link docs/reference/objects/product/accommodation_merchandise.md %})
{: .label .fs-1 }

An array of the products [accommodation merchandise fields]({% link docs/reference/objects/product/accommodation_merchandise.md %}).

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

## `product.country`
{: .d-inline-block }
string
{: .label .fs-1 }

The name of the country the product is based in.

## `product.all_dates`
{: .d-inline-block }
string
{: .label .fs-1 }

The dates of a recurring experience as a formatted string.
e.g. `November 2019` where all departure dates are in the same month.
e.g. `April - July 2023` where departure dates are across more than one month.
Called on any other type of product will return the same value as `.dates`

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

## `product.gallery`
{: .d-inline-block }
array of [Image]({% link docs/reference/objects/image.md %})s
{: .label .fs-1 }

An array of [Image]({% link docs/reference/objects/image.md %}) objects for the products gallery.

## `product.hero_image`
{: .d-inline-block }
[Image]({% link docs/reference/objects/image.md %})
{: .label .fs-1 }

The products hero [image]({% link docs/reference/objects/image.md %}).

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

The path for the product's cart shop page.

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

### Date specific

## `product.dates`
{: .d-inline-block }
string
{: .label .fs-1 }

The dates of the product as a formatted string.
e.g. `15 November 2019` for an experience with a duration of less than or equal to one day.
e.g. `15 - 20 November 2019` for an experience with a duration of more than one day.

## `product.depart_on`
{: .d-inline-block }
timestamp
{: .label .fs-1 }

If the product has fixed dates this returns the start date of the event as a timestamp, this can then be used in conjunction with Liquid's [built-in filters](https://shopify.github.io/liquid/filters/date/).
For an experience that is recurring this is the first upcoming departure date if there are any, or the first departure date if all dates are in the past. 

## `product.extras`
{: .d-inline-block }
array of [Extra]({% link docs/reference/objects/product/extra.md %})s
{: .label .fs-1 }

An array of the product's [extras]({% link docs/reference/objects/product/extra.md %})
If the product is a recurring experience this returns the extras from the next upcoming occurrence, or the first date if all dates are in the past.

## `product.featured_variant`
{: .d-inline-block }
[Variant]({% link docs/reference/objects/product/variant/index.md %})
{: .label .fs-1 }

The "featured" [variant]({% link docs/reference/objects/product/variant/index.md %}). This will be the display variant for this product or if none has been set, the variant with the cheapest per-person price, factoring in any promotions.
If the product is a recurring experience this is the featured variant of the first upcoming occurrence, or the first date if all dates are in the past.

## `product.has_infinite_stock`
{: .d-inline-block }
boolean
{: .label .fs-1 }

Returns `true` if any variant on the product has infinite stock.
If the product is a recurring experience this returns  `true` if any variant of the next upcoming occurrence has infinite stock.

## `product.has_active_promotion`
{: .d-inline-block }
boolean
{: .label .fs-1 }

Returns `true` if one of the [variants]({% link docs/reference/objects/product/variant/index.md %}) in the product has an active [promotion]({% link docs/reference/objects/product/promotion.md %}).
If the product is a recurring experience this returns  `true` if any variant of the next upcoming occurrence has an active promotion.

## `product.remaining_stock`
{: .d-inline-block }
number
{: .label .fs-1 }

The sum of remaining stock for a product's variants, if any of the variants have infinite inventory this will return `nil`.
If the product is a recurring experience this returns the remaining stock of the next upcoming occurrence.

## `product.shop_url`
{: .d-inline-block }
string
{: .label .fs-1 }

The url for the product's cart shop page.
If the product is a recurring experience this returns the url of the next upcoming occurrence.

## `product.sold_out`
{: .d-inline-block }
boolean
{: .label .fs-1 }

Returns `true` if the product is sold out.
If the product is a recurring experience this returns `true` if all variants of the next upcoming occurrence are sold out.

## `product.variants`
{: .d-inline-block }
array of [variant]({% link docs/reference/objects/product/variant/index.md %})s
{: .label .fs-1 }

An array of the product's [variants]({% link docs/reference/objects/product/variant/index.md %}).
If the product is a recurring experience this returns the variants from the next upcoming occurrence, or the first date if all dates are in the past.

## `product.variant_modifiers`
{: .d-inline-block }
array of [modifier]({% link docs/reference/objects/product/modifier.md %})s
{: .label .fs-1 }

An array of all the [modifiers]({% link docs/reference/objects/product/modifier.md %}) associated with this product through its variants.
If the product is a recurring experience this returns the modifiers from the next upcoming occurrence, or the first date if all dates are in the past.

<!--

Methods not publicly documented:

- base_resource_url

-->
