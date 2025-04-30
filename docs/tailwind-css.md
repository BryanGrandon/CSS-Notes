# Tailwind CSS

Tailwind CSS is a utility-first CSS framework with predefined classes that you can use to build and design web pages directly in your markup. It lets you write CSS in your HTML in the form of predefined classes.

## Table of content

- [Installation](#installation)
- [Introduction](#introduction)
- [Size](#size)
- [Layout](#layout)
- [Pseudo-classes](#pseudo-classes)
- [Typography](#typography)
<!-- Checking -->
- [Backgrounds](#backgrounds)
- [Flex box](#flex-box)
- [Grid](#grid)
- [Box-alignment](#box-alignment)
- [Border](#border)
- [Transitions and Animation](#transitions-and-animation)
- [Transforms](#transforms)
- [Interactivity](#interactivity)
- [Filter](#filter)
- [Effects](#effects)

## Installation

### [Vite](https://tailwindcss.com/docs/installation/using-vite)

```bash
npm install tailwindcss @tailwindcss/vite -D
```

Add the @tailwindcss/vite plugin to your Vite configuration.

```ts
// vite.config.ts
import { defineConfig } from 'vite'
import tailwindcss from '@tailwindcss/vite'
export default defineConfig({
  plugins: [tailwindcss()],
})
```

Add an @import to your CSS file that imports Tailwind CSS.

```css
@import 'tailwindcss';
```

## Introduction

Tailwind's CSS utility classes are mostly abbreviations for the properties we write in CSS.
This allows us to intuitively understand Tailwind's classes

| CSS                | TailwindCSS classes |
| ------------------ | ------------------- |
| `width: ...`       | `w-{size}`          |
| `min-width: ...`   | `min-w-{size}`      |
| `max-width: ...`   | `max-w-{size}`      |
| `padding: ...`     | `p-{size}`          |
| `margin: ...`      | `m-{size}`          |
| `display: none`    | `hidden`            |
| `overflow: hidden` | `overflow-hidden`   |

when the value that can be entered is negative, only a dash (`-`) is added at the beginning of the class

```HTML
<div class="absolute top-2"></div> <!-- CSS: top:0.5rem -->
<div class="absolute -top-2"></div> <!-- CSS: top: -0.25rem -->
```

## Size

When we want to set a **small** size, the property is indicated followed by a number `w-0`. Each number indicates by how much `0.25rem` will be multiplied.

```HTML
<div class="w-0"></div> <!-- CSS: width: 0rem -->
<div class="w-4"></div> <!-- CSS: width: 1rem -->
```

When we want to set a **medium** size, the property is indicated followed by a nomenclature similar to the nomenclature for sizes in clothing `w-md`.

| Nomenclature | Size  |
| ------------ | ----- |
| `xs`         | 20rem |
| `sm`         | 24rem |
| `md`         | 28rem |
| `lg`         | 32rem |
| `xl`         | 36rem |
| `2xl`        | 42rem |
| `3xl`        | 48rem |

```HTML
<div class="w-lg"></div> <!-- CSS: width: 32rem -->
```

When we want to set a **large** size, we specify the property followed by the `w-auto` keyword.

| Size     | CSS           |
| -------- | ------------- |
| `none`   | none          |
| `auto`   | auto          |
| `full`   | 100%          |
| `screen` | 100vw / 100vh |
| `min`    | min-content   |
| `max`    | max-content   |

```HTML
<div class="w-screen-lg"></div> <!-- CSS: width: 1024px -->
```

When we want to set a dynamic size, we specify the property followed by a fraction `w-1/2`. The fraction tells us how much of 100% will be used.

```HTML
<div class="w-1/4"></div> <!-- CSS: width: 25% -->
```

## Layout

### Breakpoints \Change

Breakpoints (screen sizes) that wrap utility classes.

| breakpoint | CSS                                |
| ---------- | ---------------------------------- |
| `sm:`      | @media (min-width: 640px) { ... }  |
| `md:`      | @media (min-width: 760px) { ... }  |
| `lg:`      | @media (min-width: 1024px) { ... } |
| `xl:`      | @media (min-width: 1200px) { ... } |
| `2xl:`     | @media (min-width: 1536px) { ... } |

### Box-sizing \Change

Sets how the total width and height of an element is calculated.

| class         | CSS                      |
| ------------- | ------------------------ |
| `box-border`  | box-sizing: border-box;  |
| `box-content` | box-sizing: content-box; |

### Display

To set the type of display box for an element, type the desired value directly.

```HTML
<div class="block"></div> <!-- CSS: display: block -->
```

### Overflow

To set how to handle content that is too large for its container, we write the property followed by its `overflow-hidden` value.

```HTML
<!-- CSS: overflow: hidden; width: 2.5rem; height: 2.5rem -->
<div class="w-10 h-10 overflow-hidden"></div>
```

In addition, you can specify horizontal (`overflow-x-{value}`) and vertical (`overflow-y-{value}`) overflow.

```HTML
<!-- CSS: overflow: hidden; width: 2.5rem; height: 2.5rem -->
<div class="w-10 h-10 overflow-y-hidden overflow-x-auto"></div>
```

### Position

To set the position of an element, the value of the CSS property `absolute` is written directly.

```HTML
<div class="fixed"></div> <!-- CSS: position: fixed; -->
```

To set the placement of a positioned element, the CSS property is used directly followed by a **number** or **fraction** `top-4`. The properties are as follows: `top`, `bottom`, `left`, `right`, `inset`.

```HTML
<div class="absolute top-1"></div> <!-- CSS: top: 0.25rem; -->
<div class="absolute -top-2"></div> <!-- CSS: top: -0.5rem; -->
<div class="absolute top-1/2"></div> <!-- CSS: top: 50%; -->
<div class="absolute inset-4"></div> <!-- CSS: inset: 1rem -->
```

### Visibility

To show or hide without affecting the layout of the document. Use `visible` to show and `invisible` to hide.

```HTML
<div class="visible"></div> <!-- CSS: visibility: visible; -->
<div class="invisible"></div> <!-- CSS: visibility: hidden; -->
```

### Z-index

To set the z-order (“stack order”) of a positioned element, we write the property followed by a number `z-10`.

```HTML
<div class="z-10"></div>
```

The higher the number, the higher the priority of the element.

## Pseudo-classes

Pseudoclasses must be written for each property to be modified in the assigned element, this is done by writing the pseudoclass followed by the property to be modified `hover:w-20`.

```HTML
<div class="hover:w-20"></div>  <!-- CSS: @:hover { width: 5rem } -->
<div class="active:scale-95"></div> <!-- CSS: @:active { scale: 0.95 } -->
```

## Typography

| Property       | TailwindCSS class      | CSS                               |
| -------------- | ---------------------- | --------------------------------- |
| Color          | `text-{color}-{light}` | color: color ;                    |
| font-size      | `text-{size}`          | font-size: ...; line-height: ...; |
| text-alight    | `text-center`          | text-align: center;               |
| text-transform | `text-uppercase`       | text-transform: uppercase;        |

```HTML
<div class="text-red-500"></div>  <!-- CSS: color: #fb2c36; -->
<div class="text-lg"></div> <!-- CSS:  font-size: 1.125rem; line-height: 1.75rem; -->
<div class="text-center"></div> <!-- CSS: text-align: center; -->
<div class="text-capitalize"></div> <!-- CSS: text-transform: capitalize; -->
```

### Font Size

| Size        | CSS                                        |
| ----------- | ------------------------------------------ |
| `text-xs`   | font-size: 0.75rem; line-height: 1rem;     |
| `text-sm`   | font-size: 0.875rem; line-height: 1.25rem; |
| `text-base` | font-size: 1rem; line-height: 1.5rem;      |
| `text-lg`   | font-size: 1.125rem; line-height: 1.75rem; |
| `text-xl`   | font-size: 1.25rem; line-height: 1.75rem;  |

### Font-family

To set the font family, you must start with the word `font` followed by the font to use `font-sans`.

| type    | CSS                                             |
| ------- | ----------------------------------------------- |
| `sans`  | font-family: ui-sans-serif, system-ui, ...;     |
| `serif` | font-family: ui-serif, Georgia, Cambria, ...;   |
| `mono`  | font-family: ui-monospace, SFMono-Regular, ...; |

```HTML
<p class="font-sans">Text</p>
```

### Font-weight

Sets the font weight. `font-{weight}`

| Weight       | CSS               |
| ------------ | ----------------- |
| `thin`       | font-weight: 100; |
| `extraLight` | font-weight: 200; |
| `light`      | font-weight: 300; |
| `normal`     | font-weight: 400; |
| `medium`     | font-weight: 500; |
| `semiBold`   | font-weight: 600; |
| `bold`       | font-weight: 700; |
| `extraBold`  | font-weight: 800; |
| `black`      | font-weight: 900; |

```html
<p class="font-bold">Text bold</p>
```

## Backgrounds

### background-attachment

Sets behavior of background images when scrolling. `bg-{attachment}`

| Attachment | CSS                           |
| ---------- | ----------------------------- |
| `fixed`    | background-attachment: fixed; |
| `local`    | background-attachment: local; |
| `scroll`   | background-attachment: scroll |

```html
<div class="bg-fixed"></div>
```

### Background-clip

Sets where a background extends. `bg-clip-{clip}`

| Clip      | CSS                                                   |
| --------- | ----------------------------------------------------- |
| `border`  | background-clip: border-box;                          |
| `padding` | background-clip: padding-box;                         |
| `content` | background-clip: content-box;                         |
| `text`    | -webkit-background-clip: text; background-clip: text; |

### Background-color

Sets background color. `bg-{color}-{strong}`

```html
<div class="bg-red-500"></div>
```

### Background-position

Sets position of a background image. `bg-{position}`

| Position       | CSS                                |
| -------------- | ---------------------------------- |
| `bottom`       | background-position: bottom;       |
| `center`       | background-position: center;       |
| `left`         | background-position: left;         |
| `left-bottom`  | background-position: left bottom;  |
| `left-top`     | background-position: left top;     |
| `right`        | background-position: right;        |
| `right-bottom` | background-position: right bottom; |
| `right-top`    | background-position: right top;    |
| `top`          | background-position: top;          |

```html
<div class="bg-center"></div>
```

### Background-size

Sets background size of a background image. `bg-{size}`

| Size      | CSS                       |
| --------- | ------------------------- |
| `auto`    | background-size: auto;    |
| `cover`   | background-size: cover;   |
| `contain` | background-size: contain; |

```html
<div class="bg-cover"></div>
```

### Gradient color

Sets the background color gradients and where to stop. `from-{color}`, `to-{color}`

```html
<div class="from-blue-600 to-red-600"></div>
```

## Flex box

### Display

Sets element to be a flex container.

| display       | CSS                   |
| ------------- | --------------------- |
| `flex`        | display: flex;        |
| `inline-flex` | display: inline-flex; |

```html
<p class="flex">Text</p>
```

### Flex-direction

Sets direction of flex items. `flex-{direction}`

| direction     | CSS                             |
| ------------- | ------------------------------- |
| `row`         | flex-direction: row;            |
| `row-reverse` | flex-direction: row-reverse;    |
| `col`         | flex-direction: column;         |
| `col-reverse` | flex-direction: column-reverse; |

```html
<p class="flex flex-col">Text</p>
```

### Flex-wrap

Creates how flex items wrap. `flex-{wrap}`

| Wrap           | CSS                      |
| -------------- | ------------------------ |
| `wrap`         | flex-wrap: wrap;         |
| `wrap-reverse` | flex-wrap: wrap-reverse; |
| `no-wrap`      | flex-wrap: nowrap;       |

```html
<p class="flex flex-row flex-no-wrap">Text</p>
```

## Grid

### Display

Sets element to be a grid container.

| Grid          | CSS                   |
| ------------- | --------------------- |
| `grid`        | display: grid;        |
| `inline-grid` | display: inline-grid; |

```html
<p class="grid">Text</p>
```

### Grid-template-columns

Defines columns for grid layout. `grid-cols-{columns}`

| Columns | CSS                                                 |
| ------- | --------------------------------------------------- |
| `1`     | grid-template-columns: repeat(1, minmax(0, 1fr));   |
| `2`     | grid-template-columns: repeat(2, minmax(0, 1fr));   |
| `3`     | grid-template-columns: repeat(3, minmax(0, 1fr));   |
| `...`   | grid-template-columns: repeat(..., minmax(0, 1fr)); |
| `12`    | grid-template-columns: repeat(12, minmax(0, 1fr));  |
| `none`  | grid-template-columns: none;                        |

```html
<div class="grid grid-cols-3"></div>
```

### Grid-template-rows

Defines rows for grid layout. `grid-rows-{type}`

| type   | CSS                                              |
| ------ | ------------------------------------------------ |
| `1`    | grid-template-rows: repeat(1, minmax(0, 1fr));   |
| `2`    | grid-template-rows: repeat(2, minmax(0, 1fr));   |
| `3`    | grid-template-rows: repeat(3, minmax(0, 1fr));   |
| `...`  | grid-template-rows: repeat(..., minmax(0, 1fr)); |
| `6`    | grid-template-rows: repeat(12, minmax(0, 1fr));  |
| `none` | grid-template-rows: none;                        |

### Grid-column, Grid-rows - start/end

Sets a grid item size and location within the grid column. `col-{type}`

Sets a grid item size and location within the grid row. `row-{type}`

| type         | CSS                                      |
| ------------ | ---------------------------------------- |
| `auto`       | grid-{column, row}: auto;                |
| `span-1`     | grid-{column, row}: span 1 / span 1;     |
| `span-2`     | grid-{column, row}: span 2 / span 2;     |
| `span-3`     | grid-{column, row}: span 3 / span 3;     |
| `span-...`   | grid-{column, row}: span ... / span ...; |
| `span-12`    | grid-{column, row}: span 12 / span 12;   |
| `span-full`  | grid-{column, row}: 1 / -1;              |
| `start-1`    | grid-{column, row}-start: 1;             |
| `start-2`    | grid-{column, row}-start: 2;             |
| `start-3`    | grid-{column, row}-start: 3;             |
| `start-...`  | grid-{column, row}-start: ...;           |
| `start-12`   | grid-{column, row}-start: 12;            |
| `start-auto` | grid-{column, row}-start: auto;          |
| `end-1`      | grid-{column, row}-end: 1;               |
| `end-2`      | grid-{column, row}-end: 2;               |
| `end-3`      | grid-{column, row}-end: 3;               |
| `end-...`    | grid-{column, row}-end: ...;             |
| `end-13`     | grid-{column, row}-end: 13;              |
| `end-auto`   | grid-{column, row}-end: auto;            |

```html
<p class="col-start-1 col-end-3">Col</p>
<p class="row-start-1 row-end-3">Col</p>
```

### Grid-auto-flow

Controls the auto placement of grid elements. `grid-flow-{direction}`

| Direction      | CSS                           |
| -------------- | ----------------------------- |
| `row`          | grid-auto-flow: row;          |
| `column`       | grid-auto-flow: column;       |
| `row-dense`    | grid-auto-flow: row dense;    |
| `column-dense` | grid-auto-flow: column dense; |

### Grid-auto-columns, Grid-auto-rows

Controls the size of auto-generated (implicit) grid columns. `auto-cols-{type}`
Controls the size of auto-generated (implicit) grid rows. `auto-rows-{type}`

| type   | CSS                                        |
| ------ | ------------------------------------------ |
| `auto` | grid-auto-{columns, rows}: auto;           |
| `min`  | grid-auto-{columns, rows}: min-content;    |
| `max`  | grid-auto-{columns, rows}: max-content;    |
| `fr`   | grid-auto-{columns, rows}: minmax(0, 1fr); |

### Gap

Sets the gaps (gutters) between rows and columns. `gap-{type}`

| type  | CSS                  |
| ----- | -------------------- |
| `0`   | gap: 0px;            |
| `1`   | gap: 0.25rem;        |
| `2`   | gap: 0.5rem;         |
| `3`   | gap: 0.75rem;        |
| `4`   | gap: 1rem;           |
| `...` | gap: ...;            |
| `x-0` | column-gap: 0px;     |
| `x-1` | column-gap: o.25rem; |
| `x-2` | column-gap: 0.5rem;  |
| `x-3` | column-gap: 0.75rem; |
| `x-4` | column-gap: 0.1rem;  |
| `...` | column-gap: ...;     |
| `y-0` | row-gap: 0px;        |
| `y-1` | row-gap: 0.25rem;    |
| `y-2` | row-gap: 0.5rem;     |
| `y-3` | row-gap: 0.75rem;    |
| `y-4` | row-gap: 1rem;       |
| `...` | row-gap: ...;        |

```html
<div class="grid gap-4">
  <p>1</p>
  <p>2</p>
</div>
```

## Box Alignment

### Justify-content

Controls how flex items are positioned along container's main axis. `justify-{type}`

| Type      | CSS                             |
| --------- | ------------------------------- |
| `start`   | justify-content: flex-start;    |
| `end`     | justify-content: flex-end;      |
| `center`  | justify-content: center;        |
| `between` | justify-content: space-between; |
| `around`  | justify-content: space-around;  |
| `evenly`  | justify-content: space-evenly;  |

### Justify-items

Controls default alignment for items on the inline axis for grids. `justify-items-{type}`

| Type      | CSS                     |
| --------- | ----------------------- |
| `start`   | justify-items: start;   |
| `end`     | justify-items: end;     |
| `center`  | justify-items: center;  |
| `stretch` | justify-items: stretch; |

### Justify-self

Controls element alignment on the inline axis for a grid item. `justify-self-{type}`

| Type      | CSS                    |
| --------- | ---------------------- |
| `auto`    | justify-self: auto;    |
| `start`   | justify-self: start;   |
| `end`     | justify-self: end;     |
| `center`  | justify-self: center;  |
| `stretch` | justify-self: stretch; |

### Align-content

Controls how lines are positioned in multi-line flex containers. `content-{type}`

| Type      | CSS                           |
| --------- | ----------------------------- |
| `start`   | align-content: flex-start;    |
| `center`  | align-content: center;        |
| `end`     | align-content: flex-end;      |
| `between` | align-content: space-between; |
| `around`  | align-content: space-around;  |
| `evenly`  | align-content: space-evenly;  |

### Align-items

Sets flex items position along a contrainer's cross axis. `items-{type}`

| Type       | CSS                      |
| ---------- | ------------------------ |
| `stretch`  | align-items: stretch;    |
| `start`    | align-items: flex-start; |
| `end`      | align-items: flex-end;   |
| `center`   | align-items: center;     |
| `baseline` | align-items: baseline;   |

### Align-self

Controls how an individual flex item is positioned along container's cross axis. `self-{type}`

| Type       | CSS                     |
| ---------- | ----------------------- |
| `auto`     | align-self: auto;       |
| `start`    | align-self: flex-start; |
| `end`      | align-self: flex-end;   |
| `center`   | align-self: center;     |
| `stretch`  | align-self: stretch;    |
| `baseline` | align-self: baseline;   |

### Padding

Controls padding in 0.25rem increments. `p-{type}`

| Type  | CSS               |
| ----- | ----------------- |
| `0`   | padding: 0px;     |
| `1`   | padding: 0.25rem; |
| `2`   | padding: 0.5rem;  |
| `3`   | padding: 0.75rem; |
| `4`   | padding: 1rem;    |
| `...` | padding: ...;     |

padding left\right `px-{type}`

padding top\bottom `py-{type}`

padding top `pt-{type}`

padding bottom `pb-{type}`

padding left `pl-{type}`

padding right `pr-{type}`

### Margin

Controls margin (and negative margin) in 0.25rem increments. `m-{type}` `-m-{type}`

| Type  | CSS              |
| ----- | ---------------- |
| `0`   | margin: 0px;     |
| `1`   | margin: 0.25rem; |
| `2`   | margin: 0.5rem;  |
| `3`   | margin: 0.75rem; |
| `4`   | margin: 1rem;    |
| `...` | margin: ...;     |

margin left\right `mx-{type}`, `-mx-{type}`

margin top\bottom `my-{type}`, `-my-{type}`

margin top `mt-{type}`, `-mt-{type}`

margin bottom `mb-{type}`, `-mb-{type}`

margin left `ml-{type}`, `-ml-{type}`

margin right `mr-{type}`, `-mr-{type}`

## Border

### border-radius

Sets border radius. `rounded-{type}`

| Type   | CSS                      |
| ------ | ------------------------ |
| `none` | border-radius: 0px;      |
| `sm`   | border-radius: 0.125rem; |
| ` `    | border-radius: 0.25rem;  |
| `md`   | border-radius: 0.375rem; |
| `lg`   | border-radius: 0.5rem;   |
| `xl`   | border-radius: 0.75rem;  |
| `2xl`  | border-radius: 1rem;     |
| `3xl`  | border-radius: 1.5rem;   |
| `full` | border-radius: 9999px;   |

`rounded-t-{type}` : border-top-left-radius: ...; border-top-right-radius: ...;

`rounded-r-{type}` : border-top-right-radius: ...; border-bottom-right-radius: ...;

`rounded-b-{type}` : border-bottom-right-radius: ...; border-bottom-left-radius: ...;

`rounded-l-{type}` : border-top-left-radius: ...; border-bottom-left-radius: ...;

`rounded-tl-{type}` : border-top-left-radius: ...;

`rounded-tr-{type}` : border-top-right-radius: ...;

`rounded-br-{type}` : border-bottom-right-radius: ...;

`rounded-bl-{type}` : border-bottom-left-radius: ...;

### Border-width

Sets border width in increments of 1px.

| Class             | CSS                       |
| ----------------- | ------------------------- |
| `border`          | border-width: 1px;        |
| `border-0`        | border-width: 0px;        |
| `border-2`        | border-width: 2px;        |
| `border-4`        | border-width: 4px;        |
| `border-8`        | border-width: 8px;        |
| `border-t-{size}` | border-top-width: ...;    |
| `border-r-{size}` | border-right-width: ...;  |
| `border-b-{size}` | border-bottom-width: ...; |
| `border-l-{size}` | border-left-width: ...;   |

### Border-style

Sets border style. `border-{style}`

| style    | CSS                   |
| -------- | --------------------- |
| `solid`  | border-style: solid;  |
| `dashed` | border-style: dashed; |
| `dotted` | border-style: dotted; |
| `double` | border-style: double; |
| `none`   | border-style: none;   |

### Border-color

Sets border color. `border-{color}`

```html
<p class="border border-solid border-black"></p>
```

## Transitions and Animation

### Transition-property

Sets the CSS properties affected by transition animations.

- `transition`

  ```CSS
  transition-property: background-color, border-color, color, fill, stroke, opacity, box-shadow, transform, filter, -webkit-backdrop-filter;
  transition-property: background-color, border-color, color, fill, stroke, opacity, box-shadow, transform, filter, backdrop-filter;
  transition-property: background-color, border-color, color, fill, stroke, opacity, box-shadow, transform, filter, backdrop-filter, -webkit-backdrop-filter;
  transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
  transition-duration: 150ms;
  ```

- `transition-none`

  ```CSS
  transition-property: none;
  ```

- `transition-all`

  ```CSS
  transition-property: all;
  transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
  transition-duration: 150ms;
  ```

- `transition-colors`

  ```CSS
  transition-property: background-color, border-color, color, fill, stroke;
  transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
  transition-duration: 150ms;
  ```

- `transition-opacity`

  ```CSS
  transition-property: opacity;
  transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
  transition-duration: 150ms;
  ```

- `transition-shadow`

  ```CSS
  transition-property: box-shadow;
  transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
  transition-duration: 150ms;
  ```

- `transition-transform`

  ```CSS
  transition-property: transform;
  transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
  transition-duration: 150ms;
  ```

### Transition-duration

Sets the length of time for a transition animations to complete. `duration-{type}`

| Type  | CSS                         |
| ----- | --------------------------- |
| `75`  | transition-duration: 75ms;  |
| `100` | transition-duration: 100ms; |
| `150` | transition-duration: 150ms; |
| `200` | transition-duration: 200ms; |
| `300` | transition-duration: 300ms; |
| `...` | transition-duration: ...ms; |

### Transition-timing-function

Sets the easing function of transition animations.

| Class         | CSS                                                       |
| ------------- | --------------------------------------------------------- |
| `ease-linear` | transition-timing-function: linear;                       |
| `ease-in`     | transition-timing-function: cubic-bezier(0.4, 0, 1, 1);   |
| `ease-out`    | transition-timing-function: cubic-bezier(0, 0, 0.2, 1);   |
| `ease-in-out` | transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1); |

### Transition-delay

Sets the delay for transitions. `delay-{time}`

| Time  | CSS                      |
| ----- | ------------------------ |
| `75`  | transition-delay: 75ms;  |
| `100` | transition-delay: 100ms; |
| `150` | transition-delay: 150ms; |
| `200` | transition-delay: 200ms; |
| `300` | transition-delay: 300ms; |
| `...` | transition-delay: ...ms; |

### Animation

Sets CSS animations. `animate-{type}`

| Type             | CSS                                                        |
| ---------------- | ---------------------------------------------------------- |
| `none`           | animation: none;                                           |
| `animate-spin`   | animation: spin 1s linear infinite;                        |
| `animate-ping`   | animation: ping 1s cubic-bezier(0, 0, 0.2, 1) infinite;    |
| `animate-pulse`  | animation: pulse 2s cubic-bezier(0.4, 0, 0.6, 1) infinite; |
| `animate-bounce` | animation: bounce 1s infinite;                             |

## Transforms

### Scale

Scales an element that has transform applied.

| Class         | CSS                                   |
| ------------- | ------------------------------------- |
| `scale-0`     | --tw-scale-x: 0; --tw-scale-y: 0;     |
| `scale-50`    | --tw-scale-x: .5; --tw-scale-y: .5;   |
| `scale-75`    | --tw-scale-x: .75; --tw-scale-y: .75; |
| `scale-90`    | --tw-scale-x: .9; --tw-scale-y: .9;   |
| `scale-100`   | --tw-scale-x: 1; --tw-scale-y: 1;     |
| `scale-x-...` | --tw-scale-x: ...;                    |
| `scale-y-...` | --tw-scale-y: ...;                    |

### Rotate

Rotates an element that has transform applied.

| Class         | CSS                   |
| ------------- | --------------------- |
| `rotate-0`    | --tw-rotate: 0deg;    |
| `rotate-1`    | --tw-rotate: 1deg;    |
| `rotate-2`    | --tw-rotate: 2deg;    |
| `rotate-3`    | --tw-rotate: 3deg;    |
| `rotate-...`  | --tw-rotate: ...deg;  |
| `-rotate-...` | --tw-rotate: -...deg; |

### Translate

Translates an element that has transform applied.

| Class              | CSS                        |
| ------------------ | -------------------------- |
| `translate-x-0`    | --tw-translate-x: 0px;     |
| `translate-x-1`    | --tw-translate-x: 0.25rem; |
| `translate-x-2`    | --tw-translate-x: 0.5rem;  |
| `translate-x-...`  | --tw-translate-x: ...rem;  |
| `-translate-x-...` | --tw-translate-x: -...rem; |
| `translate-y-0`    | --tw-translate-y: 0px;     |
| `translate-y-1`    | --tw-translate-y: 0.25rem; |
| `translate-y-2`    | --tw-translate-y: 0.5rem;  |
| `translate-y-...`  | --tw-translate-y: ...rem;  |
| `-translate-y-...` | --tw-translate-y: -...rem; |

### Transform

Sets the transform of an element.

- `transform`

  ```CSS
  --tw-translate-x: 0;
  --tw-translate-y: 0;
  --tw-rotate: 0;
  --tw-skew-x: 0;
  --tw-skew-y: 0;
  --tw-scale-x: 1;
  --tw-scale-y: 1;
  transform: translateX(var(--tw-translate-x)) translateY(var(--tw-translate-y)) rotate(var(--tw-rotate)) skewX(var(--tw-skew-x)) skewY(var(--tw-skew-y)) scaleX(var(--tw-scale-x)) scaleY(var(--tw-scale-y));
  ```

- `transform-gpu`

  ```CSS
  --tw-translate-x: 0;
  --tw-translate-y: 0;
  --tw-rotate: 0;
  --tw-skew-x: 0;
  --tw-skew-y: 0;
  --tw-scale-x: 1;
  --tw-scale-y: 1;
  transform: translate3d(var(--tw-translate-x), var(--tw-translate-y), 0) rotate(var(--tw-rotate)) skewX(var(--tw-skew-x)) skewY(var(--tw-skew-y)) scaleX(var(--tw-scale-x)) scaleY(var(--tw-scale-y));
  .transform-none
  transform: none;
  ```

- `transform-none`

  ```CSS
  transform: none;
  ```

## Interactivity

### Cursor

Changes the cursor when hovering over an element.

| Class                | CSS                  |
| -------------------- | -------------------- |
| `cursor-auto`        | cursor: auto;        |
| `cursor-default`     | cursor: default;     |
| `cursor-pointer`     | cursor: pointer;     |
| `cursor-wait`        | cursor: wait;        |
| `cursor-text`        | cursor: text;        |
| `cursor-move`        | cursor: move;        |
| `cursor-help`        | cursor: help;        |
| `cursor-not-allowed` | cursor: not-allowed; |

### Outline

Sets the outline of the element.

| Class           | CSS                                                  |
| --------------- | ---------------------------------------------------- |
| `outline-none`  | outline: 2px solid transparent; outline-offset: 2px; |
| `outline-white` | outline: 2px dotted white; outline-offset: 2px;      |
| `outline-black` | outline: 2px dotted black; outline-offset: 2px;      |

## Filter

### filter

Sets filter on elements.

| Class         | CSS                                                                                                                                                                                |
| ------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `filter`      | filter: var(--tw-blur) var(--tw-brightness) var(--tw-contrast) var(--tw-grayscale) var(--tw-hue-rotate) var(--tw-invert) var(--tw-saturate) var(--tw-sepia) var(--tw-drop-shadow); |
| `filter-none` | filter: none;                                                                                                                                                                      |

### Blur

Sets blur filter on elements (use with filter utility).

| Class       | CSS                    |
| ----------- | ---------------------- |
| `blur-0`    | --tw-blur: blur(0);    |
| `blur-none` | --tw-blur: blur(0);    |
| `blur-sm`   | --tw-blur: blur(4px);  |
| `blur`      | --tw-blur: blur(8px);  |
| `blur-md`   | --tw-blur: blur(12px); |
| `blur-lg`   | --tw-blur: blur(16px); |
| `blur-xl`   | --tw-blur: blur(24px); |
| `blur-2xl`  | --tw-blur: blur(40px); |
| `blur-3xl`  | --tw-blur: blur(64px); |

### Drop-shadow

Sets drop-shadow filter on elements (use with filter utility).

| Class              | CSS                                                                                                        |
| ------------------ | ---------------------------------------------------------------------------------------------------------- |
| `drop-shadow-sm`   | --tw-drop-shadow: drop-shadow(0 1px 1px rgba(0,0,0,0.05));                                                 |
| `drop-shadow`      | --tw-drop-shadow: drop-shadow(0 1px 2px rgba(0, 0, 0, 0.1)) drop-shadow(0 1px 1px rgba(0, 0, 0, 0.06));    |
| `drop-shadow-md`   | --tw-drop-shadow: drop-shadow(0 4px 3px rgba(0, 0, 0, 0.07)) drop-shadow(0 2px 2px rgba(0, 0, 0, 0.06));   |
| `drop-shadow-lg`   | --tw-drop-shadow: drop-shadow(0 10px 8px rgba(0, 0, 0, 0.04)) drop-shadow(0 4px 3px rgba(0, 0, 0, 0.1));   |
| `drop-shadow-xl`   | --tw-drop-shadow: drop-shadow(0 20px 13px rgba(0, 0, 0, 0.03)) drop-shadow(0 8px 5px rgba(0, 0, 0, 0.08)); |
| `drop-shadow-2xl`  | --tw-drop-shadow: drop-shadow(0 25px 25px hsla(0, 0.00%, 0.00%, 0.15));                                    |
| `drop-shadow-none` | --tw-drop-shadow: drop-shadow(0 0 #0000);                                                                  |

## Effects

### Box-shadow

Sets the shadow around an element.

| Class          | CSS                                                                                                                                                                                             |
| -------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `shadow-sm`    | --tw-shadow: 0 1px 2px 0 rgba(0, 0, 0, 0.05); box-shadow: var(--tw-ring-offset-shadow, 0 0 #0000), var(--tw-ring-shadow, 0 0 #0000), var(--tw-shadow);                                          |
| `shadow`       | --tw-shadow: 0 1px 3px 0 rgba(0, 0, 0, 0.1), 0 1px 2px 0 rgba(0, 0, 0, 0.06); box-shadow: var(--tw-ring-offset-shadow, 0 0 #0000), var(--tw-ring-shadow, 0 0 #0000), var(--tw-shadow);          |
| `shadow-md`    | --tw-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -1px rgba(0, 0, 0, 0.06); box-shadow: var(--tw-ring-offset-shadow, 0 0 #0000), var(--tw-ring-shadow, 0 0 #0000), var(--tw-shadow);    |
| `shadow-lg`    | --tw-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1), 0 4px 6px -2px rgba(0, 0, 0, 0.05); box-shadow: var(--tw-ring-offset-shadow, 0 0 #0000), var(--tw-ring-shadow, 0 0 #0000), var(--tw-shadow);  |
| `shadow-xl`    | -tw-shadow: 0 20px 25px -5px rgba(0, 0, 0, 0.1), 0 10px 10px -5px rgba(0, 0, 0, 0.04); box-shadow: var(--tw-ring-offset-shadow, 0 0 #0000), var(--tw-ring-shadow, 0 0 #0000), var(--tw-shadow); |
| `shadow-2xl`   | --tw-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.25); box-shadow: var(--tw-ring-offset-shadow, 0 0 #0000), var(--tw-ring-shadow, 0 0 #0000), var(--tw-shadow);                                    |
| `shadow-inner` | --tw-shadow: inset 0 2px 4px 0 rgba(0, 0, 0, 0.06); box-shadow: var(--tw-ring-offset-shadow, 0 0 #0000), var(--tw-ring-shadow, 0 0 #0000), var(--tw-shadow);                                    |
| `shadow-none`  | --tw-shadow: 0 0 #0000; box-shadow: var(--tw-ring-offset-shadow, 0 0 #0000), var(--tw-ring-shadow, 0 0 #0000), var(--tw-shadow);                                                                |

### Opacity

Sets the transparency of an element.

| Class         | CSS            |
| ------------- | -------------- |
| `opacity-0`   | opacity: 0;    |
| `opacity-5`   | opacity: 0.05; |
| `opacity-10`  | opacity: 0.1;  |
| `opacity-20`  | opacity: 0.2;  |
| `opacity-...` | opacity: ...;  |
| `opacity-100` | opacity: 1;    |

[🡨 Back](../README.md)
