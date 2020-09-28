---
title: "Archetypes"
date: 2020-09-28T12:42:39-06:00
draft: false
author: Author Name
---

# Archetypes

## 2020-09-28T12:42:39-06:00

Archetypes are basically starting off points. 

The archetype for this post is:

```markdown
---
title: "{{ replace .Name "-" " " | title }}"
date: {{ .Date }}
draft: false
author: Author Name
---

# {{ replace .Name "-" " " | title }}

## {{ .Date }}
```

Running this command will create the jump off point for a new note. 

```bash
hugo new notes/archetypes.md
```





