---
layout: default
title: Clear cart
parent: Cart interactions
nav_order: 3
---

# Clear the cart
You can give customers the option to clear all items from their cart. This is done by including a [clear_cart tag]({% link docs/reference/tags/form_tags/clear_cart/index.md %})

##### syntax
{% raw %}
```liquid
{% form "clear_cart" %}
	 <input type="submit" value="clear" />
 {% endform %}
```
{% endraw %}