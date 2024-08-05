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

### Specificity


## Structuring
## BEM Method
## CSS Variables
