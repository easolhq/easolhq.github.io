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