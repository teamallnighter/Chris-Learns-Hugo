---
title: "Templating Basics"
date: 2020-09-28T12:54:18-06:00
draft: false
author: Author Name
---

# Templating Basics

## 2020-09-28T12:54:18-06:00

  * [PARTIALS](#partials)
  * [The dot](#the-dot)
- [Conditionals](#conditionals)
- [Template Loops](#template-loops)

### PARTIALS

partials are what hugo calls includes. Smaller reusable sections of code. 
partials are context aware
creating a folder with the name of the layout will include those partials. 

all template tags use double curly brackets

```html
{{ partial "single/post-info.html" . }}
```


```html
<main>
	<div class="post">
		{{ partial "single/post-info.html" . }}
		{{ partial "single/title.html" . }}

		{{ partial "single/header.html" . }}

		{{ .Content }}

		{{ partial "single/footer.html" . }}
    </div>
```

### The dot

```html
{{ partial "single/header.html" . }}
```
The dot is the current context of the layout
the scope in which we access all variables. 

```html
{{ partial "comments.html" .Title }}
```

This passes the scope of "title to the comments.html partial

```html
<h1>{{ . }}</h1>
```

This would generate the title from the "."

to pass the entire context to the partial we would use 

```html
{{ . }}
```

```html
<h1>{{ .title }}</h1>
<small>{{ .params.author }}</small>
```

This would pull the title from the page and the author from the front matter

## Conditionals

We can check if certain things are met before generating from the dot

```html
<h1>{{ .title }}</h1>
{{- if .params.author }}
<small>{{ .params.author }}</small>
{{- end }}
```

## Template Loops

```yml
---
title: "First Page"
date: 2020-09-24T19:07:24-06:00
draft: false
author: Chris Connelly
tags: ['photo', 'dog', 'post']
---
```

inside the partial

```html
{{- range .Params.tags }}
#{{ . }}
{{- end}}
```
This will loop through each item in the tags front matter and add the hash 

We can create a conditional for a partial and instead have the code above put into "tags.html" and run this:

```html
{{- if Params.tags }}
{{ partial "tags.html" Params.tags }}
{{- end}}
```

This will check if the parameters are in the front matter and if they are print them within this conditional. We use the Params.tags as the partial doesnt need the entire page context

## Links

[Introduction to templating](https://gohugo.io/templates/introduction/)

[Hugo: Partials](https://gohugo.io/templates/partials/)

[Conditionals](https://gohugo.io/templates/introduction/#conditionals)

[Itiration](https://gohugo.io/templates/introduction/#iteration)

[Context (the dot)](https://gohugo.io/templates/introduction/#the-dot)
