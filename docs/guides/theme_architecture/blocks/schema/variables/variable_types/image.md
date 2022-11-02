---
layout: default
title: Image
parent: Variable types
---

# Image

Renders an image upload field and returns an [Image]({% link docs/reference/objects/image.md %}) object.

##### syntax
{% raw %}
```
---
my_variable:
    type: image
    default:
        url: https://my-image.jpg
---

<img src="{{my_variable.url}}">

```
{% endraw %}

## Setting defaults
Defaults can be defined as an image url or as an image uploaded in the theme [assets](% link docs/guides/theme_architecture/assets.md %) folder.

### Url

##### syntax
{% raw %}
```
---
my_variable:
    type: image
    default:
        url: https://my-image.jpg
---
```
{% endraw %}

### Image asset

##### syntax
{% raw %}
```
---
my_variable:
    type: image
    default:
        asset: images/my-image.jpg
---
```
{% endraw %}