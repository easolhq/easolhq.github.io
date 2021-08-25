---
layout: default
title: Footer Item
parent: Footer
---

When using a `item` object you have access to the following attributes
Can be accessed on the footer object as below

{% raw %}
```liquid
{% for item in footer.items %}    
    <a href="{{item.path}}">{{item.label}}</a>
{% endfor %}
```
{% endraw %}

# item.path

Returns the target url for the footer item

# item.label

Returns the label for the footer item
