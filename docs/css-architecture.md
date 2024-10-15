# CSS Architecture

Consists of managing CSS code with a set of rules and patterns to facilitate its readability, maintainability and scalability.

## Table of content

- [BEM](#block-element-modifier-bem)
- [ITCSS](#inverted-triangle-css)

## Block Element Modifier (BEM)

BEM is a CSS naming and code structure methodology that provides a way to write CSS class names.

- The Block is the independent part in our HTML, it does not need other elements to exist.
- An element will always be inside a block, because it is part of it and is dependent on it to exist.
- Modifiers are used in elements or blocks to represent a different characteristic that the modifier or element will have.

<img width="600px" src="https://res.cloudinary.com/practicaldev/image/fetch/s--OkBgfgPx--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/i/yc0hv58in4eyxjj7qlcg.png">

## Inverted Triangle CSS

The ITCSS architecture tells us that the organization of CSS code should be approached on the basis of an inverted triangle, according to specificity. This means that the most general and basic style rules are added first, and specific rules that override behavior such as utility classes are added last.

<img width="600px" alt="IT-CSS" src="https://res.cloudinary.com/practicaldev/image/fetch/s--vMb61lEd--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://thepracticaldev.s3.amazonaws.com/i/x1w4vpq08es26dwok6pn.png">

- Settings:

  In this folder we will place the code of declaration of variables or global configurations of our project. The base font size, color palettes, etc.

- Tools:

  In this folder we will have the mixins and functions, which can be used by the following layers.

- Generic:

  At this point we will place generic code base for the whole project, typically the CSS reset you are using

- Elements:

  Will be used to place the CSS that affects the HTML elements. We are not going to place more than styling for tags.

- Objects:

  Is where the classes for the page structure would go. In this folder is the place to place aspects related to the layout, basic media queries to accommodate the parts of our template to different screen dimensions.

- Components:

  The components are the independent sections of our website. Here we can find the typical .header or .card that are composed of a set of elements and objects.

- Trumps:

  Finally we have the Trumps layer, the layer that "triumphs" over the rest. In this layer we can overwrite everything, and it is where surely all our `!important` are. It is here where our utility classes are
