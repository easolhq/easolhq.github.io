---
layout: default
title: Variant
parent: Product
grand_parent: Objects
has_children: true
---

# Variant
{: .d-inline-block }
object
{: .label .fs-1 }

*Note:* this defines a common interface shared between
[Experience Variant]({% link docs/reference/objects/product/variant/experience_variant/index.md %}) and
[Accommodation Variant]({% link docs/reference/objects/product/variant/accommodation_variant/index.md %}).

<br>

#### Attributes

## `variant.booking_fee_rate`
{: .d-inline-block }
number
{: .label .fs-1 }

The variant's booking fee rate as a decimal between 0 and 1.

## `variant.deposit`
{: .d-inline-block }
[deposit]({% link docs/reference/objects/product/deposit.md %})
{: .label .fs-1 }

The [deposit]({% link docs/reference/objects/product/deposit.md %}) of this variant if paying with deposit is enabled, `nil` otherwise.
If the variant has an active [promotion]({% link docs/reference/objects/product/promotion.md %}) the deposit rate should be applied to the promotional price.

Example
{% raw %}
```liquid
{% assign promotional_price = variant.price | apply_promotion: variant.promotion %}
{% assign deposit_price = promotional_price.fractional | times: variant.deposit.rate %}
{{ deposit_price | money }}
```
{% endraw %}

## `variant.deposit_amount`
{: .d-inline-block }
string
{: .label .fs-1 }
deprecated
{: .label .fs-1 .label-red .ml-0 .mt-0 }

Returns a humanized price for the variant's deposit amount, if deposits are not set on the variant this will just return `extra.price` e.g. `$250 Per Person`.

Deprecated, the deposit should be calculated in Liquid, using a mixture of the `variant.price` and `variant.product.deposit.rate`.

{% raw %}
```liquid
{% assign deposit_price = variant.price.fractional | times: variant.product.deposit.rate %}
{{ deposit_price | money }}
```
{% endraw %}

## `variant.has_infinite_stock`
{: .d-inline-block }
boolean
{: .label .fs-1 }

Returns `true` if the variant has unlimited stock.

## `variant.humanized_display_amount`
{: .d-inline-block }
string
{: .label .fs-1 }
deprecated
{: .label .fs-1 .label-red .ml-0 .mt-0 }

A humanized price e.g. `$120.00`

Deprecated, the display amount should be obtained using the `variant.price` with the `money` filter.

{% raw %}
```liquid
{{ variant.price | money }}
```
{% endraw %}

## `variant.id`
{: .d-inline-block }
string
{: .label .fs-1 }

The unique id of the variant.

## `variant.image`
{: .d-inline-block }
[image]({% link docs/reference/objects/image.md %})
{: .label .fs-1 }

The variant's [image]({% link docs/reference/objects/image.md %}) if it has one.

## `variant.initial_stock`
{: .d-inline-block }
number
{: .label .fs-1 }

The initial stock for the variant, if the variant has unlimited inventory this will return `nil`.

## `variant.is_priced_per_person`
{: .d-inline-block }
boolean
{: .label .fs-1 }

Returns `true` if the variant is priced per person.

## `variant.modifier_groups`
{: .d-inline-block }
array of [modifier group]({% link docs/reference/objects/product/modifier_group.md %})s
{: .label .fs-1 }

An array [modifier groups]({% link docs/reference/objects/product/modifier_group.md %}) associated with this variant.

Note that the resulting list will encompass both pre- and post-checkout modifier groups, and therefore the use of this method in pre-checkout pages is not recommended.

For pre-checkout pages, [pre_checkout_modifier_groups]({% link docs/reference/objects/product/variant/index.md %}#variantpre_checkout_modifier_groups) should be used instead.

## `variant.max_occupancy`
{: .d-inline-block }
number
{: .label .fs-1 }

The maximum number of guests for this variant.

## `variant.min_occupancy`
{: .d-inline-block }
number
{: .label .fs-1 }

The minimum number of guests for this variant.

## `variant.name`
{: .d-inline-block }
string
{: .label .fs-1 }

The variant's name.

## `variant.payment_plan`
{: .d-inline-block }
[payment plan]({% link docs/reference/objects/product/variant/payment_plan.md %})
{: .label .fs-1 }

If the product this variant belongs to has a payment plan associated with it, this will return that [payment plan]({% link docs/reference/objects/product/variant/payment_plan.md %}).
The payment plan won't be returned if the last payment date is after the start date of the experience.
A payment plan will still be returned if the price is less than the initial payment, so this may return a payment plan that cannot be used for this variant.

## `variant.pre_checkout_modifier_groups`
{: .d-inline-block }
array of [modifier group]({% link docs/reference/objects/product/modifier_group.md %})s
{: .label .fs-1 }

An array of [modifier groups]({% link docs/reference/objects/product/modifier_group.md %}) that the customer must choose before checking out.

## `variant.price`
{: .d-inline-block }
[price]({% link docs/reference/objects/product/price.md %})
{: .label .fs-1 }

The [price]({% link docs/reference/objects/product/price.md %}) of this variant in the current customer's currency.

{% raw %}
```liquid
{{ variant.price.fractional | money }}
```
{% endraw %}

This method has some deprecated behaviour. If no methods are called on the [Price]({% link docs/reference/objects/product/price.md %}) object that is returned from this method, then it will fallback to the legacy behaviour, which will return a string of the price, e.g. `$124 Per Person`. It is difficult to apply any math filters to this price string.

The behaviour of `variant.price` has been changed to enable math filters to be applied.  It is more useful to have access to the numerical value of the price.

**Deprecated method**
{% raw %}
```
<p>{{ variant.price }}</p>
```
{% endraw %}

**Updated method**
{% raw %}
```
<p>{{ variant.price | money }} Per Person</p>
```
{% endraw %}

## `variant.prices`
{: .d-inline-block }
array of [price]({% link docs/reference/objects/product/price.md %})s
{: .label .fs-1 }

An array containing the [prices]({% link docs/reference/objects/product/price.md %}) of each tier of this variant in the current customer's currency.

{% raw %}
```liquid
{{ assign price = variant.prices | first }}
{{ price.fractional | money }}
```
{% endraw %}

## `variant.product`
{: .d-inline-block }
[product]({% link docs/reference/objects/product/index.md %})
{: .label .fs-1 }

The [product]({% link docs/reference/objects/product/index.md %}) this variant belongs to.

## `variant.promotion`
{: .d-inline-block }
[promotion]({% link docs/reference/objects/product/promotion.md %})
{: .label .fs-1 }

The variant's current active [promotion]({% link docs/reference/objects/product/promotion.md %}) if there is one.

## `variant.remaining_stock`
{: .d-inline-block }
number
{: .label .fs-1 }

The remaining stock for the variant, if the variant has infinite inventory this will return `nil`.

## `variant.segment_name`
{: .d-inline-block }
string
{: .label .fs-1 }

If the variant belongs to a segment this will return the segment name.

## `variant.sold_out`
{: .d-inline-block }
boolean
{: .label .fs-1 }

Returns `true` if the variant is sold out.

## `variant.tagline`
{: .d-inline-block }
string
{: .label .fs-1 }

The variant's tagline.

## `variant.type`
{: .d-inline-block }
string
{: .label .fs-1 }

The type of the variant, one of `experience_variant` or `accommodation_variant`.
Check what other methods you can call on this drop according to their type,
[Experience Variant]({% link docs/reference/objects/product/variant/experience_variant/index.md %}),
[Accommodation Variant]({% link docs/reference/objects/product/variant/accommodation_variant/index.md %}).
