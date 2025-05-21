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

Animations are small changes to the content or visual appearance of a page to make it more comfortable for the user to view.

### [Transition](/CSS/transition.css)

A transition is a very simple type of animation between two different states. This type of animation is generally produced by a user interaction with the website or an element of the website, in order to smooth the change of state.

```SCSS
/* transition: <property> <duration> <timing-function> <delay> */

.element {
    background: red;
    transition: background 1s ease-in;

    &:hover {
        background: green ;
    }
}

```

### [Animation](/CSS/animation.css)

Animations allow you to animate the transition between one CSS style and another. Animations consist of two components: a style describing the CSS animation and a set of frames indicating its initial and final state, as well as possible intermediate points in the animation.

```CSS
  /* animation: <name> <duration> <timing-function> <delay> <iteration-count> <direction> <fill-mode> */

  .element {
    animation: change-color 5s linear 0.5s 4 normal both;
  }
```

To define the keyframes of the animation, we will use the `@keyframes` rule.

```CSS
@keyframes change-color {
    from { background: red; } /* First key frame */
    to { background: green; } /* Second and last key frame */
}
```
