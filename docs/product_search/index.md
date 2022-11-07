---
layout: default
title: Product Search
has_children: true
nav_order: 8
has_toc: false
---

# Product Search
Product search is based on query parameters that determine which products are returned and in which order. In addition to the search query itself, there are parameters that allow you to customize the search further, for example you could:

- Choose whether unavailable products are returned
- Return only products with active promotions
- Return products for a specific date range or year
- Sort the results by departure date

The product search is executed using the [product_search tag]({% link docs/reference/tags/product_search/index.md %}). The tag returns an `items` array of [products]({% link docs/reference/objects/product/index.md %}), a `paginate` [pagination]({% link docs/reference/objects/pagination.md %}) object and  a `search` search object. 

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
The results of the search are paginated in order to speed page load, you can define the number of results displayed per page using the [page_size]({% link docs/product_search/parameters.md %}#page_size)parameter.

You can enable customers to move between the results pages using the `paginate` [pagination]({% link docs/reference/objects/pagination.md %}) object. The [default_pagination]({% link docs/reference/filters/pagination.md %}) filter can be used to return a complete pagination UI.


## Parameters
- [active_promotion]({% link docs/product_search/parameters.md %}#active_promotion)
- [category]({% link docs/product_search/parameters.md %}#category)
- [country]({% link docs/product_search/parameters.md %}#country)
- [departure_date]({% link docs/product_search/parameters.md %}#departure_date)
- [departure_month]({% link docs/product_search/parameters.md %}#departure_month)
- [duration]({% link docs/product_search/parameters.md %}#duration)
- [exclude_sold_out_products]({% link docs/product_search/parameters.md %}#exclude_sold_out_products)
- [include_organisation_products]({% link docs/product_search/parameters.md %}#include_organisation_products)
- [name]({% link docs/product_search/parameters.md %}#name)
- [series_id]({% link docs/product_search/parameters.md %}#series_id)
- [subcategory]({% link docs/product_search/parameters.md %}#subcategory)
- [page_size]({% link docs/product_search/parameters.md %}#page_size)
- [sort]({% link docs/product_search/parameters.md %}#sort)


## Accessing query params
Once the search has been executed, it can be helpful to get a reference to the params and values in the search. For that we can use the `search` object.

##### syntax
{% raw %}
```
{{search.departure_date}}
```
{% endraw %}

## Sorting
Results can be sorted asceding or descending by name, departure date or duration using the [sort]({% link docs/product_search/parameters.md %}#sort) parameter.

##### syntax
{% raw %}
```
{% product_search sort: `departure_date_asc` %}
{% endproduct_search %}
```
{% endraw %}