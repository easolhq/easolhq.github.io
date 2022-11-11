---
layout: default
title: Page
parent: Objects
---

This object represents a site page. It is returned for `page` variables used in blocks and is also available to [menu items]({% link docs/reference/objects/menu/menu_item.md %}) that are associated with a site page.

When using a `Page` object you have access to the following attributes.

# page.host

The site's domain.

`=> example.com`

# page.path

The relative path of the request.

`=> /products/my-product-2021-10-09`

# page.type

Will always return `"page"`. This is useful when an object is returned from [`menu_item.linked_resource`]({% link docs/reference/objects/menu/menu_item.md %}#itemlinked_resource) and you need to determine if it is a `Page` object.

# page.url

The full url of the page.

`=> https://example.com/products/my-product-2021-10-09`
