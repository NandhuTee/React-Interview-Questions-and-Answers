# Event Handling in React

React uses a slightly different approach to event handling compared to traditional HTML and JavaScript. In React, events are synthetic events that wrap around the native browser events. These synthetic events normalize the behavior across different browsers.

## Key Differences Between Events in React and Native JavaScript

### 1. **Synthetic Events**
React wraps browser's native events in its synthetic event system. This synthetic event system provides a consistent API across different browsers and improves performance by normalizing the events.

#### Native Event:
```
html
<button onclick="handleClick()">Click Me</button>
```
#### React Event:
```
jsx
<button onClick={handleClick}>Click Me</button>
```

### 2. Event Binding
In traditional JavaScript, you manually bind event handlers using .addEventListener(). In React, you attach event handlers directly within JSX, without needing to bind them explicitly.

#### Traditional JS:
```
js
const button = document.getElementById("button");
button.addEventListener("click", handleClick);
```
#### React:
```
jsx
<button onClick={handleClick}>Click Me</button>
```

### 3. Event Handler Methods
In React, event handler functions (like onClick, onChange, etc.) are camelCased (e.g., onClick instead of onclick). This is part of React's JSX syntax.

#### Example:
```
jsx
<input type="text" onChange={handleChange} />
```
In contrast, native HTML uses lowercase event names:
```
html
<input type="text" onchange="handleChange()" />
```

