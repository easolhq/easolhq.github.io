---
layout: default
title: Post
parent: Variable types
---

# Post

Renders a select input from which a Creator can select a blog post.
Returns a [BlogPost]({% link docs/reference/objects/blog_post.md %}) object.
The post variable only accepts a default of `random` which will select a random post from the Creator's published blog posts.

##### syntax
{% raw %}
```
---
my_variable:
    type: post
    default: random
---

{{my_variable.url}}
```
{% endraw %}