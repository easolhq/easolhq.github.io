---
layout: default
title: Package
parent: Variable types
---

# Package

Renders a select input from which a Creator can select a package from the current companies **listable** packages.
> Listable packages are packages that are not in a draft state.

Returns a [Package]({% link docs/reference/objects/package.md %}) object.


##### syntax
{% raw %}
```
---
my_variable:
    type: package
---

{{ my_variable.name }}
```
{% endraw %}
