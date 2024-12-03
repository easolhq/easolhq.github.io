---
layout: default
title: Slot
parent: Experience Slot Calendar
grand_parent: Objects
---

# Slot
{: .d-inline-block }
object
{: .label .fs-1 }


*Note:* This is a slot accessed via [calendar `dates`]({% link docs/reference/objects/experience_slot_calendar/date.md %}). Not to be mistaken for an [`experience_slot`]({% link docs/reference/objects/product/experience_slot.md %}).

<br>

#### Attributes

## `slot.end_on`
{: .d-inline-block }
timestamp
{: .label .fs-1 }

The date the slot ends on. This can then be used in conjunction with Liquid's [built-in filters](https://shopify.github.io/liquid/filters/date/).

## `slot.end_time`
{: .d-inline-block }
string
{: .label .fs-1 }

The end time for this slot as a formatted time string in the current user's locale. For example, "11:00" for English or "11:00AM" for American English.

This will return `nil` if the experience does not have a start time.

## `slot.id`
{: .d-inline-block }
string
{: .label .fs-1 }

The ID of the experience slot.

## `slot.price`
{: .d-inline-block }
[price]({% link docs/reference/objects/product/price.md %})
{: .label .fs-1 }

The price of this variant on this slot in the current user's currency.

## `slot.product`
{: .d-inline-block }
[Product]({% link docs/reference/objects/product/index.md %})
{: .label .fs-1 }

The experience that this slot belongs to.

## `slot.remaining_stock`
{: .d-inline-block }
number
{: .label .fs-1 }

The remaining stock for this variant on this slot. It will return 0 if this variant on this slot is manually marked as 'Sold Out'. It will return `nil` if there is infinite stock.

## `slot.shop_url`
{: .d-inline-block }
string
{: .label .fs-1 }

The url for the cart shop page with this slot preselected.

## `slot.sold_out`
{: .d-inline-block }
boolean
{: .label .fs-1 }

This returns true if the variant is sold out on this slot.

## `slot.start_on`
{: .d-inline-block }
timestamp
{: .label .fs-1 }

The date the slot starts on. This can then be used in conjunction with Liquid's [built-in filters](https://shopify.github.io/liquid/filters/date/).

## `slot.start_time`
{: .d-inline-block }
string
{: .label .fs-1 }

The start time for this slot as a formatted time string in the current user's locale. For example, "11:00" for English or "11:00AM" for American English.

This will return `nil` if the experience does not have a start time.
