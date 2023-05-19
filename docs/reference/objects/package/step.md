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

## `package_step.product_groups`
{: .d-inline-block }
Array of [Product]({% link docs/reference/objects/product/index.md %})s
{: .label .fs-1 }

Each product containing variants added to the Package Step by the creator. Use `.variants` to get the variants added to the step for this product.

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

## `package_step.next_step_path`
{: .d-inline-block }
URL
{: .label .fs-1 }

URL pointing to the next page of the booking journey. Navigating to this URL is only possible if the customer has added enough/the correct elements to the cart to honour the requirements set by the creator for this step.

## `package_step.validation_errors`
{: .d-inline-block }
Array of strings
{: .label .fs-1 }

If the customer has not added enough elements to the cart to honour the requirements set by the creator for this step, will contain an explanation of the fact.
