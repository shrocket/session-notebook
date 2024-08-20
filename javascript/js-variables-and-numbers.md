## Variable Declarations

Variables are a `reference` or `alias` for data stored in memory.
There are three different keywords to declare a variable:
- `const` declares a constant; the value can't be changed. This is the __default__.
  ```js
const aNewVariable = 1234;
```
- `let` declares a variable; the value __can__ be changed. This is __only used if reassigning a new value is necessary__. For example, when you want to increase a counter:
```js
let counter = 0;
counter = counter + 1; // reassigning the value of counter
```  
- `var` is __outdated__ and __no longer used__.

### The `=` Sign
The `=` means "the value of the item on the __right__ of the equal sign is saved in the item on the __left__ of it." What the item on the __right__ actually represents is calculated first and saved afterwards.

## Primitive Data Types

JavaScript is a __dynamically typed language__, which means that you don't have to specify what kind of value you want to store, JavaScript detects this automatically.

### There are 7 primitive data types:

| type        | represents                                                                                                           |
| ----------- | -------------------------------------------------------------------------------------------------------------------- |
| `string`    | a sequence of characters: "abcd"                                                                                     |
| `number`    | a number: 1234                                                                                                       |
| `boolean`   | a binary statement: `true` or `false`                                                                                |
| `null`      | represents "nothing" and is typically set by devs                                                                    |
| `undefined` | represents the state of "not existing" (anything not specified or not found in JS defaults to the value `undefined`) |
| `BigInt`    | uncommon, used for integers larger than 9007199254740991                                                             |
| `Symbol`    | uncommon, used for creating unique elements                                                                          |

## Variable Naming

