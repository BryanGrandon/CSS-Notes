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

| CSS property                 | Description                                                    |
| ---------------------------- | -------------------------------------------------------------- |
| `transition-property`        | CSS properties to which a transition effect should be applied. |
| `transition-duration`        | Time it will take for a transition animation to complete.      |
| `transition-timing-function` | The type of speed the transition will have                     |
| `transition-delay`           | Waiting time before starting the animation                     |

The abbreviated property is `transition`.

```CSS
/* transition: <property> <duration> <timing-function> <delay> */
.element {
    transition: background 1s ease-in;
}
```

### Animation

Animations allow you to animate the transition between one CSS style and another. Animations consist of two components: a style describing the CSS animation and a set of frames indicating its initial and final state, as well as possible intermediate points in the animation.

| Property                      | Description                          |
| ----------------------------- | ------------------------------------ |
| `animation-name`              | Name of the animation to be applied. |
| `animation-duration`          | Animation duration.                  |
| `animation-timing-function`   | Pace of the animation.               |
| `animation-delay`             | Delay in starting the animation.     |
| `animation-interaction-count` | Number of times to be repeated.      |
| `animation-direction`         | Animation direction.                 |
| `animation-fill-mode`         | How the animation is “completed”.    |

The abbreviated property is `animation`.

```CSS
  /* animation: <name> <duration> <timing-function> <delay> <iteration-count> <direction> */

  .element {
    animation: change-color 5s linear 0.5s 4 normal both;
  }
```

To define the keyframes of the animation, we will use the `@keyframes` rule.

```CSS
@keyframes change-color {
    /* First key frame */
    from {
        background: red;
    }
    /* Second and last key frame */
    to {
        background: green;
    }
}
```
