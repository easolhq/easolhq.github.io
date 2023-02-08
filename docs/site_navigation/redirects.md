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
2. Add a custom Liquid/CSS block to the page
3. Add the following code into the new block
```
<script>
    window.location.replace("NEWLOCATION");
</script>
```

For example:
```
<script>
    window.location.replace("https://www.coolcompany.com/products/very-cool-experience");
</script>
```
4. Set the new page as the site homepage

You can redirect the homepage to a product or site page as long as it's published. Make sure you use the full published URL of the product or site page in your redirect code.
