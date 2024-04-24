# CSS Architecture

Consists of managing CSS code with a set of rules and patterns to facilitate its readability, maintainability and scalability.

## Table of content

- [BEM](#block-element-modifier-bem)

## Block Element Modifier (BEM)

BEM is a CSS naming and code structure methodology that provides a way to write CSS class names.

- **Block**: It is the independent part in our HTML, it does not need other elements to exist.
- **Element**: An element will always be inside a block, because it is part of it and is dependent on it to exist.
- **Modifier**: Modifiers are used on elements or blocks, they are used to represent a different characteristic that the modifier or element will have.

```html
<section class="block">
  <div class="block__element"></div>
  <div class="block__element"></div>
  <div class="block__element block__element--modifier"></div>
</section>
```

<img width="600px" src="https://res.cloudinary.com/practicaldev/image/fetch/s--OkBgfgPx--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/i/yc0hv58in4eyxjj7qlcg.png">

[⬆️ Back to top ⬆️](#block-element-modifier-bem)
