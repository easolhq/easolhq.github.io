---
layout: default
title: Overview
parent: Blocks
nav_order: 1
---

# Blocks

Blocks are the main building components of sites, allowing Creators to easily build their own site pages. These are defined as liquid in a `block.html` file within a folder per block and broken down in a [index.json]({% link docs/guides/theme_architecture/blocks/index_json.md %}) file.

Blocks are comprised of a [block schema]({% link docs/guides/theme_architecture/blocks/schema/index.md %}) and the block html. You can also include styles and scripts within the block, as required.

##### Example
{% raw %}
```
---
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
    hint: Reccommended image size 1920px by 600px
---
<h1>{{heading}}</h1>
{{text}}
<img src="{{image.xxlarge_url}}">
```
{% endraw %}