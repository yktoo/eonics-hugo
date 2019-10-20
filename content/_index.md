---
title: Hugo Presentation
---

class: center, middle

# Static Site Generation

# with

![:scale 50%](/img/hugo-logo.png)

Dmitry Kann · https://yktoo.solutions

---

# Agenda

1. Why would anyone make a static site?
2. Hugo is your dream's tool
3. Hugo features
4. Hugo project structure
5. Hugo page kinds
6. Quick start

---

# Introduction

A **static website** leverages a one-off content generation process, which creates the entire website.

This content can include:

* HTML pages
* Graphics
* Stylesheets
* Scripts
* XML sitemaps
* RSS feeds
* … and more

This generated set of pages can then be deployed to just about anywhere.

---

# Why?

**Write once — deploy anywhere**

> CDN, GitHub pages, Netlify, Raspbery Pi, `python -m http.server`, or your mobile

**It's efficient**

> A page is much more often viewed than it is updated

**Super fast serving**

> Important for SEO

**Secure**

> No chance for a break-in as there's nothing to break

**Version-controlled**

> Everything in your Git (or not)

---

# Sounds nice, but…

But wait… How about dynamic content?

* News
* Blog posts
* Tags, sections
* RSS feeds
* Forms

---

# Here's the deal:

In many cases, **no dynamic content is necessary**.

For the content produced by you, every page, classification term, RSS entry etc. is known upfront.

## And if it still is…

* Client-side JS code
* Forms: external services (formspree.io, Netlify)
* Serverless implementation (AWS Lambda et al.)
* Split into *static* and *dynamic* parts

---

# Meet Hugo

Hugo comes into play!

.center[![:scale 75%](/img/hugo-logo.png)]

.center[The fastest website generator ever: **1000…5000** pages/second]

---

# Hugo is…

* Static website generator written in Go
* Incredibly fast: **< 1 ms** per page
* Utilising Go Templates
* Sophisticated: variables, loops, conditions, expressions, lists, maps etc.

Example of a Hugo template:

```hugo
<ul>
    {{ range .Data.Pages }}
    <li><a href="{{ .Permalink }}">{{ .Title }}</a></li>
    {{ end }}
</ul>
```

---

# Hugo features

* Open-source (GitHub: 38K ★, 590 contributors)
* Cross-platform (Linux, Windows, Mac OS, *BSD)
* Content in Markdown, Mmark, Org-mode or HTML
* Auto-generated taxonomies (tags, sections etc.)
* SASS/SCSS compilation (*extended version* needed)
* Asset minification (HTML/JS/CSS)
* External data sources (YAML, TOML, CSV etc.)
* Image processing (reading EXIF, scaling, filtering etc.)
* Shortcodes (example: `{{< youtube "abcdefghij" >}}` embeds a YouTube video)
* Multilingual websites
* Related content

---

# Hugo project structure

* `archetypes`
    - Content prototypes
* `assets`
    - Things that require some processing (e.g. SCSS)
* `content`
    - Site pages
* `data`
    - Data files
* `i18n`
    - Localisations
* `layouts`
    - Templates for presenting/formatting the content
* `resources`
    - Hugo's temporary folder
* `static`
    - Things served as is
* `themes`
    - Themes, which can contain defaults for assets, layouts etc.

---

# Hugo page kinds

|Kind          |Description                                            |Example                                                                      |
|--------------|-------------------------------------------------------|-----------------------------------------------------------------------------|
|`home`        |The home page                                          |`/index.html`                                                                |
|`page`        |A page showing a regular page                          |`my-post` page (`/posts/my-post/index.html`)                                 |
|`section`     |A page listing regular pages from a given section      |`posts` section (`/posts/index.html`)                                        |
|`taxonomy`    |A page listing regular pages from a given taxonomy term|page for the term `awesome` from `tags` taxonomy (`/tags/awesome/index.html`)|
|`taxonomyTerm`|A page listing terms from a given taxonomy             |page for the `tags` taxonomy (`/tags/index.html`)                            |

---

# Quick start

1. Create boilerplate directory structure:
```bash
hugo new site mysite
```
2. Download a theme:
```bash
cd mysite
git clone ... themes/THEMENAME
```
3. Adjust settings in `config.toml` (or `config.yml`)