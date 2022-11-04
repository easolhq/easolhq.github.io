---
layout: default
title: Cart interactions
parent: Carts
has_children: true
nav_order: 3
---

# Cart interactions
Interactions with a customer's cart are enabled by including [form tags]({% link docs/reference/tags/index.md %}) in block or template code.

- [Add line items to the cart]({% link docs/carts/cart_interactions/add_line_items.md %})
- [Remove line items from the cart]({% link docs/carts/cart_interactions/remove_line_items.md %})
- [Clear the cart]({% link docs/carts/cart_interactions/clear_cart.md %})


## Additional form tag parameters

### `return_to` 
By default, when submitting a form a page reload is triggered and the customer is returned to the current page. To specify a different page for the customer to be sent to on form submit, pass a URL as the value of the `return_to` param.

##### syntax
{% raw %}
```liquid
{% form "clear_cart", return_to: '/home' %}
	<input type="submit" value="clear" />
{% endform %}
```
{% endraw %}

You can also pass the url as a variable:
##### syntax
{% raw %}
```liquid
{% assign url = '/my-page' %}
{% form "clear_cart", return_to: url %}
	<input type="submit" value="clear" />
{% endform %}
```
{% endraw %}