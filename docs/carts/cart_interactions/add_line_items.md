---
layout: default
title: Add line items
parent: Cart interactions
nav_order: 1
---

# Add line items to the cart
To add an item to a customer's cart you must include a [create_line_item tag]({% link docs/reference/tags/form_tags/create_line_item/create_line_item.md %})

##### syntax
{% raw %}
```liquid
{% for item in product.variants %}
    {% form "create_line_item" %}
        <input type="hidden" name="items[][variant_id]" value="{{item.id}}"/>
        <input type="submit" value="Add to cart" />
    {% endform %}
{% endfor %}
```
{% endraw %}

Additional inputs should be included as relevant:

### Quantity
To add more than one unit to a customer's cart you must include a quantity input.

##### syntax
{% raw %}
```liquid
{% form "create_line_item" %}
    <input type="hidden" name="items[][variant_id]" value="*<variant or extra id>*"/>
    <input type="hidden" name="items[][quantity]" value="*<quantity>*" />
    <input type="submit" value="Add to cart" />
{% endform %}
```
{% endraw %}

### Modifications
Creators may choose to provide customers with additional modification options, such as the choice of a twin room or double room, or an entry time slot. Each modification should be included as an additional input on the create_line_item form. 

##### syntax
{% raw %}
```liquid
{% form "create_line_item" %}
    <input type="hidden" name="items[][variant_id]" value="*<variant or extra id>*"/>
    <input type="hidden" name="items[][modifier_ids][]" value="*<modifier id>*" />
    <input type="submit" value="Add to cart" />
{% endform %}
```
{% endraw %}

> If a modification selection is required on a variant and one is not specified on the form the item will not be added to the customer's cart.

### Adult count
Per unit variants include a [`max_occupany`]({% link docs/reference/objects/product/variant/index.md %}) and [`min_occupancy`]({% link docs/reference/objects/product/variant/index.md %}), and the price of a variant may differ based on the occupancy.
To specify the adult count an additional input field is required, if no adult count is added the max occupancy will be set by default.

{% raw %}
```liquid
  <input type="hidden" name="items[][adult_count]" value="**<adult count>**" />
```
{% endraw %}