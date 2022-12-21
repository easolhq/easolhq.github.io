---
layout: default
title: Variant
parent: Variable types
has_children: false
---

# Variant

Renders a select input from which a Creator can select a product variant.
Returns a [Variant]({% link docs/reference/objects/product/variant/index.md %}) object.
The variant variable only accepts a default of `random` which will select a random variant from the Creator's published products.

##### syntax
{% raw %}
```
---
my_variable:
    type: variant
    default: random
---

{{ my_variable.name }}
```
{% endraw %}