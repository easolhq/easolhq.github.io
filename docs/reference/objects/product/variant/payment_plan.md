---
layout: default
title: Payment plan
parent: Variant
grand_parent: Product
---

# Payment plan
{: .d-inline-block }
object
{: .label .fs-1 }

#### Attributes

## `payment_plan.initial_payment_amount_fractional`
{: .d-inline-block }
number
{: .label .fs-1 }

The upfront payment for this payment plan, in the quantity of the
smallest unit for this currency. (e.g. cents for USD, pence for GBP, yen
for JPY etc.)

This will be `nil` if there is no custom initial payment amount set.
In the case of no custom amount being set, the initial payment will be the total payment divided by the number of instalments.

## `payment_plan.is_initial_payment_fixed`
{: .d-inline-block }
boolean
{: .label .fs-1 }

Whether or not a custom initial payment amount has been set.
(See initial_payment_amount_fractional for more information).

## `payment_plan.number_of_instalments`
{: .d-inline-block }
number
{: .label .fs-1 }

The number of instalments needed to pay off this plan.
