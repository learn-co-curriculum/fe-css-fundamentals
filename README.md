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

Selects an element of the specified type

|CSS|HTML|
|---|----|
|```css
p {
    color: red;
}
```|```html
<p>Lorem ipsum</p>
```|

#### Class

...

#### Id

...

#### Descendent

...

#### Child

...

#### Sibling

...

#### Attribute

...

#### Pseudo Class

...

### Text Properties

...

## Summary

- CSS allows us to style our HTML pages.
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
