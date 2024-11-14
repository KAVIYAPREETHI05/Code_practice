### 1.Conditional Rendering using if else

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

### 2. Conditional Rendering using logical && operator
