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
2. Hugo **is** the tool
3. Hugo features
4. TODO

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
* ... and many more

This generated set of pages can then be deployed to just about anywhere.

---

# Why?

Lots of benefits:

**Write once — deploy anywhere**

> CDN, GitHub pages, Netlify, Raspbery Pi, `python -m http.server`, or your mobile

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
* Incredibly fast
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

* Cross-platform (Linux, Windows, Mac OS)
* Content in Markdown, Mmark, Org-mode or HTML
* Auto-generated taxonomies (tags, sections)
* SASS/SCSS compilation (*extended version* needed)
* Asset minification (HTML/JS/CSS)
* External data sources (YAML, TOML, CSV etc.)
* Image processing (reading EXIF, scaling, filtering etc.)
* Shortcodes (example: `{{< youtube "abcdefghij" >}}` embeds a YouTube video)
* Multilingual websites
* Related content