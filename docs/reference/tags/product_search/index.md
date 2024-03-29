---
layout: default
title: Product search
parent: Tags
grand_parent: Reference
---

# Product search

For additional examples see [here]({% link docs/product_search/index.md %}).

The Product Search Tag executes a search on the company's experiences, it then paginates those results.

##### input
{% raw %}
```liquid
{% product_search name: 'Beyond', duration: { greater_than: 3, less_than: 8 }, page_size: 12, sort: 'departure_date_asc' %}
    {% for item in result.items %}
        <p>{{ item.name }}</p>
    {% endfor %}
    <div>
        {{ paginate.collection_size }} Results
        {{ paginate | default_pagination }}
    </div>
{% endproduct_search %}
```
{% endraw %}

##### output
{% raw %}
```html
<p>Beyond Sahara</p>
<p>Beyond Archipelago</p>
<p>Beyond Sahara Friends & Family</p>
<p>Beyond Archipelago Friends & Family</p>
<p>Beyond Asia</p>
<div>
    112 Results
    <span class="prev">
    <a href="http://beyondadventures.com/pagination-test?page=2">Previous</a>
    </span>
    <span class="page">
    <a href="http://beyondadventures.com/pagination-test?page=1">1</a>
    </span>
    <span class="page">
    <a href="http://beyondadventures.com/pagination-test?page=2">2</a>
    </span>
    <span class="page current">3</span>
    <span class="page">
    <a href="http://beyondadventures.com/pagination-test?page=4">4</a>
    </span>
    <span class="page">
    <a href="http://beyondadventures.com/pagination-test?page=5">5</a>
    </span>
    <span class="deco">&hellip;</span>
    <span class="page">
    <a href="http://beyondadventures.com/pagination-test?page=9">9</a>
    </span>
    <span class="next">
    <a href="http://beyondadventures.com/pagination-test?page=4">Next</a>
    </span>
</div>
```
{% endraw %}

The tag returns an `items` array and a `Paginate` pagination object to the block passed in, the items array represents 1 page of the results from the search.


## Pagination

The results of this search are paginated for performance reasons, with this you can define the number of results to display per page as the `page_size` attribute, which defaults to 12.

## Available months
The product search returns `available_months`, an array of `Date` objects, which can be used to construct the month and year filters for searching.

Each `Date` is dated 1st of the month, and there is one for each month in which a product's slot `start_on` date occurs.

E.g. Today is `1st Jan 2024``. You have a product with a 10 day duration, with the following slots (all future or ongoing);
- `31th Dec 2023`
- `15th Jan 2024`
- `20th Jan 2024`
- `31th Jan 2024`
- `28th Feb 2024`
The `available_months` will be `Date`s with the following dates:
- `1st Dec 2023`
- `1st Jan 2024`
- `1st Feb 2024`

You can use these to construct search filters, e.g.

##### input
{% raw %}
```liquid
{% product_search %}
  ...

  <select name="departure_month">
    {% for month in available_months %}
      <option value="{{ month | date: "%m" }}">
        {{ month | date: "%B" }}
      </option>
    {% endfor %}
  </select>
{% endproduct_search %}
```
{% endraw %}

##### output
{% raw %}
```html
  <select name="departure_month">
    <option value="12">December</option>
    <option value="01">January</option>
    <option value="02">February</option>
  </select>
```
{% endraw %}

## Search Params

Search params can be handled in one of two ways:

### Passing explicit attributes

It's possible to use any of the following attributes in the search tag itself, this is useful for building a page responsible for a specific type of product.

#### active_promotion
Passing `true` to this will mean all items returned will have a currently active promotion.

#### category
Will search for products which match the category passed, this must use one of Easol's predefined categories and will accept either a single Category or an array.

#### country
This attribute accepts either Country Codes or Country Names and can be passed as a single attribute or as an array, e.g. `country: ['FR', 'DE']`

#### departure_date
This attribute takes an object which specifies how to handle the search, through `equal_to` `greater_than` `greater_or_equal_than` or `less_than` each taking a date in SQL format `YYYY-MM-DD` e.g. `departure_date: {greater_than: 'now', less_than: '2019-12-28' }`

#### departure_month
This allows you to specify which month the trips should depart in, e.g. passing `departure_date: 'Apr'` would return any trips departing in april 2020, april 2021 ..., You can also pass the number of the month i.e. `departure_month: 4` would return the same results.

#### duration
This attribute takes an object which specifies how to handle the search, through `equal_to` `greater_than` or `less_than` each taking a number of days e.g. `duration: {greater_than: 3, less_than: 8 }`

#### name
This executes a partial search on the string passed in and will return any products whose name matches the argument.

#### subcategory
Will search for products which match the subcategory passed, this must use one of Easol's predefined subcategories and will accept either a single Subcategory or an array.

#### page_size
Will determine how many results are shown per page. If this is not included it will default to 12 results per page. e.g. `page_size: 12`

#### include_organisation_products
This allows you to include products from other companies which are linked in the same organisation. e.g. `include_organisation_products: true`

#### sort
The sorting order of results. The available options are: `name_asc`, `name_desc`, `duration_asc`, `duration_desc`, `departure_date_asc` and `departure_date_desc`, where the `_asc` and `_desc` parts represent ascending and descending orders respectively.

#### series_id
The id of the series to filter by.

### As query params

It's also possible to pass search params as query params, this is useful when building dynamic search pages.

Any of the above attributes can be used as a query param and should all be namespaced to search

e.g.
`http://beyondadventures.com/search?search[name]=beyond&search[departure_date][greater_than]=2021-11-22`

Params passed through a query param will overwrite any of those specified as an attribute

## Sorting

It's possible to also sort the results by name, departure date and duration. This can be done either through an attribute on the tag or through the search query param.

These should be passed as a string describing the dimension to sort on and the direction either ascending or descending. i.e. one of

`name_asc` `name_desc` `duration_asc` `duration_desc` `departure_date_asc` `departure_date_desc`

{% raw %}
```liquid
{% product_search name: 'Beyond', sort: 'name_asc' %}
    {% for item in result.items %}
        <p>{{ item.name }}</p>
    {% endfor %}
    <div>
        {{ paginate.collection_size }} Results
        {{ paginate | default_pagination }}
    </div>
{% endproduct_search %}
```
{% endraw %}

or

`http://beyondadventures.com/search?search[name]=beyond&search[sort]=name_asc`

## Accessing the query params

Once the search has been executed, it can be helpful to get a reference to the params and values in the search.
For that, we can use the `Search` object, which exposes all of the params listed above in the "Passing explicit attributes" section.

{% raw %}
```liquid
{{ search.departure_date }}

or

{{ search["departure_date"] }}
```
{% endraw %}
