---
layout: default
title: Organisation
parent: Objects
---

# Organisation

{: .d-inline-block }
object
{: .label .fs-1 }

<br>

#### Attributes

## `organisation.name`
{: .d-inline-block }
string
{: .label .fs-1 }

The name of the organisation.

## `organisation.companies`
{: .d-inline-block }
array of [Company]({% link docs/reference/objects/company.md %})s
{: .label .fs-1 }

An array of the organisation's [companies]({% link docs/reference/objects/company.md %}). e.g

{% raw %}

```liquid
{% for company in organisation.companies %}
    {{ company.name }}
{% endfor %}
```

{% endraw %}
