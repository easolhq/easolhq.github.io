---
layout: default
title: Company
parent: Objects
---

Company is a _global_ variable, meaning it will always be accessible on any Liquid template.

# company.authors

A list of all the company's [authors]({% link docs/reference/objects/author.md %}).

# company.avatar_logo

The company's logo as an [image]({% link docs/reference/objects/image.md %}). The logo is set within **Settings** > **Your Brand**.

# company.biographies

A list of all the company's [biographies]({% link docs/reference/objects/content_library.md %}).

# company.countries

A list of the names of countries with products. e.g. `["Canada", "United Kingdom"]`

# company.facebook_username

The Facebook username set within **My Site** > **Social**.

# company.instagram_username

The Instagram username set within **My Site** > **Social**.

# company.logo

The company's wordmark logo as an [image]({% link docs/reference/objects/image.md %}). The logo is set within **Settings** > **Your Brand**.
# company.name

The name of the company.

# company.posts

A list of all the company's published [blog posts]({% link docs/reference/objects/blog_post.md %}), ordered by the most recently published first.

# company.products

A list of the company's published [products]({% link docs/reference/objects/product/index.md %}) excluding any private products.
e.g.

{% raw %}
```liquid
{% for product in company.products %}
    {{ product.name }}
{% endfor %}
```
{% endraw %}


# company.series

A list of all the company's [series]({% link docs/reference/objects/series.md %}).

# company.subdomain

The subdomain of the company.

# company.twitter_username

The Twitter username set within **My Site** > **Social**.
