---
layout: default
title: Experience Slot
parent: Product
has_children: false
---

# Experience Slot
{: .d-inline-block }
object
{: .label .fs-1 }

*Note:* Experience slots are returned as part of an [`experience_slot_search`]({% link docs/experience_slot_search/index.md %}) or when using the [`experience_slot` variable type]({% link docs/theme_architecture/blocks/schema/variables/variable_types/experience_slot.md %}). Not to be mistaken for a [calendar `slot`]({% link docs/reference/objects/experience_slot_calendar/slot.md %}).

<br>

#### Attributes

## `experience_slot.deposit`
{: .d-inline-block }
[Deposit]({% link docs/reference/objects/product/deposit.md %})
{: .label .fs-1 }

The [deposit]({% link docs/reference/objects/product/deposit.md %}) for this
slot's experience. The returned deposit will consider this slot's `start_on`
when determining if the deposit is enabled for use.

## `experience_slot.end_on`
{: .d-inline-block }
timestamp
{: .label .fs-1 }

The date the slot ends on. This can then be used in conjunction with Liquid's [built-in filters](https://shopify.github.io/liquid/filters/date/).

## `experience_slot.end_time`
{: .d-inline-block }
string
{: .label .fs-1 }

The end time for this slot as a formatted time string in the current user's locale. For example, "11:00" for English or "11:00AM" for American English.

This will return nil if the experience does not have a start time.

## `experience_slot.extras`
{: .d-inline-block }
array of [Extra]({% link docs/reference/objects/product/extra.md %})s
{: .label .fs-1 }

An array of the date's [extras]({% link docs/reference/objects/product/extra.md %}).

## `experience_slot.featured_variant`
{: .d-inline-block }
[Variant]({% link docs/reference/objects/product/variant/index.md %})
{: .label .fs-1 }

The "featured" [variant]({% link docs/reference/objects/product/variant/index.md %}). This will be the display variant for the date's product or if none has been set, the variant with the cheapest per-person price, factoring in any promotions.

## `experience_slot.humanized_date_range`
{: .d-inline-block }
string
{: .label .fs-1 }

The dates of the experience slot as a formatted string.
e.g. `15 November 2024` for an experience with a duration of less than or equal to one day.
e.g. `15 - 20 November 2024` for an experience with a duration of more than one day.

## `experience_slot.id`
{: .d-inline-block }
string
{: .label .fs-1 }

The experience slot id.

## `experience_slot.payment_plan`
{: .d-inline-block }
[Payment Plan]({% link docs/reference/objects/product/variant/payment_plan.md %})
{: .label .fs-1 }

Returns a [payment plan]({% link
docs/reference/objects/product/variant/payment_plan.md %}) if one is available
on this slot's experience and the last payment date is before the slot's
`start_on`.

## `experience_slot.product`
{: .d-inline-block }
[Product]({% link docs/reference/objects/product/index.md %})
{: .label .fs-1 }

The product that the date belongs to.

## `experience_slot.remaining_stock`
{: .d-inline-block }
number
{: .label .fs-1 }

The sum of remaining stock for a date's variants. If any of the variants have infinite stock this will return `nil`.

## `experience_slot.shop_url`
{: .d-inline-block }
string
{: .label .fs-1 }

The url for the date's cart shop page.

## `experience_slot.sold_out`
{: .d-inline-block }
boolean
{: .label .fs-1 }

Returns `true` if all stock for this date is sold out, i.e. all stock is sold or variants have been manually marked as 'Sold Out'. Any slot in the past is also considered sold out.

## `experience_slot.start_on`
{: .d-inline-block }
timestamp
{: .label .fs-1 }

The date the slot starts on. This can then be used in conjunction with Liquid's [built-in filters](https://shopify.github.io/liquid/filters/date/).

## `experience_slot.start_time`
{: .d-inline-block }
string
{: .label .fs-1 }

The start time for this slot as a formatted time string in the current user's locale. For example, "11:00" for English or "11:00AM" for American English.

This will return nil if the experience does not have a start time.

## `experience_slot.variants`
{: .d-inline-block }
array of [variant]({% link docs/reference/objects/product/variant/index.md %})s
{: .label .fs-1 }

An array of the slot's [variants]({% link docs/reference/objects/product/variant/index.md %}).
