---
layout: default
title: Color
parent: Variable types
---

# Color

Renders a colour picker, from which a Creator can choose a colour from the theme palette defined in [Site Styles]({% link docs/guides/site_styles/index.md %}), or a custom hex colour.
Returns a [Color]({% link docs/reference/objects/color.md %}) object.

##### syntax
{% raw %}
```
---
my_variable:
    type: color
    default:
        palette: body-color
---

{{my_variable.rgba}}

```
{% endraw %}

## Setting defaults
Defaults can be defined as colours from the Creator's theme palette or or as a `rgba` colour.

### Theme palette

##### syntax
{% raw %}
```
---
my_variable:
    type: color
    default:
        palette: body-bg
---
```
{% endraw %}

| Reference     | Palette colour          |
|:--------------|:------------------------|
| `body-color`  | Site text colour        |
| `body-bg`     | Site background colour  |
| `primary`     | Primary colour          |
| `secondary`   | Secondary colour        |

### rgba

##### syntax
{% raw %}
```
---
my_variable:
    type: color
    default:
        r: 255
        g: 255
        b: 255
        a: 0
---
```
{% endraw %}