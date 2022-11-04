---
layout: default
title: Modifiers
parent: Product Management and Merchandising
nav_order: 7
---

For quick reference, see [Modifer]({% link docs/reference/objects/product/modifier.md %}) and [Modifier Group]({% link docs/reference/objects/product/modifier_group.md %}).

Modifiers modify variants or extras and are arranged into modifier groups. For example, a food festival may sell a half-day ticket (variant) where customers choose from morning or afternoon slots (first modifier group) and three workshop options (second modifier group). 

Creators decide if customers must make their modifier selection during purchase, or if they can make the selection afterward i.e. pre-checkout, or post-checkout. It's important to clearly communicate modifiers that must be decided pre-checkout to ensure the checkout flow is quick and easy for customers. These are identified with {% raw %}`variant.pre_checkout_modifier_groups`{% endraw %} and {% raw %}`extra.pre_checkout_modifier_groups`{% endraw %}.
