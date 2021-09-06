---
layout: default
title: Page
parent: Objects
---

Page is a _global_ variable, meaning it should always be accessible to you when developing themes on Easol

If a user visits https://example.com/shop/my-product-2021-10-09 for example

The following will be available in the templates:

# page.url

The full url of the request

`=> https://example.com/shop/my-product-2021-10-09`

# page.host

The request host

`=> example.com`

# page.path

The relative path of the request

`=> /shop/my-product-2021-10-09`
