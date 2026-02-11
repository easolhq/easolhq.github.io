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
| `package[start_date]`              | The customers selected start date for the package. (Only required if packages.requires_date is true)|
| `package[start_time]`              | The customers selected start time for the package. (optional)|
| `package[adult_count]`             | The number of adults for the package. (Only available for flexible adult count packages)|
| `package[items][][id]`             | The ID of the package item for which to add modifiers. |
| `package[items][][modifier_ids][]` | The ID of the modifier to add to the cart.             |


##### syntax
{% raw %}

```liquid
{% form 'add_package_to_cart' %}
  <input name="package[id]" value="1" type="hidden" />
  <input name="package[quantity]" min="1" value="1" type="number" />
  <input name="package[start_date]" type="date" />
  <input name="package[start_time]" type="time" />
  <input name="package[adult_count]" type="number" />
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

### Forwarding params to the booking journey

You can forward date selections to the package booking template by including hidden inputs under the `step_params` namespace. These values will be appended as query params on the redirect to the first step of the booking journey, making them accessible via `page.params` in the package booking template.

| Field name                  | Description                                                           |
| --------------------------- | --------------------------------------------------------------------- |
| `step_params[start_date]`   | A start date to forward as a query param to the step page URL.        |
| `step_params[end_date]`     | An end date to forward as a query param to the step page URL.         |

Only `start_date` and `end_date` are supported. Any other keys are ignored.

##### syntax
{% raw %}

```liquid
{% form 'add_package_to_cart' %}
  <input name="package[id]" value="{{ package.id }}" type="hidden" />
  <input name="step_params[start_date]" value="2025-06-15" type="hidden" />
  <input name="step_params[end_date]" value="2025-06-20" type="hidden" />
  <input type="submit" value="Add">
{% endform %}
```

{% endraw %}

The values are then available in the package booking template via the [`page.params`]({% link docs/reference/objects/page.md %}#pageparams) object:

{% raw %}

```liquid
{{ page.params.start_date }}
{{ page.params.end_date }}
```

{% endraw %}
