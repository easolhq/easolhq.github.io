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

The number of instalments needed to pay off this plan. For flexible plans (where `minimum_number_of_instalments` and `maximum_number_of_instalments` differ), this is the resolved count based on the product's start date — the most instalments that fit before departure.

## `payment_plan.minimum_number_of_instalments`
{: .d-inline-block }
number
{: .label .fs-1 }

The minimum number of instalments configured on this plan. For non-flexible plans this equals `number_of_instalments`.

## `payment_plan.maximum_number_of_instalments`
{: .d-inline-block }
number
{: .label .fs-1 }

The maximum number of instalments configured on this plan. For non-flexible plans this equals `number_of_instalments`.

## `payment_plan.monthly`
{: .d-inline-block }
boolean
{: .label .fs-1 }

Returns `true` if this payment plan collects instalments on a monthly rolling basis (e.g. today, +1 month, +2 months, etc.).

## `payment_plan.specific_dates`
{: .d-inline-block }
boolean
{: .label .fs-1 }

Returns `true` if this payment plan collects instalments on specific calendar dates configured by the creator.

## `payment_plan.instalment_schedule`
{: .d-inline-block }
array
{: .label .fs-1 }

An array of up to 12 schedule items representing when each instalment payment is due. The first item is always today (the checkout payment); the remaining items are follow-up due dates.

For monthly plans, follow-up dates are computed as rolling monthly intervals from today. For specific-date plans, follow-up dates come from the dates configured by the creator.

Each item in the array has a single attribute:

- `due_date` — the date this instalment payment is due, which can be formatted with Liquid's [date filters](https://shopify.github.io/liquid/filters/date/).

Example
{% raw %}
```liquid
{% if payment_plan %}
  <p>Payment schedule:</p>
  <ul>
    {% for instalment in payment_plan.instalment_schedule %}
      <li>
        {% if forloop.first %}
          Due at checkout ({{ instalment.due_date | date: "%d %B %Y" }})
        {% else %}
          {{ instalment.due_date | date: "%d %B %Y" }}
        {% endif %}
      </li>
    {% endfor %}
  </ul>
{% endif %}
```
{% endraw %}
