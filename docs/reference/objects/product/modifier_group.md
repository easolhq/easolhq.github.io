---
layout: default
title: Modifier group
parent: Product
grand_parent: Objects
---

# Modifier group
{: .d-inline-block }
object
{: .label .fs-1 }

#### Attributes

## `modifier_group.id`
{: .d-inline-block }
string
{: .label .fs-1 }

The unique id of the modifier group.

## `modifier_group.max_selection`
{: .d-inline-block }
number
{: .label .fs-1 }

The maximum number of modifiers that can be selected in this group.

## `modifier_group.min_selection`
{: .d-inline-block }
number
{: .label .fs-1 }

The minimum number of modifiers that need to be selected in this group.

## `modifier_group.modifiers`
{: .d-inline-block }
array of [modifier]({% link docs/reference/objects/product/modifier.md %})s
{: .label .fs-1 }

A list of the [modifiers]({% link docs/reference/objects/product/modifier.md %}) in this group.

## `modifier_group.name`
{: .d-inline-block }
string
{: .label .fs-1 }

The name of the modifier group.

## `modifier_group.rules_validation_message`
{: .d-inline-block }
string
{: .label .fs-1 }

The validation message to be shown if an incorrect number of modifiers have been selected.

## `modifier_group.tagline`
{: .d-inline-block }
string
{: .label .fs-1 }

The tagline of the modifier group. This is labelled 'Help text for customer' in the Creator Admin.
