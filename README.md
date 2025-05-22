# CSS Notes

CSS or **Cascading Style Sheets** is the language used to style the frontend of any website. CSS is a cornerstone technology of the World Wide Web, alongside HTML and JavaScript.

- [Reset Styles](/CSS/reset-styles.css)

## Table of content

- [Variables](#variables)
- [Length](#length)
- [Colors](#colors)
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

## Length

The length data type consists of a number followed by one of the units measurement.

- `Absolute` length units of measurement in CSS refer to units that do not change, those that are the same in all context.

  - Inches: `in`
  - Centimeters: `cm`
  - Picas: `pc`
  - Millimeters: `mm`
  - Points: `pt`
  - Pixels `px`
  - Quarter-millimeters: `q`

- The units of measurement in `relative` CSS depend on the element or factor to which they refer.

  - `em`: Font-size of the element.
  - `rem`: Font-size of the root element.
  - `vw`: 1% of the viewport's width.
  - `vh`: 1% of the viewport's height.
  - `%`: Percentage relative to the parent element.

## Colors

Color is an essential part of web design. It can influence the actions visitors take within a page, the way they read your content and, above all, how they feel when navigating your page.

| Types       | Description                                                                                                         |
| ----------- | ------------------------------------------------------------------------------------------------------------------- |
| Keyword     | Colors are represented by names instead of numbers                                                                  |
| Hexadecimal | It starts with # followed by 3 pairs of characters representing (red, green, blue). Values can range from 00 to FF. |
| RGB         | Starts with rgb() inside indicates the color intensity (red, green, blue) on a scale from 0 to 255.                 |
| HSL         | Starts with hsl() inside indicates the hue, saturation and lightness. the hue goes from 0 to 360 the rest in %.     |

```CSS
.element {
  color: red; /* keyword */
  color: #ff0000; /* hexadecimal */
  color: rgb(255, 0, 0); /* RGB */
  color: hsl(0, 100%, 50%); /* HSL */
}
```

### Alpha

The alpha parameter allows the color to have transparency. The values range from 0.0 (totally transparent) to 1.0 (totally opaque).

- Hexadecimal: a couple of additional characters are added to represent the alpha value.
- RGB: Start with `rgba()` to add alpha value.
- HSL: Start with `hsla()` to add alpha value.

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
