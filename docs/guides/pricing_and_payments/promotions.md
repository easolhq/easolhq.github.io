---
layout: default
title: Promotions
parent: Pricing & Payments
---

For quick reference please see [Promotions]({% link docs/reference/objects/product/promotion.md %}).

Promotions are discounts which are configured on a variant level.

Promotions must have a start date, they may have expiry date and/or have been expired manually. `promotion.active` will return true only if today's date is on or after the start date, the end date is after today and the promotion has not been manually expired.

Creators want to advertise promotions as often as possible in Sites and there are many ways you may wish to do this for them.

### Show the promotion category, tagline, expiry date, or discount amount

{% raw %}
```liquid
{% for variant in product.variants %}
    {% assign has_promotion = false %}
    {% if variant.promotion.active %}
        {% assign has_promotion = true %}
        {% assign promo_category = variant.promotion.category %}
        {% assign promo_tagline = variant.promotion.tagline %}
        {% assign promo_expiry = variant.promotion.ends_on %}
        {% if variant.promotion.discount_is_percentage %}
            {% assign promo_discount_amount = variant.promotion.discount_percentage | append: "%" %}
        {% else %}
            {% assign promo_discount_amount = variant.promotion.discount_amount_fractional | money %}
        {% endif %}
    {% endif %}

    <div>
        <p>{{variant.name}}</p> 
        {% if has_promotion %}
        <p> Save {{promo_discount_amount}} with our <span class="promo-label">{{promo_category}} offer</span></p>
        {% if promo_tagline != "" %}<p>{{promo_tagline}}</p>{% endif %}
        {% if promo_expiry %}<p>Offer ends {{promo_expiry | date: "%d %B %Y"}}</p>{% endif %}
        {% endif %}
    </div>

{% endfor %}
```
{% endraw %}

This might render:
{% raw %}
```html
    <div>
        <p>Yoga Retreat - Adult</p> 
        <p> Save 20% with our <span class="promo-label">Early release offer</span></p>
        <p>Book your spot on the retreat of a lifetime</p>
        <p>Offer ends 12 January 2023</p>
    </div>
    <div>
        <p>Yoga Retreat - Child</p> 
    </div>
```
{% endraw %}

### Show the promotional price in comparison to the full price for each variant:

{% raw %}
```liquid
{% for variant in product.variants %}
    {% assign has_promotion = false %}
    {% assign full_price = variant.price.fractional | money %}
    {% if variant.promotion.active %}
        {% assign has_promotion = true %}
        {% assign promo_price_drop = variant.price | apply_promotion: variant.promotion %}
        {% assign promo_price = promo_price_drop.fractional | money %}
    {% endif %}
        
    <p>{{variant.name}}</p> 
    {% if has_promotion %}
        <p>Price reduced from {{full_price}} to {{promo_price}}</p>
    {% else %}
        <p>Price is {{full_price}} </p>
    {% endif %}

{% endfor %}
```
{% endraw %}

This might render:
{% raw %}
```html
    <p>Yoga Retreat - Adult</p> 
    <p>Price reduced from $300.00 to $250.00</p> 

    <p>Yoga Retreat - Child</p>
    <p>Price is $20.00 </p>

```
{% endraw %}
