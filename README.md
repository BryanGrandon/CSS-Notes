# CSS Notes

CSS or **Cascading Style Sheets** is the language used to style the frontend of any website. CSS is a cornerstone technology of the World Wide Web, alongside HTML and JavaScript.

## Table of content

- [Variables](#variables)

## Variables

Custom properties (sometimes referred to as CSS variables or cascading variables) are entities defined by CSS authors that represent specific values to be reused throughout a document.

```CSS
/* The variable name must be clear and consistent. */

:root {
  --color-primary: #f00;
  --font-custom: 'JetBrains Mono', sans-serif;
}
.class {
  color: var(--color-primary);
  font-family: var(--font-custom);
}
```
