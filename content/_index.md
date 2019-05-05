---
title: "A Kitchen Sink Example for Hugo"
---


## Hello and welcome!

This is a "[Kitchen Sink Example](https://stackoverflow.com/questions/33779296/what-is-exact-meaning-of-kitchen-sink-in-programming)" for [Hugo](https://gohugo.io/), a static website generator.

### A few notes

This is not for beginners. 

This assumes that you already have Hugo running on your machine, and at least gone through the [Quick Start](https://gohugo.io/getting-started/quick-start/), or have a basic Hugo site set up, and perhaps ready to explore the more complicated features available. Ideally you will also have read through most of the docs.

This is not intended to be a tutorial. Instead, it is meant to showcase the various features Hugo has, and how these might be implemented on a project. 

This is **not the only way** to implement features. There are probably better ways to do some things, depending on your exact use case.


### How this works

- This site has several [sections](https://gohugo.io/content-management/sections/t): {{< utils/sections >}}. The [Examples](/examples/) section is the one containing the various example pages. The rest are Lorem Ipsum type filler sections, intended to demonstrate features.
- Each example will generally consist of the following:
  - Links to parts of the Hugo Documentation that are relevant to the example;
  - Code samples that demonstrate the concept:
      - Locations of the files containing the code snippets will be provided. It will look somewhat like this:  
      `{{< utils/theme >}}/layouts/partials/head/scss.html`
      - Where extraneous code are also present, relevant lines may be highlighted.
  - A brief explanation: this assumes that you have read the docs pages suggested;
  - Alternative ways of implementation may be provided;
- Most of the layout code are under the `kitchen` theme: {{< utils/theme >}}. 

### Feedback

is welcome. Get in touch through [GitHub](https://github.com/pointyfar/hugo-kitchen-sink).

### Acknowledgement

Open source is awesome. Thanks go to the people behind 

- [Hugo](https://gohugo.io/)
- [Bulma](https://bulma.io/)
- [higlight.js](https://highlightjs.org/download/)
- [tocbot](https://tscanlin.github.io/tocbot/)

and other open source projects without which this site would not be possible.

### Ready?

[Start Here &#9656;](/examples/)