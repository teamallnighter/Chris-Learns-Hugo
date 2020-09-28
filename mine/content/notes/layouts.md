---
title: "Layouts"
date: 2020-09-28T12:45:13-06:00
draft: false
author: Author Name
---

# Layouts

## 2020-09-28T12:45:13-06:00

Layouts have basic inheritance. the theme taking last priority

/themes/layouts/_default/basof.html is the base layout for all pages and they outter most html. Hugo will always look for basof.html

### Single Page

If a page doesnt have a layout hugo will go to /themes/layouts/_default/siungle.html

--> baseof.html ---> single.html

Baseof.html:

```html
<!DOCTYPE html>
<html lang="{{ .Site.LanguageCode | default "en" }}">
    {{ partial "head.html" . }}
    <body>
        {{ partial "header.html" . }}
        {{ block "main" . }}{{ end }}
        {{ partial "footer.html" . }}
    </body>
</html>
```
single.html

```html
{{ define "main" }}

<main>
	<div class="post">
		{{ partial "single/post-info.html" . }}
		{{ partial "single/title.html" . }}

		{{ partial "single/header.html" . }}

		{{ .Content }}

		{{ partial "single/footer.html" . }}
	</div>

	<div class="pagination">
		{{- if .PrevPage }}
		<a href="{{ .PrevPage.RelPermalink }}" class="left arrow">&#8592;</a>
		{{- end }}
		{{- if .NextPage }}
		<a href="{{ .NextPage.RelPermalink }}" class="right arrow">&#8594;</a>
		{{- end }}

		<a href="#" class="top">Top</a>
	</div>
</main>

{{ end }}

```

### Blocks

blocks are sort of like partials but in reverse. 

### Important layouts

basof.html
single.html
list.html
summary.html
taxonomy.html





