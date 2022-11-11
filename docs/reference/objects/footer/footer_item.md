---
layout: default
title: Item
parent: Footer
---

The `item` object can be accessed on the footer object as below.

{% raw %}
```liquid
{% for item in footer.items %}
    <a href="{{item.path}}">{{item.label}}</a>
{% endfor %}
```
{% endraw %}

When using a `item` object you have access to the following attributes.

# item.label

The label for the footer item.

# item.linked_resource

The object associated with the footer item, if there is one. This can be one of the following:

- [Page]({% link docs/reference/objects/page.md %})
- [Product]({% link docs/reference/objects/product/index.md %}) (for experiences and accommodations)
- [Blog post]({% link docs/reference/objects/blog_post.md %})

You can use the `type` attribute to distinguish between these. For example:

```
{% raw %}
{% case item.linked_resource.type %}
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

It will return `nil` if the footer item uses an external URL.

# item.new_tab

Returns true if clicking this item should open a new tab.

# item.path _(deprecated)_

The target url for the footer item.

> **Deprecated**
>
> This is deprecated as it will return a full URL. Please use `item.url` instead.

# item.url

The target url for the footer item.
