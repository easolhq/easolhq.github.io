---
layout: default
title: Metadata
parent: SEO
---

Creators can add metadata to their site pages.

If this isn't added, the title is constructed from the page name and Company, the description tag is empty and no image tag exists, e.g.

{% raw %}
```html
<meta name="title" property="og:title" content="Company | Page name">
<meta name="description" property="og:description">
```
{% endraw %}

Once this has been configured this might instead be:

{% raw %}
```html
<meta name="title" property="og:title" content="My Title">
<meta name="description" property="og:description" content="My description ">
<meta name="image" property="og:image" content="<url to social image>">
```
{% endraw %}

For Product/Merchandising Pages, the image is the hero image and the description is the tagline.
