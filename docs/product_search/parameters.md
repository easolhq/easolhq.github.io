---
layout: default
title: Product Search Parameters
parent: Product Search
---

# Product Search Parameters
Product search is based on parameters that determine which products are returned and in which order.

### active_promotion
Accepts: `true` or `false`.<br>
Passing `true` will return items with a currently active [promotion]({% link docs/reference/objects/product/promotion.md %}#promotionactive).

##### as a search tag attribute
{% raw %}
```
{% product_search active_promotion: true %}
{% endproduct_search %}
```
{% endraw %}

##### as a query paramameter
```
https://mysite.com/search?search[active_promotion]=true
```

### category
Accepts a string and is case-sensitive.<br>
Currently the available Easol categories are: "Festival", "Wellness", "Adventure", "Food and Drink", "Active".<br>
Will accept either a single category or an array.<br>
Will return products which match the [category]({% link docs/reference/objects/product/index.md %}#productcategory) passed.

##### as a search tag attribute
{% raw %}
```
{% product_search category: 'Active' %}
{% endproduct_search %}

{% product_search subcategory: ['Active','Adventure'] %}
{% endproduct_search %}
```
{% endraw %}

##### as a query paramameter
```
https://mysite.com/search?search[category]=active
```

### country
Accepts any of the Easol predefined [countries]({% link docs/reference/objects/product/index.md %}#productcountry) as either Country Codes or Country Names<br>
Will accept either a single country or an array.<br>
Will return products which match the country passed.

##### as a search tag attribute
{% raw %}
```
{% product_search country: 'FR' %}
{% endproduct_search %}

{% product_search country: ['FR','DE'] %}
{% endproduct_search %}
```
{% endraw %}

##### as a query paramameter
```
https://mysite.com/search?search[country]=DE
```

### departure_date
Accepts an object which specifies how to handle the search through `equal_to` `greater_than` `greater_or_equal_than` or `less_than` each taking a date in SQL format `YYYY-MM-DD`.
Will return experiences which depart within the [departure date]({% link docs/reference/objects/product/index.md %}#productdepart_on) range.

##### as a search tag attribute
{% raw %}
```
{% product_search departure_date: {greater_or_equal_than: 'now', less_than: '2023-12-28' } %}
{% endproduct_search %}
```
{% endraw %}

##### as query paramameters
```
https://mysite.com/search?search[departure_date][greater_or_equal_than]=2022-11-19&search[departure_date][less_than]=2023-12-28
```

### departure_month
Accepts a month as either a 3 letter abreviation, or the month number i.e. `Apr` or `4`.<br>
Will return experiences which [depart]({% link docs/reference/objects/product/index.md %}#productdepart_on) within the specified month, this may be across multiple years e.g. Apr 2023 and Apr 2024.

##### as a search tag attribute
{% raw %}
```
{% product_search departure_month: 'Apr' %}
{% endproduct_search %}

{% product_search departure_month: 4 %}
{% endproduct_search %}
```
{% endraw %}

##### as query paramameters
```
https://mysite.com/search?search[departure_month]=Apr
https://mysite.com/search?search[departure_month]=4
```

### duration
Accepts an object which specifies how to handle the search, through `equal_to` `greater_than` or `less_than` each taking a number of days.<br>
Will return experiences which have a [duration]({% link docs/reference/objects/product/index.md %}#productduration) within the defined range.<br>
Note: Experience [durations]({% link docs/reference/objects/product/index.md %}#duration) can be returned as a number of hours, 1 day or a number of nights, whereas product_search `duration` always takes the duration as a number of days or number of hours. i.e. `duration: {equal_to: 2}` will return experiences that have a duration of 2 hours or 1 night (2 days).

##### as a search tag attribute
{% raw %}
```
{% product_search duration: {greater_than: 3, less_than: 8 } %}
{% endproduct_search %}
```
{% endraw %}

##### as query paramameters
```
https://mysite.com/search?search[duration][greater_than]=3&search[duration][less_than]=8
```

### exclude_sold_out_products
Accepts: `true` or `false`.<br>
Passing `true` will exclude [sold out]({% link docs/reference/objects/product/index.md %}#productsold_out) products from the products returned.

##### as a search tag attribute
{% raw %}
```
{% product_search exclude_sold_out_products: true %}
{% endproduct_search %}
```
{% endraw %}

##### as a query paramameter
```
https://mysite.com/search?search[exclude_sold_out_products]=true
```

### include_organisation_products
Accepts: `true` or `false`.<br>
Passing `true` will include products from other companies which are linked in the same organisation.

##### as a search tag attribute
{% raw %}
```
{% product_search include_organisation_products: true %}
{% endproduct_search %}
```
{% endraw %}

##### as a query paramameter
```
https://mysite.com/search?search[include_organisation_products]=true
```

### name
Executes a partial search on the string passed in. Case insensitive.<br>
Will return any products whose [name]({% link docs/reference/objects/product/index.md %}#productname) matches the argument.

##### as a search tag attribute
{% raw %}
```
{% product_search name: 'my experience' %}
{% endproduct_search %}
```
{% endraw %}

##### as a query paramameter
```
https://mysite.com/search?search[name]=my+experience
```

### series_id
Accepts a series id.<br>
Will return products which match the [series id]({% link docs/reference/objects/series.md %}#seriesid) passed.

##### as a search tag attribute
{% raw %}
```
{% product_search series_id: 'abcd1234-1234-abcd-1234-abcd1234abcd' %}
{% endproduct_search %}
```
{% endraw %}

##### as a query paramameter
```
https://mysite.com/search?search[series_id]=abcd1234-1234-abcd-1234-abcd1234abcd
```

### subcategory
Accepts a string and is case-sensitive.<br>
Will accept either a single subcategory or an array.<br>
Will return products which match the [subcategory]({% link docs/reference/objects/product/index.md %}#productsubcategory) passed.

##### as a search tag attribute
{% raw %}
```
{% product_search subcategory: 'Wellness' %}
{% endproduct_search %}

{% product_search subcategory: ['4 Star','5 Star'] %}
{% endproduct_search %}
```
{% endraw %}

##### as a query paramameter
```
https://mysite.com/search?search[subcategory]=wellness
```

### page_size
Accepts a number.<br>
Will determine how many results are shown per page. If this is not included it will default to 12 results per page.

Page size cannot be passed as a query parameter.

##### as a search tag attribute
{% raw %}
```
{% product_search page_size: 8 %}
{% endproduct_search %}
```
{% endraw %}

### sort
Accepts `name_asc`, `name_desc`, `duration_asc`, `duration_desc`, `departure_date_asc` and `departure_date_desc`, where the `_asc` and `_desc` parts represent ascending and descending orders respectively.<br>
Will determine the order of the returned products.

##### as a search tag attribute
{% raw %}
```
{% product_search sort: `departure_date_asc` %}
{% endproduct_search %}
```
{% endraw %}

##### as a query paramameter
```
https://mysite.com/search?search[sort]=departure_date_asc
```