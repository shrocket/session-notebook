[see here](https://github.com/neuefische/bo-web-23-4/blob/main/sessions/css-flexbox-new/css-flexbox.md)

## Flexbox does the following:
- all child elements will be displayed next to each other along the __horizontal axis__ (which is default)
- if the width of the child elements exceeds the container's width, the elements will be shrunk to fit the space

## Important Flex Properties

| __property__                                                                        | __effect__                                                                                                                                                                                                                                                                                 |
| ----------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| [justify-content](https://developer.mozilla.org/en-US/docs/Web/CSS/justify-content) | defines the positioning of elements along the main axis. Useful values: `flex-start`, `flex-end`, `center`, `space-between`, `space-around`, `space-evenly`                                                                                                                                |
| [align-items](https://developer.mozilla.org/en-US/docs/Web/CSS/align-items)         | defines the positioning of elements along the cross axis. useful values: `flex-start`, `flex-end`, `center`                                                                                                                                                                                |
| align-self                                                                          | accepts the same values as `align-items` but can be used for single items                                                                                                                                                                                                                  |
| [gap](https://developer.mozilla.org/en-US/docs/Web/CSS/gap)                         | defines the minimum spacing between elements                                                                                                                                                                                                                                               |
| [flex-direction](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-direction)   | sets the direction of the main axis. useful values: `row`, `row-reverse`, `column`, `column-reverse`                                                                                                                                                                                       |
| [flex-wrap](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-wrap)             | modifies how elements can wrap into another row instead of being squashed into one row. useful values: `wrap`, `no-wrap`, `wrap-reverse`                                                                                                                                                   |
| order                                                                               | by default, items have a value of 0, but this property can be used to set that value to a positive or negative integer.                                                                                                                                                                    |
| flex-flow                                                                           | the two properties `flex-direction` and `flex-wrap` are used together so frequently that the shorthand property `flex-flow` was created to combine them. this property accepts the value of the two properties separated by a space, e.g. `flex-flow: row wrap` to set rows and wrap them. |
| align-content                                                                       | determines the spacing between lines (_does not work if only one line is present!_). useful values: `flex-start`, `flex-end`, `center`, `space-between`, `space-around`, `stretch`                                                                                                         |
### Check out [this very detailed cheatsheet](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)!!!

### Flex-direction
![[flex-direction.png]]

### Flex-wrap
With the property set to `flex-wrap: wrap`, the elements flow into th enext row when they wouldn't fit into the current row. Depending on the screen width, the content can align itself, as shown in the following example.
![[flex-wrap.png]]
