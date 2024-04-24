# CSS Notes

CSS or **Cascading Style Sheets** is the language used to style the frontend of any website. CSS is a cornerstone technology of the World Wide Web, alongside HTML and JavaScript.

- [CSS Architecture](/docs/css-architecture.md)
- [Projects](/docs/projects.md)

## _Table of content_

- [Selector](#selector)
- [Pseudo-classes](#pseudo-classes)
- [Pseudo-element](#pseudo-element)
- [Fonts](#fonts)
- [Length](#length)
- [Colors](#colors)
- [Box Model](#box-model)
- [Position](#position)
- [Background](#background)
- [Display](#display)
- [Flex](#flex)
- [Variables](#variables)
- [Reset css styles](#reset-css-styles)

## _Introduction_

This project is to have a record of what i have learned about CSS.

### Related websites

- [CSS Tips](https://markodenic.com/css-tips/#css-typing-effect)

[⬆️ Back to top ⬆️](#css-notes)

## [Selector](/code/selector.css)

Selectors define on which elements a set of CSS rules will be applied.

- **Universal selector** allows you to select all HTML elements.
- **Type selector** allows you to select the HTML tag itself.
- **Class selector** allows you to select all the elements that have the same name in the class attribute
- **Id selector** allows you to select a specific HTML element, since the name assigned to the id attribute must be unique.
- **Attribute selector** allow you to select all the elements that correspond to a specific attribute or to a defined attribute value.

[⬆️ Back to top ⬆️](#css-notes)

## [Pseudo-classes](/code/pseudo-classes.css)

A CSS pseudo class is a keyword added to selectors that specifies a special state of the selected element.

- `:hover` Allows you to apply a style when hovering over an element.
- `:active` Allows to apply a style when the element is activated.
- `:visited` Styles are applied once the link has been visited by the user.
- `:link` The styles are applied to the link that has not yet been visited.

See more in [MDN web docs](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes)

[⬆️ Back to top ⬆️](#css-notes)

## [Pseudo-element](/code/pseudo-element.css)

Pseudo-elements are added to the selectors, but they do not describe a special state, but allow you to add styles to a specific part of the document.

- `::after` allows us to add a cosmetic content after the element using the `content` property.
- `::before` allows us to add a cosmetic content before the element using the `content` property.
- `::first-letter` Applies styles to the first letter of the content.
- `::first-line` Apply styles to the first line of content.
- `::selection` Applies styles to the part of a document that has been highlighted by the user.
- `::placeholder` represents the temporary text in an `<input>` element or a `<textarea>` element.

See more in [MDN web docs](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements)

[⬆️ Back to top ⬆️](#css-notes)

## [Fonts](/code/fonts.css)

CSS Fonts is the CSS module that defines everything related to typographic resources.

- `font-family` defines a list of fonts or font families.
- `font-size` specifies the size of the letter.
- `font-weight` specifies the weight or thickness of the letter.
- `font-style` allows you to define the appearance of a font family.
- `font-variant` select between normal and small-caps aspects.
- `line-height` set the distance between lines of text.

See more in [MDN web docs](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_fonts)

[⬆️ Back to top ⬆️](#css-notes)

## Length

The length data type consists of a number followed by one of the units measurement.

### _Absolute length units_

Absolute units of measurement in CSS refer to units that do not change, those that are the same in all context.

- Inches: `in`
- Centimeters: `cm`
- Picas: `pc`
- Millimeters: `mm`
- Points: `pt`
- Pixels `px`
- Quarter-millimeters: `q`

### _Relative length units_

The units of measurement in relative CSS depend on the element or factor to which they refer.

- `em`: Font-size of the element.
- `rem`: Font-size of the root element.
- `vw`: 1% of the viewport's width.
- `vh`: 1% of the viewport's height.
- `%`: Percentage relative to the parent element.

[⬆️ Back to top ⬆️](#css-notes)

## [Colors](/code/color.css)

Color is an essential part of web design. It can influence the actions visitors take within a page, the way they read your content and, above all, how they feel when navigating your page.

- Keyword

  - Colors in HTML are represented by names instead of numbers. Currently 140 color names are available that can be supported by existing browsers.

- Hexadecimal

  - Hexadecimal color codes consist of a # sign and three pairs of characters representing the intensity of the three primary colors (red, green and blue, in that order). The values can range from 00 (which is the lowest intensity) to FF (which is the highest intensity).

- RGB

  - RGB color codes are composed of three numbers separated by commas. Each represents the intensity of the primary colors by an integer on a scale from 0 to 255.

- HSL

  - The main difference between HSL and RGB is that the HSL values do not represent the intensity of each primary color. Instead, the values represent hue, saturation and lightness. Hue is measured on a scale that goes from 0 to 360

- Alpha

  - The alpha parameter allows the color to have transparency. The values range from 0.0 (totally transparent) to 1.0 (totally opaque).

[⬆️ Back to top ⬆️](#css-notes)

## [Box Model](/code/box-model.css)

Everything in CSS has box around it, and understanding these boxes in key to being able to create more complex layouts with CSS, or to align items with other items.

- `padding`: Padding represents the amount of inner space an element has.
- `margin`: The margin is whitespace available surrounding an element.
- `width`: The width property allows you to set how wide your container will be.
- `height`: The height CSS property specifies the height of an element.
- `border`: The border property allows you to define in a single rule all the borders of the selected elements.
- `box-sizing`: The box-sizing CSS property sets how the total width and height of an element is calculated.

[⬆️ Back to top ⬆️](#css-notes)

## [Position](/code/position.css)

The position CSS property sets how an element is positioned in a document.

- `static`: The element is positioned according to the normal document flow
- `relative`: The element is positioned according to the normal flow of the document, and then offset relative to itself, based on the values of top, right, bottom, and left. The offset does not affect the position of any other element.
- `absolute`: An element with position: absolute is removed from the normal document flow. It is automatically positioned at the starting point of its parent element.
- `fixed`: Fixed positioning causes an element to be positioned relative to the viewport. You tell it where to position the element, and it stays there while the user scrolls.
- `sticky`: Sticky positioning can be considered a hybrid of relative and fixed positioning.

[⬆️ Back to top ⬆️](#css-notes)

## [Background](/code/background.css)

The background shorthand CSS property sets all background style properties at once, such as color, image, origin and size, or repeat method.

- `background-color`: Sets the background color of an element.
- `background-image`: Sets one or more background images on an element.
- `background-size`: Set a different size to the background image.
- `background-repeat`; Repetition of the background image.
- `background-position`; Position of the background image (x, y).
- `background-attachment`; Background image behavior.
- `background-clip`; Background image relented.
- `opacity`: Sets the transparency of the element

[⬆️ Back to top ⬆️](#css-notes)

## Display

The CSS display property specifies whether an element is treated as a block or inline element.

- `block`: Makes the behavior of the element like a block.
- `inline`: The element will be rendered in line with other elements.
- `inline-block`: The element will have a mixed behavior between the two previous ones.
- `none`: Hides an element, so it will not take up any space.

[⬆️ Back to top ⬆️](#css-notes)

## [Flex](/code/flex.css)

The Flexible Box Module, commonly as a one-dimensional layout model, and as a method that con help distribute the space between items in an interface and improve alignment capabilities.

- `flex-direction`: The flex-direction CSS property sets how flex items are placed in the flex container defining the main axis and the direction (normal or reversed).
- `flex-wrap`: The CSS flex-wrap property specifies whether "child" elements are forced to stay on a single line or can flow on multiple lines.
- `justify-content`: The CSS justify-content property defines how the browser distributes space between and around content items along the main-axis of a flex container.
- `align-items`: The CSS align-items property sets the align-self value on all direct children as a group.
- `gap`: The gap CSS shorthand property sets the gaps (gutters) between rows and columns.

[⬆️ Back to top ⬆️](#css-notes)

## Variables

Custom properties (sometimes referred to as CSS variables or cascading variables) are entities defined by CSS authors that represent specific values to be reused throughout a document.

```CSS
:root {
  --variable-color: #f00;
}
.class {
  color: var(--variable-color);
}
```

[⬆️ Back to top ⬆️](#css-notes)

## Reset css styles

Reset all default browser styles.

```CSS
*{
  margin:0;
  padding:0;
  box-sizing: border-box;
  min-width:0;
}

body{
  min-height:100dvh;
}

h1, h2, h3, h4 {
  text-wrap: balance;
}

p {
  text-wrap: pretty;
}
```

Another way to reset the styles is to use a [css file](/code/reset-css-styles.css)

[⬆️ Back to top ⬆️](#css-notes)
