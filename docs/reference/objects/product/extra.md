---
layout: default
title: Extra
parent: Product
grand_parent: Objects
---

# Extra
{: .d-inline-block }
object
{: .label .fs-1 }

#### Attributes

## `extra.address`
{: .d-inline-block }
[address]({% link docs/reference/objects/product/address.md %})
{: .label .fs-1 }

The [address]({% link docs/reference/objects/product/address.md %}) associated with this extra.

## `extra.country`
{: .d-inline-block }
string
{: .label .fs-1 }

The name of the country for the product that this extra is part of.

## `extra.deposit_amount`
{: .d-inline-block }
string
{: .label .fs-1 }
deprecated
{: .label .fs-1 .label-red .ml-0 .mt-0 }

A humanized price for the extras deposit amount, if deposits are not set on the extra this will just return `extra.price` e.g. `$250 Per Person`.

Deprecated, the deposit should be calculated in Liquid, using a mixture of the `extra.price` and `extra.product.deposit.rate`.

{% raw %}
```liquid
{% assign deposit_price = extra.price.fractional | times: extra.product.deposit.rate %}
{{ deposit_price | money }}
```
{% endraw %}

## `extra.has_infinite_stock`
{: .d-inline-block }
boolean
{: .label .fs-1 }

Returns `true` if the extra has unlimited stock.

## `extra.hero_image`
{: .d-inline-block }
[Image]({% link docs/reference/objects/image.md %})
{: .label .fs-1 }

The hero [image]({% link docs/reference/objects/image.md %}) of the [product]({% link docs/reference/objects/product/index.md %}) the extra belongs to.

## `extra.id`
{: .d-inline-block }
string
{: .label .fs-1 }
The unique id of the extra.

## `extra.image`
{: .d-inline-block }
[Image]({% link docs/reference/objects/image.md %})
{: .label .fs-1 }

The extra's [image]({% link docs/reference/objects/image.md %}) if it has one associated.

## `extra.initial_stock`
{: .d-inline-block }
number
{: .label .fs-1 }

The initial stock for the extra, if the extra has unlimited inventory this will return `nil`.

## `extra.modifier_groups`
{: .d-inline-block }
array of [modifier group]({% link docs/reference/objects/product/modifier_group.md %})s
{: .label .fs-1 }

An array of [modifier groups]({% link docs/reference/objects/product/modifier_group.md %}) associated with this extra.

Note that the resulting list will encompass both pre- and post-checkout modifier groups, and therefore the use of this method in pre-checkout pages is not recommended.

For pre-checkout pages, [pre_checkout_modifier_groups]({% link docs/reference/objects/product/extra.md %}#extrapre_checkout_modifier_groups) should be used instead.

## `extra.name`
{: .d-inline-block }
string
{: .label .fs-1 }

The extras name.

## `extra.overview_image`
{: .d-inline-block }
[Image]({% link docs/reference/objects/image.md %})
{: .label .fs-1 }

The overview [image]({% link docs/reference/objects/image.md %}) of the [product]({% link docs/reference/objects/product/index.md %}) the extra belongs to.

## `extra.price`
{: .d-inline-block }
[Price]({% link docs/reference/objects/product/price.md %})
{: .label .fs-1 }

The [price]({% link docs/reference/objects/product/price.md %}) of this extra in the current customer's currency.

{% raw %}
```liquid
{{ extra.price.fractional | money }}
```
{% endraw %}

This method has some deprecated behaviour. If no methods are called on the [Price]({% link docs/reference/objects/product/price.md %}) object that is returned from this method, then it will fallback to the legacy behaviour, which will return a string of the price, e.g. `$124 Per Person`. It is difficult to apply any math filters to this price string.

The behaviour of `extra.price` has been changed to enable math filters to be applied.  It is more useful to have access to the numerical value of the price.

**Deprecated method**
{% raw %}
```
<p>{{ extra.price }}</p>
```
{% endraw %}

**Updated method**
{% raw %}
```
<p>{{ extra.price | money }} Per Person</p>
```
{% endraw %}


## `extra.pre_checkout_modifier_groups`
{: .d-inline-block }
array of [modifier group]({% link docs/reference/objects/product/modifier_group.md %})s
{: .label .fs-1 }

An array of [modifier groups]({% link docs/reference/objects/product/modifier_group.md %}) associated with this extra that the customer must choose before checking out.

## `extra.prices`
{: .d-inline-block }
array of [price]({% link docs/reference/objects/product/price.md %})s
{: .label .fs-1 }

An array containing the single [price]({% link docs/reference/objects/product/price.md %}) of this extra in the current customer's currency.

{% raw %}
```liquid
{{ assign price = extra.prices | first }}
{{ price.fractional | money }}
```
{% endraw %}

## `extra.product`
{: .d-inline-block }
[Product]({% link docs/reference/objects/product/index.md %})
{: .label .fs-1 }

The [product]({% link docs/reference/objects/product/index.md %}) this extra belongs to.

## `extra.promotion`
{: .d-inline-block }
[Promotion]({% link docs/reference/objects/product/promotion.md %})
{: .label .fs-1 }

The extra's current active [promotion]({% link docs/reference/objects/product/promotion.md %}) if there is one.

## `extra.remaining_stock`
{: .d-inline-block }
number
{: .label .fs-1 }

The remaining stock for the extra, if the extra has unlimited inventory this will return `nil`.

## `extra.segment_name`
{: .d-inline-block }
string
{: .label .fs-1 }

If the extra belongs to a segment this will return the segment name.

## `extra.sold_out`
{: .d-inline-block }
boolean
{: .label .fs-1 }

Returns `true` if the extra is sold out.

## `extra.tagline`
{: .d-inline-block }
string
{: .label .fs-1 }

The extra's tagline.

## `extra.type`
{: .d-inline-block }
string
{: .label .fs-1 }

Will always return "`extra`". This is useful when you have a list of `Variant` and `Extra` objects and you need to distinguish between them.
