---
layout: default
title: Page
parent: Objects
---

# Page
{: .d-inline-block }
object
{: .label .fs-1 }

The Page object represents a site page.

<br>

#### Attributes

## `page.host`
{: .d-inline-block }
string
{: .label .fs-1 }

The site's domain.

`=> example.com`

## `page.params`
{: .d-inline-block }
object
{: .label .fs-1 }

The query params included in the current URL.

For example, given the URL https://my-url.com?page=4,
using {% raw %}`{{page.params.page}}`{% endraw %} would return "4".

## `page.path`
{: .d-inline-block }
string
{: .label .fs-1 }

The relative path of the request.

`=> /products/my-product-2021-10-09`

## `page.type`
{: .d-inline-block }
string
{: .label .fs-1 }

Will always return "`page`". This is useful when an object is returned from [`menu_item.linked_resource`]({% link docs/reference/objects/menu/menu_item.md %}#itemlinked_resource) and you need to determine if it is a `Page` object.

## `page.url`
{: .d-inline-block }
string
{: .label .fs-1 }

The full url of the page.

`=> https://example.com/products/my-product-2021-10-09`
