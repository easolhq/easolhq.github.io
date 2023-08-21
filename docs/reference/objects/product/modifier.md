---
layout: default
title: Modifier
parent: Product
grand_parent: Objects
---

# Modifier
{: .d-inline-block }
object
{: .label .fs-1 }


The modifier object will behave slightly differently depending on how it is accessed.
- When accessed through an [experience date]({% link docs/reference/objects/product/experience_date.md %}), some methods will return a result that is specific to that given date.
- When accessed independently or through a product, those methods will take into account all upcoming dates on the product.

Please check the method descriptions for more details.


#### Attributes

## `modifier.id`
{: .d-inline-block }
string
{: .label .fs-1 }

The unique ID for the modifier.

## `modifier.checkbox_attributes`
{: .d-inline-block }
html
{: .label .fs-1 }

A string of HTML attributes to be used on a checkbox for the modifier.

- The `checked` attribute is included if this modifier has been selected by the customer. Currently used on the selections page.
- The `disabled` attribute is included if the modifier is sold out and not already selected.

{% raw %}
```
<input {{ modifier.checkbox_attributes }}>
```
{% endraw %}

## `modifier.contents`
{: .d-inline-block }
array of [biographies]({% link docs/reference/objects/content_library.md %})
{: .label .fs-1 }

An array of [biographies]({% link docs/reference/objects/content_library.md %}) that are associated with the modifier.

## `modifier.custom_fields`
{: .d-inline-block }
array of key-value pairs
{: .label .fs-1 }

An array of custom properties defined on this modifier. Each custom field has two methods: `key` and `value`.

{% raw %}
```liquid
<ul>
  {% for field in modifier.custom_fields %}
    <li>{{ field.key }}: {{ field.value }}</li>
  {% endfor %}
</ul>
```
{% endraw %}

## `modifier.custom_fields_data`
{: .d-inline-block }
object
{: .label .fs-1 }

An object containing the custom properties for the modifier.

{% raw %}
```
{{ modifier.custom_fields_data.category }}
```
{% endraw %}

## `modifier.data_attributes`
{: .d-inline-block }
html
{: .label .fs-1 }

A string of HTML data attributes for the modifier, including `id`, `name` and if present, `start-at` and `end-at`. e.g.
```
[
  "data-modifier-id='076f47e9-7061-4c01-90a5-a36b1970ffe3'",
  "data-modifier-name='Parking'",
  "data-modifier-start-at='2023-04-25 00:00'",
  "data-modifier-end-at='2023-05-06 00:00'"
]
```

It can be used in the Liquid markup like this:

{% raw %}
```
<input {{ modifier.checkbox_attributes }} {{ modifier.data_attributes }}>
```
{% endraw %}

## `modifier.end_at`
{: .d-inline-block }
timestamp
{: .label .fs-1 }

The end time for this modifier.

{% raw %}
```liquid
{% modifier.end_at | date: "%d-%m-%Y %k:%M" %}
```
{% endraw %}

## `modifier.filter_attributes`
{: .d-inline-block }
html
{: .label .fs-1 }

A string of HTML data attributes representing the custom field key-value pairs that have been specified as filterable.

For example, a modifier with filterable custom fields and values "Category" and "Yoga", and "Difficulty" and "Hard" would end up with data attributes `data-category="Yoga"` and `data-difficulty="Hard"`.

The first attribute, `data-filter-target="filterable"` identifies the element to the filter controller and is always present.

This is useful for handling the filtering of modifiers via Javascript.

## `modifier.has_infinite_stock`
{: .d-inline-block }
boolean
{: .label .fs-1 }

Returns `true` if the modifier has unlimited stock.
- When accessed through an [experience date]({% link docs/reference/objects/product/experience_date.md %}), it will return `true` if the modifier has unlimited stock on the given date.
- When accessed independently or through a product, it will return `true` if the modifier has unlimited stock on at least one of the upcoming dates.

## `modifier.image`
{: .d-inline-block }
[Image]({% link docs/reference/objects/image.md %})
{: .label .fs-1 }

The modifier's [image]({% link docs/reference/objects/image.md %}).

## `modifier.initial_stock`
{: .d-inline-block }
number
{: .label .fs-1 }

The initial stock for the modifier. If the modifier has unlimited inventory this will return `nil`.
- When accessed through an [experience date]({% link docs/reference/objects/product/experience_date.md %}), it will return the initial stock for the modifier on the given date.
- When accessed independently or through a product, it will return the sum of the initial stock for the modifier across all upcoming dates.

## `modifier.label_attributes`
{: .d-inline-block }
html
{: .label .fs-1 }

A string of HTML attributes to be used on an input label for the modifier.

{% raw %}
```
<label {{ modifier.label_attributes }}>{{ modifier.name }}</label>
```
{% endraw %}

## `modifier.name`
{: .d-inline-block }
string
{: .label .fs-1 }

The name of the modifier.

## `modifier.price`
{: .d-inline-block }
number
{: .label .fs-1 }

The price of the modifier as a fractional in the sub-unit of the current customer's currency.
e.g. considering the amount $19.50, it will return 1950.
- When accessed through an [experience date]({% link docs/reference/objects/product/experience_date.md %}), it will return the price for the modifier on the given date.
- When accessed independently or through a product, it will return the default price for the modifier, managed in **Experience > Modifiers**.

## `modifier.remaining_stock`
{: .d-inline-block }
number
{: .label .fs-1 }

The remaining stock for the modifier. If the modifier has unlimited inventory this will return `nil`.
- When accessed through an [experience date]({% link docs/reference/objects/product/experience_date.md %}), it will return the remaining stock for the modifier on the given date.
- When accessed independently or through a product, it will return the sum total of remaining stock for the modifier across all upcoming dates.

## `modifier.selected`
{: .d-inline-block }
boolean
{: .label .fs-1 }

Returns `true` if this modifier has been selected by the customer. Currently used on the selections page.

## `modifier.sold_out`
{: .d-inline-block }
boolean
{: .label .fs-1 }

Returns `true` if the modifier is sold out.
- When accessed through an [experience date]({% link docs/reference/objects/product/experience_date.md %}), it will return `true` if the modifier is sold out on the given date.
- When accessed independently or through a product, it will return `true` if the modifier is sold out across all upcoming dates.

## `modifier.start_at`
{: .d-inline-block }
timestamp
{: .label .fs-1 }

The start time for this modifier.

{% raw %}
```liquid
{% modifier.start_at | date: "%d-%m-%Y %k:%M" %}
```
{% endraw %}

## `modifier.tagline`
{: .d-inline-block }
string
{: .label .fs-1 }

The tagline of the modifier.
