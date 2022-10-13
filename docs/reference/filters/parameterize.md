---
layout: default
title: Parameterize
parent: Filters
---

# parameterize

Returns a version of the provided string where special characters are removed and white space replaced with dashes (`-`), thus making it URL parameter-friendly.

### Example:

{% raw %}
```liquid
<h1>{{ "Donald E. Knuth" | parameterize }}</h1>
```
{% endraw %}

The above would result in `<h1>donald-e-knuth</h1>`.
