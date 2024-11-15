### 1.Conditional Rendering using if else


### js
```js
function MainComponent(props) {
    const myBool = props.myBool;
    if (myBool) {
        return <Component1/>;
    } else{
        return <Component2/>;
    }
}
```

### js to jsx

### jsx

```jsx
import React from 'react';
import Component1 from './Component1'; // Assuming you have Component1 and Component2 as separate files
import Component2 from './Component2';

function MainComponent({ myBool }) {
    return myBool ? <Component1 /> : <Component2 />;
}

export default MainComponent;

```

```jsx
import React, { useState } from "react";
import ReactDOM from "react-dom";

// Message Component
function Message({ isLoggedIn }) {
	return <h1>{isLoggedIn ? "Welcome User" : "Please Login"}</h1>;
}

// Login Component
function Login({ clickFunc }) {
	return <button onClick={clickFunc}>Login</button>;
}

// Logout Component
function Logout({ clickFunc }) {
	return <button onClick={clickFunc}>Logout</button>;
}

// Parent Homepage Component
function Homepage() {
	// Using useState to manage the isLoggedIn state
	const [isLoggedIn, setIsLoggedIn] = useState(false);

	// Handler functions for login and logout
	const ifLoginClicked = () => setIsLoggedIn(true);
	const ifLogoutClicked = () => setIsLoggedIn(false);

	return (
		<div>
			<Message isLoggedIn={isLoggedIn} />
			{isLoggedIn ? (
				<Logout clickFunc={ifLogoutClicked} />
			) : (
				<Login clickFunc={ifLoginClicked} />
			)}
		</div>
	);
}

ReactDOM.render(<Homepage />, document.getElementById("root"));
```

### 2. Conditional Rendering using logical && operator

```jsx
import React from 'react';
import ReactDOM from 'react-dom';

// Example Component
function Example(){
	const counter = 5;
	return(<div>
			{
				(counter==5) &&
				<h1>Hello World!</h1>
			}
		</div>
		);
}
ReactDOM.render(
	<Example />, 
	document.getElementById('root')
);
```



