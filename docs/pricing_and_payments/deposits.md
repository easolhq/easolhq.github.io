---
layout: default
title: Deposits
parent: Pricing & payments
---

# Deposits

For quick reference please see [Deposit]({% link docs/reference/objects/product/deposit.md %}).

Setting a deposit on a product allows customers to choose to pay a percentage of the total product price at the time of booking, and the remaining balance any time before the due date. 

A deposit is set at a product level and applies to all [variants]({% link docs/reference/objects/product/variant/index.md %}) and [extras]({% link docs/reference/objects/product/extra.md %}) of that product. It does not apply to [modifiers]({% link docs/reference/objects/product/modifier.md %}).

To display the deposit amount in Sites, note;

- Deposits can be set on both Experience and Accommodation product types, but cannot currently be displayed in Sites for Accommodation types. 
- If a promotion is applied, the deposit applies to the promotional price. 
- If the price is 0, `deposit.enabled` may return true, but it doesn't make sense to present a deposit price.
- If the due date has passed (or is today), the method `deposit.enabled` will return false, you don't need to check for this.

Check for the deposit at the product level:

{% raw %}
```liquid
{% if product.deposit.enabled and product.type != 'accommodation' %}
    {% assign deposit_active = true %}
    {% assign deposit_rate = product.deposit.rate %}
{% endif %}
```
{% endraw %}

`cheapest_price` in the following examples is the price with any promotions applied, this may be the full price or the promotional price in its fractional form.
See [promotions]({% link docs/pricing_and_payments/promotions.md%}) for more information on calculating this.

Display the deposit at the product level (i.e. only the featured variant):
{% raw %}
```liquid
<!-- calculate cheapest_price -->
{% assign deposit_price = cheapest_price | times: deposit_rate | money %}
{% if deposit_active == true and cheapest_price != 0 %}
    {% assign deposit_price = cheapest_price | times: deposit_rate | money %}

    <p>PAY ONLY {{ deposit_price }} DEPOSIT</p>

{% endif %}
```
{% endraw %}

When displaying a series summary, the approach is similar (i.e. only the featured variant of the series):
{% raw %}
```liquid
{% if series.featured_variant.product.deposit.enabled %}
    {% assign deposit_active = true %}
    {% assign deposit_rate = series.featured_variant.product.deposit.rate %}
{% endif %}
 <!-- calculate cheapest_price -->
{% if deposit_active == true and cheapest_price != 0 %}
    {% assign deposit_price = cheapest_price | times: deposit_rate | money %}

    <p>PAY ONLY {{ deposit_price }} DEPOSIT</p>

{% endif %}
```
{% endraw %}

You may wish to display the deposit amount for each variant or extra when looping through them:
{% raw %}
```liquid
{% for variant in product.variants %}
    <!-- calculate cheapest_price -->
    {% if deposit_active == true and cheapest_price != 0 %}
        {% assign deposit_price = cheapest_price | times: deposit_rate | money %}

        <p>PAY ONLY {{ deposit_price }} DEPOSIT</p>

    {% endif %}
{% endfor %}
```
{% endraw %}

By using the `series.featured_variant`, the resulting `deposit_price` may not be the cheapest deposit, however, it is the deposit for the cheapest variant.

Reminder: reset with {% raw %}`{% assign deposit_active = false %}`{% endraw %} when looping through products.
