## HOOKS

In React, hooks are special functions that allow developers to use state and other React features in functional components. 

Hooks cannot be used with class components.

They were introduced in React 16.8 to simplify state management, lifecycle methods, and side-effect handling, without the need for class components.

### Types of Hooks

**1. React State Hooks**

State Hooks stores and provide access to the information. To add state in Components we use:

**useState Hook:** useState Hooks provides state variable with direct update access.

**useReducer Hook:** useReducer Hook provides a state variable along with the update logic in reducer function.

``const [count, setCount] = useState(0)``

**2. React Context Hooks**

Context hooks make it possible to access the information without being passed as a prop.

**useContext Hooks:** shares the data as a global data with passing down props in component tree. It reduces the use of props drilling.

``const context = useContext(myContext);``

**3. React Ref Hooks**
Refs creates the variable containing the information not used for rendering e.g. DOM nodes.

**useRef:** Declares a reference to the DOM elements mostly a DOM Node.

**useImperativeHandle:** It is an additional hook that declares a customizable reference

``const textRef = useRef(null);
``

**4. React Effect Hooks**

Effects connect the components and make it sync with the system. It includes changes in browser DOM, networks and other libraries.

**useEffect:** useEffect Hook connects the components to external system

**useLayoutEffect:** used to measure the layout, fires when the screen rerenders.

**useInsertionEffect:** used to insert the CSS dynamically, fires before the changes made to DOM.

``useEffect(()->{
    // Code to be executed
}, [dependencies] ``
  
 

 **5. React Performance Hooks:**

Performace hooks are a way to skip the unnecessary work and optimise the rendering preformance.

**useMemo:** return a memoized value reducing unnecessary computations.

**useCallback:** returns a memoized callback that changes if the dependencies are changed.

``const memoizedValue = useMemo(functionThatReturnsValue, arrayDependencies)``

**Additional hooks**

**useTransition:** enables us to specify which state changes are critical or urgent and which are not.

**useDefferedValue:** allows you to postpone the rendering of a component until a specific condition is met.

**useDebugValue:** To display a label in React DevTools for custom hooks.

**useId:** To generate unique IDs for accessibility attributes like id and aria-*.

**useSyncExternalStore:** For subscribing to external stores and ensuring compatibility with concurrent rendering.

*React developers note that classes lack efficiency and may hinder hot reloading reliability, a concern Hooks address effectively*

(Hot reloading is a mechanism where changes to the code (e.g., updates to components, styles, or state logic) are applied in the browser without requiring a full page reload.)


Class Components	|React Hooks
------------------|-------------
``this.state`` and lifecycle methods|	``useState`` and ``useEffect``
Spread across methods, can be complex	|Smaller, focused functions
Difficult to reuse logic	|Easy to create and reuse custom hooks
Familiar to OOP developers|	Requires different mindset than classes
Supported|	Not currently supported
Some libraries rely on them	|May not all be compatible yet
