# Tailwind CSS

Tailwind CSS is a utility-first CSS framework with predefined classes that you can use to build and design web pages directly in your markup. It lets you write CSS in your HTML in the form of predefined classes.

## Table of content

- [Installation](#installation)
- [Pseudo-classes](#pseudo-classes)
- [Typography](#typography)
- [Sizing](#sizing)
- [Backgrounds](#backgrounds)

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

Sets the maxiumum width of an element. `max-w-{width}`

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

Sets the maxiumum height of an element. `max-h-{height}`

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

[🡨 Back](../README.md)
