## Life Cycle

The React lifecycle is divided into three main phases:

1.**Initialization phase**: This is the stage where the component is constructed with the given Props and default state. This is done in the constructor of a Component Class.

2.**Mounting Phase**: This phase begins when a component is created and inserted into the DOM.

 - constructor
 - static getDerivedStateProps
 - render()
 - componentDidMount()

3.**Updating Phase**: This occurs when a component is re-rendered due to changes in props or state.

  - getDerivedStateFromProps
  - setState() Function
  - shouldComponentUpdate()
  - getSnapshotBeforeUpdate() Method
  - componentDidUpdate()

4.**Unmounting Phase**: This is the final phase when a component is removed from the DOM.

  - componentWillUnmount() Function

![image](https://github.com/user-attachments/assets/809627f6-d2e3-4543-a0f5-d6cacf560da3)

