---
layout: default
title: Clear cart
parent: Tags
grand_parent: Reference
---

# Clear cart

The `clear_cart` tag renders a button that clears the customer's cart. 

##### input
{% raw %}
```liquid
{% form "clear_cart" %}
	 <input type="submit" value="clear" />
 {% endform %}
```
{% endraw %}

##### output
{% raw %}
```html
<form action="/sites/cart" data-form-action="clear_cart" accept-charset="UTF-8" method="post">
    <input type="hidden" name="_method" value="delete" autocomplete="off">
    <input type="hidden" name="return_to" id="return_to" value="https://www.creator-website.com/book-tickets" autocomplete="off">
    <input type="submit" value="Clear">
</form>
```
{% endraw %}


## Extra parameters

### return_to

The `clear_cart` tag will reload the customer's current page by default on form submit.
To direct a customer to a different page you can pass a URL as the value of the `return_to:` param.

The following example redirects to the homepage.

##### input
{% raw %}
```liquid
{% form "clear_cart", return_to: '/' %}
	 <input type="submit" value="clear" />
 {% endform %}
```
{% endraw %}
