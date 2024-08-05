# CSS Notes

CSS or **Cascading Style Sheets** is the language used to style the frontend of any website. CSS is a cornerstone technology of the World Wide Web, alongside HTML and JavaScript.

- [CSS Architecture](/docs/css-architecture.md)
- [CSS Preprocessor](/docs/css-preprocessor.md)

## Table of content

- [Selector](/docs/code/01-selector.md)
- [Pseudo-classes](/docs/code/02-pseudo-classes.md)
- [Pseudo-element](/docs/code/03-pseudo-element.md)
- [Fonts](/docs/code/04-fonts.md)
- [Length](/docs/code/05-length.md)
- [Colors](/docs/code/06-colors.md)
- [Box Model](/docs/code/07-box-model.md)
- [Position](/docs/code/08-position.md)
- [Background](/docs/code/09-background.md)
- [Display](/docs/code/10-display.md)
- [Flex](/docs/code/11-flex.md)
- [Variables](/docs/code/13-variables.md)

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
