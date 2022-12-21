---
layout: default
title: Modifier selection session
parent: Objects
---

# Modifier selection session
{: .d-inline-block }
object
{: .label .fs-1 }

This drop is available on the post-checkout selection page as `item`.
It combines the data for a particular line item with the guest information for the customer currently logged in.

<br>

#### Attributes

## `item.id`
{: .d-inline-block }
string
{: .label .fs-1 }

The id of the line item.

## `item.title`
{: .d-inline-block }
string
{: .label .fs-1 }

The title of the line item.

## `item.start_on`
{: .d-inline-block }
timestamp
{: .label .fs-1 }

The start date of the line item.

## `item.end_on`
{: .d-inline-block }
timestamp
{: .label .fs-1 }

The end date of the line item.

## `item.guest_id`
{: .d-inline-block }
string
{: .label .fs-1 }

The guest id.

## `item.description`
{: .d-inline-block }
string
{: .label .fs-1 }

The title concatenated with the guest's name, if there is a guest.

## `item.guest_name`
{: .d-inline-block }
string
{: .label .fs-1 }

The name of the guest (or guest [some number] if no name is set yet).

## `item.product`
{: .d-inline-block }
[Product]({% link docs/reference/objects/product/index.md %})
{: .label .fs-1 }

The line item's parent product or the product itself.

## `item.variant`
{: .d-inline-block }
[Variant]({% link docs/reference/objects/product/variant/index.md %})
{: .label .fs-1 }

The variant attached to the line item.

## `item.selection_filters`
{: .d-inline-block }
array of [Selection filter]({% link docs/reference/objects/selection_filter.md %})s
{: .label .fs-1 }

Represents a group of filter options for this line item's variant to be used in the post-checkout selections UI on sites.

Example usage:

{% raw %}
```liquid
{% for filter in item.selection_filters %}
  <h3>{{ filter.name }}</h3>
  <ul>
    {% for option in filter.options %}
      <li {{ option.attributes }}>{{ option.name }}</li>
    {% endfor %}
  </ul>
{% endfor %}
```
{% endraw %}
