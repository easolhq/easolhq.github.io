---
layout: default
title: Extra
parent: Product
grand_parent: Objects
---

When using an `extra` object you have access to the following attributes.

# extra.address

Returns the [address]({% link docs/reference/objects/product/address.md %}) associated with this extra.

# extra.country

Returns the name of the country for the product that this extra is part of.

# extra.deposit_amount _(deprecated)_

Returns a humanized price for the extras deposit amount, if deposits are not set on the extra this will just return `extra.price` e.g. `$250 Per Person`.

> **Deprecated**
>
> The deposit should be calculated in Liquid, using a mixture of the `extra.price` and `extra.product.deposit.rate`.
>
> {% raw %}
> ```liquid
> {% assign deposit_price = extra.price.fractional | times: extra.product.deposit.rate %}
> {{deposit_price | money}}
> ```
> {% endraw %}

# extra.has_infinite_stock

Returns true if the extra has unlimited stock.

# extra.hero_image

Returns the hero [image]({% link docs/reference/objects/image.md %}) of the [product]({% link docs/reference/objects/product/index.md %}) the extra belongs to.

# extra.id

Returns a unique id for the extra.

# extra.image

Returns the extras [image]({% link docs/reference/objects/image.md %}) if it has one associated.

# extra.initial_stock

Returns the initial stock for the extra, if the extra has unlimited inventory this will return `nil`.

# extra.modifier_groups

Returns a list of [modifier groups]({% link docs/reference/objects/product/modifier_group.md %}) associated with this extra.

Note that the resulting list will encompass both pre- and post-checkout modifier groups, and therefore the use of this method in pre-checkout pages is not supported.

For pre-checkout pages, [pre_checkout_modifier_groups]({% link docs/reference/objects/product/extra.md %}#extrapre_checkout_modifier_groups) should be used instead.

# extra.name

Returns the extras name.

# extra.overview_image

Returns the overview [image]({% link docs/reference/objects/image.md %}) of the [product]({% link docs/reference/objects/product/index.md %}) this extra belongs to.

# extra.price

Returns the [price]({% link docs/reference/objects/product/price.md %}) of this extra in the current customer's currency.

{% raw %}
```liquid
{{extra.price.fractional | money}}
```
{% endraw %}

> This method has some deprecated behaviour. If no methods are called on the [price]({% link docs/reference/objects/product/price.md %}) object that is returned from this method, then it will fallback to the legacy behaviour, which will return a string of the price, e.g. `$124 Per Person`.
>
> We have changed this behaviour because it is difficult to apply any math filters to this price string. It is more useful to have access to the numerical value of the price.
>
> **Good**
>{% raw %}
> ```
> <p>{{extra.price | money}} Per Person</p>
> ```
> {% endraw %}
>
> **Bad**
> {% raw %}
> ```
> <p>{{extra.price}}</p>
> ```
> {% endraw %}

# extra.pre_checkout_modifier_groups

Returns a list of [modifier groups]({% link docs/reference/objects/product/modifier_group.md %}) associated with this extra that the customer must choose before checking out.

# extra.prices

Returns an array containing the single [price]({% link docs/reference/objects/product/price.md %}) of this extra in the current customer's currency.

{% raw %}
```liquid
{{assign price = extra.prices | first}}
{{price.fractional | money}}
```
{% endraw %}

# extra.product

Returns the [product]({% link docs/reference/objects/product/index.md %}) this extra belongs to.

# extra.promotion

Returns the extra's current active [promotion]({% link docs/reference/objects/product/promotion.md %}) if there is one.

# extra.remaining_stock

Returns the remaining stock for the extra, if the extra has unlimited inventory this will return `nil`.

# extra.segment_name

If the extra belongs to a segment this will return the segment name.

# extra.sold_out

Returns true if the extra is sold out.

# extra.tagline

Returns the extras tagline.

# extra.type

Will always return `"extra"`. This is useful when you have a list of `variant` and `extra` objects and you need to distinguish between them.
