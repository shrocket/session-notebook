([see here](https://github.com/neuefische/bo-web-23-4/blob/main/sessions/css-responsive/css-responsive.md))

## Mobile First Design
__do not fucking forget this in the future__

## Responsive Units
Responsive units are _relative_ to the __size of the viewport__, the __current font size__, or the __size of their parent element__.

- `vh` (viewport height): 1vh is 1% of the viewport height
- `vw` (viewport width): 1vw is 1% of the viewport width
- `em`: 1em is the font size of the current element
- `rem`: 1rem is the font size of the root element
- `%`: is relative to the related property of the parent or current element - every property has its own rules regarding what it is relative to:
	- `width 1%` is set relative to the parent element width
	- `padding-top: 10%` means 10% of the parent height
	- `font-size: 50%` means half as big as the parent font-size
	- `transform: translateX(50%)` means translate on the x axis by 50% of the current element's width
	- `calc()`: allows you to combine multiple units and do math
		- e.g. `calc(100vh - 100px`
		- or `calc(50% - 10rem)`

## Media Queries
Media queries allow you to write CSS for specific media types, screen sizes, orientations and more.

They adhere to the following syntax:
```css
@media (media feature) {
	/* CSS rules */
}
```
### Media Types
You can target a specific media type with the `screen` and `print` media types.

### Screen Size
You can target specific screen sizes with the `min-width` and `max-width` media features.

```css
@media (min-width: 600px) {
/* CSS rules that are only applied when the screen is at least 600px wide */
}

@media (max-width: 600px) {
	/* CSS rules that are only applied when the screen is at most 600px wide */
}
```

>[!caution] Avoid `max-width` media queries!
>It's easier to think about the smallest screen size first, and then add media queries for larger screens.

### Orientation
You can target specific orientations with the `orientation` media feature.

```css
@media (orientation: portrait) {
	/* CSS rules that are only applied when the screen is in portrait orientation */
}

@media (orientation: landscape) {
	/* CSS rules that are only applied when the screen is in landscape orientation */
}
```

>[!info] You can also target a specific aspect ration with the [`aspect-ratio` media feature](https://developer.mozilla.org/en-US/docs/Web/CSS/@media/aspect-ratio).

### Pointer
You can target specific pointer types with the `any-pointer` media feature.

```css
@media (any-pointer: none) {
	/* CSS rules that are only applied when the device has NO pointer */
}

@media (any-pointer: coarse) {
	/* CSS rules that are only applied when the device has a coarse pointer (mostly touch) */
}

@media (any-pointer: fine) {
	/* CSS rules that are only applied when the device has a fine pointer (cursor) */
}
```

### Device Pixel Ratio (Pixel Density)
You can target specific device pixel ratios with the `device-pixel-ratio` media feature.
- 1 is for older screens
- 2 is for newer screens like the retina screen on the MacBook
- 3 is for some high resolution tablets and phones

### Color Scheme
You can target specific color schemes with the `prefer-color-scheme` media feature.

```css
@media (prefers-color-scheme: dark) {
	/* CSS rules */
}

@media (prefers-color-scheme: light) {
	/* CSS rules */
}
```

### Other Media Features
There are also media features for other (accessibility) features like `inverted-colors`. The list of all media features is always growing. Check out the [full list](https://github.com/neuefische/bo-web-23-4/blob/main/sessions/css-responsive/css-responsive.md) on mdn.

### Combining Media Features
You can combine multiple media features with `and`.

### Testing for multiple Media Features
You can use a comma-separated list to apply styles when the user's device matches any one of various media types.

```css
@media (min-width: 600px), (orientation: portrait) {
	/* CSS rules that are only applied wien the screen is EITHER at least 680px high or in portrait orientation */
}
```

### Simulating Media Features
You can simulate media features in the browser devtools.

### Common Breakpoints
When using `min-width` media queries, it can be helpful to use common breakpoints.
- no media query (default): extra-small, xs, mobile
- `(min-width: 600px)`: small, sm, large mobile
- `(min-width: 900px)`: medium, md, tablet
- `(min-width: 1200px)`: large, lg, desktop
- `(min-width: 1536)`: extra-large, xl, large desktop

>[!info]
>These breakpoints are based on the [MUI breakpoints](https://mui.com/material-ui/customization/breakpoints/). Other frameworks and projects might define a completely different set of breakpoints. Mostly, they are defined to be between the most common screen sizes. Another example for common breakpoints are the [ones from Tailwind CSS](https://tailwindcss.com/docs/breakpoints). 

>[!pro-tip] Pro Tip:
>You can use media queries to redefine the values of CSS custom properties. This way you can use the property as a value that dynamically changes based on the media query.

```css
:root {
	--font-size: 12px;
}

@media (min-width: 600px) {
	:root {
		--font-size: 16px;
	}
}

@media (min-width: 1200px) {
	:root {
		--font-size: 20px;
	}
}

body {
	font-size: var(--font-size);
}
```

