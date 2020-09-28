---
title: "Template Variables"
date: 2020-09-28T13:52:29-06:00
draft: false
author: Author Name
---

# Template Variables

## 2020-09-28T13:52:29-06:00

[Hugo Docs: Template Variables](https://gohugo.io/templates/introduction/#variables)

```html
{{ $titleColor := "hotpink" }}

{{ if eq .Type "photos" }}
{{ $titleColor = "red" }}
{{ end }}
<h1 style="color: {{ $titleColor }}">I AM THE TITLE</h1>
```

