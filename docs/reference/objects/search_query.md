---
layout: default
title: Search query
parent: Objects
---

When using a `search` object each product search query parameter is available as an attribute.

# search.active_promotion
Returns `true` or `false`.

# search.category
Returns the category as a string.

# search.country
Returns the country as a string.

# search.departure_date
Returns the departure_date as an object i.e. `{"greater_than"=>"2022-11-19", "less_than"=>"2023-12-28"}`.
Specific values can be accessed via: `search.departure_date.equal_to`, `search.departure_date.greater_than` and `search.departure_date.less_than` as relevant.

# search.departure_month
Returns the departure_month as a string in the form it was passed in i.e. `Jan` or `1`.

# search.duration
Returns the duration as an object i.e. `{"greater_than"=>"3", "less_than"=>"8"}`. 
Specific values can be accessed via: `search.duration.equal_to`, `search.duration.greater_than` and `search.duration.less_than` as relevant.

# search.exclude_sold_out_products
Returns `true` or `false`.

# search.include_organisation_products
Returns `true` or `false`.

# search.series_id
Returns the series_id as a string.

# search.subcategory
Returns the subcategory as a string.

# search.sort
Returns `name_asc`, `name_desc`, `duration_asc`, `duration_desc`, `departure_date_asc` or `departure_date_desc`.