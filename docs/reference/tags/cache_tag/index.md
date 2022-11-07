---
layout: default
title: Cache
parent: Tags
grand_parent: Reference
has_children: false
---

The Cache tag caches its content and renders the result using the currency provided by the template register. 
The Cache tag assigns a unique key to avoid conflicts between blocks with identical params.

##### input
{% raw %}
```liquid
{% cache variant %}
    <h1>variant.min_price</h1>
{% endcache %}
```
{% endraw %}

##### output
{% raw %}
```html
<h1>£100</h1>
```
{% endraw %}

##### expiry

The cache clears every 30 minutes by default and refreshes on the next page load.
A custom expiry time can be set by passing in an `expires_in` argument and the time in seconds. 

The following example pased two variant keys sets an expiry time of 5 minutes: `expires_in: 300`

##### input
{% raw %}
```liquid
{% cache variant, variant.product, expires_in: 300 %}
   {{product.name}}
   {{variant.min_price}}
 {% endcache %}
```
{% endraw %}

# Extra Params

* `expires_in:` Passing an integer of seconds before the cache expires. 
* `cache keys` Any number of variables can be passed into the cache as keys.
