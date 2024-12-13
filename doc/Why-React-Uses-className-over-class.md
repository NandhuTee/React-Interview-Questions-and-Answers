# Why React Uses `className` Over `class` Attribute

## Introduction
In React, the `className` attribute is used instead of the standard `class` attribute found in HTML. This is a deliberate choice made to avoid conflicts with JavaScript keywords and ensure compatibility with the React component model.

---

## Key Reasons for Using `className`

### 1. **Avoids Reserved Keywords in JavaScript**
- The term `class` is a reserved keyword in JavaScript, used for defining classes in ES6.
- Using `class` directly as an attribute in JSX would result in syntax errors or conflicts.

### 2. **Ensures Compatibility with JSX**
- JSX is a syntax extension of JavaScript, which allows HTML-like syntax within JavaScript.
- To maintain compatibility and avoid parsing errors, React uses `className` instead of `class`.

### 3. **Semantic Consistency with Other Attributes**
- React attributes like `htmlFor` (instead of `for`) and `className` follow a pattern to differentiate between JSX attributes and DOM properties.
- This ensures consistency and avoids confusion.

### 4. **Aligns with React’s Virtual DOM**
- React’s Virtual DOM uses JavaScript objects to represent elements.
- Using `className` makes it clear that it’s a property of the object, not a direct HTML attribute.

---

## Code Comparison
### HTML Example
```html
<div class="my-class">Hello, World!</div>
```

### React Equivalent
```jsx
<div className="my-class">Hello, World!</div>
```

---

## Transition from `class` to `className`
In early versions of React, developers often mistakenly used `class` instead of `className`, leading to errors. By standardizing `className`, React provides a clear distinction and ensures JSX code adheres to JavaScript conventions.

---

## Common Pitfalls
1. **Mixing `class` and `className`**:
   - Incorrect: `<div class="my-class">...</div>`
   - Correct: `<div className="my-class">...</div>`

2. **Dynamic Class Names**:
   - Use template literals or conditional operators for dynamic class names:
     ```jsx
     <div className={`my-class ${isActive ? 'active' : ''}`}>...</div>
     ```

---

## Conclusion
The use of `className` in React is a thoughtful decision to maintain compatibility, avoid conflicts, and provide a seamless development experience. By adhering to this convention, developers can ensure their code is robust, error-free, and aligned with modern JavaScript practices.

