# CSS Notes

CSS or **Cascading Style Sheets** is the language used to style the frontend of any website. CSS is a cornerstone technology of the World Wide Web, alongside HTML and JavaScript.

- [Selector](#selector)
- [Pseudo Classes](#pseudo-classes)

<!-- - [Pseudo Element]() -->
<!-- - [Fonts]() -->
<!-- - [Lengths]() -->
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
