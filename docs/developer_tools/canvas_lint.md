---
layout: default
title: Canvas Lint
parent: Developer Tools
nav_order: 2
---

Easol has developed and maintains a gem called easol-canvas, which is used for validating Easol themes (See [RubyGems](https://rubygems.org/gems/easol-canvas) or [GitHub](https://github.com/easolhq/canvas)).

The `canvas lint` command will run the following validation checks:

1. RequiredFilesCheck
    1. Checks that the required files exist (e.g. `templates/product/index.html`).
2. ValidHtmlCheck
    1. Validates all `.html` files contain valid HTML.
3. ValidLiquidCheck
    1. Validates all `.html` files contain valid Liquid.
4. COMING SOON: Validate the schemas in blocks, headers and footers.

## Usage

To use the gem locally, you can install it and use the `canvas lint` command in the root of your theme directory:

```jsx
gem install easol-canvas
canvas lint
```

There is a [canvas-linter-action](https://github.com/easolhq/canvas-linter-action), which should be [set up](https://github.com/easolhq/canvas-linter-action/blob/main/README.md) inside a theme repo to run validations on each push. 
