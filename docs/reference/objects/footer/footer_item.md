---
layout: default
title: Item
parent: Footer
---

# Footer Item
{: .d-inline-block }
object
{: .label .fs-1 }

The `Item` object can be accessed on the [`Footer`]({% link docs/reference/objects/footer/index.md %}) object as below.

{% raw %}
```liquid
{% for item in footer.items %}
    <a href="{{item.path}}">{{item.label}}</a>
{% endfor %}
```
{% endraw %}

<br>

#### Attributes

## `item.label`
{: .d-inline-block }
string
{: .label .fs-1 }

The label for the footer item.

## `item.linked_resource`
{: .d-inline-block }
[Page]({% link docs/reference/objects/page.md %}) or [Product]({% link docs/reference/objects/product/index.md %}) or [Blog post]({% link docs/reference/objects/blog_post.md %})
{: .label .fs-1 }

The object associated with the footer item, if there is one. This can be one of the following:

- [Page]({% link docs/reference/objects/page.md %})
- [Product]({% link docs/reference/objects/product/index.md %}) (for experiences and accommodations)
- [Blog post]({% link docs/reference/objects/blog_post.md %})

You can use the `type` attribute to distinguish between these. For example:

{% raw %}
``` liquid
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
```
{% endraw %}

It will return `nil` if the footer item uses an external URL.

## `item.new_tab`
{: .d-inline-block }
boolean
{: .label .fs-1 }

Returns `true` if clicking this item should open a new tab.

## `item.path`
{: .d-inline-block }
string
{: .label .fs-1 }
deprecated
{: .label .fs-1 .label-red .ml-0 .mt-0 }

The target url for the footer item.

This is deprecated as it will return a full URL. Use `item.url` instead.

## `item.url`
{: .d-inline-block }
string
{: .label .fs-1 }
The target url for the footer item.
