## React

JSX- Javascript Syntax Extension

JSX stands for JavaScript XML.

JSX combines HTML and JavaScript, allowing you to embed JavaScript objects within HTML elements.

```jsx
const name = "GeekforGeeks";
const ele = <h1>Welcome to {name}</h1>;
```

React was invented by Facebook developers who found the traditional DOM slow. By implementing a virtual DOM, React addressed this issue and gained popularity rapidly.

The current stable version of ReactJS is 18.2.0, released on June 14, 2022.


### virtual DOM

The DOM (Document Object Model) represents the structure of a web page, and it can be slow to update directly, especially when changes are frequent or involve complex elements.
To make this process more efficient, the Virtual DOM was introduced as a lightweight, in-memory representation of the actual DOM.

1. Virtual Representation: When there’s a change in the data or state of a component, a new virtual DOM tree is created that represents the updated UI.

2. Diffing: The virtual DOM then compares (or "diffs") this new virtual tree with the previous version to identify what has changed.

3. Minimal Updates: Based on this comparison, only the parts of the real DOM that need updating are modified, rather than re-rendering (Rendering takes the abstract instructions and layouts defined in the code and turns them into a visible web page.)the entire DOM tree.

4. Efficiency: This selective updating reduces the time-consuming DOM operations, making the UI updates faster and more efficient.

React follows **one-way data binding**, where data flows from parent components to child components.

**Component-based** architecture contribute to better performance. React divides web pages into reusable and immutable components.

### props

Props are used to pass data from a parent component to a child component. 
They are a way to make components reusable by allowing them to receive different values based on their usage.
Props are read-only and cannot be modified by the child component that receives them. This ensures that data flows in a single direction (from parent to child).

```jsx
function Greeting(props) {
  return <h1>Hello, {props.name}!</h1>;
}

// Usage in parent component
<Greeting name="Alice" />  // Displays: Hello, Alice!

```

### state

State is a data structure that allows a component to maintain and manage its own data internally. Unlike props, state is mutable, meaning it can be changed within the component.
```jsx
import React, { useState } from 'react';

function Counter() {
  // Initialize state with useState
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={() => setCount(count + 1)}>Increment</button>
    </div>
  );
}
```

**Expression** 

As JSX is an expression, we can use it inside of if statements and for loops, assign it to variables, accept it as arguments, or return it from functions.

To embed any JavaScript expression in a piece of code written in JSX we will have to wrap that expression in **curly braces {}.**

**Attributes**

JSX allows us to use attributes with the HTML elements just like we do with normal HTML. But instead of the normal naming convention of HTML, JSX uses the camelcase convention for attributes.

 JSX will throw an error if the HTML is not correct or if there are multiple child elements without a parent element.

 Comments in JSX begin with /* and ends with */.

 Close all the tags: <img/>

   
