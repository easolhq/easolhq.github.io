---
layout: default
title: Company
nav_order: 2
parent: Objects
---

Company is a _global_ variable, meaning it should always be accessible to you when developing on canvas

# company.products

This will return an array of the companies published [products]({% link docs/reference/objects/product/index.md %}) excluding any private products
e.g.

{% raw %}
```liquid
{% for product in company.products %}
    {{ product.name }}
{% endfor %}
```
{% endraw %}


# company.series

This will return an array of the companies [series]({% link docs/reference/objects/series.md %})

# company.biographies

This will return an array of the companies [biographies]({% link docs/reference/objects/biography.md %})

# company.countries

This will return an array of the names of countries with products
e.g.

# company.name

Returns the name of the company

# company.subdomain

Returns the subdomain of the company

# company.facebook_username

Returns the facebook username set within My Site > Social

# company.instagram_username

Returns the instagram username set within My Site > Social

# company.twitter_username

Returns the twitter username set within My Site > Social

# company.avatar_logo

Returns the company's logo as an [image]({% link docs/reference/objects/image.md %}). The logo is set within Settings > Your Brand.

# company.logo

Returns the company's workmark logo as an [image]({% link docs/reference/objects/image.md %}). The logo is set within Settings > Your Brand.

