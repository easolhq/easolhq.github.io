---
layout: default
title: Price Formatting
parent: Pricing & Payments
---

If no method is called on a price object, it will default to showing with the currency symbol and either /pp or /night depending on the [per person, unit, or night pricing]({% link docs/guides/pricing_and_payments/per_person_unit_or_night.md %}).

e.g. {% raw %}`{{variant.price}}`{% endraw %} might render as €200.00/pp 

This is great for basic use cases. However, if a price object has had a method called on it, e.g. when applying [promotions]({% link docs/guides/pricing_and_payments/promotions.md %}) the return value is another drop.

e.g {% raw %}`{{ variant.price | apply_promotion: variant.promotion }}`{% endraw %} might render VariantPriceDrop. 

To format prices consistently across a site, we therefore recommend always using the `fractional` or `per_person_fractional` prices, applying the [money filter]({%link docs/reference/filters/money.md%}), and adding a suffix of per _something_ where needed. You can further format prices with the money filter attribute `no_cents_if_whole`

e.g. {% raw %}`{{variant.price | money }}`{% endraw %} might render as €200.00<br>
so   {% raw %}`{{variant.price.fractional | money: no_cents_if_whole: true}}`{% endraw %} would render as €200<br>
and  {% raw %}`{{variant.price.per_person_fractional | money: no_cents_if_whole: true }}`{% endraw %} might render as €100
