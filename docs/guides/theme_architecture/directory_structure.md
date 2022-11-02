---
layout: default
title: Directory structure
parent: Theme architecture
nav_order: 2
---

# Directory structure

Themes must use the following directory structure:

```
theme
├── .github
│   └── workflows
│       ├── main.yml
│       └── lint.yml
├── assets
│   ├── index.css
│   ├── index.js
│   ├── recommendation.css
│   └── images
│       └── example.png
├── blocks
│   ├── example
│   │   └── block.html
│   └── index.json
├── pages
│   └── example.json
├── partials
│   ├── example.html
│   ├── footer
│   │   └── index.html
│   └── menu
│       └── index.html
├── templates
│   ├── blog_overview
│   │   ├── index.css
│   │   └── index.html
│   ├── blog_post
│   │   ├── index.css
│   │   └── index.html
│   ├── content
│   │   └── index.html
│   ├── product
│   │   ├── index.css
│   │   └── index.html
│   └── selections
│       └── index.html
└── types
    └── example.json
```

To see an example of a complete theme directory structure, refer to the [skeleton-theme](https://github.com/easolhq/skeleton-theme) repository.