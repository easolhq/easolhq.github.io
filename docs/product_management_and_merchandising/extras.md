---
layout: default
title: Extras
parent: Product Management and Merchandising
nav_order: 6
---

For quick reference, see [Extras]({% link docs/reference/objects/product/extra.md %})

Extras are add-on items that can be sold with experiences, such as spa treatments, equipment hire or airport transfers. 

Some things to consider when displaying a product's extras;
- Extras have a stock level which is independent of any variant stock levels and can be purchased independently of the variants.
- You may wish to show the stock remaining on a variant with {% raw %}`extra.remaining_stock`{% endraw %}.
- Extras can be grouped into Segments. To display these, it's advisable to use the [group_by filter]({% link docs/reference/filters/group_by.md %}), e.g.
{% raw %}
```liquid
{% assign extra_groups = product.extras | group_by: "segment_name" | sort: "segment_name" %}
{% for group in extra_groups %}
    <h2>{{group.name}}</h2>
    <ul>
        {% for extra in group.items %}
             <li>{{extra.name}}</li>
        {% endfor %}
    </ul>
{% endfor %}
```
{% endraw %}

Might render:
{% raw %}
```html
<h2>Double Rooms</h2>
<ul>
    <li>Winter Wonderland Room</li>
    <li>Bears Den Room</li>
    <li>Log Cabin Room</li>
</ul>

<h2>Single Rooms</h2>
<ul>
    <li>Winter Wonderland Room</li>
    <li>Bears Den Room</li>
    <li>Log Cabin Room</li>
</ul>
```
{% endraw %}
