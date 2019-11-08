# Eonics Open Hack Night #19: Hugo wizardry

This repository contains a presentation implemented with [remark.js](https://remarkjs.com/) and—naturally—Hugo.

## The Presentation

In order to try it out, you'll first need to [install](https://gohugo.io/getting-started/installing/) Hugo.

Once it's installed, run `hugo server` in the project directory, then point your browser to [http://localhost:1313](http://localhost:1313/).

If you're curious how it's built, feel free to inspect the project's files. The overall skeleton is at `layouts/_default/baseof.html`, and the slides live in `content/_index.md`.


## The Workshop

### The assignment

In this workshop we're going to create a portfolio website of a fictitious press agency named **Acme Press**.

The agency is selling photographs to be used by news websites, other agencies, blogs and so on.

The actual webshop functionality requires a server part, so we'll assume it's implemented elsewhere. The objective of this workshop is building an online catalogue of the available items, properly classified by author, tags, and image properties.

For the content we use a pre-cooked set of portfolio items.

### Getting started

0. [Install](https://gohugo.io/getting-started/installing/) Hugo.
1. Create a boilerplate directory structure (we ask Hugo to create a YAML config file):
```bash
hugo new site acme-press -f yml
```
2. Download the **Creative Portfolio** theme:
```bash
cd acme-press
git clone https://github.com/kishaningithub/hugo-creative-portfolio-theme.git themes/hugo-creative-portfolio-theme
rm -rf themes/hugo-creative-portfolio-theme/.git
```
3. Copy the starter site content from this repository: everything below `_acme-press/` should be copied as-is into the new site root.
```bash
cp -r /path/to/eonics-hugo/_acme-press/* .
```
4. Try out the result: run `hugo server`, then go to [http://localhost:1313](http://localhost:1313/). The result should look as follows:

![](static/img/screenshot-acme-press-1.png)

### Further assignment steps

#### 1. Make portfolio items visible

Make each portfolio article display a big version of the picture. Add the file `layouts/portfolio/single.html` with the following content:

```html
{{ define "main" }}
<div class="col-xs-12 col-sm-8 col-md-9 content-column white-background">
  {{ partial "mobile_nav_toggle.html" . }}
  <div class="row">
    <div class="col-lg-8">
      <div class="content-column-content">
         <h1>{{ .Title }}</h1>
         <div>
         {{ with .Params.image }}
         <img src="{{ . | absURL }}" alt="Image">
         {{ end }}
         </div>
         {{ .Content }}
      </div>
    </div>
  </div>
</div>
{{ end }}
```

#### 2. Add a price parameter to each item

Add `price: X.XX` (feel free to make up a number in each case) to the front matter of each `workN.md` file under `content/portfolio`.

#### 3. Add price display

Make the price show up in both list and single views.

Hint: fetch the price value as `{{ .Params.price }}`

#### 4. Add navigation buttons

Add **Previous** and **Next** buttons for portfolio items in the single view.

#### 5. Add authors taxonomy

* Add `authors` taxonomy to `config.yml`.
* Add `authors:` parameter to the content pages' front matter, with a single author.
* Add list and terms templates: `layouts/authors/list.html` and `layouts/authors/terms.html` respectively.
* Add Author heading to the single item view.
* Add Authors link to the side menu.

Hint: read about [Taxonomies](https://gohugo.io/content-management/taxonomies/) in Hugo docs.

#### 6. Add tags taxonomy

* Add `tags` taxonomy to `config.yml`.
* Add `tags:` parameter to the content pages' front matter, with a list of tags.
* Add list and terms templates: `layouts/tags/list.html` and `layouts/tags/terms.html` respectively.
* Add Tags link to the side menu.

#### 7. Bonus task: deploy your website to a hosting

If you want your website to actually be available online, you can choose from a number of free alternatives.

But first you'll need to check it into a GitHub repository. Make sure to add the following to your `.gitignore`:

```gitignore
/public/
/resources/
```

Then follow the steps for the hosting of your choice:

* [Render.com](https://gohugo.io/hosting-and-deployment/hosting-on-render/)
* [Netlify](https://gohugo.io/hosting-and-deployment/hosting-on-netlify/)
* [GitHub pages](https://gohugo.io/hosting-and-deployment/hosting-on-github/)

### Useful links

* Hugo templating: https://gohugo.io/templates/introduction/
* Hugo function docs: https://gohugo.io/functions/
* Hugo `Page` variables: https://gohugo.io/variables/page/

### Solution

The workable solution to all of the above is located under `_solution`.