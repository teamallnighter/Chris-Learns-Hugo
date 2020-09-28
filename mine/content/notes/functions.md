---
title: "Functions"
date: 2020-09-28T14:01:03-06:00
draft: false
author: Author Name
---

# Functions

## 2020-09-28T14:01:03-06:00

[Hugo Docs: Functions](https://gohugo.io/functions/)

```html
<hr>
is 22 more than 8? {{ if gt 22 8 }}YES{{ else }}NO{{ end }}
<hr>
```

to refactor using the cond feature

```html
<hr>
is 22 greater than 8? {{ cond (gt 22 8) "YES" "NO" }}
<hr>
```

```html
{{ humanize "some-dashed-string" }}
```

```html
{{ md5 "some-dashed-string }}
```


```html
{{ split "apple,grape,orange" "," }}
```

functions can also be context aware

