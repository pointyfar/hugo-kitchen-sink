---
title: "SCSS"
date: 2019-04-28T21:29:27+10:00
docs: 
  - https://gohugo.io/hugo-pipes/scss-sass/
  - https://gohugo.io/hugo-pipes/resource-from-template/
  - https://gohugo.io/hugo-pipes/scss-sass/
---


### Relevant files
  
1. {{< utils/theme >}}/layouts/partials/head/scss.html
{{< highlight "go-html-template" "linenos=table,hl_lines=8-10">}}
{{< utils/readfile file="layouts/partials/head/scss.html" >}}
{{< /highlight >}}

1. {{< utils/theme >}}/assets/scss/main.scss
{{< highlight "scss" "linenos=table,hl_lines=5-8">}}
{{< utils/readfile file="assets/scss/main.scss" >}}
{{< /highlight >}}

1. config.toml
{{< highlight "toml" "linenos=table,hl_lines=5 31-32">}}
{{< utils/readfile file="config.toml" theme="~" >}}
{{< /highlight >}}

### Breaking things down

`scss.html` contains the code that transforms our SCSS asset, `{{< utils/theme >}}/assets/scss/main.scss` into a CSS file.

1. `resources.Get` retrieves the asset at `[assetDir]/scss/main.scss`
1. The result is then piped to `resources.ExecuteAsTemplate`, which allows us to use Go Templates in the asset. In our example, we take the value of `site.Params.scss.primary`, set in our `config.toml`, and use that value in the `main.scss` file.
1. `toCSS` then transforms it into a CSS file.
1. We take the `.Permalink` to the CSS resource to link to.