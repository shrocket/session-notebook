inde[see here](https://github.com/neuefische/bo-web-23-4/blob/main/sessions/js-basics/js-basics.md)
## Connect a JavaScript file

```html
<head>
	...
	<script scr="./index.js" defer></script>
</head>
<body>
...
</body>
```

The `script` tag has two attributes:
1. `scr="./index.js"` sets the URL to our JavaScript file
2. `defer` tells the browser to delay the loading of the script until all HTML elements have been loaded


## Hello World: `console.log()`

In JS, we can print text to the console of the web browser. This can be used for debugging or error logging.

```javascript
console.log("Hello World!"); //logs into console
console.clear(); // clears console
console.error("Error!"); // logs as error into console
```


## Simple Variables
```js
const hacking = "Happy hacking!";
console.log(hacking);

// the sentence stored in the variable is then, with the .log, diplayed in the console
```


## Selecting HTML Elements: `.querySelector()`

Before we can add interactivity, we need to select the necessary HTML elements:

```html
<body>
	<main class="main" id="main" data-js="main">...</main>
</body>
```

There are multiple ways to select the above `<main>` section within our JS. A good practice is to use a [data-* attribute](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/data-*), like the __data-js__ in the following example:

```javascript
const mainElement = document.querySelector('[data-js="main"]');
```

Other CSS selectors work as well, but the data-* attribute selectors should be preferred.

```javascript
//tag as identifier
const mainElement = document.querySelector("main");
// class as identifier -> .
const mainElement = document.querySelector(".main");
// id as identifier -> #
const mainElement = document.querySelector("#main");
```

>[!info] Keep concerns separated: Classes are for CSS and data-* attributes are for JS


## Add Interaction: `.addEventListener()`

The method `addEventListener` is used to react to events like clicks on an Element. When triggered, code is executed.

```html
<button type="button" data-js="button">Log into console</button>
```

```js
const button = document.querySelector('[data-js="button"]');
button.addEventListener("click", () => {});
```

First, you specify the kind of event, e.g. __click__, then you define what code should be executed when the event is triggered. You write that code between the curly braces `{}`, e.g. a `console.log`.

```js
const button = document.querySelector('[data-js="button"]');
button.addEventListener("click", () => {
	console.log("Yeah");
});
```

There are several different events you can listen to, for example:

```js
button.addEventListener("mouseover", () => {});
```

```js
button.addEventListener("keydown", () => {});
```

>[!info] You can find a list of event types [here](https://developer.mozilla.org/en-US/docs/Web/Events#event_listing)


## Add/remove & Toggle Classes: `.classList.`

You can add, remove, and toggle classes in order to, for example, change the styling of an element.

```html
<main data-js="main">
	<button type="button" data-js="button">Add a class</button>
</main>
```

Add __page--primary__ class to the above main section by using the `selectdElement.classList.add` method:

```js
const main = document.querySelector('[data-js="main"]');
const button = document.querySelector('[data-js="button"]');

button.addEventListener("click", () => {
	main.classList.add("page--primary");
})'
```

A click on the button adds the class __page--primary__ to the main element:

```html
<main data-js="main" class="page--primary">
	<button type="button" data-js="button">Add a class</button>
</main>
```

You can also __remove__ or __toggle__ a class in the same way:

```js
main.classList.remove("page--primary");
```

```js
main.classList.toggle("page--primary");
```


## Resources
[see here](https://github.com/neuefische/bo-web-23-4/blob/main/sessions/js-basics/js-basics.md)
