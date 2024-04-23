---
layout: default
title: Package Step Item
parent: Package Step Product
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

Whether the item requires a slot selection.

## `item.available_slots_for_selection`
{: .d-inline-block }
Array of [Experience Slot]({% link docs/reference/objects/product/experience_slot.md %})s
{: .label .fs-1 }

The available experience slots for the item. This will only be present if `requires_slot_selection` is `true`.
