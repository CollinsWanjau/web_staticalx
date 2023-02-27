# Working with Selectors 
The most common selectors:
* Type selector
* Class selector
* ID selector

### Type Selectors

* Type selectors target elements by their element type.e.g should we wish
to target all division elements, <div>, we would use a type selector of div.

css

```
div {...}
```

html

```
<div>...</div>
<div>...</div>
```

### Class Selectors

* Class selectors allow us to select an element based on the element's class

* Class selectors are a little more specific than type selectors, as they
select a particular group of elements rather than all elements of one type.

* Class selectors allow us to apply the same styles to different elements all at once using the same `class` attribute value across multiple elements.
* Within CSS, classes are denoted by a leading period., followed by the
class attr value.

css
```
.awesome { ... }
```

HTML
```
<div class="awesome">...</div>
<p class="awesome">...</p>
```

### ID Selectors

* ID selectors are even more presice than class selectors, as they target
only one unique element at a time

* IDs selectors use an element's id attribute value as a selector.

* Within CSS, ID selectors are denoted by a leading hash sign , #, followed
by id attr value.

css
```
#shayhowe { ... }
```

HTML
```
<div id="shayowe">...</div>
```

## Referencing CSS

```
<head>
  <link rel="stylesheet" href="main.css">
</head>
```

## Identifying Divisions & spans

* <div> & <span> are HTML elements that act as containers solely for 
styling purposes.As generic containers, they do not come with any semantic
value

#### Block vs. Inline Elements

* Block-level elements begin on a new line, stacking
one on top of the other
,and occupy any available width.

* Block elements may be nested inside one another and
may wrap inline-level elements.

* Inline-level elements do not begin on a new line.
They fall into the normal 
flow of a document, lining up one after the other, and
only maintain the width
of their content.

* Inline-level elements may be nested inside one another; however, they 
cannot wrap block-level elements.

* Both <div>s and <span>s, however, are extremely valuable when building a website
in that they give us the ability to apply targeted styles to a contained set of content.

* A <div> is a block-level element that is commonly used to identify large groups
of content and which helps to build a web page's layout and design.

* A <span>, on the other hand, is an inline-level element commonly used to identify
smaller groupings of text within a block-level element.

## Relative & Absolute Paths

* These links are identified by their href attr values, also known as their
paths.

* Links pointing to other pages of the same website will have a relative path, 
which does not include the domaiin(.com, .org, .edu) in the href attribute

* Because the link is pointing to another page on the
same website, the href attr value
needs to include only the filename of the page being linked to.`about.html` ,for example

* Linking to other websites outside of the current one
requires an `absolute path`, 
where the href attribute value must include the full domain, .com in this case.

* A link to google would need the `href` attr value of `http://google.com`

<!-- Relative Path -->
<a href="about.html">About</a>

<!-- Absolute Path-->
<a href="http://www.google.com/">Google</a>

## Linking to an Email Address

* To create an email link, the href attr value needs to start with `mailto:` followed by the 
email address to which email should be sent.

* To add a subject line, we'll include the `subject=` 
parameter after email address.

* The first parameter following the email address must begin with a `?`, to bind to the
hyperlink path.Multiple words within a subject line require that spaces be encoded using `%20`.

* Adding body text works in the same way as adding the subject, this time using the `body=`
paramter in the `href` attribute value.

* Because we are binding one parameter to another we need to use the ampersand, `&`, to separate
the two.

* As with the subject, spaces must be encoded using `%20`, and line breaks msut be encoded 
using `%0A`.

```
<a href="mailto:tripperskripper@gmail.com?subject=Reaching%20Out&body=How%20are%20you">
```
## Opening Links in a New Window

`<a href="http:http://localhost:5555/styles-conference" target="_blank">Style</a>`

## Linking to Parts of the Same Page

<body id="top">
<a href="#top"></a>
</body>

# Getting to know CSS

## Calculating the Speficity

* The type selector has the lowest specificity weight and holds a point value of `0-0-1`.

* The class selector has a medium specificity weight and holds a point value of `0-1-0`.

* the ID selector has a high specificity weight and holds a point value of 1-0-0.

* The first column counts ID selectors, the second column counts class selectors, and the third column counts type selectors.

## Combining Selectors

<b>HTML</b>
```
<div class="hotdog">
  <p>...</p>
  <p>...</p>
  <p class="mustard">...</p>
</div>
```

<b>CSS</b>
```
.hotdog p {
  background: brown;
}
.hotdog p.mustard {
  background: yellow;
}
```

## Layering Styles with Multiple Classes

* One way to keep the specificity weights of our selectors low is to be modular as possible,
sharing similar styles from element to element.

<b>HTML</b>
```
<a class="btn btn-danger">...</a>
<a class="btn btn-success">...</a>
```

<b>CSS</b>
```
.btn {
  font-size: 16px;
}

.btn-danger {
  background: red;
}

.btn-sucess {
  background: green;
}
```

## border-bottom

* The `border-bottom` shorthand CSS property sets an element's bottom border

* It sets the values of `border-bottom-width`, `border-bottom-style` and
`border-bottom-color`

### Syntax

border-bottom: 1px;
border-bottom: 2px dotted;
border-bottom: medium dashed blue;

##  Border
### Syntax
```
/* style */

border: solid;

/* width | style */

border: 2px dotted;

/* style | color */

border: outset #f33;

/* width | style | color */

border: medium dashed green;
```

#### Values

* `line-width`
-> Sets the thickness of the border `border-width`.

* `line-style`
-> Sets the style of the border.Defaults to none `border-style`.

* `color`
-> Sets the color of the border.Defaults to currentcolor `<border-color>`

## Background

* `Background` shorthand sets all background style properties at once, such
as color, image, origin and size, or repeate method

### Constituent Properties

1. background-attachment

2. background-color

3. background-image

4. background-origin

5. background-position

6. background-repeat

7. background-size

### Syntax 

```
/* Using a <background-color> */
background: green;

/* Using a <bg-image> and <repeat-style> */
background: url("test.jpg") repeat-y;

/* Using a <box> and <background-color> */
background: border-box red;

/* A single image, centered and scaled */
background: no-repeat center/80% url()
```

## Box Sizing

* The `box-sizing` sets how the totsl width and height of an element is
calculated.

* Note that it often useful to set `box-sizing` to `border-box` to lay out
elements.This makes dealing with the sizes of elements much easier, and generally
eleiminates a number of pitfalls you can stumble on while laying out
your content.

* On the other hand, when using `position: relative` or `position: absolute`,
use of `box-sizing: content-box` allows the positioning values to be relative
to the content, and independent of changes to border and padding sizes,
which is sometimes desirable.

### Values

* `content-box`
-> This is the initial and default value as specified by the CSS standard.The
`width` and `height` properties include the content, but does not include
the padding, border or margin.

* The dimensions of the element are calcuted as: width = width of the content,
and height = height of the content.(Borders and padding not included).

* `border-box`
-> The width and height properties include the content, padding and border,
but do not include margin.

* `.box {width: 350px; border: 10px solid black;}` renders a box that is 350px
wide, with the area for content being 330px wide.The content can't be negative
and is floored to 0, making it impossible to use `border-box` to make element
dissappear.

* width = border + padding + width of the content

* Height = border + padding + height of the content

## Flex

* The `flex` sets how a flex item will grow or shrink to fit the space available
in it's flex container.

#### Constituent properties

* This property is a shorthand for the following:

* `flex-grow`, `flex-shrink`, `flex-basis`

### Syntax

```
/* keyword values */
flex: auto
flex: initial
flex: none

/* One value, unitless number: flex-grow 
flex-basis is then equal to 0. */
flex: 2;

/* One value, width/height: flex-basis */
flex: 10em;
flex: 30%;
flex: min-content

/* Two values: flex-grow | flex-basis */
flex: 1  30px;

/* Two values: flex-grow | flex-shrink */
flex: 2 2;

/* Three values: flex-grow | flex-shrink | flex-basis */

```

## Margin

* The `margin` CSS sets the margin area on all four sides of an element.

### Syntax

```
/* Apply to all four sides

margin: 1em;
margin: -3px;

/* top and bottom | left and right */
margin: 5% auto;
-> sets a margin of 5% on all four sides of an element and centers it
horizontally within its parent container.

* The "auto" value for the horizontal margin (left and right) instructs
the broswer to automatically calculate and distribute the remaining space
evenly on both sides, effectively centering the element horizontally
within it's container.

* The vertical margin (top and bottom) will be 5% of the element's height.

/* top | left and right | bottom */
margin: 1em auto 2em;

/* top | right | bottom | left */
margin: 2px 1em 0 auto;
```


## Position: Relative

* Relative allows you to move an element relative to its original position
within its container, without affecting the position of other elements
around it.
