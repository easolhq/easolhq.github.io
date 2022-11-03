---
layout: default
title: Per Person, Per Unit, Per Night
parent: Pricing & Payments
---

For quick reference please see [Variant]({% link docs/reference/objects/product/variant/index.md %}).

Product variants can be priced per person or per unit (experience type products) or per night (accommodation products).

You can check which type a product or variant is with either `product.type` which returns one of "experience" or "accommodation" or `variant.type` which returns one of "experience_variant" or "accommodation_variant".

## Experience Products

If `variant.is_priced_per_person` returns true if it is a per person variant, and false if it is a per unit variant. 

### Per person
Per person pricing is very straight forward to display;
{% raw %}
```liquid
{% assign full_price = variant.price.fractional | money %}
```
{% endraw %}

### Per unit
Per unit pricing is still approached from a 'per person' perspective. 
The creator sets a per person price, along with a minimum and maximum occupancy, so the full price of the unit is;
{% raw %}
```liquid
{% assign full_price = variant.max_occupancy | times: variant.price.fractional | money %}
```
{% endraw %}

Per unit variants can have [pricing tiers]({% link docs/guides/pricing_and_payments/price_tiers_and_occupancy.md %}).

## Accommodation Products

### Per night
For per night pricing the Creator sets a per night price, along with a minimum and maximum occupancy. With just this basic configuration, the standard full price for a night is;
{% raw %}
```liquid
{% assign full_price = variant.price.fractional | money %}
```
{% endraw %}

The Creator can make two further configurations to per night pricing.

#### Price Override
The standard price per night may have an override applied to any particular date. 

In order to access these prices on the frontend, you need to use the [accommodation availability tag]({% link docs/reference/tags/accommodation_availability_tag/index.md %}).

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

If there was a price override on 7th November, this might render something like:

{% raw %}
```html
<p>On Nov 06, 23</p>
<p>The price for 1 adult(s) is $300.00</p>
<p>The price for 2 adult(s) is $300.00</p>
<p>The price for 3 adult(s) is $300.00</p>
<p>The price for 4 adult(s) is $300.00</p>
<p>The price for 5 adult(s) is $300.00</p>
<p>On Nov 07, 23</p>
<p>The price for 1 adult(s) is $500.00</p>
<p>The price for 2 adult(s) is $500.00</p>
<p>The price for 3 adult(s) is $500.00</p>
<p>The price for 4 adult(s) is $500.00</p>
<p>The price for 5 adult(s) is $500.00</p>
```
{% endraw %}

#### Per guest discount
A per guest discount is a discount for customers booking accommodation where they will not be making full use of the maximum occupancy. It is cumulative for each missing occupant i.e. a 5 person room, priced at $300 per night, with a $20 per guest discount would cost;

| Adult count | Price per night |
|:------------|:----------------|
| 5           | $300            |
| 4           | $280            |
| 3           | $260            |
| 2           | $240            |
| 1           | $220            |

In order to access these prices on the frontend, you need to use the [accommodation availability tag]({% link docs/reference/tags/accommodation_availability_tag/index.md %}).

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

If there was a per guest discount on 7th November, this might render something like:

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