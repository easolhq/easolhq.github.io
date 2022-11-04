---
layout: default
title: Shop pages
parent: Carts
nav_order: 1
---

# Easol shop pages
In addition to a [product page]({% link docs/theme_architecture/templates.md %}), each experience has an automatically generated 'shop' page, which can be found at `site.com/shop/product-slug`. 

This page includes key details of the experience including the name, country, dates, tagline and the hero image. On this page customers are able to add items to their cart, remove items from their cart, update item quantities and see a breakdown of the contents of their cart before proceeding to checkout.

## Shop page customisation
The Creator's [brand colours]({% link docs/site_styles/index.md %}) set under My Site > Styles are applied to some elements of the shop page by default. 

You are not able to amend the html or add additional javascript to shop pages. However, further customisations can be applied to the shop page by adding additional styles into the [index.css]({% link docs/theme_architecture/assets.md %}) file of a theme, using selector `.cart-shop` to scope them to the shop pages.

> Styles added to the [index.css]({% link docs/theme_architecture/assets.md %}) of a theme are also applied to the shop pages. We recommend testing shop pages for a variety of [product configurations]({% link docs/product_management_and_merchandising/accommodation_and_experience_products.md %}) after updating global styles to ensure the shop page still functions correctly.