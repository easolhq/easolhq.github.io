---
layout: default
title: Footer Template
parent: Site Navigation
nav_order: 2
---

# Footer Template
Apart from the [main site navigation]({% link docs/site_navigation/header.md %}) the site can have a secondary navigation in the **footer template** (partials/footer/index.html). One can't be accessed from the other.
The [footer]({% link docs/reference/objects/footer/index.md %}) is a special kind of [partial]({% link docs/theme_architecture/partials.md %}) which is rendered in all site pages, always at the end of the `body` tag. It contains a [schema]({% link docs/theme_architecture/blocks/schema/index.md %}) where [variables]({% link docs/theme_architecture/blocks/schema/variables/index.md %}) can be added, removed or edited. The footer template might be used to include additional [libraries]({% link docs/libraries/index.md %}).

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
{% unless footer.items == blank %}
    {% for item in footer.items %}
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
{% endunless %}
```
{% endraw %}

### Custom variables
All [variables]({% link docs/theme_architecture/blocks/schema/variables/index.md %}) defined in the footer's [schema]({% link docs/theme_architecture/blocks/schema/index.md %}) need to be accessed with `footer` and dot notation:

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
<footer>
    {% if footer.brand_slogan %}
    <h6>{{footer.brand_slogan}}</h6>
    {% endif %}
</footer>
```
{% endraw %}