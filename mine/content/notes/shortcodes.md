---
title: "Shortcodes"
date: 2020-09-28T14:13:47-06:00
draft: false
author: Author Name
---

# Shortcodes

## 2020-09-28T14:13:47-06:00

Shortcodes work a lot like in wordpress. Hugo has built in shortcodes like the youtube short code

```html

{" { < youtube adqBE3jHVI0 > } "}

```

{{< youtube adqBE3jHVI0 >}}





you can build your own shortcodes as well. 

inside of layouts/shortcodes/placehold.html

```html
<img src="https://placehold.it/750x400" alt="Placehold image"/>
```

We can now call this short code the same way 

```html
{ "{< placehold >} "}
```
{{< placehold 700 1000 >}}

if we want to add variables

```html
{{ $width := .Get "width"  }}
{{ $height := .Get "height" }}
<img src="https://placehold.it/{{$width}}x{{$height}}" alt="Placehold image"/>
```

no we can call 

```html
{ "{< placehold 700 400 >}" }
```
{{< placehold 250 250 >}}