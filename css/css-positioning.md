[see here](https://github.com/neuefische/bo-web-23-4/blob/main/sessions/css-positioning/css-positioning.md)

The position property comes in handy if you want to place an HTML element manually.
There are 5 different values to define the position:

| __type__             | __description__                                                                                                     |
| -------------------- | ------------------------------------------------------------------------------------------------------------------- |
| `position:static`    | the position of the element is determined by the document flow (default)                                            |
| `position: relative` | position the element relative to where the element would be placed normally                                         |
| `position: absolute` | position the element absolutely inside the nearest non-static ancestor element                                      |
| `position: fixed`    | position the element on a fixed position on the screen                                                              |
| `position: sticky`   | the element is placed normally in the document flow, but keeps an offset relative to its nearest scrolling ancestor |
The position is specified by the four position properties:
- `top`
- `bottom`
- `right`
- `left`
These work differently depending on the positioning method.

### `position: static`

Elements are positioned according to the normal document flow and then displaced by the 
- `top`
- `bottom`
- `right`
- `left`
properties. This method is also used to set the reference frame for an absolutely positioned child element. By doing so, the child element will be placed absolutely inside this element.

![[position-relative.png]]

### `position: absolute`

Elements are removed from the normal document flow and no space is created for them - so they leave no gap in the page. With `position: absolute` you place an element (with the `top`, `bottom`, `right`, `left` properties) relative to a reference frame. The reference frame is the view-box of the closest ancestor element that does not have `position:static` (default).

<span style="background-color:red; color:white;">example image missing</span>

### `position: fixed`

Elements are removed from the normal document flow and no space is created for them - so they leave no gap in the page. An element with position fixed is not influenced by scrolling and therefore stays at the specified position. This is often used for navigation bars or "back to top" buttons.

<span style="background-color:red; color:white;">example image missing</span>

### `position: sticky`

This is an unusual but very nifty positioning method. The element is not affected by the positioning until it comes near the border of its scrolling container (normally the page itself). When the user continues scrolling, a specified offset is enforced. The element sticks to this offset and appears like a fixed element.

![[position-sticky.png]]

### `z-index`

The z-index defines the stacking order of HTML elements. Elements with a higher stacking order appear on top if they overlap with other elements. The z-index can be an integer number (negative \#s possible), or it can have the default value `auto` which sets the stack order equal to its parents. The z-index only effects positioned elements - that is elements with a non-static position value.