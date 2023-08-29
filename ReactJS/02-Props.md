# ReactJS Interview Questions

<div style="text-align: justify">

## React Props:

---

**What are props in React?**  
Props (properties) in React allow you to pass data from a parent component down to a child component.
Some key characteristics of props:
- They are passed to components similar to function parameters.
- They are immutable in the child component.
- They can only be passed from parent to child, not the other way.
- The child component receives them as a props object parameter.
```jsx
// Parent component
<ChildComponent name="John" age={12} />

// Child component receives props
const ChildComponent = (props) => {
  return <p>{props.name} is {props.age}</p> 
}
```
</div>
