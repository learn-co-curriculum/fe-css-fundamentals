# CSS Fundamentals

## Overview

In this lesson we will learn about the fundamentals of CSS including syntax, formatting, selecting HTML elements to style, as well as font and color properties. 

## Objectives

1. Purpose of CSS
1. Getting to know CSS syntax
2. Various formats of CSS
3. CSS Selectors
4. Font & Color Properties

## Styling The Front-End

<iframe width="640" height="480" src="//www.youtube.com/embed/-k-1TU8qq0Q?rel=0" frameborder="0" allowfullscreen></iframe>

*Note: Slides for this lecture video are provided in the resources at the bottom of this lesson.*

### What Is The Purpose of CSS?

CSS stands for Cascading Style Sheet. Cascading because it can apply to multiple elements across many pages, and style sheet because it is a single body of code that adds style across the many pages it effects. If we imagine the HTML as the structure of a house, the brick and motar, the walls, the ceilings, the roof. The CSS paints the walls and arranges the furniture. It is the decorator that breathes color, typographic style, and positioning of elements among other things. It was created as an easier way to style our pages from a single location.

### Syntax

CSS has a unique syntax separate from HTML.

```css
p { 
  color: red;
}
```

In the code example above `p` is known as a selector, in this case it is selecting all paragraphs in the HTML pages linking to this CSS file. Selectors determine which elements will be effected by the styles we set. following in `{}` curly braces contains declarations which are CSS rules that will style our selected element. Declarations are made up of a property shown here as `color` c followed by a value shown here as `red`. Notice that we use a `:` colon to separate the property from its value. All decalrations end in a `;` semicolon. Multiple declarations can be applied to the same selector like so,

```css
p {
    color: red;
    font-weight: bold;
}
```
### Formats

CSS can appear in our code in three distinct formats: Inline, Internal, or External.

#### Inline

Inline CSS is written within a `style` attribute and only effects the single element that the attribute is included within.

```html
<p style="color:red;">Lorem ipsum</p>
```

#### Embedded

Embedded CSS is included typically wihtin the `<head>` section of an HTML document within `<style>` elements. This only effects the elements selected across the particular page it is includded within.

```html
<style>
  p {
    color: red;
  }
</style>
```
#### External

External CSS is writeen inside an external and separate file that is then linked to from other HTML pages. This is the preferred format to use as it allows us the effect the style of many HTML pages site-wide from a single file. This has two components to make it work, our CSS must be written in its own `.css` file and in our HTML file we must link to our CSS from our head section,

**css/style.css**

```css
p {
   color: red; 
}
```

**index.html**

```html
<!DOCTYPE html>
<html>
  <head>
    <link rel="stylesheet" href="css/style.css">
  </head>
  <body>
    <p>Lorem ipsum</p>
  </body>
</html>
```

### Selectors

CSS gives us a variety of ways to select different elements and style them.

#### Type

```css
p {
  color: red;
}
```

Selects an element of the specified type based directly on providing the element name.

```html
<p>Lorem ipsum</p>
```

#### Class

```css
.thick {
  font-weight: bold;
}
```

Selects an element with matching class attribute name. This selector is indicated by the preceeding `.` dot (period).

```html
<span class="thick">I'm thick</span>
```

#### Id

```css
#box {
  background: blue;
}
```

Selects an element with matching id attribute name. This selector is indicated by the preceeding `#` hashtag symbol.

```html
<div id="box">I'm a box</span>
```
#### Compound

h1, h2, #box {
  font-family: Arial, Helvetica, sans-serif;
}
```

Selects all matched elements in the compound set. This selector is indicated by a `,` comma separating the selectors of the set. Each element within the coma separated list will be styled the same.

```html
<h1>Heading</h1>
<h2>Subheading</h2>
<div id="box">I'm a box</span>
```

#### Descendent

```css
#nav li {
  background: blue;
}
```

Selects an element that is nested inside of the specified parent element. This selector is indicated by a ` ` keyboard space between the parent and the child to be selected.

```html
<ul id="nav">
  <li>child</li>
</ul>
```

#### Child

```css
#list > li {
  color: black;
}
```

Selects an element that is nested only one level deep inside of the specified parent element. Only selects direct children and not grandchildren. This selector is indicated by a `>` greater than symbol between the parent and the child to be selected.

```html
<ul id="list">
  <li>child</li>
  <li>child
    <ul>
      <li>grand child</li>
    </ul>
  </li>
</ul>
```

#### Adjacent Sibling

```css
h3 + p {
  color: green;
}
```

Selects an element that appears directly after the former element assuming they are both siblings (in the same level of nesting, in the same parent). This selector is indicated by a `+` plus symbol between the former sibling and the selected element that follows.

```html
<h3>Heading</h3>
<p>I'm a paragraph that is selected because I come directly after an h3.</p>
<p>I'm not selected.</p>
```

#### General Sibling (Preceded)

```css
h2 ~ p {
  color: black;
}
```

Selects all elements that appear directly after the former element. This selector is indicated by a `~` tilda symbol between the former sibling and the selected element that follows.

```html
<h2>Sub heading</h2>
<p>I'm selected because I appear after an h2.</p>
<p>I'm also selected for the same reason, in fact any paragraphs on the rest of the page after the h2 will be selected.</p>
```

#### Universal

```css
* {
  color: orange;
}
```

Selects elements where the properties specified have not been styled by any other selectors. This selector is indicated by a `*` asterisk symbol.

```html
<h5>Sub heading</h5>
```

We haven't yet specified a color style for `h5` anywhere else yet on our CSS so they will get the color orange now being covering under the universal selector.

#### Attribute

```css
img[alt="Cat"] {
  border: 1px solid black;
}
```

Selects an element with a matching attribute value. This selector is indicated by `[]` square brackets, followed by the attribute property and value of the selected element within the brackets.

```html
<img src="myimage.jpg" alt="Cat">
```

##### Other attribute selectors include:

`a[href^="http"]` The `^=` carrot symbol selects elements that start with the matching value. Such as `<a href="http://google.com">google</a>`.

`p[class$="dog"]` The `$=` dollar sign selects elements that end with the matching value. Such as `<p class="bigbdog">...</a>`.

`img[alt*="love"]` The `*=` asterisk selects elements that have the matched characters appearing anywhere within the value. Such as `<img src="myimage.jpg" alt="I love you.">`.

`p[class~="monkey"]` The `~=` tilda symbol selects elements that contain the term within a space separated value. Such as `<p class="zoo monkey details">...</p>`.

`p[class|="birds"]` The `|=` pipe symbol selects elements that contain the term within a dash separated value. Such as `<p class="new-birds-today">...</p>`.

#### Pseudo Class

```css
a:link {
  text-decoration: none;
}
```

Selects an element with based on the unique relationship or state described in the selector. This selector is indicated by `:` colon symbol, followed by the psuedo class that describes the elements state or positioning amongst other elements.

```html
<a href="about.html">About</a>
```

##### Other psuedo class selectors include:

`a:link` selects links in their default state before the visitor has interacted with them.

`a:visited` selects links after the user has already clicked on them and is visiting that page again.

`a:hover` selects links when the user is hovering their mouse over the link.

`a:active` selects links for only the moment when the mouse button is pressed when clicking on the link.

`p:first-child` selects elements that are the first child when appearing inside a common parent. Such as `<div><p>I'm selected</p><p>I'm not</p><p>Neither am I</p></div>`

`p:last-child` selects elements that are the last child when appearing inside a common parent. Such as `<div><p>I'm not selected</p><p>Neither am I</p><p>I'm selected</p></div>`

These are just a few psuedo selectors, there are many additional ones you can explore in the resource links provided at the botoom of this lesson.

### Authority & Inheritance

...

### Text Properties

...

## Summary

- CSS allows us to style our HTML pages.
- CSS has three distinct formats, although external CSS is considered the best option for styling websites.
- CSS provides a wide range of selectors to select different elements. Get to know them all.
- ...

## Resources

- [Presentation Slides](https://docs.google.com/presentation/d/1wTkUPKfSKt7ueUeKsZ6cYQ0RjRzpnEDLCqKKTB041P8/edit?usp=sharing)
- [MDN - CSS Tutorials for Beginners](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Getting_started)
- [MDN - CSS Property Reference](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference)
- [Tuts Plus - 30 CSS selectors to Memorize](http://code.tutsplus.com/tutorials/the-30-css-selectors-you-must-memorize--net-16048)
- [Learn More Pseudo Selectors](http://css-tricks.com/pseudo-class-selectors/)
- [CSS3.info - Using Web Fonts](http://www.css3.info/preview/web-fonts-with-font-face/)
- [CSS Authority, Specificity](https://www.youtube.com/watch?v=In78mSOHmls&feature=youtu.be)
- [CSS Performance & Organization, Best Practices](http://learn.shayhowe.com/advanced-html-css/performance-organization/)
- [CSS Validator](http://jigsaw.w3.org/css-validator/)
- [CSS Diner Online Game](http://flukeout.github.io/)
- [Adobe - Color Scheme Tool](https://color.adobe.com/create/color-wheel/)

<p data-visibility='hidden'>View <a href='https://learn.co/lessons/fe-css-fundamentals' title='CSS Fundamentals ~ 25min'>CSS Fundamentals ~ 25min</a> on Learn.co and start learning to code for free.</p>
