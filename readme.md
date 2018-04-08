# react-prop-logger

## APIs
#### logProps
HOC ```logProps```, log props in lifecycle methods.

```jsx
// only componentDidMount
@logProps('componentDidMount')
class App extends Component {...}

// componentDidMount and componentDidUpdate
@logProps([
  'componentDidMount',
  'componentDidUpdate',
])
class App extends Component {...}

// except for shouldComponentUpdate and componentWillUnmount
@logProps({
  shouldComponentUpdate: false,
  componentWillUnmount: false
})
class App extends Component {...}
```

#### log
normal property descriptor ```log``` to intercept a function.

```jsx
// log all args
@log()
shouldComponentUpdate (nextProps) {...}

// log partial
@log((nextProps, nextState) => { console.log(nextState.name) })
shouldComponentUpdate (nextProps, nextState) {...}
```
