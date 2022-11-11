---
layout: default
title: Deposit
parent: Product
grand_parent: Objects
---

# Deposit
{: .d-inline-block }
object
{: .label .fs-1 }

#### Attributes

## `deposit.enabled`
{: .d-inline-block }
boolean
{: .label .fs-1 }

Returns `true` if this variant or extra can be paid with a deposit.

## `deposit.rate`
{: .d-inline-block }
number
{: .label .fs-1 }

The deposit rate as a value between `0` and `1`. For example, if the deposit is 50% this will return `0.5`.
If the variant has an active [promotion]({% link docs/reference/objects/product/promotion.md %}) the deposit rate should be applied to the promotional price.

Example
{% raw %}
```liquid
{% assign promotional_price = variant.price | apply_promotion: variant.promotion %}
{% assign deposit_price = promotional_price.fractional | times: variant.deposit.rate %}
{{ deposit_price | money }}
```
{% endraw %}
