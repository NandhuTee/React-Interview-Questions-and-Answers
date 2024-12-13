# What are props in React?

- In React, **props (short for "properties")** are a way to pass data from a parent component to a child component. Props are read-only, meaning they cannot be modified by the child component, and they allow components to be dynamic and reusable by providing different values.

## Key Points about Props:

- **Data Flow:** Props are passed down from a parent component to a child component.
- **Immutability:** Props cannot be changed by the child component. The child can only access the props and render them.
- **Dynamic Components:** By using props, the parent component can pass dynamic values to child components, enabling the creation of flexible and reusable components.
- **Type:** Props can be any type of data: strings, numbers, objects, arrays, functions, and even other React components.
  
### Example:
```jsx


import React from 'react';

// Parent Component
function ParentComponent() {
  return <ChildComponent name="Alice" age={25} />;
}

// Child Component
function ChildComponent(props) {
  return (
    <div>
      <h1>Hello, {props.name}!</h1>
      <p>You are {props.age} years old.</p>
    </div>
  );
}

export default ParentComponent;

```
In the example above:
- The **ParentComponent** passes name and age as props to the ChildComponent.
- The **ChildComponent** receives these props via the props object and renders the data.

## Prop Types (Optional):
You can use PropTypes to define the expected type of props, helping with debugging and type-checking.
```jsx
import PropTypes from 'prop-types';

function ChildComponent({ name, age }) {
  return (
    <div>
      <h1>Hello, {name}!</h1>
      <p>You are {age} years old.</p>
    </div>
  );
}

ChildComponent.propTypes = {
  name: PropTypes.string.isRequired,
  age: PropTypes.number.isRequired,
};
```
## In summary:
- Props are the mechanism for *passing data to child components*.
- They make components *reusable* and dynamic by providing different inputs.
- Props are *immutable* once set, meaning they should only be modified in the parent component.
