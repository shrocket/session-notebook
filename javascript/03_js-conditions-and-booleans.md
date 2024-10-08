[see here](https://github.com/neuefische/bo-web-23-4/blob/main/sessions/js-conditions-and-booleans/js-conditions-and-booleans.md)

***

## Boolean Values

A boolean value, named after [George Boole](https://en.wikipedia.org/wiki/George_Boole), only has two states: True or False. Booleans are often used in conditional statements which can execute different code depending on their value.

## Truthy and Falsy Values

Sometimes you want to have a condition depending on another type of value. JS can transform any value into a boolean with _type coercion_ (see [[02_js-variables-and-numbers]]). That means that some values act _as if_ they were true and other _as if_ they were false: _Truthy_ values become true, _falsy_ values become false.

- _truthy_ values:
	- non zero numbers: `1`, `2`, `3`, etc.
	- non empty strings: `"hello"`
	- `true`
- _falsy_ values:
	- `0` / `-0`
	- `null`
	- `false`
	- `undefined`
	- empty string: `""`

***

## Comparison Operators

Comparison operators produce boolean values by comparing two expressions:

| Operator  | Effect                                                                              |
| --------- | ----------------------------------------------------------------------------------- |
| A `===` B | __strict equal__: is `true` if both values are equal (including their type)         |
| A `!==` B | __strict not equal__: is `true` if both values are not equal (including their type) |
| A `>` B   | __strictly greater than__: is `true` if A is greater than B                         |
| A `<` B   | __strictly less than__: is `true` if A is less than B                               |
| A `>=` B  | __greater than or equal__: is `true` if A is greater than or equal to B             |
| A `<=` B  | __less than or equal__: is `true` if A is less than or equal to B                   |
>[!note] Please notice that JS uses three equal signs (`===`) to check for equality. Do not be confused!
> - `=` (`const x=0`) is the assignment operator and has nothing to do with comparison.
> - `==` and `!=` are non-strict equality operators. __You should avoid them 99% of the time.__ Non-strict equality tries to use type coercion to convert both values to the same type: `"3" == 3` is `true`, which is seldomly what you want.
> - `===` and `!==` are strict equality operators. __This is what you need almost always.__ Strict equality checks if type _and_ value are the same: `"3" === 3` is `false`.

 ***
## Logical Operators

Logical operators combine up to two booleans into a new boolean.

| Operator | Effect                                                |
| -------- | ----------------------------------------------------- |
| `!`A     | `not`: flips a `true` value to `false` and vice versa |
| A \|\| B | `or`: is `true` if either A `or` B is true            |
| A `&&` B | `and`: is `true` if both A `and` B are true           |
>[!note] You can combine logical operators with brackets to define which operator should be evaluated first, e.g.:
>- `(A || B) && (C || D)`
>- `!(A || B)`

>[!note] Be careful when using `&&` or `||` with non-boolean values. They actually return one of the original values. That can be useful, but can also quickly lead to confusion. The behavior is called [short-circuit evaluation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Logical_AND#short-circuit_evaluation) and is a more advanced topic.
>- `"some string" || "some other string"` evaluates to `"some string"`
>- `0 || 100` evaluates to `100`
>- `null && "yet another string"` evaluated to `null`

***

## Control Flow: `if / else`

With an if statement we can control whether a part of our code is executed or not, based on a condition.

```js
const isSunShining = true;

if (isSunShining) {
	// code that is executed only if condition "isSunShining" is true
}
```

The else block is executed only if the condition is `false`.

```js
const isSunShining = false;

if (isSunShining) {
	// code that is executed only if condition "isSunShining" is true
} else {
	// code that is executed only if condition "isSunShining" is false
}
```

The condition expression between the `()` parentheses can be composed of logical or comparison operators as well. You can distinguish between more cases by chaining `else if` statements.

```js
if (hour < 12) {
	console.log("Good Morning.");
} else if (hour < 18) {
	console.log("Good afternoon.);
} else if (hour === 24) {
	console.log("Good night.");
} else {
	console.log("Good evening.");
}
```

If the condition is not a boolean, it is converted into one by type coercion. This can be used to check whether a value is not 0 or an empty string:

```js
const name = "Alex";
if (name) {
	console.log("Hi " + name + "!"); //only executed if name is not an empty string
}
```

***

## Ternary Operator: `? :`

With if/else statements whole blocks of code can be controlled. The ternary operator can be used if you want to decide between two _expressions_, e.g. which value should be stored in a variable:

```js
const greetingText = time < 12 ? "Good morning." : "Good afternoon.";
```

```js
// a simple examples
const time = 13
const greetingText = time < 12 ? "Good morning." : "Good afternoon.";
console.log(greetingText);
```

The ternary operator has the following structure:

```js
condition ? expressionIfTrue : expressionIfFalse;
```

If the condition is true, the first expression is evaluated, otherwise the second expression. The ternary operator can be used to decide which function should be called:

```js
usUserLoggedIn ? logoutUser() : loginUser();
```

It can also distinguish which value should be passed as an argument to a function:

```js
moveElement(xPos > 300 ? 300 : xPos); // the element can't be moved further than 300.
```

>[!warning] The operator can only distinguish between two _expressions_ like values, math / logical operations or function calls, not between _statements_ like variable declarations, if/else statements or multi-line code blocks.

***

## Advanced: The strangeness of boolean coercion and making use of non-strict equality
[see here](https://github.com/neuefische/bo-web-23-4/blob/main/sessions/js-conditions-and-booleans/js-conditions-and-booleans.md#advanced-the-strangeness-of-boolean-coercion-and-making-use-of-non-strict-equality)

***


## Challenges

## Statements

I had some trouble with Part 5: Greeting. I was able to get the console to output the correct thing by making a long and unwieldy ternary operator, but I had to look up the more simple solution:

```js
const greeting = "Hello" + (userName === "Archibald" ? "Coach" : userName) + "!";
console.log(greeting);
```

## Teenager check

I was able to write both an if/else statement _and_ a ternary operator that correctly logged the text to the console, but could not remember how to change the text.

I knew I needed to do something with `output = document.querySelector('[data-js="age-output"]');`, but not _what_.

I did a search in the froggy slack and found Eli's solution [here](https://codesandbox.io/p/sandbox/nifty-cartwright-zw53my?file=%2Fjs%2Findex.js).

It would have been nice if `(output.textContent = "XXX")` had been in _any_ of the notes leading up to this point.