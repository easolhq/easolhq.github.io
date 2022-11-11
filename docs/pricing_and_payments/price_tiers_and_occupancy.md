---
layout: default
title: Price tiers and occupancy
parent: Pricing & payments
---

# Price tiers and occupancy

## Price tiers

[Per unit variants]({% link docs/pricing_and_payments/per_person_unit_or_night.md%}) may have pricing tiers applied. 

The variant method `.prices` will return an array containing the prices of each tier. So to display all pricing tiers you would loop through these;

E.g.
{% raw %}
```liquid
<h4>{{variant.name}}</h4>
 {% for tiered_price in variant.prices %}
    <p>The price for {{ tiered_price.occupancy }} adult(s) is {{ tiered_price.fractional | money }}</p>
{% endfor %}
```
{% endraw %}

This might render:

{% raw %}
```html
<h4>Hot Air Balloon Ride</h4>
<p>The price for 1 adult(s) is $230.00</p>
<p>The price for 2 adult(s) is $250.00</p>
<p>The price for 3 adult(s) is $300.00</p>
```
{% endraw %}

## Occupancy

[Per night variants]({% link docs/pricing_and_payments/per_person_unit_or_night.md%}) may have price reductions applied based on occupancy, sometimes called a per guest discount.

It is cumulative for each missing occupant i.e. a 5 person room, priced at $300 per night, with a $20 per guest discount would cost;

| Adult count | Price per night |
|:------------|:----------------|
| 5           | $300            |
| 4           | $280            |
| 3           | $260            |
| 2           | $240            |
| 1           | $220            |


To display occupancy-based pricing, you need to use the [accommodation availability tag]({% link docs/reference/tags/accommodation_availability_tag/index.md %}).

E.g.
{% raw %}
```liquid
 {% accommodation_availability variant %}
    {% for day in result.days %}
        <p>On {{day.date | date:"%b %d, %y"}}</p>
        {% for price in day.prices %}
            <p>The price for {{ price.occupancy }} adult(s) is {{ price.fractional | money }}</p>
        {% endfor %}
    {% endfor %}
{% endaccommodation_availability %}
```
{% endraw %}

If the standard price was $300 per night and a per guest discount of $20 was applied on 7th November, this would render:

{% raw %}
```html
<p>On Nov 06, 23</p>
<p>The price for 1 adult(s) is $300.00</p>
<p>The price for 2 adult(s) is $300.00</p>
<p>The price for 3 adult(s) is $300.00</p>
<p>The price for 4 adult(s) is $300.00</p>
<p>The price for 5 adult(s) is $300.00</p>
<p>On Nov 07, 23</p>
<p>The price for 1 adult(s) is $220.00</p>
<p>The price for 2 adult(s) is $240.00</p>
<p>The price for 3 adult(s) is $260.00</p>
<p>The price for 4 adult(s) is $280.00</p>
<p>The price for 5 adult(s) is $300.00</p>
```
{% endraw %}
