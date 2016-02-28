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

You can apply a class name to as many elements as you like acroos the same page and across any pages in your website. This is a good selector for sprinkling the same style to many different elements.

You can also apply more than one class to the same element for example lets apply two classes to the same paragraph.

```css
.thick {
    font-weight: bold;
}

.alert {
    color: red;
}
```

To apply the two classes we simply use a space to separate their names,

```html
<p class="thick alert">Warning...</p>
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

A single Id name should only be applied to one element per page.

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

### Authority

It is common when we are styling our HTML pages that we might accidentally write two selectors that are targeting the same element. Let's say for example you intend all `<h1>` level 1 headings to have light blue text, but you also gave some of the headings a class of intro `<h1 class="intro">` and these intro headings should have the text color of dark blue instead. What happens to the `<h1 class="intro">` elements will they have light blue or dark blue text? Fortunately CSS has rules that determine which selector wins. The strength of a selector to override another is known as authority. In CSS the more specific a selector the more authority it carries.

```css
h1 {
  color: lightblue;
}

.intro {
  color: darkblue;
}
```

In the CSS code above our first selector `h1` selects all level 1 headings, where as our second selector `.intro`, selects elements that have the specific class of `intro` applied. In the case of the following html which will beat the other?

```html
<h1 class="intro">Welcome</h1>
```

In this case a class is more specific as it is applied to only certain h1, where as selecting all h1s is very general. Thus classes like `.intro` have more authority than a type selector such as `h1`. The end result is that the heading has dark blue text instead of light blue. The general rule is descendent overrides id which overrides class which overrides type which overrides universal. 

If there are two selectors of equal authgority the one that is written further down the page (closer to the bottom) will win. This is the last man rule.

See the link in the resources at the bottom of the lesson to explore CSS selector authority in more detail.

#### Inheritance

Certain CSS styles are inherited from a parent down to its child elements. One such example is most of the typography properties. We will discuss these in more detail below, but just to give you a quick example. Lets say we add the `font-family: Arial;` to a `ul` unordered list.

```css
ul {
    font-family: Arial;
}
```

```html
<ul>
    <li>Apples</li>
    <li>Oranges</li>
    <li>Bananas</li>
</ul>
```

In this case, all the `li` list items that are children of the `ul` will inherit the Arial font from their `ul` parent simply by being inside of it.

Certain properties like `font-family` can be inherited by a parent, however other propertied by default are not directly inherited, for example

```css
ul {
  border: 1pc solid black;
}
```

A border will only effect the `ul` it is applied to and the `li` will not inherit the border by default. It is good to know which properties are inherited and which are not. there are also some CSS values that allow us to change the defualt behavior of inheritance. See 

### Colors

#### Names

There are 16 cross browser compatible color names: aqua, black, fuchsia, (gray, grey), green, lime, maroon, navy, olive, purple, red, silver, teal, white, and yellow.

#### Hexidecimal

There are over 16 million possible color combinations using hex values. Hex values are preceeded by a `#` hashtag symbol and follow with three values back to back listed as numbers 0-9 and letters A-F. The first two characters are for the amount of red, followed by green, and blue. For example with F being the largest amount of a color and 0 being the lowest, the hex color `#FF0000` is the brightest color red. In situtaions where the three pairs of hex values match as in the last example you can shorten this to: `#F00` instead. Note that this only works for hex values where each of the three pairs match. The hex color `#3345AF` which incidentally is a dark blue color can not be shortened.

#### RGB and RGBA

We can produce any color our eye can see using RGB values. These are created by listing a set of numbers for red, green, and blue respectively using a range of 0 the absence of light and 255 the brightest amount of light possible for that color. These values are comma separated and enclosed in parenthesis and preceeded by rgb, `rbg(255,0,0)` is the color red. Using RGBA we supply a fourth number which is the alpha value. This is the opcaity given in a range of 0-1, where 0 is 0% and 100 is 100% opacity. rgba(255,0,0,0.5) is 50% transparent red color.

#### HSL and HSLA

There are other supported values such as HSL (Hue Saturation Lightness) or HSLA (Hue Saturation, LIghtness, Alpha) These are less commonly seen, but if you're interested you can read more about them in the resource links at the end of the lesson.

### Font Properties

There are many font properties you can adjust. Here are a few useful ones and some of their possible values separated by `|` pipes.

`font-family: Arial, Helvetica, san-serif`

`font-size: 100% | 1em | 12pt | 16px`

`font-style: normal | italic`

`font-weight: normal | bold`

`color: white | #FFF | rgba(255,255,255,1)`

`font: bold 1em/2em Arial, sans-serif`

`text-align: left | center | right`

`text-decoration: none | overline | underline | line-through`

`text-indent: 1% | 1em | 12pt | 16px`

`text-shadow: 3px 3px 10px #000`

`text-transform: none | uppercase | lowercase | capitalize`

`letter-spacing: normal | 1em | 12pt | 16px`

`line-height: normal | 1em | 12pt | 16px`

`word-spacing: normal | 1em | 12pt | 16px`

`word-wrap: normal | break-word`

`white-space: normal | no-wrap`

### Web Fonts

...

```shell

```

...

```css
@font-face {
  font-family: "Skolar";
  src: url("../fonts/Skolar.webfont");
}

p {
  font-family: "Skolar", Georgia, serif;
}
```

...

### Comments

To comment in CSS simply start with `/*` and end with `*/`

```css
/* this is a comment */

/* It can be single, 
   or multiple lines */
```

## Summary

- CSS allows us to style our HTML pages.
- CSS has three distinct formats, although external CSS is considered the best option for styling websites.
- CSS provides a wide range of selectors to select different elements. Get to know them all.
- ...

## Resources

- [Presentation Slides](https://docs.google.com/presentation/d/1wTkUPKfSKt7ueUeKsZ6cYQ0RjRzpnEDLCqKKTB041P8/edit?usp=sharing)
- [MDN - CSS Tutorials for Beginners](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Getting_started)
- [MDN - CSS Property Reference](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference)
- [MDN - CSS Inheritance](https://developer.mozilla.org/en-US/docs/Web/CSS/inheritance)
- [Tuts Plus - 30 CSS selectors to Memorize](http://code.tutsplus.com/tutorials/the-30-css-selectors-you-must-memorize--net-16048)
- [Learn More Pseudo Selectors](http://css-tricks.com/pseudo-class-selectors/)
- [CSS3.info - Using Web Fonts](http://www.css3.info/preview/web-fonts-with-font-face/)
- [CSS Authority, Specificity](https://www.youtube.com/watch?v=In78mSOHmls&feature=youtu.be)
- [CSS Performance & Organization, Best Practices](http://learn.shayhowe.com/advanced-html-css/performance-organization/)
- [CSS Validator](http://jigsaw.w3.org/css-validator/)
- [CSS Diner Online Game](http://flukeout.github.io/)
- [Adobe - Color Scheme Tool](https://color.adobe.com/create/color-wheel/)
- [CSS Tricks - HSLA](https://css-tricks.com/yay-for-hsla/)

<p data-visibility='hidden'>View <a href='https://learn.co/lessons/fe-css-fundamentals' title='CSS Fundamentals'>CSS Fundamentals</a> on Learn.co and start learning to code for free.</p>
