---
layout: default
title: Pluralize
parent: Filters
grand_parent: Reference
---

# pluralize

Outputs the singular or plural version of a string based on a given number.

### Example:

{% raw %}
```liquid
<h1>{{ item_count }} {{ item_count | pluralize: 'item' }} in your cart</h1>
```
{% endraw %}

The above would result in `<h1>2 items in your cart</h1>` when `item_count` has the value of `2`.

This filter accepts a custom plural version as a param.

### Example:

{% raw %}
```liquid
<h1>{{ people_count }} {{ people_count | pluralize: 'person', 'users' }} in your venue</h1>
```
{% endraw %}

The above would result in `<h1>2 users in your venue</h1>` when `people_count` has the value of `2`.
