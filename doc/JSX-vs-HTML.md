# JSX vs HTML: Understanding the Differences and How JSX is Processed

## What is JSX?

JSX (JavaScript XML) is a syntax extension for JavaScript, primarily used in React to describe what the UI should look like. It allows developers to write HTML-like code within JavaScript, making it more readable and easier to visualize the component structure of a React app.

JSX is not a string or an HTML document but rather a syntax that gets transformed into JavaScript function calls.

### Example of JSX:

```jsx
const element = <h1>Hello, World!</h1>;
```
In this example, the JSX code looks like HTML, but it's actually JavaScript that will be processed by a React app.

### How JSX is Different from HTML
## Syntax:

  **JSX:** JSX allows embedding expressions in curly braces {}. For instance, variables, functions, or even JavaScript expressions can be embedded inside JSX tags.
  
```jsx
const name = 'John';
const element = <h1>Hello, {name}!</h1>;
```
 **HTML:** In HTML, you can't directly embed JavaScript expressions inside elements.


## Attributes:
**JSX:** JSX uses camelCase for attribute names. For example, instead of class, you use className in JSX to avoid conflicts with JavaScript’s class keyword.

```jsx
<div className="container">Content</div>
```

**HTML:** In HTML, you use class to define a CSS class.

```html
<div class="container">Content</div>
```

## Self-Closing Tags:

**JSX:** In JSX, elements like
 ```html <img />, <input />, and <br /> ```
  must be self-closed. This is due to the fact that JSX is an XML-like syntax.

```jsx
<img src="image.jpg" alt="Image" />
```

**HTML:** In HTML, some elements are allowed to be self-closed, but it's not mandatory. For example, <img> and <br> tags in HTML are often written without the closing slash.

```html
<img src="image.jpg" alt="Image">
```

## Event Handling:

**JSX:** Event handlers in JSX are written in camelCase, and the value is usually a function.
```jsx
<button onClick={handleClick}>Click me</button>
```

**HTML:** In HTML, event handlers are written in lowercase, and they usually refer to strings of JavaScript code.

```html

<button onclick="handleClick()">Click me</button>
```
## Conditionals and Loops:

**JSX:** JSX allows embedding JavaScript logic like conditional statements or loops directly within the code using expressions.
```jsx

const isLoggedIn = true;
const message = isLoggedIn ? <h1>Welcome back!</h1> : <h1>Please log in.</h1>;
```
- **HTML:** In HTML, you can't directly use JavaScript logic inside the markup.
HTML Entities.
- **JSX:** JSX automatically converts special characters like & and < into their corresponding HTML entities, but this needs to be handled explicitly if they are used as JavaScript expressions.
HTML: In HTML, special characters like &, <, and > are automatically recognized as entities.

### How Browser Understands JSX
**JSX:**is not directly understood by browsers. It must first be transpiled into regular JavaScript code before it can be executed in the browser. This is typically done using tools like Babel.

### Steps for JSX Transformation:
**Babel:** JSX is processed by Babel, a JavaScript compiler, that converts JSX syntax into JavaScript React.createElement() calls.

For example, this JSX:

```jsx

<h1>Hello, World!</h1>
```

Gets transpiled to:

```javascript

React.createElement('h1', null, 'Hello, World!');
```

- **Browser:** After JSX is transpiled into regular JavaScript, the browser can interpret it as usual and render the components to the DOM.

### Transpilation Example:
If you write the following JSX code:

```jsx
const element = <h1>Hello, World!</h1>;
It is transpiled by Babel into:
```

```javascript
const element = React.createElement('h1', null, 'Hello, World!');
```

The browser can then execute this code and render it into the DOM as expected.

## Summary
### Feature	JSX	HTML
- _SyntaxHTML_ - syntax inside JavaScript	Markup language used in web pages
- Attributes	camelCase (e.g., className, htmlFor)	Lowercase (e.g., class, for)
-*Embedding JavaScript*	Allows embedding expressions inside {}	Not directly possible
- *Self-Closing Tags*	Must self-close ```html (<img />, <input />)```	Optional self-closing tags
-*Event Handling*	camelCase (onClick, onChange)	Lowercase (onclick, onchange)
-Conditional Rendering	Can use JavaScript logic ```js (if, ? :)```	Cannot directly embed JavaScript logic

## Conclusion
JSX is a powerful extension to JavaScript, enabling developers to write UI elements in a more declarative and readable way. While it may look like HTML, JSX is actually transformed into JavaScript by a compiler like Babel before being rendered in the browser. Understanding the differences between JSX and HTML is important for React developers to effectively leverage JSX for building dynamic user interfaces.







