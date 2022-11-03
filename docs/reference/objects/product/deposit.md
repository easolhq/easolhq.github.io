---
layout: default
title: Deposit
parent: Product
grand_parent: Objects
---

This object represents a deposit of a variant or extra.<br>
When using a `deposit` object you have access to the following attributes:

# deposit.enabled

Returns true if this variant can be paid with a deposit.

# price.rate

The rate of this deposit as a value between `0` and `1`. For example, if the deposit is 50% this will return `0.5`.
If the variant has an active [promotion]({% link docs/reference/objects/product/promotion.md %}) the deposit rate should be applied to the promotional price.

Example
{% raw %}
```liquid
{% assign promotional_price = variant.price | apply_promotion: variant.promotion %}
{% assign deposit_price = promotional_price.fractional | times: variant.deposit.rate %}
{{ deposit_price | money }}
```
{% endraw %}
