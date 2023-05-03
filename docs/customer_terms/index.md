---
layout: default
title: Customer terms
has_children: true
nav_order: 14
---

# Customer terms pages
Creators can add customer terms to their site within their company settings. These are broken down into three key pages which are automatically generated at the following urls:

| Customer Terms        | Url                                  |
|:----------------------|:-------------------------------------|
| Payment Plan Terms    | site.com/terms/payment_plan_terms    |
| Terms and Conditions  | site.com/terms/terms_and_conditions  |
| Privacy Policy        | site.com/terms/privacy_policy        |

These are linked to from each Creator's checkout page.

You are not able to amend the html of terms pages, however, any general styles added to the [index.css]({% link docs/theme_architecture/assets.md %}) of a theme are also applied to the terms pages.

To style the terms pages specifically within the [index.css]({% link docs/theme_architecture/assets.md %}) file, use the helper class `.terms-page`. This class has been added to the body of each of the three terms pages and can be used to target specific elements on those pages.
