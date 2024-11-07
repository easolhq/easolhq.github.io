---
layout: default
title: Package step product search
parent: Tags
grand_parent: Reference
---

# Package step product search

The package step product search tag executes a search on the given step's listable products, and paginates the results. The results are [PackageStepProducts]({% link docs/reference/objects/package/product.md %}). The only parameter it accepts right now is `step_id`. When we use this on the package booking template, we'll have access to this via the `package_step`.

##### Input
{% raw %}
```liquid
{% package_step_product_search step_id: package_step.id, page_size: 3 %}
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

## Pagination

The results of this search are paginated for performance reasons.
You can paginate results into equal page sizes, defining the number of results to display per page using the `page_size` attribute. There is a maximum page size of 100.