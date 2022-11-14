---
layout: default
title: Easol badge
parent: Tags
grand_parent: Reference
has_children: false
---

# Easol badge

The `easol_badge` tag returns an HTML anchor tag linking to easol.com. The tag includes UTM parameters to track referrals from Creator sites.

##### input
{% raw %}
```liquid
{% easol_badge %}
```
{% endraw %}

##### output
{% raw %}
```html
<a target="_blank\" style="font-size: 0.8rem;line-height: 1.33;letter-spacing: 0.166em;text-transform: uppercase;" rel="noopener\" href="https://easol.com?utm_content=creator_site_name&utm_medium=creator-site&utm_source=referral\">Powered by Easol Experience Commerce</a>
```
{% endraw %}