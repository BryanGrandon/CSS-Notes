# Tailwind CSS

Tailwind CSS is a utility-first CSS framework with predefined classes that you can use to build and design web pages directly in your markup. It lets you write CSS in your HTML in the form of predefined classes.

## Table of content

- [Installation](#installation)
- [Pseudo-classes](#pseudo-classes)
- [Typography](#typography)
- [Sizing](#sizing)
- [Backgrounds](#backgrounds)
- [Flex box](#flex-box)
- [Grid](#grid)
- [Box-alignment](#box-alignment)

## [Installation](https://tailwindcss.com/docs/installation/using-vite)

```bash
npm install tailwindcss @tailwindcss/vite -D
```

### Configure the Vite plugin

Add the @tailwindcss/vite plugin to your Vite configuration.

```ts
// vite.config.ts
import { defineConfig } from 'vite'
import tailwindcss from '@tailwindcss/vite'
export default defineConfig({
  plugins: [tailwindcss()],
})
```

### Import Tailwind CSS

Add an @import to your CSS file that imports Tailwind CSS.

```css
@import 'tailwindcss';
```

## Pseudo-classes

### Hover

Add the hover: prefix to only apply a utility on hover. `hover:`

```html
<p class="hover:text-red-500">Text</p>
```

### Active

Add the active: prefix to only apply a utility when an element is active. `active:`

```html
<p class="active:text-red-500">Text</p>
```

### Focus

Add the focus: prefix to only apply a utility on focus. `focus:`

```html
<p class="focus:text-red-500">Text</p>
```

## Typography

### Text color

Sets background color. `text-{color}-{strong}`

```html
<p class="text-gray-100">Text</p>
<p class="text-red-500">Text</p>
```

### Text opacity

Sets background opacity when used with bg-[color]. `text-opacity-{%}`

```html
<p class="text-opacity-50">Text</p>
```

### Font-family

Sets the font family. `font-{type}`

| type    | CSS                                             |
| ------- | ----------------------------------------------- |
| `sans`  | font-family: ui-sans-serif, system-ui, ...;     |
| `serif` | font-family: ui-serif, Georgia, Cambria, ...;   |
| `mono`  | font-family: ui-monospace, SFMono-Regular, ...; |

```html
<p class="font-sans">Text sans</p>
```

### Font-size

Sets the font size. `text-{size}`

| Size   | CSS                                        |
| ------ | ------------------------------------------ |
| `xs`   | font-size: 0.75rem; line-height: 1rem;     |
| `sm`   | font-size: 0.875rem; line-height: 1.25rem; |
| `base` | font-size: 1rem; line-height: 1.5rem;      |
| `lg`   | font-size: 1.125rem; line-height: 1.75rem; |
| `xl`   | font-size: 1.25rem; line-height: 1.75rem;  |

```html
<p class="text-sm">Text</p>
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

### Text-align

Sets the alignment of text. `text-{alignment}`

| Alignment | CSS                  |
| --------- | -------------------- |
| `left`    | text-align: left;    |
| `center`  | text-align: center;  |
| `right`   | text-align: right;   |
| `justify` | text-align: justify; |

```html
<p class="text-center">Text bold</p>
```

### Text-transform

Sets the capitalization of text. `text-{transform}`

| Transform     | CSS                         |
| ------------- | --------------------------- |
| `uppercase`   | text-transform: uppercase;  |
| `lowercase`   | text-transform: lowercase;  |
| `capitalize`  | text-transform: capitalize; |
| `normal-case` | text-transform: none;       |

```html
<p class="capitalize">Text bold</p>
```

## Sizing

### Width

Sets the width of an element. `w-{width}`

| Width    | CSS                 |
| -------- | ------------------- |
| `0`      | width: 0px;         |
| `1`      | width: 0.25rem;     |
| `2`      | width: 0.5rem;      |
| `3`      | width: 0.75rem;     |
| `4`      | width: 1rem;        |
| `...`    | width: ...;         |
| `auto`   | width: auto;        |
| `1/2`    | width: 50%;         |
| `full`   | width: 100%;        |
| `screen` | width: 100vw;       |
| `min`    | width: min-content; |
| `max`    | width: max-content; |

```html
<div class="w-10"></div
```

### Min-width

Sets the minimum width of an element. `min-w-{width}`

| Width  | CSS                     |
| ------ | ----------------------- |
| `0`    | min-width: 0px;         |
| `full` | min-width: 100%;        |
| `min`  | min-width: min-content; |
| `max`  | min-width: max-content; |

```html
<div class="min-w-max"></div
```

### Max-width

Sets the maximum width of an element. `max-w-{width}`

| Width                  | CSS               |
| ---------------------- | ----------------- |
| `0`                    | max-width: 0rem;  |
| `none`                 | max-width: none;  |
| `xs`                   | max-width: 20rem; |
| `sm`                   | max-width: 24rem; |
| `md`                   | max-width: 28rem; |
| `lg`                   | max-width: 32rem; |
| `xl`                   | max-width: 36rem; |
| `2xl`                  | max-width: 42rem; |
| `3xl`                  | max-width: 48rem; |
| `screen-{breakpoints}` | max-width: 640px; |

```html
<div class="max-w-ld"></div
<div class="max-w-screen-sm"></div
```

### Height

Sets the height of an element. `h-{height}`

| Height   | CSS              |
| -------- | ---------------- |
| `0`      | height: 0px;     |
| `1`      | height: 0.25rem; |
| `2`      | height: 0.5rem;  |
| `3`      | height: 0.75rem; |
| `4`      | height: 1rem;    |
| `...`    | height: ...;     |
| `auto`   | height: auto;    |
| `1/2`    | height: 50%;     |
| `full`   | height: 100%     |
| `screen` | height: 100vh    |

```html
<div class="h-8"></div>
```

### Min-height

Sets the minimum width of an element. `min-h-{width}`

| Width    | CSS                |
| -------- | ------------------ |
| `0`      | min-height: 0px;   |
| `full`   | min-height: 100%;  |
| `screen` | min-height: 100vh; |

```html
<div class="min-h-full"></div>
```

### Max-height

Sets the maximum height of an element. `max-h-{height}`

| Height   | CSS                  |
| -------- | -------------------- |
| `0`      | max-height: 0px;     |
| `1`      | max-height: 0.25rem; |
| `2`      | max-height: 0.5rem;  |
| `3`      | max-height: 0.75rem; |
| `4`      | max-height: 1rem;    |
| `...`    | max-height: ...;     |
| `full`   | max-height: 100%;    |
| `screen` | max-height: 100vh;   |

```html
<div class="max-h-screen"></div>
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

[🡨 Back](../README.md)
