---
layout: default
title: Recommendation
parent: Objects
---

# Recommendation
{: .d-inline-block }
object
{: .label .fs-1 }

#### Attributes

## `recommendation.cart`
{: .d-inline-block }
[CartDrop]({% link docs/reference/objects/cart/index.md %})
{: .label .fs-1 }

The cart associated with the recommendation.

## `recommendation.checkout_url`
{: .d-inline-block }
string
{: .label .fs-1 }

This url will direct the user to checkout in order to purchase the recommendation.

## `recommendation.expired`
{: .d-inline-block }
boolean
{: .label .fs-1 }

Whether the recommendation has expired.
Users can still visit the recommendation page if the recommendation has expired, but they will not be able to book it.

## `recommendation.guest_count`
{: .d-inline-block }
string
{: .label .fs-1 }

The guest count set on the recommendation.
Note: This is an optional field and may not be set.

## `recommendation.hero_image`
{: .d-inline-block }
[Image]({% link docs/reference/objects/image.md %})
{: .label .fs-1 }

The hero image of the recommendation.

## `recommendation.message`
{: .d-inline-block }
string
{: .label .fs-1 }

The message of the recommendation.

## `recommendation.name`
{: .d-inline-block }
string
{: .label .fs-1 }

The name of the recommendation.

## `recommendation.terms_and_conditions_url`
{: .d-inline-block }
string
{: .label .fs-1 }

The URL of the recommendation's terms.
If the recommendation has custom terms it will display those, otherwise it will default to the company's terms.

## `recommendation.user_email`
{: .d-inline-block }
string
{: .label .fs-1 }

The guest email set on the recommendation.
Note: This may not be the same as the user who books the recommendation.
