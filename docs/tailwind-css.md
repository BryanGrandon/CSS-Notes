# Tailwind CSS

Tailwind CSS is a utility-first CSS framework with predefined classes that you can use to build and design web pages directly in your markup. It lets you write CSS in your HTML in the form of predefined classes.

## Table of content

- [Installation](#installation)
- [Introduction](#introduction)
- [Size](#size)
- [Layout](#layout)
- [Pseudo-classes](#pseudo-classes)
- [Typography](#typography)
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

Sets the behavior of background images when scrolling. type `bg` followed by the value of attachment.

```HTML
<div class="bg-fixed"></div> <!-- CSS: background-attachment: fixed; -->
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

Sets the background color. type `bg` followed by the color.

```html
<div class="bg-red-500"></div>
```

### Background-position

Sets the position of a background image. type `bg` followed by the position value.

```HTML
<div class="bg-center"></div> <!-- CSS: background-position: center; -->
```

### Background-size

Sets the background size of a background image. you type `bg` followed by the value of the property.

```HTML
<div class="bg-cover"></div> <!-- CSS: background-size: cover; -->
```

### Gradient color

Sets the background color gradients and where to stop. `from-{color}`, `to-{color}`

```html
<div class="from-blue-600 to-red-600"></div>
```

## Flex box

### Display

Sets element to be a flex container. write the value of the property

```HTML
<p class="flex">Text</p> <!-- CSS: display: flex; -->
```

### Flex-direction

To set the address of flexible elements, type `flex` followed by the address you want to set.

```HTML
<p class="flex-col">Text</p> <!-- CSS: flex-direction: column; -->
```

### Flex-wrap

Creates how flex items wrap. It is written `flex` followed by the value of the `flex-wrap` property.

```HTML
<div class="flex-wrap"></div> <!-- CSS: flex-wrap: wrap -->
<div class="flex-no-wrap"></div> <!-- CSS: flex-wrap: nowrap -->
```

## Grid

### Display

Sets the element to be a grid container. write the value of the property

```HTML
<p class="grid">Text</p> <!-- CSS: display: grid; -->
```

### Grid-template-columns

Defines columns for grid layout. type `grid-cols` followed by the value to set.

```HTML
<div class="grid-cols-2"></div> <!-- grid-template-columns: repeat(2, minmax(0, 1fr)); -->
```

### Grid-template-rows

Defines rows for grid layout. type `grid-rows` followed by the value to set.

```HTML
<div class="grid-rows-3"></div> <!-- CSS: grid-template-rows: repeat(3 minmax(0, 1fr)); -->
```

### Grid-column, Grid-rows

Sets the size and location of a grid element within the column and row of the grid. type `col` for column and `row` for rows followed by the distribution to set.

```HTML
<div class="col-span-1"></div> <!-- CSS: grid-column: span 1 /span 1; -->
<div class="row-span-full"></div> <!-- CSS: grid-row: 1 / -1; -->
```

Sets the location of the start and end of a grid element.

```HTML
<div class="row-start-1"></div> <!-- CSS: grid-row-start: 1; -->
<div class="col-end-auto"></div> <!-- CSS: grid-column-end: auto; -->
```

### Grid-auto-flow

Controls the auto placement of grid elements. type `grid-flow` followed by the address you want to set.

```HTML
<div class="grid-flow-column"></div> <!-- CSS: grid-auto-flow: column; -->
```

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

To set the gaps (gutters) between rows and columns, type the `gap` property directly followed by the [size](#size) you want to assign

```HTML
<div class="gap-4"></div> <!-- CSS: gap: 1rem; -->
```

To set the gap between columns type `gap-x` followed by the size to be set and to set the gap between rows change the x by the y

```HTML
<div class="gap-x-2"></div> <!-- CSS: column-gap: 0.5rem; -->
<div class="gap-y-3"></div> <!-- CSS: row-gap: 0.75rem; -->
```

## Box Alignment

### Justify-content

Controls how flex items are positioned along container's main axis. the `justify` property is written directly followed by the property value.

```HTML
<div class="justify-between"></div> <!-- CSS: justify-content: space-between; -->
```

### Justify-items

Controls default alignment for items on the inline axis for grids. the `justify-items` property is written directly followed by the property value.

```HTML
<div class="justify-items-end"></div> <!-- CSS: justify-items: end; -->
```

### Justify-self

Controls element alignment on the inline axis for a grid item. the `justify-self` property is written directly followed by the property value.

```HTML
<div class="justify-self-stretch"></div> <!-- CSS: justify-self: stretch; -->
```

### Align-content

Controls how lines are positioned in multi-line flex containers. type `content` followed by the value of the property.

```HTML
<div class="content-evenly"></div> <!-- CSS: align-content: space-evenly; -->
```

### Align-items

Sets the position of the flexible elements along the transverse axis of a container. type `items` followed by the value of the property.

```HTML
<div class="items-center"></div> <!-- CSS: align-items: center; -->
```

### Align-self

Controls how an individual flexible element is positioned along the cross axis of the container. type `self` followed by the property value.

```HTML
<div class="self-auto"></div> <!-- CSS: align-self: auto; -->
```

### Padding

To set the padding, type `p` followed by the [size](#size) to be set.

```HTML
<div class="p-4"></div> <!-- CSS: padding: 1rem; -->
```

Padding can be set vertically, horizontally and individually

```HTML
<div class="px-4"></div> <!-- CSS: padding-left: 1rem; padding-right: 1rem; -->
<div class="pt-4"></div> <!-- CSS: padding-top: 1rem; -->
```

### Margin

To set the margin, type `m` followed by the [size](#size) to be set.

```HTML
<div class="m-4"></div> <!-- CSS: margin: 1rem; -->
```

Margin can be set vertically, horizontally and individually

```HTML
<div class="mx-4"></div> <!-- CSS: margin-left: 1rem; margin-right: 1rem; -->
<div class="mt-4"></div> <!-- CSS: margin-top: 1rem; -->
```

## Border

### border-radius

To set the border radius, type `rounded` followed by the nomenclature of the size to be set.

```HTML
<div class="rounded-2xl"></div> <!-- CSS: border-radius: 1rem; -->
```

In addition, the border radius can be set for each position.

```HTML
<div class="border-t-2xl"></div> <!-- CSS: border-top-left-radius: 1rem; border-top-right-radius: 1rem; -->
<div class="border-tl-2xl"></div> <!-- CSS: border-top-left-radius: 1rem; -->
```

### Border-width

To set the border style, directly type the `border` property followed by the size you want to set.

```HTML
<div class="border"></div> <!-- border-width: 1px; -->
```

In addition, each side of the element can be set individually.

| Position | TailwindCSS class | CSS                      |
| -------- | ----------------- | ------------------------ |
| top      | `border-t-2`      | border-top-width: 2px    |
| bottom   | `border-b-3`      | border-bottom-width: 3px |
| left     | `border-l-4`      | border-left-width: 4px   |
| right    | `border-r-5`      | border-right-width: 5px  |

### Border-style

To set the border style, directly type the `border` property followed by the value of the property to set.

```HTML
<div class="border-solid"></div> <!-- CSS: border-style: solid; -->
```

### Border-color

To sets border color, type directly the `border` property followed by the color to set.

```HTML
<p class="border-black"></p> <!-- CSS: border-color: black; -->
```

## Transitions and Animation

### Transition

To set the CSS properties affected by transition animations, the `transition` property is typed directly and can be followed by the property to which you want to apply it.

```CSS
/* This CSS applies to all */
transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
transition-duration: 150ms;
```

```HTML
<div class="transition"></div> <!-- CSS: transition-property: various properties...; -->
```

- Properties: `none`, `all`, `colors`, `opacity`, `shadow`, `transform`

```HTML
<div class="transition-colors"></div> <!-- CSS: transition-property: background-color, border-color, color, fill, stroke; -->
```

### Transition-duration

To set the duration of the transitions, the `duration` property is written directly followed by the time in ms.

```HTML
<div class="duration-200"></div> <!-- CSS: transition-duration: 200ms; -->
```

### Transition-timing-function

Sets the easing function of transition animations.

| Class         | CSS                                                       |
| ------------- | --------------------------------------------------------- |
| `ease-linear` | transition-timing-function: linear;                       |
| `ease-in`     | transition-timing-function: cubic-bezier(0.4, 0, 1, 1);   |
| `ease-out`    | transition-timing-function: cubic-bezier(0, 0, 0.2, 1);   |
| `ease-in-out` | transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1); |

### Delay

To set the delay of the transitions, the `delay` property is written directly followed by the time in ms.

```HTML
<div class="daley-150"></div> <!-- CSS: transition-delay: 150ms; -->
```

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

To set the scale of an element, the `scale` property is typed directly followed by a number.

```HTML
<div class="scale-90"></div> <!-- CSS: --tw-scale-x: .9; --tw-scale-y: .9; -->
```

You can also set both vertical and horizontal scaling.

```HTML
<div class="scale-x-100"></div> <!-- CSS: --tw-scale-x: 1; -->
<div class="scale-y-50"></div> <!-- CSS: --tw-scale-y:.5; -->
```

### Rotate

To apply the rotation, type directly the property `rotate` followed by a number that will be the degree of rotation.

```HTML
<div class="rotate-10"></div> <!-- CSS: --tw-rotate: 10deg; -->
<div class="-rotate-100"></div> <!-- CSS: --tw-rotate: -100deg; -->
```

### Translate

With the translate property you can move the element vertically and horizontally, for this you type directly the `translate` property followed by orientation and followed by [size](#size).

```HTML
<div class="translate-x-4"></div> <!-- CSS: --tw-translate-x: 1rem; -->
<div class="translate-y-2"></div> <!-- CSS: --tw-translate-y: 0.5rem; -->
```

## Interactivity

### Cursor

To set the cursor on the element, the CSS property is written directly followed by the value of the `cursor-auto` property.

```HTML
<div class="cursor-pointer"></div> <!-- CSS: cursor: pointer; -->
```

### Outline

Sets the outline of the element.

| Class           | CSS                                                  |
| --------------- | ---------------------------------------------------- |
| `outline-none`  | outline: 2px solid transparent; outline-offset: 2px; |
| `outline-white` | outline: 2px dotted white; outline-offset: 2px;      |
| `outline-black` | outline: 2px dotted black; outline-offset: 2px;      |

## Filter

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

To set the drop-shadow filter on the element you directly type the CSS property followed by the size you want to set `drop-shadow-sm`.

- `sm`, `md` , `lg`, `xl`, `2xl`, `none`

```HTML
<div class="drop-shadow"></div>
```

```CSS
--tw-drop-shadow: drop-shadow(0 1px 2px rgba(0, 0, 0, 0.1));
drop-shadow(0 1px 1px rgba(0, 0, 0, 0.06));
```

## Effects

### Box-shadow

To set the shadow around an element you directly type the CSS property followed by the size you want to set `shadow-sm`.

- `sm`, `md`, `lg`, `xl`, `2xl`, `inner`, `none`.

```HTML
<div class="shadow"></div>
```

```CSS
--tw-shadow: 0 1px 3px 0 rgba(0, 0, 0, 0.1), 0 1px 2px 0 rgba(0, 0, 0, 0.06);
box-shadow: var(--tw-ring-offset-shadow, 0 0 #0000), var(--tw-ring-shadow, 0 0 #0000), var(--tw-shadow);
```

### Opacity

To set the transparency of an element, the CSS property is typed directly followed by an `opacity-10` number.

```HTML
<div class="opacity-0"></div> <!-- CSS: opacity: 0; -->
<div class="opacity-100"></div> <!-- CSS: opacity: 1; -->
```

[🡨 Back](../README.md)
