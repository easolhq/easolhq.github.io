---
layout: default
title: Filters
has_children: true
nav_order: 10
---

# Filters

Liquid filters modify Liquid output. They can be applied to any liquid output and may accept parameters.

{% raw %}
```liquid
{{ product.name | remove: "!" }}
```
{% endraw %}


For documentation on Liquid's built-in filters, see [Liquid Filters](https://shopify.github.io/liquid/basics/introduction/#filters).

For reference to key filters, see [filters]({% link docs/reference/filters/index.md %}).
