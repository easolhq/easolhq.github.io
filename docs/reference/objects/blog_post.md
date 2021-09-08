---
layout: default
title: Blog post
parent: Objects
---

When using a `blog_post` object you have access to the following attributes

# blog_post.title

Returns the title of the blog_post

# blog_post.body

Returns the body of the blog_post, this is a rich text field and so will return html

# blog_post.hero_image

Returns the blog post's [hero image]({% link docs/reference/objects/image.md %})

# blog_post.published_at

If blog post is published it will return the published_at as a timestamp, this can then be used in conjunction with liquids[ built in filters ](https://shopify.github.io/liquid/filters/date/)
