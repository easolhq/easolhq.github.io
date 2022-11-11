---
layout: default
title: Link
parent: Objects
---

The `Link` object has the following attributes.

# link.host _(deprecated)_

The host of the URL for this link.

> **Deprecated**
>
> This is deprecated.

# link.linked_resource

The object associated with the link, if there is one. This can be one of the following:

- [Page]({% link docs/reference/objects/page.md %})
- [Product]({% link docs/reference/objects/product/index.md %}) (for experiences and accommodations)
- [Blog post]({% link docs/reference/objects/blog_post.md %})

You can use the `type` attribute to distinguish between these. For example:

```
{% raw %}
{% case link.linked_resource.type %}
{% when "page" %}
    ...
{% when "experience" %}
    ...
{% when "accommodation" %}
    ...
{% when "blog_post" %}
    ...
{% endcase %}
{% endraw %}
```

It will return `nil` if the link uses an external URL.

# link.new_tab

Returns true if clicking this link should open a new tab.

# link.path _(deprecated)_

The path of the URL for this link.

> **Deprecated**
>
> This is deprecated as it will return a full URL. Please use `link.url` instead.

# link.url

The full URL for the link.
