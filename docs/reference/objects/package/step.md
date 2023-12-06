---
layout: default
title: Package Step
parent: Objects
---

# Package Step
{: .d-inline-block }
object
{: .label .fs-1 }

Represents a creator-defined step along a [package]({% link docs/reference/objects/package.md %}) booking journey.

<br>

#### Attributes

## `package_step.id`
{: .d-inline-block }
string
{: .label .fs-1 }

The database id of the step.

## `package_step.name`
{: .d-inline-block }
string
{: .label .fs-1 }

The name given to the step.

## `package_step.tagline`
{: .d-inline-block }
string
{: .label .fs-1 }

The description given to the step.

## `package_step.path`
{: .d-inline-block }
URL
{: .label .fs-1 }

URL pointing to the step's page in the package booking journey.

## `package_step.package`
{: .d-inline-block }
[Package]({% link docs/reference/objects/package.md %})
{: .label .fs-1 }
The related package.

## `package_step.product_groups`
{: .d-inline-block }
Array of [Package Product]({% link docs/reference/objects/package/product.md %})s
{: .label .fs-1 }

Each step contains a creator-selected number of bookable elements. Those selections are exposed to Liquid templates as an array of [Package Product]({% link docs/reference/objects/package/product.md %})s, where each provides:

- the subset of variants that the creator chose to belong to the package
- and the product which those chosen variants are part of

## `package_step.required_start_date`
{: .d-inline-block }
Date
{: .label .fs-1 }

Creators may specify that customers must book accommodation dates which include a specific date range. This will return the start date of that range.

## `package_step.required_end_date`
{: .d-inline-block }
Date
{: .label .fs-1 }

Creators may specify that customers must book accommodation dates which include a specific date range. This will return the end date of that range.

## `package_step.next_page_path`
{: .d-inline-block }
URL
{: .label .fs-1 }

URL pointing to the next page of the booking journey. Navigating to this URL is only possible if the customer has added enough/the correct elements to the cart to honour the requirements set by the creator for this step.

## `package_step.step_valid?`
{: .d-inline-block }
`true` or `false`
{: .label .fs-1 }

This will return `false` if the customer has not added enough elements to the cart to honour the requirements set by the creator for this step, and `true` if they have.

## `package_step.validation_errors`
{: .d-inline-block }
Array of strings
{: .label .fs-1 }

If the customer has not added enough elements to the cart to honour the requirements set by the creator for this step, will contain an explanation of the fact.

## `package_step.accommodated_adult_count`
{: .d-inline-block }
Integer
{: .label .fs-1 }

The total guests that have been selected so far for this package step.

## `package_step.min_guests_required`
{: .d-inline-block }
Integer
{: .label .fs-1 }

If the package step requires a specific guest count equal to the package adult count, then we return the package adult count.

If we don't require the guest count to equal the package adult count, but the step has required dates, the minimum will be 1.

Otherwise, this will be 0.

## `package_step.max_guests_required`
{: .d-inline-block }
Integer
{: .label .fs-1 }

This is the package adult count.
