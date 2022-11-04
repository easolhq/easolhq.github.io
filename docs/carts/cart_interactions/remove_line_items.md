---
layout: default
title: Remove line items
parent: Cart interactions
nav_order: 2
---

# Remove line items from the cart
You can give customers the option to remove a line item from their cart. This is done by including a [remove_line_item tag]({% link docs/reference/tags/form_tags/remove_line_item/index.md %})

##### syntax
{% raw %}
```liquid
{% for item in cart.items %}
    {% form 'remove_line_item' %}
        <!-- line item info -->
        <input name="items[]" value="{{item.id}}" type="hidden" />
        <input type="submit" value="Remove" />
    {% endform %}
{% endfor %}
```
{% endraw %}