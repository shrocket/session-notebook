[see here](https://github.com/neuefische/bo-web-23-4/blob/main/sessions/css-structure/css-structure.md)

## Oder of Importance
### Cascade
The cascade is the algorithm that defines which CSS rules are applied when conflicts arise.
When stying an element, the browser:
1. Searches for all rules with matching selectors
2. Sorts the rules by their importance, taking into account:
	- Whether the declaration is followed by `!important`
	- The rule's origin (browser stylesheet, user stylesheet, author stylesheet)
3. Sorts rules by their specificity (if #2 finds multiple rules with same importance)
4. Chooses the __last__ declaration over the __previous__ one
See [CSS Cascade mdn docs](https://developer.mozilla.org/en-US/docs/Web/CSS/Cascade)

> [!warning] 
> Avoid `!important`

### Specificity
More specific CSS rules win over less specific ones.
A good list of the specificity of different selectors can be found at [specifishity.com](https://specifishity.com/).
The universal selector is the least specific. It is overwritten by any other rules with any other matching selector.
__type__ selectors like `div` have a __low specificity__ and can easily be overwritten.
__class__ selectors like `.bright` and __attribute__ selectors like `[type=checkbox]` have higher specificity.

## Structuring Best Practices
- keep your CSS consistent! In collaborative projects, there are often style guidelines.
- separate global and local styles into different files (or sections of files)
- create multiple stylesheets for different parts of your application
	- structure your code by thinking in reusable __components__ (each component in its own CSS file).
### Import one stylesheet into another
```css
@import "customer-card.css"
```

## BEM Method
__BEM__ stands for **B**lock, **E**lement, **M**odifier, and is a method that allows one to create reusable components through CSS class naming conventions.
```css
/* A block is a standalone entity or component */
.block {
	...;
}

/* An element is a part of your block (or component) that has no standalone meaning. */
.block__element {
	...;
}

/* A modifier is a flag on your block (or component) that is used to change its appearance or behavior, e.g. disabled, checked, bright, etc. */
.block--modifier {
	...;
}
```
You can find an introduction to BEM [here](http://getbem.com/introduction/)

### Kebab Case in BEM
```css
.customer-card {
	...;
}

.customer-card__button {
	...;
}

.customer-card--disabled {
	...;
}
```

## CSS Variables
