---
layout: default
title: Experience variant
parent: Variant
grand_parent: Product
---

# Experience variant
{: .d-inline-block }
object
{: .label .fs-1 }

The `experience_variant` object will inherit all attributes defined on
the [Variant]({% link docs/reference/objects/product/variant/index.md %}) object, plus
it has access to the following attributes.

<br>

#### Attributes

## `experience_variant.deposit`
{: .d-inline-block }
[Deposit]({% link docs/reference/objects/product/deposit.md %})
{: .label .fs-1 }

The [deposit]({% link docs/reference/objects/product/deposit.md %}) of this
experience variant if there's a deposit present on the product. If the
experience variant is accessed through an [experience slot]({% link
docs/reference/objects/product/experience_slot.md %}), the deposit will consider
its availability on that specific slot, otherwise it will consider the last
available slot's `start_on`.

## `experience_variant.payment_plan`
{: .d-inline-block }
[Payment Plan]({% link docs/reference/objects/product/variant/payment_plan.md %})
{: .label .fs-1 }

The same as [variant]({% link
docs/reference/objects/product/variant/index.md %}) `deposit` method
with the caveat that if the experience variant is accessed through an
[experience slot]({% link docs/reference/objects/product/experience_slot.md
%}), a [payment plan]({% link
docs/reference/objects/product/variant/payment_plan.md %}) will only be
returned if the last payment date is before the slot's `start_on`.

## `experience_variant.type`
{: .d-inline-block }
string
{: .label .fs-1 }

Will return `experience_variant`.

