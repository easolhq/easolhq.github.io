---
layout: default
title: Product
parent: Variable types
---

# Product

Renders a select input from which a Creator can select a product.

Returns a [Product]({% link docs/reference/objects/product/index.md %}) object.

- Accepts a `default` of `random` which will select a random product from the Creator's published products.
- Has an optional `only` list, which supports restricting the product types. The allowed values are `experiences` and `accommodations`. If `only` is missing, it defaults to all types.
  `random` defaults will comply with these restrictions.

##### syntax
{% raw %}
```
---
my_variable:
    type: product
    default: random
    only:
        - experiences
        - accommodations
---

{{ my_variable.name }}
```
{% endraw %}
