---
layout: default
title: Request
parent: Objects
---

This object is accessible via the _global_ variable, `page`. This means it is always accessible when developing themes on Easol.

If a user visits https://example.com/shop/my-product-2021-10-09, for example, the following will be available in the templates:

# page.host

The request host.

`=> example.com`

# page.path

The relative path of the request.

`=> /shop/my-product-2021-10-09`

# page.url

The full url of the request.

`=> https://example.com/shop/my-product-2021-10-09`
