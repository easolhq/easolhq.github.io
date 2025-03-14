---
layout: default
title: Paginate
parent: Objects
---

# Paginate
{: .d-inline-block }
object
{: .label .fs-1 }

#### Attributes

## `paginate.collection_size`
{: .d-inline-block }
number
{: .label .fs-1 }

The total number of items returned in the collection.

## `paginate.current_offset`
{: .d-inline-block }
number
{: .label .fs-1 }

The number of items on previous pages, i.e. that we've had to skip to get to the current page.
If our collection was `[1,2,3,4]` and the offset was 2 then our result would be `[3,4]`.

## `paginate.current_page`
{: .d-inline-block }
number
{: .label .fs-1 }

The page number currently being displayed. This is driven by a query param e.g. `url.com/?page=3`.

## `paginate.next`
{: .d-inline-block }
string
{: .label .fs-1 }

The pagination link to go to the next page, if there is no next page this won't be set.

## `paginate.page_count`
{: .d-inline-block }
number
{: .label .fs-1 }

The total number of pages.

## `paginate.page_size`
{: .d-inline-block }
number
{: .label .fs-1 }

The maximum number of items displayed on each page.

## `paginate.parts`
{: .d-inline-block }
array of strings
{: .label .fs-1 }

An array of pagination links which represent links to specific page numbers of the collection, this handles abbreviation to an ellipsis if the number of pages is too high.

## `paginate.previous`
{: .d-inline-block }
string
{: .label .fs-1 }

The pagination link to go to the previous page, if there is no previous page this won't be set.
