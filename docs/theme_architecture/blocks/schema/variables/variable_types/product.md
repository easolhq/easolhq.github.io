---
layout: default
title: Product
parent: Variable types
---

# Product

Renders a select input from which a Creator can select a product.
Returns a [Product]({% link docs/reference/objects/product/index.md %}) object.
The product variable only accepts a default of `random` which will select a random product from the Creator's published products.

##### syntax
{% raw %}
```
---
my_variable:
    type: product
    default: random
---

{{my_variable.name}}
```
{% endraw %}