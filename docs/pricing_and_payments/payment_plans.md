---
layout: default
title: Payment Plans
parent: Pricing & Payments
---

For quick reference please see [Payment Plans]({% link docs/reference/objects/product/variant/payment_plan.md %}).

Setting a payment plan on a product allows customers to choose to pay in instalments. Creators must choose a number of monthly instalments to spread payment over. The initial payment is made at the time of booking and monthly due dates are set for the remaining instalments. The Creator may optionally set a fixed amount for the initial payment. 

In order to display the payment plan in Sites, note;

- Payment Plans are configured at a Product level, but you can check for payment plan details directly on Variant objects. 
- Payment Plans can be set on both Experience and Accommodation product types.
- If the price is 0 or if a promotion is applied and a fixed initial payment is set which is greater than the promotional price, `variant.payment_plan` may return true, but it doesn't make sense to present a payment plan option as being available. 
- If the last scheduled date of the payment plan would be after the product's start date,`variant.payment_plan` will return false, you don't need to check for this.

{% raw %}
```liquid

<!-- calculate lowest_price -->
{% assign has_payment_plan = variant.payment_plan %}

{% if has_payment_plan %}
    {% assign has_fixed_initial_payment = variant.payment_plan.is_initial_payment_fixed %}
    {% if has_fixed_initial_payment %}
        {% assign initial_payment = variant.payment_plan.initial_payment_amount_fractional | money %}
    {% else %}
        {% assign initial_payment = lowest_price | divided_by: variant.payment_plan.number_of_instalments | money %}
    {% endif %}

    <p>Pay just {{initial_payment}} today, and spread the remaining cost over {{variant.payment_plan.number_of_instalments | minus: 1 }} months</p>
{% endif %}
```
{% endraw %}

This might render:
{% raw %}
```html
   <p>Pay just £50 today, and spread the remaining cost over 5 months</p>
```
{% endraw %}
