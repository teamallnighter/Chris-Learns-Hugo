---
title: "Types Kinds"
date: 2020-09-28T13:37:12-06:00
draft: false
author: Author Name
---

# Types Kinds

## 2020-09-28T13:37:12-06:00

[Content Types](https://gohugo.io/content-management/types/)
[Page Kinds](https://gohugo.io/templates/section-templates/#page-kinds)
[Config](https://gohugo.io/getting-started/configuration/)

Pages dont have to be of the same type as their section

kinds include sections themselves

in layouts we create a folder "topinfo"
inside of it we create "single.html

```html
{{ define "main" }}

<main>
  <h1>{{ .Title }}</h1>
  <hr>
  <div class="content">
    {{ .Content }}
  </div>
  <small>{{ .Site.Copyright }}</small>
</main>

{{ end }}
```
on about.md

```yml
---
title: "About"
date: 2019-11-22T17:33:57+02:00
draft: true
author: Ray Viljoen
type: topinfo
---
```

hugo will now go to "themes/layouts/_default/baseof.html" to get the ouuter html then to "/layouts/topinfo/single.html"
and inset the content into the html





