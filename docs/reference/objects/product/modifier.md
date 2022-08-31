---
layout: default
title: Modifier
parent: Product
---

When using a `modifier` object you have access to the following attributes:

# modifier.id

Returns a unique ID for the modifier.

# modifier.checkbox_attributes

Returns a string of HTML attributes to be used on a checkbox for the modifier.

- The `checked` attribute is included if this modifer has been selected by the user. Currently used on the selections page.
- The `disabled` attribute is included if the modifier is sold out and not already selected.

{% raw %}
```
<input {{modifier.checkbox_attributes}}>
```
{% endraw %}

# modifier.contents

A list of [biographies]({% link docs/reference/objects/biography.md %}) that are associated with the modifier.

# modifier.custom_fields

A list of custom properties defined on this modifier. Each custom field has two methods: `key` and `value`.

{% raw %}
```liquid
<ul>
  {% for field in modifier.custom_fields %}
    <li>{{field.key}}: {{field.value}}</li>
  {% endfor %}
</ul>
```
{% endraw %}

# modifier.custom_fields_data

Returns an object containing the custom properties for the modifier.

{% raw %}
```
{{modifier.custom_fields_data.category}}
```
{% endraw %}

# modifier.data_attributes

Returns a string of HTML data attributes for the modifier, including `id`, `name` and if present, `start-at` and `end-at`. e.g.
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
<input {{modifier.checkbox_attributes}} {{modifier.data_attributes}}>
```
{% endraw %}

# modifier.end_at

The end time for this modifier.

{% raw %}
```liquid
{% modifier.end_at | date: "%d-%m-%Y %k:%M" %}
```
{% endraw %}

# modifier.filter_attributes

Returns a string of HTML data attributes representing the custom field key-value pairs that have been specified as filterable.

For example, a modifier with filterable custom fields and values "Category" and "Yoga", and "Difficulty" and "Hard" would end up with data attributes `data-category="Yoga"` and `data-difficulty="Hard"`.

The first attribute, `data-filter-target="filterable"` identifies the element to the filter controller and is always present.

This is useful for handling filtering of modifiers via Javascript.

# modifier.has_infinite_stock

Returns true if the modifier has unlimited stock.

# modifier.image

The modifier's [image]({% link docs/reference/objects/image.md %}).

# modifier.initial_stock

The initial stock for the modifier. If the modifier has unlimited inventory this will return `nil`.

# modifier.label_attributes

Returns a string of HTML attributes to be used on an input label for the modifier.

{% raw %}
```
<label {{modifier.label_attributes}}>{{modifier.name}}</label>
```
{% endraw %}

# modifier.name

The name of the modifier.

# modifier.price

The price of the modifier as a fractional in the sub-unit of the current user's currency.
e.g. considering the amount $19.50, it will return 1950.

# modifier.remaining_stock

The remaining stock for the modifier. If the modifier has unlimited inventory this will return `nil`.

# modifier.selected

Returns true if this modifer has been selected by the user. Currently used on the selections page.

# modifier.sold_out

Returns true if the modifier is sold out.

# modifier.start_at

The start time for this modifier.

{% raw %}
```liquid
{% modifier.start_at | date: "%d-%m-%Y %k:%M" %}
```
{% endraw %}

# modifier.tagline

The tagline of the modifier.