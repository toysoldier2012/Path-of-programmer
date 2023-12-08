
# QCM

### [Redux] mapStateToProps
Language knowledge (60 pts)

Which of the following statements are correct with respect to the following code snippet?  
  
![](https://static.codingame.com/work/servlet/fileservlet?id=16025763570944)  
  
_Multiple correct answers expected._

- The call to the `connect` function returns a higher order component which wraps the TodoApp component
- `state.todos` from the store is made available as `props.todos` inside TodoApp
- `props.todos` from TodoApp are made available to the store via `mapStateToProps`
- `mapStateToProps` maps the component state to the component props

### useMemo hook
Language knowledge (20 pts)

```jsx
const value = useMemo(() => {
    // A
}, [valueOne, valueTwo]);
```

When will instruction `A` be guaranteed to be executed? 

- Whenever the component updates
- On the first render
- When `valueOne` changes
- When both `valueOne` and `valueTwo` change

### React lifecycle events
Language knowledge (60 pts)

Which lifecycle hook is called **just before** non-inital **`render()`** in a React component?

- componentWillMount()
- componentWillReceiveProps()
- componentWillUpdate()
- shouldComponentUpdate()

### Rendering lists
Language knowledge (40 pts)

Consider the code below.  
  
Which of the following should be the correct code in place of `XXX`  
  
![](https://static.codingame.com/work/servlet/fileservlet?id=16025717476248)  
  
in order to have this output?  
  
![](https://static.codingame.com/work/servlet/fileservlet?id=16025722398487)

- 
```javascript
<li key={fruit.foo}>{fruit.value}</li>
```

- 
```javascript
<li>{fruit.value}</li>
```

- 
```javascript
<li key={fruit.bar}>{fruit.value}</li>
```

- 
```javascript
<li key={fruit.value}>{fruit.foo}</li>
```

### Conditional rendering
Language knowledge (40 pts)

Consider the following stateless functional component.  What will be rendered inside the DOM element with the id `container` when the following snippet is run?

```jsx
import React from 'react';
import ReactDOM from 'react-dom';

function WarningBanner(props) {
  if (!props.warn) {
    return null;
  }

  return (
    <div className="warning">
      Warning!
    </div>
  );
};

ReactDOM.render(
  <WarningBanner warn />,
  document.getElementById('container')
);
```

- Nothing will be rendered because the value of `props.warn` is not supplied
- "Warning!" will be rendered inside the container
- This code will throw a syntax error because a value for the `warn` prop is not supplied
- "null" will be rendered inside the container

### Lifecycle: shouldComponentUpdate
Language knowledge (40 pts)

Which of the following behaviors is expected with respect to the `shouldComponentUpdate` lifecycle method as implemented in the following React component?  
  
![](https://static.codingame.com/work/servlet/fileservlet?id=16025027500812)

- Component will not render anything
- Component will never update on change of either props or state
- Component will update on a change of state but will not update on a change of props
- Component will update on a change of props but will not update on a change of state

### [Redux] Reducer
Language knowledge (20 pts)

Consider the following reducer:  
  
![](https://static.codingame.com/work/servlet/fileservlet?id=16025595313719)  
  
What will the state of this reducer be after the following actions are dispatched:

```javascript
dispatch({ type: 'SET_FOO', foo: [1, 2] }); 
dispatch({ type: 'PUSH_FOO', foo: 3 }); 
dispatch({ type: 'PUSH_FOO', foo: 6 });
```

- 
```javascript
{ foo: [1, 1, 2, 3, 6], switch: false }
```

- 
```javascript
{ foo: [1, 2, 3, 6], switch: true }
```

- 
```javascript
{ foo: [6, 3, 1, 2], switch: true }
```

- 
```javascript
{ foo: 6, switch: false }
```

# Text

### React context to pass data

What would you use to pass data through the component tree without having to pass props manually to each level?

### [Redux] Actions

What's the name of the objects that are used to send data payloads to redux stores in order to update them?

### React props

In React, what is the object used to pass data from parent to child?





# Code
