---
layout: default
title: Footer
parent: Site Navigation
nav_order: 2
---

# Footer

Apart from the [main site navigation]({% link docs/site_navigation/header/index.md %}) the **footer template** (partials/footer/index.html) can have a secondary navigation.

## Footer template
The [footer]({% link docs/objects/footer/index.md %}) is a special kind of [partial]({% link docs/guides/theme_architecture/partials/index.md %}) which is rendered in all site pages, always at the end of the `body` tag. It contains a [schema]({% link docs/guides/theme_architecture/blocks/schema/index.md %}) where [variables]({% link docs/guides/theme_architecture/blocks/schema/variables/index.md %}) can be added, removed or edited.

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
{% for item in footer.items %}
    <a href="{% if item.url != null and item.url != '' %}{{item.url}}{% else %}javascript:void(0);{% endif %}"
    {% if item.new_tab %}target="_blank" rel="noopener noreferrer"{% endif %}>
        {{item.label}}
    </a>
    {% if item.items.size > 0 %}
        <ul>
        {% for nested_item in item.items %}
            <li>
                <a href="{% if nested_item.url != null and nested_item.url != '' %}{{nested_item.url}}{% else %}javascript:void(0);{% endif %}" 
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
All [variables]({% link docs/guides/theme_architecture/blocks/schema/variables/index.md %}) defined in the footer's [schema]({% link docs/guides/theme_architecture/blocks/schema/index.md %}) need to be accessed with `footer` and dot notation:

{% raw %}
```yaml
---
max_item_levels: 2
supports_open_new_tab: true
attributes:
    brand_slogan:
        type: string
        label: Slogan to display below the footer logo
---
```
```liquid
<header>
    {% if footer.brand_slogan %}
        <h6>{{footer.brand_slogan}}</h6>
    {% endif %}
</header>
```
{% endraw %}