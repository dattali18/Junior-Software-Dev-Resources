# CSS - Cascading Style Sheets

## Table of Contents

1. [Online Resources](#online-resources)
2. [Basics](#basics)

# Online Resources

## Written Tutorials

- [MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/CSS)
- [W3Schools](https://www.w3schools.com/css/)
- [CSS-Tricks](https://css-tricks.com/)
- [CSS Reference](https://cssreference.io/)

## Video Tutorials

- [freeCodeCamp](https://www.youtube.com/watch?v=1Rs2ND1ryYc)
- [Traversy Media](https://www.youtube.com/watch?v=yfoY53QXEnI)
- [Codecademy](https://www.youtube.com/watch?v=yfoY53QXEnI)
- [The Net Ninja](https://www.youtube.com/watch?v=yfoY53QXEnI)
- [Academind](https://www.youtube.com/watch?v=yfoY53QXEnI)

## Courses

- [Coursera - HTML, CSS, and Javascript for Web Developers](https://www.coursera.org/learn/html-css-javascript-for-web-developers)
- [Udemy - Build Responsive Real World Websites with HTML5 and CSS3](https://www.udemy.com/course/design-and-develop-a-killer-website-with-html5-and-css3/)
- [Udemy - HTML5 and CSS3 Fundamentals](https://www.udemy.com/course/html5-and-css3-fundamentals/)
- [Udemy - HTML5 and CSS3 for Beginners](https://www.udemy.com/course/html5-and-css3-for-beginners/)
- [Udemy - HTML5 and CSS3 for Absolute Beginners](https://www.udemy.com/course/html5-and-css3-for-absolute-beginners/)
- [Udemy - CSS - The Complete Guide 2020 (incl. Flexbox, Grid & Sass)](https://www.udemy.com/course/css-the-complete-guide-incl-flexbox-grid-sass/)

# Basics

## What is CSS?

CSS stands for Cascading Style Sheets. It is the language used to style the visual presentation of a web page. It is used to control the layout of multiple web pages all at once.

## CSS Syntax

CSS is a rule-based language — you define rules specifying groups of styles that should be applied to particular elements or groups of elements on your web page. Here is a simple example:

```css
h1 {
  color: blue;
  font-size: 12px;
}
```

In this example, the `h1` selector is used to define the style rules for all `h1` elements on the page. The rules specify that the text color should be blue and the font size should be 12 pixels.

## CSS Selectors

CSS selectors are used to target the HTML elements on which you want to apply styles. There are several types of selectors, including:

- Element selectors
- Class selectors
- ID selectors
- Attribute selectors
- Pseudo-class selectors
- Pseudo-element selectors

Here is an example of an element selector:

```css
h1 {
  color: blue;
}
```

In this example, the `h1` selector targets all `h1` elements on the page and sets the text color to blue.

## CSS Units

CSS supports a variety of units for specifying lengths and other values. Some common units include:

- Pixels (px)
- Percentages (%)
- EMs (em)
- REMs (rem)
- Viewport Width (vw)
- Viewport Height (vh)

Here is an example of using pixels to set the font size of an element:

```css
h1 {
  font-size: 24px;
}
```

In this example, the font size of all `h1` elements on the page is set to 24 pixels.

## CSS Colors

CSS supports a variety of color formats, including named colors, hexadecimal colors, RGB colors, and HSL colors. Here are some examples:

```css
h1 {
  color: red; /* Named color */
}

p {
  color: #ff0000; /* Hexadecimal color */
}

a {
  color: rgb(255, 0, 0); /* RGB color */
}

span {
  color: hsl(0, 100%, 50%); /* HSL color */
}
```

In these examples, the text color of `h1` elements is set to red using a named color, the text color of `p` elements is set to red using a hexadecimal color, the text color of `a` elements is set to red using an RGB color, and the text color of `span` elements is set to red using an HSL color.

## CSS Box Model

The CSS box model describes the layout of elements in a web page. It consists of the content area, padding, border, and margin of an element. Here is an example:

```css
.box {
  width: 200px;
  height: 100px;
  padding: 20px;
  border: 1px solid black;
  margin: 10px;
}
```

In this example, the `.box` class defines a box element with a width of 200 pixels, a height of 100 pixels, 20 pixels of padding, a 1-pixel black border, and 10 pixels of margin.

## CSS Flexbox

Flexbox is a layout model that allows you to design complex layouts more easily and efficiently. It provides a more efficient way to lay out, align, and distribute space among items in a container, even when their size is unknown and/or dynamic.

Here is an example of using Flexbox to create a simple layout:

```css
.container {
  display: flex;
  justify-content: center;
  align-items: center;
}
```

In this example, the `.container` class uses Flexbox to center its child elements both horizontally and vertically.

## CSS Grid

CSS Grid Layout is a two-dimensional layout system that allows you to create complex grid-based layouts more easily and efficiently. It provides a more efficient way to lay out, align, and distribute space among items in a container, even when their size is unknown and/or dynamic.

Here is an example of using CSS Grid to create a simple layout:

```css
.container {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  grid-template-rows: 100px 100px;
}
```

In this example, the `.container` class uses CSS Grid to create a grid layout with three columns and two rows.
