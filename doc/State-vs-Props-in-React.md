# Difference Between State and Props in React

React provides **State** and **Props** as two key concepts to manage data and behavior in components. Here's a detailed comparison:

| Feature               | State                                            | Props                                            |
|-----------------------|-------------------------------------------------|-------------------------------------------------|
| **Definition**        | State is a built-in object used to store component data that can change over time. | Props are short for "properties" and are used to pass data from a parent component to a child component. |
| **Mutability**        | State is mutable, meaning it can be updated using `setState` or hooks like `useState`. | Props are immutable, meaning they cannot be changed by the child component. |
| **Ownership**         | State is owned and managed locally by the component. | Props are received from the parent component. |
| **Usage**             | Used for managing dynamic data within the component. | Used for passing static or dynamic data and callback functions to child components. |
| **Updates**           | State changes trigger a re-render of the component. | Props changes trigger a re-render in the child component. |
| **Access**            | Accessed using `this.state` (class components) or `[state, setState]` (functional components). | Accessed using `this.props` (class components) or directly as function arguments in functional components. |
| **Scope**             | Limited to the component in which it is defined. | Passed from parent to child components. |
| **Modification**      | Modified using `this.setState` (class) or `setState` (hooks). | Cannot be modified directly; new props must be passed down from the parent. |

## Example of State
```jsx
import React, { useState } from 'react';

function Counter() {
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={() => setCount(count + 1)}>Increment</button>
    </div>
  );
}

export default Counter;
```

## Example of Props
```jsx
function Greeting({ name }) {
  return <h1>Hello, {name}!</h1>;
}

function App() {
  return <Greeting name="John" />;
}

export default App;
```

### Key Takeaways
- **State** is best suited for data that is local and subject to change within a component.
- **Props** are for passing data and functions between components to establish communication.

By understanding the differences, you can manage your React application's data flow effectively.
