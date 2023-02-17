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

`
<a href="mailto:tripperskripper@gmail.com?subject=Reaching%20Out&body=How%20are%20you">
`