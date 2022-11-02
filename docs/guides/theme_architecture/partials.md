---
layout: default
title: Partials
parent: Theme architecture
nav_order: 7
---

# Partials

Partials allow you to extract commonly used code snippets so you only have to define them once. You can reference these snippets throughout the theme with the Liquid render tag.

##### syntax
{% raw %}
```liquid
{% render 'partial' %}
```
{% endraw %}

Where `partial` is the name of the snippet to render, without the `.html` extension.

Inside snippets you can't directly access variables that are created outside of the snippet. However, you can specify variables as parameters to pass outside variables into snippets. Any changes that are made to a passed variable apply only within the snippet.

##### syntax
{% raw %}
```liquid
{% render 'partial', variable: value %}
```
{% endraw %}

You can render a snippet for every item in an array using the `for` parameter. You can also supply an optional `as` parameter to be able to reference the current item in the iteration inside the snippet. 

##### syntax
{% raw %}
```liquid
{% render 'partial' for array as item %}
```
{% endraw %}


There are also two special partials, [menu]({% link docs/guides/site_navigation/index.md %}) and [footer]({% link docs/guides/site_navigation/index.md %}), which are defined in folders. These define the menu and footer templates.