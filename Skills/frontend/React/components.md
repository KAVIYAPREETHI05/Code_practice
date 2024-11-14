## COMPONENTS

React Components are the building blocks of ReactJS application. They help to break the user interface into smaller, reusable chunks, making the code easier to manage and maintain. 
Components can be class-based or function-based.

A React component is a JavaScript function or class that returns a React element, describing how a section of the UI (User Interface) should appear.
Components can manage their own state and receive data as props, making it possible to create reusable and dynamic UI elements.

### Types of components

- Functional Components
- Class based Components

**Functional Component**

Functional components are just like JavaScript functions that accept properties and return a React element.

```jsx
function welcome() {
    return <h1>Hello, Welcome to GeeksforGeeks!</h1>;
}
```

**Class Component**

The class components are a little more complex than the functional components. A class component can show inheritance and access data of other components.

```jsx
class Welcome extends Component {
    render() {
        return <h1>Hello, Welcome to GeeksforGeeks!</h1>;
    }
}
```

Functional Components	|Class Components
----------------------|-----------------
Defined using JavaScript functions. Example: ```jsx function MyComponent() { return <div>Text</div>;``` }	|Defined using ES6 classes extending React.Component. Example: ```jsx class MyComponent extends React.Component { render() { return <div>Text</div>; } }```
Managed with React Hooks (e.g., useState). Example: ```jsx const [count, setCount] = useState(0);``` |	Managed with ```this.state and this.setState().``` Example: ```this.state = { count: 0 };```
Uses hooks (e.g., useEffect for lifecycle events). Example: ```jsx useEffect(() => { /* logic */ }, []);```	|Has built-in lifecycle methods like ``componentDidMount``, ``componentDidUpdate``, ``componentWillUnmount``.
Simpler, more concise, easier to read and test.	|Can be more complex and harder to read, especially with extensive logic.
Performance	Initially lighter, minimal performance difference in modern React.	| Slightly heavier due to class overhead, but modern React optimizations minimize differences.
Preferred in modern React development due to simplicity and hooks.	|Less common in new projects; primarily found in legacy code.


### Rendering React Components

Rendering Components means turning your component code into the UI that users see on the screen.

The name of a component should always start with a capital letter. This is done to differentiate a component tag from an HTML tag.

**props**

Props(short for properties) are a way to pass data from the parent component to the child component.

Props are like function arguments, you can use them as attributes in components.


**Components in Components**

```jsx

import React from "react";
import ReactDOM from "react-dom";

const Greet = () => {
   return <h1>Hello Geek</h1>
}

// This is a functional component
const Welcome = () => {
    return <Greet />;
};

ReactDOM.render(
    <Welcome />,
    document.getElementById("root")
);

```

### Composing and Decomposing components

**Composing Components**

Composing components refers to the practice of building larger, more complex components by combining smaller, reusable ones. 
It allows you to create a component hierarchy where one component includes or nests others.

```js
const Header = () => <header>This is the header</header>;
const Footer = () => <footer>This is the footer</footer>;

const MainPage = () => {
    return (
        <div>
            <Header />
            <h1>Welcome to the main page</h1>
            <Footer />
        </div>
    );
}

  ```

**Decomposing Components**

 Decomposing components means breaking down a large, complex component into smaller, more manageable subcomponents.
 This is essentially the opposite of composing and is often done to improve readability, maintainability, and reusability of code.

```js
const ComplexComponent = () => {
    // Original implementation is large and hard to manage
    return (
        <div>
            <header>This is the header</header>
            <section>This is a complex section with a lot of logic</section>
            <footer>This is the footer</footer>
        </div>
    );
};

// Decomposed version
const Header = () => <header>This is the header</header>;
const Section = () => <section>This is a complex section with a lot of logic</section>;
const Footer = () => <footer>This is the footer</footer>;

const ComplexComponentDecomposed = () => {
    return (
        <div>
            <Header />
            <Section />
            <Footer />
        </div>
    );
};

```



