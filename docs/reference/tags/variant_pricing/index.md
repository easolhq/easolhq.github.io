---
layout: default
title: Variant Pricing
parent: Tags
grand_parent: Reference
---

# Variant Pricing

The `variant_pricing` tag renders a self-updating `<span>` which can
interactively fetch and display up-to-date pricing information for a given
variant, provided an adult count/start date/end date combination.

You can use this tag to display up-to-date prices of each variant you're
rendering on the page, responding to user interactions with the calendar and
adult count for each displayed variant.

The tag is package-aware; if you use it in a package step template, it will
display how much upgrading to that variant will cost, or `Included` if it is
part of the package price.

##### input
{% raw %}

    {% variant_pricing variant: variant, class: "my-nice-class", adult_count: 2, start_on: "2023-01-01", end_on: "2023-01-04" %}

{% endraw %}

##### output

The `<span>` tag will initially be rendered empty:

{% raw %}

    <span class="my-nice-class"
      data-controller="variant-pricing"
      data-variant-pricing-variant-value="<id>"
      data-variant-pricing-adult-count-value="2"
      data-variant-pricing-start-on-value="2023-01-01"
      data-variant-pricing-end-on-value="2023-01-04">
    </span>

{% endraw %}

If rendering in the context of a package booking template, the package step ID is included:

{% raw %}

    <span class="my-nice-class"
      data-controller="variant-pricing"
      data-variant-pricing-variant-value="<id>"
      data-variant-pricing-adult-count-value="2"
      data-variant-pricing-start-on-value="2023-01-01"
      data-variant-pricing-end-on-value="2023-01-04"
      data-variant-pricing-package-step-id-value="<step id>">
    </span>

{% endraw %}

## Tag parameters

Parameter | Description | Required
--------- | ----------- | --------
`variant` | The variant to display the price for | Yes
`class` | The value of the span's `class` attribute (for styling and targeting in scripts) | Yes
`adult_count` | Number of guests to consider in price calculation | Yes
`start_on` | Check-in date to consider in price calculation | If rendering for an Accommodation Variant
`end_on` | Check-in date to consider in price calculation | If rendering for an Accommodation Variant
`include_fees` | Option to include booking fees and custom on platform fees in the price | No

## Bootstrapping and fetching new prices

The platform provides a Javascript component which automates the triggering of
the appropriate server requests for pricing information, interpolating the
result into the `<span>`'s inner HTML.

The component will request up-to-date pricing info when the following data
attributes on the `<span>` are programatically updated:

Attribute | Description | Expected values
--------- | ----------- | ---------------
`data-variant-pricing-adult-count-value` | Adult count chosen by the user | Integer > 0
`data-variant-pricing-start-on-value` | Check-in date chosen by the user | Date string in ISO format `YYYY-MM-DD`
`data-variant-pricing-end-on-value` | Check-out date chosen by the user | Date string in ISO format `YYYY-MM-DD`

**Important: this tag is initially rendered empty. If you need it to have
contents when the page is rendered, you must manually trigger a request by
updating the data attributes with default values.**

We recommend listening to user-driven changes on the page, and have the event
handlers:

- Target the `<span>` tags by their class
- Assign the chosen values to their data-attributes

To "bootstrap" the contents on initial page load, you might hook onto the
`DOMContentLoaded` event like so:

{% raw %}

    function bootstrapVariantPricingTags() {
      const defaultStartOn = "2023-01-01"
      const defaultEndOn = "2023-01-04"
      const defaultAdultCount = "4"

      const variantPricingTag = document.querySelector(".my-nice-class")
      variantPricingTag.dataset.variantPricingAdultCountValue = defaultAdultCount
      variantPricingTag.dataset.variantPricingStartOnValue = defaultStartOn
      variantPricingTag.dataset.variantPricingEndOnValue = defaultEndOn
    }

    document.addEventListener('DOMContentLoaded', bootstrapVariantPricingTags)
{% endraw %}

And to respond to changes to the selected adult count and check-in/out dates
you might hook onto the relevant elements' events:

{% raw %}

    document.querySelector(".adult-count-dropdown").addEventListener("change", (e) => {
      const variantPricingTag = document.querySelector(".my-nice-class")

      variantPricingTag.dataset.variantPricingAdultCountValue = e.target.value
    })

    document.querySelector(".start-on-calendar").addEventListener("change", (e) => {
      const variantPricingTag = document.querySelector(".my-nice-class")

      variantPricingTag.dataset.variantPricingStartOnValue = e.target.value
    })

    document.querySelector(".end-on-calendar").addEventListener("change", (e) => {
      const variantPricingTag = document.querySelector(".my-nice-class")

      variantPricingTag.dataset.variantPricingEndOnValue = e.target.value
    })

{% endraw %}


## Consideration with packages

When this tag is used in the context of a package step, the user may need to
choose from a range of time slots for the variant. In this case we calculate
the cheapest possible price of the possible slots. We recommend
pre-pending the price with 'From' in this case.

The slot which is used to generate the price is included in the data attributes:

{% raw %}

    <span data-variant-pricing-experience-slot-value="<slot id>">
    </span>

{% endraw %}
