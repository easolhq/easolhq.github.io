---
layout: default
title: Templates
parent: Theme architecture
---

# Templates

The templates directory contains a theme’s template files, which control what's rendered on each type of page.

## Blog overview
Used to build a blog index page, displaying all posts. 

The blog overview template consists of a `index.html` and a `index.css` file.

Blog posts are passed via a `posts` array of [Post]({% link /docs/reference/objects/blog_post.md %}) objects.

The blog overview page automatically implements pagination, displaying 12 posts per page. A [Pagination]({% link /docs/reference/objects/pagination.md %}) object can accessed via `paginate` in the html template in order to generate links to other pages, display page counts etc.

The blog overview page is automatically generated at `site.com/blog`.

## Blog post
Displays a single blog post.

The blog post template consists of a `index.html` and a `index.css` file.

The blog post is passed via a single `post` [Post]({% link /docs/reference/objects/blog_post.md %}) object.

The blog overview page automatically implements pagination, displaying 12 posts per page. A [Pagination]({% link /docs/reference/objects/pagination.md %}) object can accessed via `paginate` in the html template in order to generate links to other pages, display page counts etc.

Each blog post is automatically generated at `site.com/blog/post-slug`.

## Content
Displays a single content biography.

The content template consists of a `index.html` file.

The content biography is passed via a single `content` [Content]({% link /docs/reference/objects/content_library.md %}) object.

Each content page is automatically generated at `site.com/contents/content-slug`.

## Product
Displays a single product.

The product template consists of a `index.html` and a `index.css` file.

The product is passed via a single `product` [Product]({% link /docs/reference/objects/product %}) object.

Each product page is automatically generated at `site.com/products/product-slug`.

## Selections
Optional {: .label }

Selections is a way for a customer to come back after booking and make selections on their order, e.g. which workshops they’ll attend.

The selections template consists of a `index.html` file.

The selection is passed via a single `item` [Modifier Selection]({% link /docs/reference/objects/modifier_selection_session.html %}) object. It combines the data for a particular line item with the guest information for the user currently logged in.

Each selection page is automatically generated at `site.com/items/*booking-id*/selections` and can only be accessed by the user whose booking the selection applies to.