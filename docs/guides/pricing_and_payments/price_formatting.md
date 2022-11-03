---
layout: default
title: Price Formatting
parent: Pricing & Payments
---

If no method is called on a price object, it will default to showing with the currency symbol and either /pp or /night depending on the [per person unit or night pricing]({% link docs/guides/pricing_and_payments/per_person_unit_or_night.md %}).

e.g. `{{variant.price}}` might render as €200.00/pp 

This is great for basic use cases. However, since you can only apply [promotions]({% link docs/guides/pricing_and_payments/promotions.md %}) on fractional values, to format prices consistently across a site, we recommend starting from the `fractional` or `per_person_fractional` price, and applying the [money filter]({%link docs/reference/filters/money.md%}) along with adding a suffix of per _something_ where needed. 

You may also wish to format prices further with the money filter attribute `no_cents_if_whole`

e.g. `{{variant.price | money: no_cents_if_whole: true}}` might render as €200/pp<br>
and  `{{variant.price.per_person_fractional | money: no_cents_if_whole: true}}` might render as €100
