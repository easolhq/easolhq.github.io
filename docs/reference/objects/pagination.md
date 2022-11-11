---
layout: default
title: Pagination
parent: Objects
---

When using a `pagination` object you will have access to the following methods to manage the layout and UI.

# pagination.collection_size

The total number of items returned in the collection

# pagination.current_offset

The number of items on previous pages, i.e. that we've had to skip to get to the current page
If our collection was `[1,2,3,4]` and the offset was 2 then our result would be `[3,4]` 

# pagination.current_page

The page number currently being displayed. This is driven by a query param e.g. `url.com/?page=3` 

# pagination.next

Returns a pagination link to go to the next page, if there is no next page this won't be set

# pagination.page_count

The total number of pages

# pagination.page_size

The maximum number of items displayed on each page

# pagination.parts

This returns an array of pagination links which represent links to specific page numbers of the collection, this handles abbreviation to an ellipsis if the number of pages is too high.

# pagination.previous

Returns a pagination link to go to the previous page, if there is no previous page this won't be set

