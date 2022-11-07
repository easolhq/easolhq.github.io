---
layout: default
title: Product Search
has_children: true
nav_order: 8
---

# Product Search
Product search is based on query parameters that determine which products are returned and in which order. In addition to the search query itself, there are parameters that allow you to customize the search further, for example you could:

- Choose whether unavailable products are returned
- Return only products with active promotions
- Return products for a specific date range or year
- Sort the results by departure date

The product search is executed using the `product_search` [tag]({% link docs/reference/tags/product_search/index.md %}). The tag returns an `items` array of [products]({% link docs/reference/objects/product/index.md %}), a `paginate` [pagination]({% link docs/reference/objects/pagination.md %}) object and  a `search` search object. 

{% raw %}
```liquid
{% product_search name: 'Beyond', duration: { greater_than: 3, less_than: 8 }, page_size: 12, sort: 'departure_date_asc' %}
    {% for item in result.items %}
        <p>{{item.name}}</p>
    {% endfor %}
    <div>
        {{paginate.collection_size}} Results
        {{paginate | default_pagination}}
    </div>
{% endproduct_search %}
```
{% endraw %}

It's also possible to pass search parameters as query params, this is useful when building dynamic search pages.

{% raw %}
```
http://beyondadventures.com/search?search[name]=beyond&search[departure_date][greater_than]=2021-11-22&search[sort]=departure_date_asc
```
{% endraw %}

> Note: Parameters passed through query params will overwrite any of those specified as an attribute on the product_search tag.

## Pagination
The results of the search are paginated in order to speed page load, you can define the number of results displayed per page using the `page_size` parameter.

You can enable customers to move between the results pages using the `paginate` [pagination]({% link docs/reference/objects/pagination.md %}) object. The [default_pagination]({% link docs/reference/filters/pagination.md %}) filter can be used to return a complete pagination UI.


## Parameters
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
Accepts any of the Easol predefined categories.<br>
Will accept either a single category or an array.<br>
Will return products which match the [category]({% link docs/reference/objects/product/index.md %}#productcategory) passed.

##### as a search tag attribute
{% raw %}
```
{% product_search category: 'active' %}
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
Will return experiences which [depart]({% link docs/reference/objects/product/index.md %}#productdepart_on) within the month passed.

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
Note: Experience [durations]({% link docs/reference/objects/product/index.md %}#duration) can be returned as a number of hours, 1 day or a number of nights, whereas product_search `duration` always takes the duration as a number of days.

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
Executes a partial search on the string passed in.<br>
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
Accepts any of the Easol predefined subcategories.<br>
Will accept either a single subcategory or an array.<br>
Will return products which match the [subcategory]({% link docs/reference/objects/product/index.md %}#productsubcategory) passed.

##### as a search tag attribute
{% raw %}
```
{% product_search subcategory: 'wellness' %}
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

##### as a search tag attribute
{% raw %}
```
{% product_search page_size: 8 %}
{% endproduct_search %}
```
{% endraw %}

##### as a query paramameter
```
https://mysite.com/search?search[page_size]=8
```

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

## Accessing query params
Once the search has been executed, it can be helpful to get a reference to the params and values in the search. For that we can use the `search` object.

##### syntax
{% raw %}
```
{{search.departure_date}}
```
{% endraw %}

## Sorting
Results can be sorted asceding or descending by name, departure date or duration using the [sort]({% link docs/product_search/index.md %}#sort) parameter.

##### syntax
{% raw %}
```
{% product_search sort: `departure_date_asc` %}
{% endproduct_search %}
```
{% endraw %}