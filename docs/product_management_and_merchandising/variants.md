---
layout: default
title: Variants
parent: Product management and merchandising
nav_order: 5
---

# Variants

Variants are the varieties of what is being sold. Creators must have at least one variant of an experience e.g. "Ticket", but often have several e.g. "VIP Ticket", "Standard Adult Ticket", "Child Ticket", etc.

Some things to consider when displaying a product's variants:
- If a published experience has no variants, or all variants are hidden, i.e. {% raw %}`product.variants.size == 0`{% endraw %} this product is in a state that Easol themes display as 'Coming Soon'.
- If a variant has sold its stock, been manually marked as 'Sold Out', or all [slots]({% link docs/reference/objects/product/experience_slot.md %}) are in the past, i.e. {% raw %}`variant.sold_out == true`{% endraw %}, the variant is sold out. The product is sold out when all variants are sold out and {% raw %}`product.sold_out == true`{% endraw %}.
- You may wish to show the stock remaining on a variant with {% raw %}`variant.remaining_stock`{% endraw %}.
- Variants can be grouped into Segments. To display these, it's advisable to use the [group_by filter]({% link docs/reference/filters/group_by.md %}), e.g.
{% raw %}
```liquid
{% assign variant_groups = product.variants | group_by: "segment_name" | sort: "segment_name" %}
{% for group in variant_groups %}
    <h2>{{ group.name }}</h2>
    <ul>
        {% for variant in group.items %}
             <li>{{ variant.name }}</li>
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
