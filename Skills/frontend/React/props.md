## Props

Props in React are the objects used to pass data/information to a Component. It is short for Properties. 
It is responsible for passing the data to components and render the dynamic content.


```// Accessing props in class components
this.props.propName;

// Accessing props in functional components 
props.propName;
```

### Props drilling

 Prop drilling is basically a situation when the same data is being sent at almost every level due to requirements in the final level.

 code complexity, reduced maintainability, performance overhead, decreased component reusability, increased development.

```jsx
//without_useContext.js

import React, { useState } from "react";

function Parent() {
    const [fName, setfName] = useState("firstName");
    const [lName, setlName] = useState("LastName");
    return (
        <>
            <div>This is a Parent component</div>
            <br />
            <ChildA fName={fName} lName={lName} />
        </>
    );
}

function ChildA({ fName, lName }) {
    return (
        <>
            This is ChildA Component.
            <br />
            <ChildB fName={fName} lName={lName} />
        </>
    );
}

function ChildB({ fName, lName }) {
    return (
        <>
            This is ChildB Component.
            <br />
            <ChildC fName={fName} lName={lName} />
        </>
    );
}

function ChildC({ fName, lName }) {
    return (
        <>
            This is ChildC component.
            <br />
            <h3> Data from Parent component is as follows:</h3>
            <h4>{fName}</h4>
            <h4>{lName}</h4>
        </>
    );
}

export default Parent;
```

The problem with Prop Drilling is that whenever data from the Parent component will be needed, it would have to come from each level, Regardless of the fact that it is not needed there and simply needed in last.
Prop drilling can complicate your component structure.

### useContext hook
A better alternative to this is using useContext hook. The useContext hook is based on Context API and works on the mechanism of Provider and Consumer.

Provider needs to wrap components inside Provider Components in which data have to be consumed. Then in those components, using the useContext hook that data needs to be consumed.

```jsx
//with_useContext.js

import React, { useState, useContext } from "react";

let context = React.createContext(null);
function Parent() {
    const [fName, setfName] = useState("firstName");
    const [lName, setlName] = useState("LastName");
    return (
        <context.Provider value={{ fName, lName }}>
            <div>This is a Parent component</div>
            <br />
            <ChildA />
        </context.Provider>
    );
}

function ChildA() {
    return (
        <>
            This is ChildA Component.
            <br />
            <ChildB />
        </>
    );
}

function ChildB() {
    return (
        <>
            This is ChildB Component.
            <br />
            <ChildC />
        </>
    );
}

function ChildC() {
    const { fName, lName } = useContext(context);
    return (
        <>
            This is ChildC component.
            <br />
            <h3> Data from Parent component is as follows:</h3>
            <h4>{fName}</h4>
            <h4>{lName}</h4>
        </>
    );
}

export default Parent;

```

### List

React Lists are used to display a collection of similar data items like an array of objects and menu items. It allows us to dynamically render the array elements and display repetitive data.

```jsx
const numbers = [1, 2, 3, 4, 5];

const updatedNums = numbers.map((number) => {
    return <li>{number}</li>; // This function is called for each number in the array.
});

```

### keys

They help React identify which items have changed, are added, or are removed. Providing a unique key for each list item significantly improves performance and avoids potential bugs.

```jsx
const items = [{ id: 1, name: 'Item 1' }, { id: 2, name: 'Item 2' }];

function ItemList({ items }) {
    return (
        <ul>
            {items.map((item) => (
                <li key={item.id}>{item.name}</li>
            ))}
        </ul>
    );
}

```

When rendering a list of items in React using ``map()`` or any iteration method, you need to provide a key for each item.

Keys are used internally by React to keep track of elements in the list, so if the list changes (e.g., an item is added or removed), React can update only the necessary parts of the DOM.
