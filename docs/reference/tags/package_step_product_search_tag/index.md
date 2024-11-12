---
layout: default
title: Package step product search
parent: Tags
grand_parent: Reference
---

# Package step product search

The package step product search tag executes a search on the given step's listable products, and paginates the results. The results are [PackageStepProducts]({% link docs/reference/objects/package/product.md %}). This automatically uses the step that the current page is loaded in the context of.

##### Input
{% raw %}
```liquid
{% package_step_product_search page_size: 3 %}
    {% for item in result.items %}
        <p>{{ item.product.name }}</p>
    {% endfor %}
    <div>
        {{ paginate.collection_size }} Results
        {{ paginate | default_pagination }}
    </div>
{% endpackage_step_product_search %}
```
{% endraw %}

##### Output
{% raw %}
```html
<p>Hotel option 1</p>
<p>Hotel option 2</p>
<p>Hotel option 3</p>
<p>Hotel option 4</p>
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

## Tag-based filtering

If the company has added tags to the step's products, these can be used to filter the results outputted by the search tag.

Product tags are textual values that identify attributes of the products. They are grouped under categories which the company is also able to define.

Some examples of these might be "Star Rating", "Amenities", "Distance" etc. Consult the company for the available tags and categories.

**Syntax**

`package_step_product_search` filters results if one or more `search` query parameters are present in the URL. The search query parameters are in the format `search[<tag category>][]=<tag value>`; add as many as needed to filter the results.

You can specify multiple categories and values by repeating the `search[][]` query parameter.

At the moment, filtering returns products that match at least one of the provided values in _all_ of the filtered categories.

**Examples**

- `?search[Star Rating][]=5` - Products with a 5 star rating only.
- `?search[Star Rating][]=4&search[Star Rating][]=5` - Products with either a 4 star rating or a 5 star rating.
- `?search[Amenities][]=Pool&search[Star Rating][]=5` - Products with a 5 star rating and pool access.
- `?search[Amenities][]=Pool&search[Star Rating][]=5&search[Star Rating][]=4` - Products with pool access and either a 4 or 5 star rating.

## Pagination

The results of this search are paginated for performance reasons.
You can paginate results into equal page sizes, defining the number of results to display per page using the `page_size` attribute. There is a maximum page size of 100.
