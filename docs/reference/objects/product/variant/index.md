---
layout: default
title: Variant
parent: Product
has_children: true
---

When using a `variant` object you have access to the following attributes:<br>
*Note:* this defines a common interface shared between
[Experience Variant]({% link docs/reference/objects/product/variant/experience_variant/index.md %}) and
[Accommodation Variant]({% link docs/reference/objects/product/variant/accommodation_variant/index.md %}).

# variant.deposit

Returns the [deposit]({% link docs/reference/objects/product/deposit.md %}) of this variant if paying with deposit is enabled, `nil` otherwise.
If the variant has an active [promotion]({% link docs/reference/objects/product/promotion.md %}) the deposit rate should be applied to the promotional price.

Example
{% raw %}
```liquid
{% assign promotional_price = variant.price | apply_promotion: variant.promotion %}
{% assign deposit_price = promotional_price.fractional | times: variant.deposit.rate %}
{{ deposit_price | money }}
```
{% endraw %}

# variant.deposit_amount _(deprecated)_

Returns a humanized price for the variant's deposit amount, if deposits are not set on the variant this will just return `extra.price` e.g. `$250 Per Person`.

> **Deprecated**
>
> The deposit should be calculated in Liquid, using a mixture of the `variant.price` and `variant.product.deposit.rate`.
>
> {% raw %}
> ```liquid
> {% assign deposit_price = variant.price.fractional | times: variant.product.deposit.rate %}
> {{deposit_price | money}}
> ```
> {% endraw %}

# variant.has_infinite_stock

Returns true if the variant has unlimited stock.

# variant.humanized_display_amount

Returns a humanized display amount e.g. `$120.00`

> **Deprecated**
>
> The display amount should be obtained, using the `variant.price` with the `money` filter.
>
> {% raw %}
> ```liquid
> {{variant.price | money}}
> ```
> {% endraw %}

# variant.id

Returns a unique id for the variant.

# variant.image

Returns the variant's [image]({% link docs/reference/objects/image.md %}) it it has one.

# variant.initial_stock

Returns the initial stock for the variant, if the variant has unlimited inventory this will return `nil`.

# variant.is_priced_per_person

Returns true whether this variant is priced per-person.

# variant.modifier_groups

Returns a list of [modifier groups](({% link docs/reference/objects/product/modifier_group.md %})) associated with this variant.

# variant.max_occupancy

Returns the maximum number of guests for this variant.

# variant.min_occupancy

Returns the minimum number of guests for this variant.

# variant.name

Returns the variants name

# variant.price

Returns the [price]({% link docs/reference/objects/product/price.md %}) of this variant in the current user's currency.

{% raw %}
```liquid
{{variant.price.fractional | money}}
```
{% endraw %}

> This method has some deprecated behaviour. If no methods are called on the [price]({% link docs/reference/objects/product/price.md %}) object that is returned from this method, then it will fallback to the legacy behaviour, which will return a string of the price, e.g. `$124 Per Person`.
>
> We have changed this behaviour because it is difficult to apply any math filters to this price string. It is more useful to have access to the numerical value of the price.
>
> **Good**
>{% raw %}
> ```
> <p>{{variant.price | money}} Per Person</p>
> ```
> {% endraw %}
>
> **Bad**
> {% raw %}
> ```
> <p>{{variant.price}}</p>
> ```
> {% endraw %}

# variant.prices

Returns an array containing the [prices]({% link docs/reference/objects/product/price.md %}) of each tier of this variant in the current user's currency.

{% raw %}
```liquid
{{assign price = variant.prices | first}}
{{price.fractional | money}}
```
{% endraw %}

# variant.product

Returns the [product]({% link docs/reference/objects/product/index.md %}) this variant belongs to.

# variant.promotion

Returns the variant's current active [promotion]({% link docs/reference/objects/product/promotion.md %}) if there is one.

# variant.remaining_stock

Returns the remaining stock for the variant, if the variant has infinite inventory this will return `nil`.

# variant.segment_name

If the variant belongs to a segment this will return the segment name.

# variant.sold_out

Returns true if the variant is sold out.

# variant.tagline

Returns the variants tagline.

# variant.type

Returns the type of this variant, one of `"experience_variant"` or `"accommodation_variant"`.
Check what other methods you can call on this drop according to their type,
[Experience Variant]({% link docs/reference/objects/product/variant/experience_variant/index.md %}),
[Accommodation Variant]({% link docs/reference/objects/product/variant/accommodation_variant/index.md %}).
