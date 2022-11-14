---
layout: default
title: Cache
parent: Tags
grand_parent: Reference
---

# Cache

The `cache_tag` accepts an array of drops or keys as an argument which will be used to cache the entire contents of the tag. The cache tag assigns a unique key to avoid conflicts between blocks with identical params.

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

## Expiry

The cache clears every 30 minutes by default and refreshes on the next page load.
A custom expiry time can be set by passing in an `expires_in` argument and the time in seconds. 

The following example sets an expiry time of 5 minutes: `expires_in: 300`.

##### input
{% raw %}
```liquid
{% cache variant, variant.product, expires_in: 300 %}
   {{product.name}}
   {{variant.min_price}}
 {% endcache %}
```
{% endraw %}

## Cache keys
Any number of variables can be passed into the cache as keys. A change to one of these keys will invalidate the cache regardless of when the next expiry is due.