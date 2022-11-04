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

## Form tag parameters

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