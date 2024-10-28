---
layout: default
title: Package Step Item
parent: Package Product
---

# Package Step Item
{: .d-inline-block }
object
{: .label .fs-1 }

Represents a single item in a [package step]({% link docs/reference/objects/package/step.md %}).

<br>

#### Attributes


## `item.variant`
{: .d-inline-block }
[Variant]({% link docs/reference/objects/product/variant/index.md %})
{: .label .fs-1 }

The variant for the item.

## `item.requires_slot_selection`
{: .d-inline-block }
boolean
{: .label .fs-1 }

Whether the item requires the customer to select a slot.

## `item.available_slots_for_selection`
{: .d-inline-block }
Array of [Experience Slot]({% link docs/reference/objects/product/experience_slot.md %})s
{: .label .fs-1 }

If the item requires the customer to select a slot, this will return an array of available experience slots. If the item does not require the customer to select a slot, this will return an array with a single experience slot.

In the event that there are no available slots, the array will be empty.

