---
layout: default
title: Deposit
parent: Product
---

This object represents a deposit of a variant or extra.<br>
When using a `deposit` object you have access to the following attributes:

# deposit.enabled

Returns true if this variant can be paid with a deposit.

# price.rate

The rate of this deposit as a value between `0` and `1`. For example, if the deposit is 50% this will return `0.5`.
If the variant has an active [promotion]({% link docs/reference/objects/product/promotion.md %}) the deposit rate should be applied to the promotional price.
