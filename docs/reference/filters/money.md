---
layout: default
title: Money
parent: Filters
---

# money

This filter will return a formatted price in the user's currency. It expects an integer of the price as a fractional in the sub-unit of the currency. e.g. `7500` for the price of `£75`

##### input
{% raw %}
```liquid
  <h1>{{ 150 | money }}</h1>
```
{% endraw %}

##### output
Assuming the user's currency is GBP

{% raw %}
```html
  <h1>£1.50</h1>
```
{% endraw %}

# apply_promotion

This filter will return the discounted version of a given [price]({% link docs/reference/objects/product/price.md %}) when a [promotion]({% link docs/reference/objects/product/promotion.md %}) is applied. It will return a [price]({% link docs/reference/objects/product/price.md %}) object.

##### input
{% raw %}
```liquid
  {% assign reduced_price = price | apply_promotion: promotion %}
  <h1>{{ reduced_price.fractional }}</h1>
```
{% endraw %}

##### output
Assuming an initial price of `120.00` and a percentage discount of `25%`

{% raw %}
```html
  <h1>9000</h1>
```
{% endraw %}

# extract_money_decimal

This filter can be used to extract the numerical value from a price string.

##### input
{% raw %}
```liquid
  <h1>{{ '$1,020.89/pp'' | extract_money_decimal }}</h1>
```
{% endraw %}

##### output

{% raw %}
```html
  <h1>1020.89</h1>
```
{% endraw %}


