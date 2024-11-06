---
layout: default
title: Experience slot search
has_children: true
nav_order: 8
has_toc: false
---

# Experience slot search

Experience slot search enables you to filter a Creator's experiences with a separate result for each departure date of each experience.

The experience slot search is executed using the [experience_slot_search tag]({% link docs/reference/tags/experience_slot_search_tag/index.md %}). The tag returns an `items` array of [ExperienceSlots]({% link docs/reference/objects/product/experience_slot.md %}), a `paginate` [Paginate]({% link docs/reference/objects/paginate.md %}) object, a `search` [Search]({% link docs/reference/objects/search_query.md %}) object, and an `available_months` array of Date objects (see [Liquid documentation for Dates](https://shopify.github.io/liquid/filters/date)).

The experience slot search will only return public, published dates i.e. where the experience is published and has not been marked as private under 'Manage product availability' in the product settings.

{% raw %}
```liquid
{% experience_slot_search name: 'Beyond', duration: { greater_than: 3, less_than: 8 }, page_size: 12, sort: 'departure_date_asc' %}
  {% for item in result.items %}
    <p>{{ item.name }}</p>
  {% endfor %}
  <div>
    {{ paginate.collection_size }} Results
    {{ paginate | default_pagination }}
  </div>
{% endexperience_slot_search %}
```
{% endraw %}

It's also possible to pass search parameters as query params, this is useful when building dynamic search pages.

{% raw %}
```
http://beyondadventures.com/search?search[name]=beyond&search[departure_date][greater_than]=2021-11-22&search[sort]=departure_date_asc
```
{% endraw %}

> Note: Parameters passed through query params will overwrite any of those specified as an attribute on the experience_slot_search tag.

## Pagination
The results of the search are paginated to speed up page load, you can define the number of results displayed per page using the [page_size]({% link docs/experience_slot_search/parameters.md %}#page_size) parameter.

You can enable customers to move between the results pages using the `paginate` [Paginate]({% link docs/reference/objects/paginate.md %}) object. The [default_pagination]({% link docs/reference/filters/pagination.md %}) filter can be used to return a complete pagination UI.

You can assign the value of a Liquid variable to `page_size`.

## Available Months
The experience slot search returns `available_months`, an array of `Date` objects, which can be used to construct the month and year filters for searching.

Each `Date` is dated 1st of the month, and there is one for each month in which a product's slots `start_on` dates occur.

E.g. Today is `1st Jan 2024`. You have a product with a 10 day duration, with the following slots (all future or ongoing);
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
{% experience_slot_search %}
  ...

  <select name="departure_month">
    {% for month in available_months %}
      <option value="{{ month | date: "%m" }}">
        {{ month | date: "%B" }}
      </option>
    {% endfor %}
  </select>
{% endexperience_slot_search %}
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

## Parameters
- [category]({% link docs/experience_slot_search/parameters.md %}#category)
- [country]({% link docs/experience_slot_search/parameters.md %}#country)
- [departure_date]({% link docs/experience_slot_search/parameters.md %}#departure_date)
- [departure_month]({% link docs/experience_slot_search/parameters.md %}#departure_month)
- [duration]({% link docs/experience_slot_search/parameters.md %}#duration)
- [duration_unit]({% link docs/experience_slot_search/parameters.md %}#duration_unit)
- [exclude_sold_out_products]({% link docs/experience_slot_search/parameters.md %}#exclude_sold_out_products)
- [name]({% link docs/experience_slot_search/parameters.md %}#name)
- [product_id]({% link docs/experience_slot_search/parameters.md %}#product_id)
- [subcategory]({% link docs/experience_slot_search/parameters.md %}#subcategory)
- [page_size]({% link docs/experience_slot_search/parameters.md %}#page_size)
- [sort]({% link docs/experience_slot_search/parameters.md %}#sort)

## Accessing query params
Once the search has been executed, it can be helpful to get a reference to the params and values in the search. For that, we can use the `search` [Search]({% link docs/reference/objects/search_query.md %}) object.

##### syntax
{% raw %}
```
{{ search.departure_date }}
```
{% endraw %}

## Sorting
Results can be sorted ascending or descending by name, departure date or duration using the [sort]({% link docs/experience_slot_search/parameters.md %}#sort) parameter.

##### syntax
{% raw %}
```
{% experience_slot_search sort: `departure_date_asc` %}
{% endexperience_slot_search %}
```
{% endraw %}
