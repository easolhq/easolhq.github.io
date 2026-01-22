---
layout: default
title: Search query
parent: Objects
---

# Search
{: .d-inline-block }
object
{: .label .fs-1 }

#### Attributes

## `search.active_promotion`
{: .d-inline-block }
boolean
{: .label .fs-1 }

Returns `true` or `false`.

## `search.category`
{: .d-inline-block }
string
{: .label .fs-1 }

Returns the category searched.

## `search.city`
{: .d-inline-block }
string
{: .label .fs-1 }

Returns the city searched.

## `search.country`
{: .d-inline-block }
string
{: .label .fs-1 }

Returns the country searched.

## `search.departure_date`
{: .d-inline-block }
object
{: .label .fs-1 }

Returns the departure_date as an object i.e. `{"greater_than"=>"2022-11-19", "less_than"=>"2023-12-28"}`.
Specific values can be accessed via: `search.departure_date.equal_to`, `search.departure_date.greater_than` and `search.departure_date.less_than` as relevant.

## `search.departure_month`
{: .d-inline-block }
string
{: .label .fs-1 }

Returns the departure_month as a string in the form it was passed in i.e. `Jan` or `1`.

## `search.duration`
{: .d-inline-block }
object
{: .label .fs-1 }

Returns the duration as an object i.e. `{"greater_than"=>"3", "less_than"=>"8"}`.
Specific values can be accessed via: `search.duration.equal_to`, `search.duration.greater_than` and `search.duration.less_than` as relevant.

## `search.exclude_sold_out_products`
{: .d-inline-block }
boolean
{: .label .fs-1 }

Returns `true` or `false`.

## `search.include_organisation_products`
{: .d-inline-block }
boolean
{: .label .fs-1 }

Returns `true` or `false`.

## `search.include_organisation_packages`
{: .d-inline-block }
boolean
{: .label .fs-1 }

Returns `true` or `false`.

## `search.month`
{: .d-inline-block }
number
{: .label .fs-1 }

Returns the month as a number, e.g. `2` would represent February.

## `search.series_id`
{: .d-inline-block }
string
{: .label .fs-1 }

Returns the series_id searched.

## `search.subcategory`
{: .d-inline-block }
string
{: .label .fs-1 }

Returns the subcategory searched.

## `search.sort`
{: .d-inline-block }
string
{: .label .fs-1 }

Returns `name_asc`, `name_desc`, `duration_asc`, `duration_desc`, `departure_date_asc` or `departure_date_desc`.

## `search.year`
{: .d-inline-block }
number
{: .label .fs-1 }

Returns the year as a number, e.g. `2023`.
