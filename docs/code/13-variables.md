# Variables

Custom properties (sometimes referred to as CSS variables or cascading variables) are entities defined by CSS authors that represent specific values to be reused throughout a document.

```CSS
:root {
  --variable-color: #f00;
}
.class {
  color: var(--variable-color);
}
```
