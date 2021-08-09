---
layout: default
title: Promotion
parent: Product
---

When using a `promotion` object you have access to the following attributes
Can be accessed on a variant like below

# promotion.active

Returns true if the promotion is currently active

# promotion.dates

Returns the dates the promotion is active for as a humanized string e.g. `7 - 14 August 2019`

# promotion.discount_amount

Returns the discount the promotion will apply, if the promotion represents a percentage discount this will be formatted as `25%` if it is a monetary discount this will be as `$25.00` 

# promotion.category

Returns the category of the promotion

# promotion.ends_on

Returns the date the promotion will end on as a timestamp, this can then be used in conjunction with liquids[ built in filters ](https://shopify.github.io/liquid/filters/date/)

# promotion.name

Returns the name of the promotion

# promotion.starts_on

Returns the date the promotion will start on as a timestamp, this can then be used in conjunction with liquids[ built in filters ](https://shopify.github.io/liquid/filters/date/)

# promotion.tagline

Returns the tagline for the promotion

