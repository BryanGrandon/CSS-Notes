# CSS Notes

CSS or **Cascading Style Sheets** is the language used to style the frontend of any website. CSS is a cornerstone technology of the World Wide Web, alongside HTML and JavaScript.

- [Projects](/projects/projects.md)

## _Table of content_

- [Selector](#selector)
- [Pseudo Classes](#pseudo-classes)
- [Pseudo Element](#pseudo-element)
- [Fonts](#fonts)
- [Length](#length)
- [Colors](#colors)
- [Box Model](#box-model)
- [Position](#position)
- [Background](#background)
- [Display](#display)
- [Flex](#flex)
- [Variables](#variables)

## _Introduction_

This project is to have a record of what i have learned about CSS.

### Related websites

- [CSS Tips](https://markodenic.com/css-tips/#css-typing-effect)

## _Selector_

Selectors define on which elements a set of CSS rules will be applied.

```CSS
/* All elements */
* {}

/* Elements HTML */
div {}

/* Attribute Class */
.class {}

/* Attribute Id */
#id {}

/* Descendent */
.parent .child {}

/* Direct descendent */
.parent > .child {}

/* Adjacent sibling */
.child + .sibling {}

/* Far sibling */
.child ~ .sibling {}

/* Have both classes */
.class1.class2 {}

/* Attribute */
[attribute-name] {}
[exact="value"] {}
[Has~="value"] {}
[end-in$="ends in"] {}
[begins-with^="begins"] {}
```

## _[Pseudo Classes](/code/pseudo-classes/pseudo-classes.html)_

A CSS pseudo class is a keyword added to selectors that specifies a special state of the selected element.

```CSS
/* Allows you to apply a style when hovering over an element. */
.hover:hover {}

/* Allows to apply a style when the element is activated. */
.active:active {}

/* Styles are applied once the link has been visited by the user. */
.visited:visited {}

/* The styles are applied to the link that has not yet been visited. */
.link:link {}

/* Styles are applied to the element that is currently selected and ready to receive actions. */
.focus:focus {}

/* Styles are applied to any element that has the required attribute set. */
.required:required {}

/* Styles are applied to any element that is validated. */
.valid:valid {}

/* Styles are applied to any validated element that does not meet their constraints. */
.valid:invalid {}

/* Styles are applied to the element when it is disabled. */
.disabled:disabled {}

/* :first-of-type */
.of-type li:first-of-type {}

/* :last-of-type */
.of-type li:last-of-type {}

/* :nth-of-type() */
.of-type li:nth-of-type(3) {}

/* :first-child */
.of-child li:first-child {}

/* :last-child */
.of-child li:last-child {}

/* :nth-child
      - ( odd ) 1,3,5,7...
      - ( even ) 2,4,6,8...
*/
.of-child li:nth-child(3) {}
```

## [Pseudo Element](/code/pseudo-element/pseudo-element.html)

Pseudo-elements are added to the selectors, but they do not describe a special state, but allow you to add styles to a specific part of the document.

```CSS
/* ::first-letter */
.first-letter::first-letter {}

/* ::first-line */
.first-line::first-line {}

/* ::selection */
.selection::selection {}

/* ::before */
.before::before {}

/* ::after */
.after::after {}
```

## _Fonts_

The CSS fonts module defines font-related properties and how font resource are loaded.

```CSS
p {
  font-family: "Times New Roman", Times, serif;
  font-size: 20px;
  font-weight: bolder;
  font-style: italic;
  text-align: center;
  text-decoration: overline;
  text-transform: capitalize;
  letter-spacing: 5px;
  line-height: 1.4;
}
```

## _Length_

The length data type consists of a number followed by one of the units measurement.

```CSS
/* Absolute length units */

.length__inches {
  size: 10in;
}
.length__centimeters {
  size: 10cm;
}
.length__millimeters {
  size: 100mm;
}
.length__points {
  size: 100pt;
}
.length__picas {
  size: 100pc;
}
.length__pixels {
  size: 100px;
}

/* Relative length units */
/*
    - `em` -> Font-size of the element.
    - `rem` -> Font size of the root element.
    - `vw` -> 1% of the viewport's width.
    - `vh` -> 1% of the viewport's height.
    - `vmin` -> 1% of the viewport's smaller dimension.
    - `vmax` -> 1% of the viewport's larger dimension.
    - `%` -> Percentage relative to the parent element.
*/
```

## _Colors_

Ways to add colors to website.

```CSS
.keyword {
  color: red;
}
.hexadecimal {
  color: #ff0000;
}
.rgb {
  color: rgb(255, 0, 0);
}
.hsl {
  color: hsl(0, 100%, 50%);
}

.alpha {
  color: rgba(255, 0, 0, 0.2);
  color: hsla(0, 100%, 50%, 0.2);
  color: #ff000033;
}
```

## _[Box Model](/code/box-model/box-model.html)_

Everything in CSS has box around it, and understanding these boxes in key to being able to create more complex layouts with CSS, or to align items with other items.

```CSS
/* padding: top right bottom left */
.padding {
  padding-top: 20px;
  padding-right: 20px;
  padding-bottom: 20px;
  padding-left: 20px;

  padding: 20px;
}
/* margin: top right bottom left */
.margin {
  margin-top: 20px;
  margin-right: 20px;
  margin-bottom: 20px;
  margin-left: 20px;

  margin: 20px;
}
.width {
  width: 200px;
}
.height {
  display: inline-block;
  height: 100px;
}
.border__solid {
  border: 3px solid mediumaquamarine;
}
.border__double {
  border: 3px double mediumorchid;
}
.border__dotted {
  border: 3px dotted mediumpurple;
}
.border__dashed {
  border: 3px dashed mediumseagreen;
}
.border__groove {
  border: 3px groove mediumslateblue;
}
.border__ridge {
  border: 3px ridge mediumspringgreen;
}
.border__inset {
  border: 3px inset mediumturquoise;
}
.border__outset {
  border: 3px outset mediumvioletred;
}
.border-sizing__border-box {
  box-sizing: border-box;
}
.border-sizing__content-box {
  box-sizing: content-box;
}
```

## _Position_

The position CSS property sets how an element is positioned in a document.

```CSS
/* The element is positioned according to the normal document flow. */
.position__static {
  position: static;
}

/* The element is positioned according to the normal flow of the document, and then offset relative to itself, based on the values of top, right, bottom, and left. The offset does not affect the position of any other element. */
.position__relative {
  position: relative;
}

/* An element with position: absolute is removed from the normal document flow. It is automatically positioned at the starting point of its parent element. */
.position__absolute {
  position: absolute;
}

/* Fixed positioning causes an element to be positioned relative to the viewport. You tell it where to position the element, and it stays there while the user scrolls. */
.position__fixed {
  position: fixed;
}

/* Sticky positioning can be considered a hybrid of relative and fixed positioning. */
.position__sticky {
  position: sticky;
}
```

## _Background_

The background shorthand CSS property sets all background style properties at once, such as color, image, origin and size, or repeat method.

```CSS
.background {
  background-color: mediumpurple;
  background-image: url("https://");

  /* Set a different size to the background image */
  background-size: contain;

  /* Repetition of the background image */
  background-repeat: no-repeat;

  /* Position of the background image */
  background-position-x: 30px;
  background-position-y: 10px;

  /* Background image behavior */
  background-attachment: scroll;

  /* Background image relented */
  background-clip: content-box;

  /* Sets the transparency of the element */
  opacity: 0.5;
}
```

## _Display_

The CSS display property specifies whether an element is treated as a block or inline element.

```CSS
.display {
  display: inline;
  display: block;
  display: inline-block;
  display: none;
}
```

## _[Flex](/code/flex/flex.html)_

The Flexible Box Module, commonly as a one-dimensional layout model, and as a method that con help distribute the space between items in an interface and improve alignment capabilities.

```CSS
.flex-direction {
  display: flex;
  flex-direction: row;
  flex-direction: row-reverse;
  flex-direction: column;
  flex-direction: column-reverse;
}
.flex-wrap {
  display: flex;
  flex-wrap: nowrap;
  flex-wrap: wrap;
  flex-wrap: wrap-reverse;
}
.justify-content {
  display: flex;
  justify-content: flex-start;
  justify-content: center;
  justify-content: flex-end;
  justify-content: space-between;
  justify-content: space-around;
  justify-content: space-evenly;
}
.align-items {
  display: flex;
  align-items: start;
  align-items: end;
  align-items: center;
  align-items: stretch;
}
.gap {
  display: flex;
  gap: 30px;
}
```

## _Variables_

Custom properties (sometimes referred to as CSS variables or cascading variables) are entities defined by CSS authors that represent specific values to be reused throughout a document.

```CSS
:root {
  --variable-color: #f00;
}
.class {
  color: var(--variable-color);
}
```
