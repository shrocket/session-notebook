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

### Variable Naming

Expressive variable names are very important to __code readability__! There are some key guidelines one should follow:
- use camel case: `soçialFeedEntry` instead of `socialfeedentry`
- write out all words: `error` instead of `e`, `followTheButton` instead of `flBtn`
- be very specific; longer names are better than shorter: `updatedFollowerCounter` instead of `counter`

## Math & Operators

Programmers sometimes have to use mathematical operations to calculate certain widths or positions of elements. Operators calculate values based on one or two expressions.

| operator | effect                                                                                              |
| -------- | --------------------------------------------------------------------------------------------------- |
| `+`      | adds two numbers together                                                                           |
| `-`      | subtracts one number from another                                                                   |
| `*`      | multiples two numbers                                                                               |
| `/`      | divides two numbers                                                                                 |
| `**`     | potentiates two numbers: `2 ** 4 -> 16`                                                             |
| `%`      | the __remainder__ or __modulus__ gives you what remains after a whole number division: `8 % 3 -> 2` |

### More on the Remainder: `%`

The remainder is a very useful operator, but might be difficult to understand at first. A real life example would be in time on a clock. After noon, you don't reach 13 a.m., but you start over at 1 p.m. Three hours after midnight isn't 15 p.m. (or 27h in the 24h format), but 3 a.m. It is whatever hour we have mod 12.

```js
5 % 12; // -> 5
12 % 12; // -> 0
13 % 12; // -> 1
15 % 12; // -> 3
27 % 12; // -> 3
```

This operator can also be used to determine if a number is even or odd:

```js
6 % 2; // -> 0
```

The result is `0` for all __even numbers__, because after dividing an even number by `2` nothing remains.

```js
5 % 2; // -> 1
```

The result is `1` for all __odd numbers__, because after dividing an odd number by `2` there is always `1` left over .

In "real world" terms, an even number divided by `2` produces a whole number answer, but an odd number divided by `2` always produces a fraction.

### Operator Precedence

#### __PEMDAS__

> [!info] You can read more about [__Operator precedence__ in the mdn](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Operator_Precedence).

> [!info] If you are uncertain, use parentheses to denote precedence manually (the __P__ in __PEMDAS__!). Prettier will remove any unnecessary parentheses from your expression automatically.

### Assignment Operators

`=` is the default assignment operator. This operator simply assigns the value on the __right__ to the element on the __left__. There are more assignment operators for very common actions like increasing a variable by a fixed value.

| operator | effect                                                                                                                 |
| -------- | ---------------------------------------------------------------------------------------------------------------------- |
| `+=`     | increases the value of the variable on the left by the the value on the right: `count += 6` -> count is increased by 6 |
| `-=`     | decreases the value of the variable on the left by the value on the right                                              |
| `*=`     | multiplies the variable on the left by the value on the right                                                          |
| `/=`     | divides the variable on the left by the the value on the right                                                         |
| `++`     | __increments__ the value of a variable by one: `count++` -> the count is increased by one                              |
| `--`     | __decrements__ the value of a variable by one: `count--` -> the count is decreased by one                              |

### Type Coercion

If you use an operator with a variable of an unfitting type, JS will automatically convert (coerce) the variable into a fitting type. For example:

```js
4 / "2"; // -> 4 / 2
```

In the above, `"2"` is a string, not a number. JS converts the string to a number.

> [!warning] There is another `+` operator in JS that links two strings together: `"a" + "b"`->`"ab"`. When "adding" a number and a string, the number is converted to a string: `"a" + 6`->`"a6"`. Make sure that both variables are numbers if you want to add them!

> [!info] Read more about [__Type coersion__ in the mdn](https://developer.mozilla.org/en-US/docs/Glossary/Type_coercion).

### Number Systems

When working with computers, it is sometimes useful to work with a different number system than the standard 10 digit system, since a computer only understands `binary` numbers composed of `1` and `0`. 
- `decimal system`: the standard numbers, has 10 symbols "0" to "9"
- `binary system`: only has 2 symbols "0" and "1." If you want to write a bigger number than 1, you add another digit: 2 -> "10" in binary.
- `hexadecimal system`: has 16 symbols: "0" to "9" and "a" to "f." If you want to write a number bigger than 15, you add another digit: 12 -> "c" in hexadecimal.