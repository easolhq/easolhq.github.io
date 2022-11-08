---
layout: default
title: Header
parent: Site Navigation
nav_order: 1
---

# Header

The main site navigation can be defined by Creators in **My Site > Header** or any site page. Its template can be edited in the **menu template** (partials/menu/index.html). Please note that the terms "Header" and "Menu" might be used interchangeably.

## Menu template
The [menu]({% link docs/objects/menu/index.md %}) is a special kind of [partial]({% link docs/guides/theme_architecture/partials/index.md %}) which is rendered in all site pages, always at the start of the `body` tag. It contains a [schema]({% link docs/guides/theme_architecture/blocks/schema/index.md %}) where [variables]({% link docs/guides/theme_architecture/blocks/schema/variables/index.md %}) can be added, removed or edited. The site navigation and all its attributes can be accessed through the [menu]({% link docs/reference/objects/menu/index.md %}) object. Refer to it for a full reference and examples.

## Common examples

### Rendering navigation
The essential code to render a 2-level navigation is:

{% raw %}
```yaml
---
max_item_levels: 2
supports_open_new_tab: true
...
---
```
```liquid
{% for item in menu.items %}
    <a href="{% if item.url != '' %}{{item.url}}{% else %}javascript:void(0);{% endif %}"
    {% if item.new_tab %}target="_blank" rel="noopener noreferrer"{% endif %}>
        {{item.label}}
    </a>
    {% if item.items.size > 0 %}
        <ul>
        {% for nested_item in item.items %}
            <li>
                <a href="{% if nested_item.url != '' %}{{nested_item.url}}{% else %}javascript:void(0);{% endif %}" 
                {% if nested_item.new_tab %}target="_blank" rel="noopener noreferrer"{% endif %}>
                    {{nested_item.label}}
                </a>
            </li>
        {% endfor %}
        </ul>
    {% endif %}
{% endfor %}
```
{% endraw %}

### Custom variables
All [variables]({% link docs/guides/theme_architecture/blocks/schema/variables/index.md %}) defined in the menu's [schema]({% link docs/guides/theme_architecture/blocks/schema/index.md %}) need to be accessed with `menu` and dot notation:

{% raw %}
```yaml
---
max_item_levels: 2
supports_open_new_tab: true
attributes:
    festival_announcement:
        type: string
        label: A special announcement
---
```
```liquid
<header>
    {% if menu.festival_announcement %}
        <h6>{{menu.festival_announcement}}</h6>
    {% endif %}
</header>
```
{% endraw %}