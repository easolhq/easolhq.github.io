---
layout: default
title: Blog Post
parent: Objects
---

When using a `blog_post` object you have access to the following attributes.

# blog_post.author

The blog post's [author]({% link docs/reference/objects/author.md %}).

# blog_post.body

The blog post's body as a string.

# blog_post.hero_image

The blog post's hero [image]({% link docs/reference/objects/image.md %}).

# blog_post.next_post

A `blog_post` object for the next post for the blog.

# blog_post.previous_post

A `blog_post` object for the previous post for the blog.

# blog_post.published_at

The date the blog was published as a timestamp. This can then be used in conjunction with Liquid's [ built in filters ](https://shopify.github.io/liquid/filters/date/).

# blog_post.tagline

The blog post's tagline as a string.

# blog_post.title

The blog post's title as a string.

# blog_post.type

The string `"blog_post"`.

# blog_post.url

The URL of the blog post as a string.
