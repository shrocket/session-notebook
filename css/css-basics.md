# CSS Basics 
[see: https://github.com/neuefische/bo-web-23-4/blob/main/sessions/css-basics/css-basics.md](https://github.com/neuefische/bo-web-23-4/blob/main/sessions/css-basics/css-basics.md)

The term _cascading_ in CSS refers to an algorithm that resolves conflicts when multiple styles are defined for a particular element. When deciding which style to apply, CSS takes into account three key factors: specificity, source order, and inheritance.

- Specificity refers to how precisely a selector targets an element. Styles with higher specificity take precedence over those with lower specificity.

- The source order of styles also plays a role in determining which style should be applied. When multiple styles with the same specificity are defined, the style that appears last in the stylesheet will override any previous styles for that element.

- Additionally, CSS allows styles to be inherited from parent elements to their child elements. This means that certain styles can be passed down through the document tree, affecting multiple elements simultaneously.

The term _stylesheet_ refers to a collection of rulesets declared using CSS, usually within a `.css` file.


## Linking Stylesheets

To separate your HTML and CSS code, you can create a new file, like `css/styles.css` and link it to
your HTML file by placing a `<link>` tag in the `<head>` of your HTML document.

```html
<head>
  …
  <link rel="stylesheet" href="css/styles.css" />
</head>
```


## CSS syntax

Any stylesheet consists of a collection of **ruleset**s. A ruleset consists of four parts:

|                | Description                                                                                                              |
| -------------- | ------------------------------------------------------------------------------------------------------------------------ |
| Selector       | Selects to which elements the style declarations are applied, followed by curly braces (`{}`) enclosing the declarations |
| Declaration    | A combination of a property and a property value, separated by a colon (`:`) and ending with a semicolon (`;`)           |
| Property       | The property you want to style, e.g. `color`, `font-size`, `text-align`                                                  |
| Property Value | The value assigned to the property, e.g `blue` for the `color` property, `3rem` for the `font-size` property             |

## Selectors
Three (five?) different selectors:
- type / element
	- h1
	- p
	- div
	- a
	- etc.
- class
	- in the HTML, the class would be "superpink"
	- in the CSS, it's ".superpink"
- pseudo-classes
	- selects elements in a state
		- :hover
		- :focus
		- :active
		- [etc.](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes)
- attribute selectors
- the universal selector
## Combinators

- You can combine multiple selectors with a comma to create a new selector that selects all elements that are selected by **any one** of the selectors.
```
h1,
h2,
h3 {
	color: hotpink;
}
```
- The descendant combinator ` ` (space) selects all elements that are descendants (children) of another selector.
```
article .superpink {
	color: hotpink
}
```
- The above selects all `.superpink` elements that are descendants of an `article` element.
- [see also](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes)

## Inheritance

If the body's background-color is set to hotpink, the the paragraph element will also have a background-color of hotpink, unless the background-color of the paragraph element is explicitly set.

## Box Model

All elements of a website are rectangular boxes described by the **box model**. Each of those boxes has four areas: content, padding, border and margin.

| Box model part | Function                                                               |
| -------------- | ---------------------------------------------------------------------- |
| margin         | The outer space measured from the border to other elements on the page |
| border         | The border of the element                                              |
| padding        | The inner space between the content and the border of the element      |
| content        | The actual content box of the element                                  |
The box model has an old (content-box) version, and a more modern one (border-box). The old only calculated height and width (padding and border were calculated in the content of the box). The new has (see above) all four. This is why we set
```
*{
	box-sizing: border-box;
}
```
at the beginning of our .css file

## Inline and block elements

### Inline elements 
are as wide as their maximum content width and flow with text.
- common inline elements:
	- `a`
	- `span`
	- `strong`
	- `img`
	- etc.
### Block elements
take up the full width of the parent element and always start on a new line.
- common block elements:
	- `p`
	- `h1` - `h6`
	- `div`
	- `section`
	- `article`
	- etc.
## Display property
Inline can be changed to block and vice versa:
```
h2{
	display: inline;
}
```

```
a{
	display: block;
}
```
