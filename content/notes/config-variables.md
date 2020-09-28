---
title: "Config Variables"
date: 2020-09-28T13:20:28-06:00
draft: false
author: Author Name
---

# Configuration & Variables

## 2020-09-28T13:20:28-06:00

## Site Variables

[Site Variables](https://gohugo.io/variables/site/#readout)

> Many, but not all, site-wide variables are defined in your site’s configuration. However, Hugo provides a number of built-in variables for convenient access to global values in your templates.

```html
<hr>
{{ .site.Title }}
<br>
{{ .site.BaseURL }}
<hr>
```

In the config file

```toml
baseURL = "http://example.org/"
languageCode = "en-us"
title = "Chris Learns Hugo"
theme = "tale"
author = "Chris Connelly"
```
```html
<hr>
{{- range .Site.Pages }}
{{ . }} <br>
{{- end }}
<hr>
---

## Page Variables

[Page Variables](https://gohugo.io/variables/page/)




