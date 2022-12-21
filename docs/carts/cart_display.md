---
layout: default
title: Displaying carts
parent: Carts
nav_order: 2
---

# Displaying a customer's cart

## The Cart object
A [Cart]({% link docs/reference/objects/cart/index.md %}) object represents the experience that a customer intends to book and the costs associated with the cart.

The prices can be formatted in the customer's currency by applying the [money filter]({% link docs/reference/filters/money.md %}) to the price.

##### syntax
{% raw %}
```
SUBTOTAL: {{ cart.subtotal | money }}

DISCOUNT: {{ cart.total_price_reduction | money }}
BOOKING FEE: {{ cart.total_fee | money }}

TOTAL: {{ cart.total | money }}

Pay with a deposit of {{ cart.total_deposit | money }} or with a first instalment of {{ cart.first_instalment_amount | money }}.
```
{% endraw %}

## Cart line items
A [cart item]({% link docs/reference/objects/cart/cart_item.md %}) is a single line in a customer's cart that records which variant of an experience was added, the associated quantity, dates, adult count and modifications.

> If two of the same item are added to the cart, but have unique line item properties, then they’ll be split into separate line items.

A breakdown of the items in a customer's cart can be displayed by looping through the items.

##### syntax
{% raw %}
```
{% for item in cart.items %}
    {{ item.quantity }}x {{ item.variant_name }}
    {% if item.adult_count %}
        {{ item.adult_count }} {% if item.adult_count == 1 %}person{% else %}people{% endif %}
    {% endif %}
{% endfor %}
```
{% endraw %}

Creators may choose to provide customers with additional modification options, such as the choice of a twin room or double room, or an entry time slot. These may also incur an additional cost. These can be accessed via the [Selections]({% link docs/reference/objects/cart/modifier_selection.md %}) object on a cart item.

##### syntax
{% raw %}
```
{% for item in cart.items %}
    {{ item.quantity }}x {{ item.variant_name }}
    {% if item.adult_count %}
        {{ item.adult_count }} {% if item.adult_count == 1 %}person{% else %}people{% endif %}
    {% endif %}
    {% for selection in item.selections %}
        {{ selection.modifier_name }}
        {{ selection.price | money }}
    {% endfor %}
{% endfor %}
```
{% endraw %}

## Proceed to checkout
A Creator's checkout can be found at `/checkout`.