# CSS Notes

CSS or **Cascading Style Sheets** is the language used to style the frontend of any website. CSS is a cornerstone technology of the World Wide Web, alongside HTML and JavaScript.

- [Selector](#selector)
- [Pseudo Classes](#pseudo-classes)
- [Pseudo Element](#pseudo-element)
- [Fonts](#fonts)
- [Length](#length)

<!-- - [Colors]() -->
<!-- - [Box Model]() -->
<!-- - [Position]() -->
<!-- - [Background]() -->
<!-- - [Display]() -->
<!-- - [Flex]() -->
<!-- - [Variables]() -->

## _Introduction_

This project is to have a record of what i have learned about CSS.

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
