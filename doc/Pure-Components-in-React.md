# Pure Components in React

A **Pure Component** in React is a component that only re-renders when its **props** or **state** change. It implements a **shallow comparison** of the props and state to determine whether the component needs to update. If the previous and next props or state are the same, the component will not re-render, improving performance by avoiding unnecessary re-renders.

## Key Points

- **Shallow Comparison**: Pure components compare the previous and next props/state with a shallow comparison, meaning that it checks for changes in primitive values or object references. If the props or state are complex objects (e.g., arrays or objects), the component will only re-render if the reference to the object changes.
- **Automatic Optimization**: Pure components are typically used to optimize performance in React applications, especially when components have complex UI structures or are re-rendered frequently.

## Example of a Pure Component

```jsx
import React, { PureComponent } from 'react';

class MyPureComponent extends PureComponent {
  render() {
    console.log('Rendering MyPureComponent');
    return <div>{this.props.name}</div>;
  }
}

export default MyPureComponent;
```

- In this example, **MyPureComponent** will only re-render if the name prop changes. If the name prop stays the same, React will skip the render.

## PureComponent vs Regular Component:
- **PureComponent:** React automatically implements shouldComponentUpdate with a shallow comparison of props and state.
- **Regular Component:** React does not implement shouldComponentUpdate by default, which means the component re-renders on every state or prop change unless shouldComponentUpdate is explicitly defined.

## When to Use Pure Components:
- **Performance Optimization:** When you have components that render with the same inputs multiple times and you want to avoid unnecessary re-renders.
-**Component Stability:** Pure components work well when the props and state are immutable or handled carefully to avoid accidental changes to references.

## Example with Shallow Comparison:
```jsx 
class ParentComponent extends React.Component {
  state = {
    name: 'Nandini',
  };

  handleChange = () => {
    this.setState({ name: 'Nandhu' });
  };

  render() {
    return (
      <div>
        <button onClick={this.handleChange}>Change Name</button>
        <MyPureComponent name={this.state.name} />
      </div>
    );
  }
}

class MyPureComponent extends React.PureComponent {
  render() {
    console.log('Rendering MyPureComponent');
    return <div>{this.props.name}</div>;
  }
}
```
## When Not to Use Pure Components:
- **Complex Objects as Props:** If your props or state are complex objects or arrays that can change frequently, shallow comparison might not be efficient. In such cases, regular components with custom shouldComponentUpdate logic may be more suitable.

## Conclusion:
**Pure components** offer a simple way to **optimize performance** in React by preventing unnecessary renders when props or state have not changed. However, they should be used carefully with the understanding that they perform a **shallow comparison**, which may not be effective with complex or mutable data structures.