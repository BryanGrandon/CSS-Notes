# CSS Notes

CSS or **Cascading Style Sheets** is the language used to style the frontend of any website. CSS is a cornerstone technology of the World Wide Web, alongside HTML and JavaScript.

## Table of content

- [Variables](#variables)
- [Animations](#animations)

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

## Animations

Animations are small changes in the content or visual aspect of a page, so that it is more user-friendly to view. They can be simple, such as changing the color or size of an image, as well as more complex animations, such as transformations or specific movements.

### [Transition](/CSS/transition.css)

A transition is a very simple type of animation between two different states. This type of animation is generally produced by a user interaction with the website or an element of the website, in order to smooth the change of state.

| CSS property                 | It allows us to.                                                                                                  |
| ---------------------------- | ----------------------------------------------------------------------------------------------------------------- |
| `transition-property`        | Allows us to set the CSS properties to which a transition effect should be applied.                               |
| `transition-duration`        | Allows us to set the time it will take for a transition animation to complete.                                    |
| `transition-timing-function` | Allows us to set how the intermediate values of CSS properties affected by a transition effect are calculated.    |
| `transition-delay`           | Allows us to specify the time to wait before starting the transition effect of a property when its value changes. |

The abbreviated property is `transition`.

```CSS
/* transition: property duration timing-function delay */
.element {
    transition: background 1s ease-in;
}
```
