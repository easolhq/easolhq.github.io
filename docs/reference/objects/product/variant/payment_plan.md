---
layout: default
title: PaymentPlan
parent: Variant
has_children: false
---

A `payment_plan` has the following attributes:

# payment_plan.initial_payment_amount_fractional

The up front payment for this payment plan, in the quantity of the
smallest unit for this currenct. (e.g. cents for USD, pence for GBP, yen
for JPY etc.)

This will be nil if there is no custom initial payment amount set.
In the case of no custom amount being set, the initial payment will be the total payment divided by the number of instalments.

# payment_plan.is_initial_payment_fixed

Whether or not a custom initial payment amount has been set.
(See initial_payment_amount_fractional for more information).

# payment_plan.number_of_instalments

The number of payments needed to pay off this plan.
