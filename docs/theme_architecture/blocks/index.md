---
layout: default
title: Blocks
parent: Theme architecture
has_children: true
nav_order: 5
---

# Blocks

Blocks are the main building components of sites, allowing Creators to easily build their site pages. These are defined as liquid in a `block.html` file within a folder per block and are all listed in an [index.json]({% link docs/theme_architecture/blocks/index_json.md %}) file.

Blocks are comprised of a [block schema]({% link docs/theme_architecture/blocks/schema/index.md %}) and the block html. You can also include styles and scripts within the block, as required.

##### Example
{% raw %}
```
---
attributes:
    heading:
        type: string
        label: Block Heading
        group: content
    text:
        type: text
        default: Enter some nice copy about your experience
    image:
        type: image
        default:
            asset: images/sky.png
        label: Background Image
        group: design
        hint: Recommended image size 1920px by 600px
---
<h1>{{ heading }}</h1>
{{ text }}
<img src="{{ image.xxlarge_url }}">
```
{% endraw %}