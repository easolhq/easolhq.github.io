---
layout: default
title: Image
parent: Objects
---

# Image
{: .d-inline-block }
object
{: .label .fs-1 }

> By using the most suitable url method you can help ensure faster load times on pages using the theme

{% raw %}
```html
<img alt='{image.name}' src='{image.thumbnail_url}'/>
```
{% endraw %}

<br>

#### Attributes

## `image.name`
{: .d-inline-block }
string
{: .label .fs-1 }

The filename of the original image, useful for adding alt texts to the images.

## `image.url`
{: .d-inline-block }
string
{: .label .fs-1 }

The original unedited url for the image.
This has alternatives for resizing the image as below.


| Attribute             | Maximum width (px)|
|:----------------------|:------------------|
| `image.thumbnail_url` | 405               |
| `image.small_url`     | 540               |
| `image.medium_url`    | 720               |
| `image.large_url`     | 960               |
| `image.xlarge_url`    | 1140              |
| `image.xxlarge_url`   | 1920              |

## `image.signature`
{: .d-inline-block }
string
{: .label .fs-1 }

The unique id of the image.
