# HTML - HyperText Markup Language

HTML is the language used for creating web pages. It is the backbone of every website and is used to create the structure of a webpage. HTML is not a programming language, but a markup language that defines the structure of your content.

## Table of Contents

1. [Online Resources](#online-resources)
2. [Basics](#basics)


## Online Resources

### Written Tutorials

- [MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/HTML)
- [W3Schools](https://www.w3schools.com/html/)
- [HTML Dog](https://htmldog.com/guides/html/)
- [HTML.com](https://html.com/)
- [Tutorialspoint](https://www.tutorialspoint.com/html/index.htm)

### Video Tutorials

- [freeCodeCamp](https://www.youtube.com/watch?v=pQN-pnXPaVg)
- [Traversy Media](https://www.youtube.com/watch?v=UB1O30fR-EE)
- [Codecademy](https://www.youtube.com/watch?v=UB1O30fR-EE)
- [The Net Ninja](https://www.youtube.com/watch?v=UB1O30fR-EE)
- [Academind](https://www.youtube.com/watch?v=UB1O30fR-EE)

### Courses

- [Coursera - HTML, CSS, and Javascript for Web Developers](https://www.coursera.org/learn/html-css-javascript-for-web-developers)
- [Udemy - Build Responsive Real World Websites with HTML5 and CSS3](https://www.udemy.com/course/design-and-develop-a-killer-website-with-html5-and-css3/)
- [Udemy - HTML5 and CSS3 Fundamentals](https://www.udemy.com/course/html5-and-css3-fundamentals/)
- [Udemy - HTML5 and CSS3 for Beginners](https://www.udemy.com/course/html5-and-css3-for-beginners/)
- [Udemy - HTML5 and CSS3 for Absolute Beginners](https://www.udemy.com/course/html5-and-css3-for-absolute-beginners/)


## Basics

### What is HTML?

HTML stands for HyperText Markup Language. It is the standard markup language for documents designed to be displayed in a web browser. It can be assisted by technologies such as Cascading Style Sheets (CSS) and scripting languages such as JavaScript.

### HTML Elements

An HTML element is defined by a start tag, some content, and an end tag:

```html
<tagname>Content goes here...</tagname>
```

The HTML element is everything from the start tag to the end tag:

```html
<h1>This is a heading</h1>
<p>This is a paragraph.</p>
```

### HTML Attributes

HTML elements can have attributes. Attributes provide additional information about an element. Attributes are always specified in the start tag. Attributes usually come in name/value pairs like: name="value".

```html
<a href="https://www.example.com">This is a link</a>
```

### HTML Headings

HTML headings are defined with the `<h1>` to `<h6>` tags. `<h1>` defines the most important heading, `<h6>` defines the least important heading.

```html
<h1>This is heading 1</h1>
<h2>This is heading 2</h2>
<h3>This is heading 3</h3>
```

### HTML Paragraphs

HTML paragraphs are defined with the `<p>` tag.

```html
<p>This is a paragraph.</p>
<p>This is another paragraph.</p>
```

### HTML Links

HTML links are defined with the `<a>` tag. The link's destination is specified in the href attribute.

```html
<a href="https://www.example.com">This is a link</a>
```


### HTML Images

HTML images are defined with the `<img>` tag. The source file (src), alternative text (alt), width, and height are provided as attributes.

```html
<img src="img.jpg" alt="Image description" width="500" height="600">
```

### HTML Lists

HTML lists are defined with the `<ul>` (unordered list), `<ol>` (ordered list), and `<li>` (list item) tags.

```html
<ul>
  <li>Item 1</li>
  <li>Item 2</li>
  <li>Item 3</li>
</ul>
```

```html
<ol>
  <li>Item 1</li>
  <li>Item 2</li>
  <li>Item 3</li>
</ol>
```

### HTML Tables

HTML tables are defined with the `<table>` tag. A table is divided into rows with the `<tr>` tag. Each row is divided into data cells with the `<td>` tag.

```html
<table>
  <tr>
    <td>Row 1, Cell 1</td>
    <td>Row 1, Cell 2</td>
  </tr>
  <tr>
    <td>Row 2, Cell 1</td>
    <td>Row 2, Cell 2</td>
  </tr>
</table>
```

### HTML Forms

HTML forms are defined with the `<form>` tag. An HTML form contains form elements such as input elements, radio buttons, checkboxes, etc.

```html
<form action="/submit-form" method="post">
  <label for="name">Name:</label>
  <input type="text" id="name" name="name">
  <input type="submit" value="Submit">
</form>
```

### HTML Semantic Elements

Semantic elements are HTML elements that represent the meaning of the content. They provide information about the structure of the web page.

```html
<header>
  <h1>Heading</h1>
</header>
<nav>
  <ul>
    <li><a href="#">Home</a></li>
    <li><a href="#">About</a></li>
    <li><a href="#">Contact</a></li>
  </ul>
</nav>
<section>
  <h2>Section Heading</h2>
  <p>Section content...</p>
</section>
<footer>
  <p>&copy; 2021</p>
</footer>
```

### HTML Comments

HTML comments are not displayed in the browser. You can use comments to explain your code, or to prevent the browser from rendering specific parts of your code.

```html
<!-- This is a comment -->
```

### HTML Doctype

The `<!DOCTYPE html>` declaration defines the document type and helps the browser to render the web page correctly.

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Page Title</title>
  </head>
  <body>
    <h1>This is a heading</h1>
    <p>This is a paragraph.</p>
  </body>
</html>
```

### HTML Metadata

HTML metadata is data about the HTML document. Metadata is not displayed on the web page but is used by browsers and search engines.

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Page Title</title>
    <meta charset="UTF-8">
    <meta name="description" content="Free Web tutorials">
    <meta name="keywords" content="HTML, CSS, JavaScript">
    <meta name="author" content="John Doe">
  </head>
  <body>
    <h1>This is a heading</h1>
    <p>This is a paragraph.</p>
  </body>
</html>
```

### HTML Layouts

HTML layouts are used to structure a web page. Common layout elements include headers, navigation bars, content areas, sidebars, and footers.

```html
<header>
  <h1>Header</h1>
</header>
<nav>
  <ul>
    <li><a href="#">Home</a></li>
    <li><a href="#">About</a></li>
    <li><a href="#">Contact</a></li>
  </ul>
</nav>
<section>
  <h2>Section Heading</h2>
  <p>Section content...</p>
</section>
<aside>
  <h2>Aside Heading</h2>
  <p>Aside content...</p>
</aside>
<footer>
  <p>&copy; 2021</p>
</footer>
```