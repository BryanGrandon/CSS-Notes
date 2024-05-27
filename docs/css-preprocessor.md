# CSS Preprocessor

These are scripting languages that extend the default capabilities of CSS.

## Table of content

- [Sass](#sass)

## Sass

SASS is a CSS preprocessor compatible with all versions of CSS.

- Variables
- Nesting
- Mixins
- Operator
- Modules

### Variables

```scss
$color-main: #ccc;
$color-second: #770af4;

body {
  background: $color-main;
  color: $color-second;
}
```

### Nesting

```HTML
 <section class="box">
   <h2>Title</h2>
   <p>Relate text</p>
 </section>
```

```Scss

.box {
  font-family: cursive;
  h2 {
    color: red;
  }
  p {
   color: #1f1235;
  }
}
```

### Mixins

```scss
@mixin customized-box($color: white) {
  white: 300px;
  height: 100px;
  background-color: $color;
  border: 1px solid #1f1235;
}

.box {
  @include customized-box($color: #770af4);
}
```

### Operator

```Scss
.text {
font-size: 8px + 10px;
font-size: 20px - 2px;
font-size: 36px / 2;
font-size: 6px \* 3;
}

```

### Modules

```Scss
@use "_other";

div {
@include customized-box($fund: #ccc);
}
```

```Scss
// ---- _other.scss ---- //
@mixin customized-box($fund: withe) {
width: 300px;
height: 100px;
background-color: $fund;
border: 1px solid #666;
}
```
