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

Returns `true` if this variant, extra or package can be paid with a deposit.

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


## `deposit.due_date`
{: .d-inline-block }
Date
{: .label .fs-1 }

The date the final balance payment will be due, if this can be calculate and the deposit is enabled. This can be formatted with Liquid's [date filters](https://shopify.github.io/liquid/filters/date/). The Creator may have set this as a number of days relative to the experience or accommodation start date, or they may have selected a specific date from a calendar. They also may have not set a value, in which case a default of 60 days before start date is used.

- When accessed through an [experience slot]({% link docs/reference/objects/product/experience_slot.md %}) it will return a date.
- When accessed through a single slot experience it will return a date.
- When accessed through a fixed-date package it will return a date.
- When accessed through a multislot experience, an accommodation, or a multi-date package, it will return `nil`.

Example
{% raw %}
```liquid
{{ deposit.due_date | date: "%Y-%m-%d" }}
{% endif %}
```
{% endraw %}
