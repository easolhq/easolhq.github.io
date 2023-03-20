---
layout: default
title: Variant
parent: Variable types
has_children: false
---

# Variant

Renders two select inputs from which a Creator can select a product and then a variant.

Returns a [Variant]({% link docs/reference/objects/product/variant/index.md %}) object.

- Accepts a `default` of `random` which will select a random variant from the Creator's published products.
- Has an optional `only_from` list, which supports restricting the product types. The allowed values are `experiences` and `accommodations`. If `only_from` is missing, it defaults to all types.
  `random` defaults will comply with these restrictions.

##### syntax
{% raw %}
```
---
my_variable:
    type: variant
    default: random
    only_from:
        - experiences
        - accommodations
---

{{ my_variable.name }}
```
{% endraw %}
