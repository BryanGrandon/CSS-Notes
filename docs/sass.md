# [Sass](https://sass-lang.com/)

SASS is a CSS preprocessor compatible with all versions of CSS. It is therefore a tool used by web developers to translate non-standard stylesheet code into standard CSS code, readable by most browsers.

```bash
npm install -g sass -D
```

## Table of Content

- [File extension](#file-extension)
- [Variables](#variables)
- [Nesting](#nesting)
- [Mixins](#mixins)
- [Modules](#modules)
- [Folder structure](#folder-structure)

## File extension

Sass supports two different syntaxes. Each one can load the other, so it’s up to you and your team which one to choose.

To use one or the other, you only have to change the extension of the file

```scss
// .sass
.box
  color : #f00
```

```scss
// .scss
.box {
  color: #f00;
}
```

## Variables

The way to declare a variable in sass is as
follows. `$<variable>:<value>`

```scss
$main: #ccc;

body {
  background: $main;
}
```

### Array of variables

```scss
$colors: (
  'white': #fff,
  'purple': #770af4,
);

.header {
  color: map-get($colors, 'purple');
}
```

## Nesting

Instead of repeating the same selectors over and over again, Sass allows you to write style rules inside another one.
Since Sass will automatically combine the outer rule selector with the inner rule selector.

```css
h1 {
  color: #f00;
}

h1 a {
  color: #00f;
}

h1 a:hover {
  color: #0f0;
}
```

```scss
h1 {
  color: #f00;

  a {
    color: #00f;

    &:hover {
      color: #f0f;
    }
  }
}
```

## Mixins

A mixin is a “function” in the sense that it allows us to reuse code and that it accepts arguments, however, it is not a function as such (we can say this because in SASS there are also functions). The characteristic of mixins is that they define properties that are then included in a selector.

```scss
@mixin name {
  property: value;
  property: value;
  ...
}

a {
  @include name();
}
```

### Mixins with variables

```scss
@mixin flexBox($direction, $wrap, $just, $align) {
  display: flex;
  flex-flow: $direction $wrap;
  justify-content: $just;
  align-items: $align;
}

.flex {
  @include flexBox(column, wrap, space-evenly, center);
}
```

## Modules

Sass provides many built-in modules that contain useful functions (and the occasional combination). These modules can be loaded with the @use rule like any user-defined style sheet, and their functions can be called like any other module member.

```scss
@use '_mixins' as *;

div {
  @include flexBox(column, nowrap, normal, normal);
}
```

## Folder structure

![sass folder](../assets/folder-structure-sass.png)

- 📂 base/: It contains the basic styles, including normalization, typography and base styles.

- 📂 layout/: It includes the styles for the main structural sections such as the header, footer, among others.

- 📂 utilities/: It hosts helpers such as variables, functions and mixins that make writing CSS easier.

- 📄main.scss: It imports all partial files and is the entry point for the compilation.

[🡨 Back](../README.md)
