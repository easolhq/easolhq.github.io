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

This is determined by finding the cheapest variant that is available across the slots for this date, accounting for promotions.

The price used is the price of the variant at its maximum occupancy, not the per person price.

If an experience has a "display" variant defined, it will use the price of that variant and ignore prices of other variant from that experience.


## `date.experience`
{: .d-inline-block }
[product]({% link docs/reference/objects/product/index.md %})
{: .label .fs-1 }

The experience associated with this date. If the date is associated with multiple experiences, this will return the first one.

This is a convenience method to be used when you know there is only one single experience. If it's possible the date is associated with multiple experiences, `date.experiences` should be used instead.

## `date.experiences`
{: .d-inline-block }
array of [products]({% link docs/reference/objects/product/index.md %})
{: .label .fs-1 }

The experiences associated with this date.

## `date.initial_stock`
{: .d-inline-block }
number or nil
{: .label .fs-1 }

Sums the starting inventory for all slot-variant mappings on this date, unless any mapping is infinite (in which case it returns nil).

## `date.remaining_stock`
{: .d-inline-block }
number or nil
{: .label .fs-1 }

Sums the available inventory for all slot-variant mappings on this date, unless any mapping is infinite (in which case it returns nil). If any slot is marked as sold out, it is treated as having zero remaining stock.

## `date.slot_count`
{: .d-inline-block }
number
{: .label .fs-1 }

The total number of slots across all variants for this date. Note that this number does not represent available slots, but rather the total number of slots created on this date.

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
