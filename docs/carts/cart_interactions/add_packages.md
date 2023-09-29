---
layout: default
title: Add a package
parent: Cart interactions
nav_order: 4
---

# Add a package to your cart

This form allows you to add a package to your cart. It will create a cart if one does not exist.
This will add all of the package's included items to the cart.
> If any of the items are sold out or the quanity of items being added is greater than the quantity available, the entire package will not be added to the cart.

## Form fields

| Field name                         | Description                                            |
| ---------------------------------- | ------------------------------------------------------ |
| `package[id]`                      | The ID of the package to add to the cart.              |
| `package[quantity]`                | The number of the packages to add to the cart at once. |
| `package[items][][id]`             | The ID of the package item for which to add modifiers. |
| `package[items][][modifier_ids][]` | The ID of the modifier to add to the cart.             |


##### syntax
{% raw %}

```liquid
{% form 'add_package_to_cart' %}
  <input name="package[id]" value="1" type="hidden" />
  <input name="package[quantity]" min="1" value="1" type="number" />
  <input type="submit" value="Add">
{% endform %}
```

{% endraw %}

### Modifications
Creators may choose to provide customers with additional modification options, such as the choice of a twin room or double room, or an entry time slot. Each modification should be included as an additional input on the add_package_to_cart form.

##### syntax
{% raw %}

```liquid
{% form 'add_package_to_cart' %}
  <input name="package[id]" value="1" type="hidden" />
  <input name="package[quantity]" min="1" value="1" type="number" />

  <h3>Package name</h3>
  {% for item in package.items %}
    <h4>{{item.variant.name}}</h4>
    <input type="hidden" name="package[items][][id]" value="{{item.id}}" />
    {% for group in item.variant.pre_checkout_modifier_groups %}
      <h4>{{item.variant.name}} - {{group.name}}</h4>

      {% for modifier in group.modifiers %}
        <label for="{{modifier.id}}">{{modifier.name}}</label>
        <input type="checkbox" id="{{modifier.id}}" name="package[items][][modifier_ids][]" value="{{modifier.id}}" />
      {% endfor %}
    {% endfor %}
  {% endfor %}

  <input type="submit" value="Add">
{% endform %}
```

{% endraw %}
> If a modification selection is required on a package item's variant and one is not specified on the form the entire package will not be added to the customer's cart.
