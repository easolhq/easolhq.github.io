---
layout: default
title: Creating a theme
parent: Getting started
---

# Creating a theme

## Step 1: Get the base theme code

There are two options for getting the base theme code. Both require Easol authorisation —

### Option 1: Start with an existing Easol theme

This option is ideal if you’re looking to make custom modifications to an Easol theme. Easol can grant you access to fork a theme repository.

### Option 2: Start with the skeleton theme

This option is ideal if you’re developing a fully custom site on Easol. The skeleton theme includes all the basic requirements for Easol themes in terms of structure, files and workflows. Easol can grant you access to fork the skeleton theme.


---

## Step 2: Connect your theme to an Easol Site

1. Speak to Easol to obtain 3 things; your unique theme key, your Easol key, and Easol secret.
2. In your theme repo, go to **Workflows > main.yml**. Update the **THEME_KEY** to your unique theme key. These are usually of the form: **[name of creator]-theme** (e.g. “bayou-theme”).
3. In your repo's Github, go to **Settings > Secrets > Actions > Repository Secrets** and set your easol key and secret **EASOL_KEY** and **EASOL_SECRET**
4. Once your theme has been successfully deployed once, any Creator with Developer access can add the theme to an Easol Site, by entering the unique theme key when choosing a theme.


---

## Step 3: Develop your theme

A few things to keep in mind while you develop your theme:

From the moment a theme is chosen for a site, a copy of all the theme code is added to that site. If you make changes to your theme code, the newer version does not replace the theme code in existing sites. This has a few effects worth thinking about: 
- As you develop and test your theme, all other theme files (e.g. theme css, js) need to be updated manually in the Easol company admin under **Site > Theme**.
- Updates to [blocks]({% link docs/theme_architecture/blocks/index.md %}) will not update any blocks which have already been added to site pages. However, changes will appear in the block library, which is presented when editing pages. This can lead to having multiple versions of the same block present on the same site. 
- When updating the theme via Github, go to **Actions > Workflows** to check that there were no issues deploying the theme. There are two workflows to look out for: **Canvas Lint** and **Theme Deploy**. 
- Updates can take up to 15mins to be available to sites.