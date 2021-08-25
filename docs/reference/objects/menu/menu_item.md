---
layout: default
title: Item
parent: Menu
---
When using a `item` object you have access to the following attributes
Can be accessed on the menu object as below

{% raw %}
```liquid
{% for item in menu.items %}    
    <a href="{{item.path}}">{{item.label}}</a>
{% endfor %}
```
{% endraw %}

# item.path

Returns the target url for the menu item

# item.label

Returns the label for the menu item

