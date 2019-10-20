# Eonics Open Hack Night #19: Hugo wizardry

This repository contains a presentation implemented with [remark.js](https://remarkjs.com/) and—naturally—Hugo.

In order to try it out, you'll first need to [install](https://gohugo.io/TODO) Hugo.

Once it's installed, run `hugo server` in the project directory, then point your browser to [http://localhost:1313](localhost:1313).

If you're curious how it's built, feel free to inspect the project's files. The overall skeleton is at `layouts/_default/baseof.html`, and the slides live in `content/_index.md`.

## Workshop

### The assignment

In this workshop we're going to create a portfolio website of a fictitious press agency named **Acme Press**.

The agency is selling photographs to be used by news websites, other agencies, blogs and so on.

The actual webshop functionality requires a server part, so we'll assume it's implemented elsewhere. The objective of this workshop is building an online catalogue of the available items, properly classified by author, tags, and image properties.

For the content we use a pre-cooked set of portfolio items.

### Getting started

1. Create a boilerplate directory structure (we ask Hugo to create a YAML config file):
```bash
hugo new site acme-press -f yml
```
2. Download a theme:
```bash
cd mysite
git clone TODO themes/THEMENAME
```
3. Activate the theme in `config.yml` by adding the line:
```yaml
theme: TODO
```
4. Download a starter image package:
```bash
mkdir content/portfolio
curl -fsSL https://wetransfer.com/...TODO... | tar -xzC content/portfolio
```

### Add your homepage template

...TODO...


### Bonus task: deploy your website to a hosting

If you want your website to actually be available online, you can choose from a number of free alternatives.

But first you'll need to check it into a GitHub repository. Make sure to add the following to your `.gitignore`:

```gitignore
/public/
/resources/
``` 

* [Render.com](...TODO...)
* [Netlify](...TODO...)
* [GitHub pages](...TODO...)

### Useful links

* Hugo function docs: https://gohugo.io/functions/
* Hugo template docs: ...TODO...
