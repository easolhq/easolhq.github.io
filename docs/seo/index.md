---
layout: default
title: SEO
has_children: true
nav_order: 15
has_toc: false
---

# SEO

Some SEO considerations when developing an Easol theme:
- Canonical tags are added to the head of all pages, you don't need to worry about query parameters or pagination cannibalising page results.
- Some [Metadata]({% link docs/seo/metadata.md %}) can be configured on individual site pages and is added to product pages. 
- Once a product (experience or accommodation) is published a merchandising page (/products/*) is automatically published and made available to search engines. The page cannot be unpublished without also unpublishing the product.
