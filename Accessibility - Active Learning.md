## Semantic HTML 
Semantic HTML helps screen readers and other assistive tech get useful info on the structure of a website.
### Semantic Tags
- use only __one__ `h1` heading per page
- do not skip heading levels
- user elements like `header`, `nav`, `main`, `section`, `article` etc to structure pages (instead of putting everything into a `div`)
## ARIA
- __ARIA__ is short for **A**ccessible **R**ich **I**nternet **A**pplications. A set of attributes and roles that help make websites more accessible
### ARIA Roles 
ARIA roles are attributes that can be added to an HTML element and give semantic meaning to those elements. There are __six different categories__:
	1. __Document structure roles__ like `note` or `tooltip` describe the structure of a section of content
	2. __Widget roles__ like `slider` or `menu` describe the type of elements presented on a website
	3. __a comprehensive list of ARIA roles and their categories can be found [here](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles)__
### ARIA States and Properties
These provide specific info on elements, their state, and relationship/s to other elements. Assistive technologies like screen readers use them to present content.
__A list of ARIA states and properties can be found [here](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes)__
Two important ARIA attributes are
- `aria-label`: defines a label for an interactive element. Use it when the accessible name of an element is missing, for example, when a button contains no text but only an icon
```
<button aria-label="Close" onclick="{}">
	<svg ...><path ... /></svg>
</button>
```
- `aria-labelledby`: Identifies which element labels the element it is applied to. Some elements have a native way of referencing another element with its label. If there is no native way to reference a labelling element use the aria-labelledby attribute:
```
<nav aria-labelledby="title">
	<h2 id="title">Products</h2>
...
</nav>
```
## Accessible Forms
Forms are interactive and therefore super important when it comes to accessibility!
### Things to keep in mind when creating accessible forms
- inputs __not__ wrapped in a `<form>` element will __not__ trigger validation
- inputs __not__ wrapped in a `<form>` element will __not__ trigger any action when the `Enter` key is pressed
- all labels should/must have a corresponding `for` attributes that __matches__ the `id` attribute of the input field; labels without a `for` attribute will __not__ focus the corresponding input field when clicked
#### Accessible Form: Code Example
```
<form>
	<label for="name">Name</label>
	<input id="name" type="text" />
</form>
```

### Accessibility Quick Wins
1. Use `alt` attributions on your images! The `alt` attribute describes the content of an image. Screen readers will read the `alt` text if the image can't be displayed. This is also vital for SEO.
```
<img src="..." alt="funny looking cat" />
```
If the image cannot be found, the alt text will be displayed instead.
```
<img
	src="https://image.not.found"
	alt="An image of a cat going through papers, seemingly a bit lost"
/>
```
2. Use high contrast colors so your content is shown clearly on all devices
3. Make sure all your interactive elements have an accessible name. This is the text read out by screen readers (for example, if you have a button with an icon, make sure to add an `aria-label`to it).
4. Use plain and simple language (avoiding, it at all possible, redundancies such as "plain" and "simple").

## Resources
- [MDN: Accessibility](https://developer.mozilla.org/en-US/docs/Web/Accessibility)
- [The A11y Project: Checklist](https://www.a11yproject.com/checklist/)
- [Web Accessibility Initiative: Intro to Web Accessibility](https://www.w3.org/WAI/fundamentals/accessibility-intro/)
- [Web Accessibility for Designers](https://webaim.org/resources/designers/)
