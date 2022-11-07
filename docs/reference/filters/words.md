---
layout: default
title: Words
parent: Filters
grand_parent: Reference
---

# to_sentence

This is a helper to create listing sentences based on the provided array of strings.

For instance, say we have 3 products named "surf", "yoga" and "beer" respectively.

We can use the native `map` filter to get the product names into a list that can then be passed into `to_sentence` as follows:

{% raw %}
```liquid
{{ products | map: 'name' | to_sentence }}
```
{% endraw %}

The above would result in the string "surf, yoga and beer".
