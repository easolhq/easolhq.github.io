---
layout: default
title: Link
parent: Objects
---

# Link
{: .d-inline-block }
object
{: .label .fs-1 }

#### Attributes

## `link.host`
{: .d-inline-block }
string
{: .label .fs-1 }
deprecated
{: .label .fs-1 .label-red .ml-0 .mt-0 }

The host of the URL for this link.

## `link.linked_resource`
{: .d-inline-block }
string
{: .label .fs-1 }

The object associated with the link, if there is one. This can be one of the following:

- [`Page`]({% link docs/reference/objects/page.md %})
- [`Product`]({% link docs/reference/objects/product/index.md %}) (for experiences and accommodations)
- [`Blog post`]({% link docs/reference/objects/blog_post.md %})

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

## `link.new_tab`
{: .d-inline-block }
boolean
{: .label .fs-1 }

Returns true if clicking this link should open a new tab.

## `link.path`
{: .d-inline-block }
string
{: .label .fs-1 }
deprecated
{: .label .fs-1 .label-red .ml-0 .mt-0 }

The path of the URL for this link.

## `link.url`
{: .d-inline-block }
string
{: .label .fs-1 }

The full URL for the link.
