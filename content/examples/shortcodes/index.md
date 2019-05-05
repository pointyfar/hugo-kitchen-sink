---
title: "Shortcodes"
date: 2019-04-28T22:34:06+10:00
docs: 
  - https://gohugo.io/content-management/shortcodes
  - https://gohugo.io/variables/shortcodes/
  
---

> Shortcodes are simple snippets inside your content files calling built-in or custom templates.

Shortcodes can be called from your content files in different ways:

### Un-paired shortcodes

#### Shortcode example: `shortcodes/sc/one.html`

{{< highlight "go-html-template" "">}}
{{< utils/readfile file="/layouts/shortcodes/sc/one.html">}}
{{< /highlight >}}

#### Shortcode usage

```go-html-template
{{</* sc/one */>}}
```
{{< sc/one >}}

```go-html-template
{{%/* sc/one */%}}
```
{{% sc/one %}}

##### Shortcode with parameters

```go-html-template
{{</* sc/one "zeroth" "first" "second" */>}}
```
{{< sc/one "zeroth" "first" "second" >}}

```go-html-template
{{</* sc/one c="zeroth" b="first" a="second" */>}}
```
{{< sc/one c="zeroth" b="first" a="second" >}}

### Paired shortcodes

The following examples show how Hugo treats the `.Inner` content depending on the shortcode delimiters used (`% %` vs `< >`)

#### Shortcode: using `< >`

*{{< utils/theme >}}/shortcodes/sc/two.html*
{{< highlight "go-html-template" "">}}
{{< utils/readfile file="/layouts/shortcodes/sc/two.html">}}
{{< /highlight >}}


---

This is an example of a shortcode where markdown syntax is not processed: https://gohugo.io/content-management/shortcodes/#shortcodes-without-markdown


{{< highlight "" "">}}
{{</* sc/two */>}}
{{< utils/readfile file="/examples/shortcodes/input.md" theme="~">}}
{{</* /sc/two */>}}
{{< /highlight >}}


##### Output:

{{< sc/two >}}
{{< utils/readfile file="/examples/shortcodes/input.md" theme="~">}}
{{< /sc/two >}}


---

{{< highlight "" "">}}
{{%/* sc/two */%}}
{{< utils/readfile file="/examples/shortcodes/input.md" theme="~">}}
{{%/* /sc/two */%}}
{{< /highlight >}}

This example would have worked pre-`0.55.x`; see next example below for how to keep old behaviour.

##### Output:

{{% sc/two %}}
{{< utils/readfile file="/examples/shortcodes/input.md" theme="~">}}
{{% /sc/two %}}

---

#### Shortcode: `% %` (keep old behaviour)

Example from the docs to make shortcodes behave as in pre-`0.55.x`: https://gohugo.io/content-management/shortcodes/#shortcodes-with-markdown 


*{{< utils/theme >}}/shortcodes/sc/two.html*
{{< highlight "go-html-template" "">}}
{{< utils/readfile file="/layouts/shortcodes/sc/three.html">}}
{{< /highlight >}}


{{< highlight "" "">}}
{{%/* sc/three */%}}
{{< utils/readfile file="/examples/shortcodes/input.md" theme="~">}}
{{%/* /sc/three */%}}
{{< /highlight >}}

##### Output:

{{% sc/three %}}
{{< utils/readfile file="/examples/shortcodes/input.md" theme="~">}}
{{% /sc/three %}}


---

#### Shortcode: `% %` (behaviour > `0.55.x`)
Example of shortcode using markdown input: https://gohugo.io/content-management/shortcodes/#shortcodes-with-markdown

*{{< utils/theme >}}/shortcodes/sc/two.html*
{{< highlight "go-html-template" "">}}
{{< utils/readfile file="/layouts/shortcodes/sc/four.html">}}
{{< /highlight >}}


{{< highlight "" "">}}
{{%/* sc/four */%}}
{{< utils/readfile file="/examples/shortcodes/input.md" theme="~">}}
{{%/* /sc/four */%}}
{{< /highlight >}}

##### Output:

{{% sc/four %}}
[Lorem](/) **Ipsum** Dolor _Sit_ <strong>~~Amet~~</strong>
{{% /sc/four %}}


---
---

### Nested Shortcodes

{{< highlight "" "">}}

{{%/*  sc/four */%}}
Outer Shortcode 
{{%/*  sc/four */%}}
Middle Shortcode
{{%/*  sc/four */%}}
Inner Shortcode
{{%/*  /sc/four */%}}
{{%/*  /sc/four */%}}
{{%/*  /sc/four */%}}

{{< /highlight >}}


{{% sc/four %}}
Outer Shortcode 
{{% sc/four %}}
Middle Shortcode
{{% sc/four %}}
Inner Shortcode
{{% /sc/four %}}
{{% /sc/four %}}
{{% /sc/four %}}

