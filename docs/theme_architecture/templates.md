---
layout: default
title: Templates
parent: Theme architecture
nav_order: 4
---

# Templates

The templates directory contains a theme’s template files, which control what's rendered on each type of page.

## Blog overview
Used to build a blog index page, displaying all posts. 

The blog overview template consists of an `index.html` and an `index.css` file.

Blog posts are passed via a `posts` array of [Post]({% link docs/reference/objects/blog_post.md %}) objects.

The blog overview page automatically implements pagination, displaying 12 posts per page. A [Paginate]({% link docs/reference/objects/paginate.md %}) object can be accessed via `paginate` in the `index.html` code to generate links to other pages, display page counts etc.

The blog overview page is automatically generated at `site.com/blog`.

## Blog post
Displays a single blog post.

The blog post template consists of an `index.html` and an `index.css` file.

The blog post is passed via a single `post` [Post]({% link docs/reference/objects/blog_post.md %}) object.

Each blog post is automatically generated at `site.com/blog/post-slug`.

## Content
Displays a single content biography.

The content template consists of an `index.html` file.

The content biography is passed via a single `content` [Content]({% link docs/reference/objects/content_library.md %}) object.

Each content page is automatically generated at `site.com/contents/content-slug`.

## Product
Displays a single product.

The product template consists of an `index.html` and an `index.css` file.

The product is passed via a single `product` [Product]({% link docs/reference/objects/product/index.md %}) object.

Each product page is automatically generated at `site.com/products/product-slug`. If the product is part of a series, the product page will also be available at `site.com/products/*series-slug*/*product-departure-date*`.

Product templates can include a [schema]({% link docs/theme_architecture/blocks/schema/index.md %}) in order to define the [variables]({% link docs/theme_architecture/blocks/schema/variables/index.md %}) a Creator can use to customise the template.

## Selections
`Optional`

Selections is a way for a customer to come back after booking and make selections on their order, e.g. which workshops they’ll attend.

The selections template consists of an `index.html` file.

The selection is passed via a single `item` [Modifier Selection]({% link docs/reference/objects/modifier_selection_session.md %}) object. It combines the data for a particular line item with the guest information for the customer currently logged in.

Each selection page is automatically generated at `site.com/items/*booking-id*/selections` and can only be accessed by the customer to whose booking the selection applies.

## Recommendation
`Optional`

The template is passed via a single `recommendation` [Recommendation]({% link docs/reference/objects/recommendation.md %}) object.

The recommendation page is automatically generated at site.com/recommendations/*recommendation_slug* when a valid recommendation has been created.

This template will only render if it has been configured on the associated site - otherwise, the default recommendation page will be rendered.

## Package booking
`Optional`

Packages allow creators to build their own custom multi-step booking journeys.

Each step will expose a number of creator-selected variants that the customer may choose from to complete their package booking.

On each step of the journey, the customer adds one of the available options and moves on to the next step.

Behind the scenes, the platform is "orchestrating" the booking journey by linking them from step URL to step URL until checkout, and steps are rendered using the Package Booking template.

The details of the current step (name, description, available variants, URL of the next page) are exposed to the template via the `package_step` [Package Step]({% link docs/reference/objects/package/step.md %}) object.

Package booking templates can include a [schema]({% link docs/theme_architecture/blocks/schema/index.md %}) in order to define the [variables]({% link docs/theme_architecture/blocks/schema/variables/index.md %}) a Creator can use to customise the template.
