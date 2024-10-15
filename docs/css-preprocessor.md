# CSS Preprocessor

CSS preprocessors make it easy to automate repetitive tasks, reduce the number of errors and code bloat, create reusable code snippets, and ensure backward compatibility.

## [Sass](https://sass-lang.com/)

SASS is a CSS preprocessor compatible with all versions of CSS. It is therefore a tool used by web developers to translate non-standard stylesheet code into standard CSS code, readable by most browsers.

```bash
npm install -g sass
```

- [Variables](/scss/_variables.scss)
- [Nesting](/scss/_nesting.scss)
- [Mixins](/scss/_mixins.scss)
- [Operator](/scss/_operator.scss)
- [Modules](/scss/_modules.scss)

### Folder structure

![sass folder](../assets/folder-structure-sass.png)

- 📂 base/: It contains the basic styles, including normalization, typography and base styles.

- 📂 layout/: It includes the styles for the main structural sections such as the header, footer, among others.

- 📂 utilities/: It hosts helpers such as variables, functions and mixins that make writing CSS easier.

- 📄main.scss: It imports all partial files and is the entry point for the compilation.
