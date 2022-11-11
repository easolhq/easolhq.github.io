---
layout: default
title: Best Practices
has_children: true
nav_order: 17
---

# Best Practices
To optimise the site builder experience for Creators, we recommend the following best practices.

## Image sizing
Including raw images in the block code can greatly slow down page load speed. Each image uploaded via the Easol platform is resized to six different image sizes which can be accessed via the image's [Image]({% link docs/reference/objects/image.md %}#imageurl) object. By specifying an image size you can ensure you use the smallest possible image required. 

## Block previews
When choosing which blocks to add to their site pages, Creators are shown a preview of each block. We therefore recommend assigning [default values]({% link docs/theme_architecture/blocks/schema/variables/index.md %}#default) to block variables whenever possible to ensure that Creators have an accurate visual representation of the block.

## Default colours
Creators' [site styles]({% link docs/site_styles/index.md %}) are applied to block previews. To ensure the previews are aligned with Creator branding we recommend assigning default colours as a colour from the Creators [theme palette]({% link docs/theme_architecture/blocks/schema/variables/variable_types/color.md %}#theme-palette).

## Scoping styles in blocks
A Creator may choose to have multiple instances of a block in a single page. Therefore when including styles or javascript within a block schema these should be scoped to the block to ensure there are no conflicts with other blocks on the page. This can be done by referencing the unique [block.id]({% link docs/reference/objects/block.md %}#theme-palette) in a block.

## Cache tags
To improve page load speed and reduce database calls, content should be wrapped in [cache tags]({% link docs/reference/tags/cache_tag/index.md %}) where possible, particularly when rendering a large number of [products]({% link docs/reference/objects/product/index.md %}) or [variants]({% link docs/reference/objects/product/variant/index.md %}). The cache clears every 30 minutes by default and refreshes on the next page load, however, a custom expiry time can also be set.