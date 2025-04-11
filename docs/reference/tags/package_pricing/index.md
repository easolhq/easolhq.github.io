---
layout: default
title: Package Price
parent: Tags
grand_parent: Reference
---

# Package Price

The `package_price` tag can be used to fetch the price information for a
sum-total package, given a date & time and an adult count.

This tag has been designed to work with sum-total packages that hide their
element prices. So a site can display the predicted full price of the package,
without having to display any element prices.

It will sum to the price of the included items and will also predict the
price of required steps by using the step's merchandising item to represent
the price of the step.

Required steps must satisfy the following in order to be included in the price:
1. Have a merchandising item defined.
2. Have required nights defined if it is an accommodation step.

If a step has "Require that customers select accommodation for every guest" as
true, it will use the price for the package's adult count, otherwise it will use
variant's minimum occupancy.

> Note: This tag does not support custom-priced packages and will raise a Liquid error if this tag is rendered with one.

##### input
{% raw %}

    {% package_price package, adult_count: 2, start_date: "2024-04-15", start_time: "11:00" %}
      Price: {{ result.price.fractional | money }}
      Fees: {{ result.fees.fractional | money }}
      Price with fees: {{ result.price_with_fees.fractional | money }}
    {% endpackage_price %}

{% endraw %}

##### output

{% raw %}

    Price: £100.00
    Fees: £20.00
    Price with fees: £120.00

{% endraw %}

## Tag parameters

Parameter | Description | Required
--------- | ----------- | --------
`package` | The package to fetch the price for | Yes
`adult_count` | Number of guests for the package | Yes
`start_date` | The selected start date for the package | If the package is multi-date
`start_time` | The selected start time for the package | No
