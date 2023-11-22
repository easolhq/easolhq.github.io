---
layout: default
title: Date
parent: Experience Slot Calendar
grand_parent: Objects
---

# Date
{: .d-inline-block }
object
{: .label .fs-1 }

#### Attributes

## `date.date`
{: .d-inline-block }
timestamp
{: .label .fs-1 }

The date.

## `date.display_price`
{: .d-inline-block }
[price]({% link docs/reference/objects/product/price.md %})
{: .label .fs-1 }

The display price for this date in the current user's currency.

This is determined by finding the cheapest variant that is available across the slots for this date. If an experience has defined a "display" variant, it will use the price of that variant and ignore prices of other variant from that experience.

The price used is the total price of the variant at its maximum occupancy, not the per person price, and promotions are not taken into consideration.

## `date.slot_count`
{: .d-inline-block }
number
{: .label .fs-1 }

The number of slots available on this date.

## `date.slots_by_variant`
{: .d-inline-block }
array of objects
{: .label .fs-1 }

This returns slot information grouped by variant. It will return an array of objects, each containing the following methods:

- `variant`{: .d-inline-block }
  [variant]({% link docs/reference/objects/product/variant/index.md %}){: .label .fs-1 }

- `slots`{: .d-inline-block }
  [array of slots]({% link docs/reference/objects/experience_slot_calendar/slot.md %}){: .label .fs-1 }


## `date.sold_out`
{: .d-inline-block }
boolean
{: .label .fs-1 }

This returns true if all variants are sold out across all slots on this date.
