---
title: "Menus"
date: 2019-04-28T22:26:20+10:00
docs:
  - https://gohugo.io/content-management/menus/
  - https://gohugo.io/templates/menu-templates/#section-menu-for-lazy-bloggers
---

### Relevant files

1. config.toml
{{< highlight "toml" "linenos=table,hl_lines=14">}}
{{< utils/readfile file="config.toml" theme="~" >}}
{{< /highlight >}}

1. {{< utils/theme >}}/layouts/partials/header/nav-menu.html
{{< highlight "go-html-template" "linenos=table,hl_lines=6-12">}}
{{< utils/readfile file="layouts/partials/header/nav-menu.html" >}}
{{< /highlight >}}

---

### Breaking things down

#### Section Menu for Lazy Bloggers 

There are several ways to create menus in Hugo. The simplest one involves simply adding one line in our config:

```toml
sectionPagesMenu = "main"
```

The Relevant File #2 contains the code snippet that prints out the actual menu entries.

You can see this in action on the top nav bar:

![Main Menu](main.png)

Accessing the menu from this page, we see the Examples entry is highlighted. This happens because `$currentPage.HasMenuCurrent "main" .` is returning `true`.

---

##### `.HasMenuCurrent` vs `.IsMenuCurrent`

To see the difference as to when `.HasMenuCurrent` returns true vs `.IsMenuCurrent`, observe the Examples menu entry when viewing these pages:

- this current page,
- [/examples](/examples/), and
- [the homepage](/).

`.HasMenuCurrent` returning true adds the `.has-menu-current` class to the menu entry. Similarly, `.IsMenuCurrent` adds the `.is-menu-current` class.

To make comparison easier, different styles have been defined for these two classes:

```css
.has-menu-current {
  text-decoration: underline;
}
.is-menu-current {
  text-transform: uppercase;
}
```

This is ideal for very simple cases. 
---