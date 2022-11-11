---
layout: default
title: Clear Cart
parent: Tags
grand_parent: Reference
has_children: false
---

The Clear Cart Tag renders a button that clears the user's cart. 

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
<form action="/sites/cart" accept-charset="UTF-8" method="post">
    <input type="hidden" name="_method" value="delete" autocomplete="off">
    <input type="hidden" name="return_to" id="return_to" value="https://www.creator-website.com/book-tickets" autocomplete="off">
    <input type="submit" value="Clear">
</form>
```
{% endraw %}

##### redirect
The Clear Cart Tag will redirect to the user's current page by default.
See the `return_to:` param to customise.

##### Extra Params
* `return_to:` To specify the redirect location, pass a URL as the value of the return_to: param.
The following example redirects to the homepage.

##### input
{% raw %}
```liquid
{% form "clear_cart", return_to: '/home' %}
	 <input type="submit" value="clear" />
 {% endform %}
```
{% endraw %}
