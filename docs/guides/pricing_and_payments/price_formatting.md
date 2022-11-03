---
layout: default
title: Price Formatting
parent: Pricing & Payments
---

If no method is called on a price object, it will default to showing with the currency symbol and either /pp or /night depending on the [per person, unit, or night pricing]({% link docs/guides/pricing_and_payments/per_person_unit_or_night.md %}).

e.g. `{{variant.price}}` might render as €200.00/pp 

This is great for basic use cases. However, if a price object has had a method called on it, e.g. when applying promotions [promotions]({% link docs/guides/pricing_and_payments/promotions.md %}) the return value is another drop.

e.g `{{ variant.price | apply_promotion: variant.promotion }}` might render VariantPriceDrop. 

To format prices consistently across a site, we therefore recommend always using the `fractional` or `per_person_fractional` prices, applying the [money filter]({%link docs/reference/filters/money.md%}), and adding a suffix of per _something_ where needed. You can further format prices with the money filter attribute `no_cents_if_whole`

e.g. `{{variant.price | money: no_cents_if_whole: true}}` might render as €200<br>
so   `{{variant.price.fractional | money: no_cents_if_whole: true}}` would render as €200<br>
and  `{{variant.price.per_person_fractional | money: no_cents_if_whole: true }}` might render as €100
