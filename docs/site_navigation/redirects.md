---
layout: default
title: Redirects
parent: Site Navigation
nav_order: 3
---

# Redirects

The URL redirects are managed in **My Site > Redirects**, by anyone with the 'Create and edit site pages' permission. Redirects can be chained and can be set to unpublished pages (in that case users not logged in the Easol platform will be redirected to a login page).

## URLs that can't be redirected

Redirects can't be set up **from** URL paths that start with:
- admin
- b
- blog (1)
- bookings
- cart
- checkout
- common
- log-in
- log-out
- p
- products (1)
- robots
- script
- shop
- shop-style
- sign-up
- style
- t
- terms

(1) In these cases only if the slug is not taken. E.g. `/blog/april-12` can't be redirected because `/april-12` is an existing blog post.

## Redirecting the homepage

Redirecting the homepage requires a different approach. To do this, follow these steps:
1. Create a new blank page 
1. Add a custom Liquid/CSS block to the page
1. Add the following code into the new block

{% raw %}
```liquid
---
redirect_link:
  type: link
  label: Page to redirect to
---

{% if redirect_link %}
  <script>
    const hostname = window.location.hostname
    if(!hostname.includes('myeasol')) {
      window.location.replace('{{ redirect_link.url }}')
    }
  </script>
{% endif %}
```
{% endraw %}

{:style="counter-reset:none"}
1. Set the new page as the site homepage

The creator will be able to select which page to redirect to by setting it via the `redirect_link` field.