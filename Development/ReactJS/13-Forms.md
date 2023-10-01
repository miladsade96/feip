# ReactJS Interview Questions

<div style="text-align: justify">

## React Forms:

---

**What are uncontrolled components?**  
Uncontrolled components in React are components that maintain their own internal state. Their values are not
controlled by React. For example, this is an uncontrolled input:
```jsx
<input type="text" />
```
The input manages its own state internally, and React has no control over its value.
Some characteristics of uncontrolled components:
- They maintain their own internal state
- The state can only be updated via DOM events
- Their value is not set by React props
- Examples include native input and textarea elements
- Use refs to read their state when needed

---

**What are controlled components?**  
Controlled components in React are components that have their values controlled by React. Typically, this is done by:
1. Specifying the component's value via props
2. Updating the value via callbacks like onChange

For example, this input is a controlled component:
```jsx
function MyInput({ value, onChange }) {
  return (
    <input 
      value={value}
      onChange={onChange} 
    />
  );
}
```

The key aspects are:
- The input value is passed in via the value prop
- onChange handler updates the parent component's state
- Input is controlled through props rather than local state

Advantages of controlled components:
- Input values are predictable and trackable
- Parent maintains control over form data
- Easy to validate or sanitize input
- Can simplify complex inputs handling multiple states

</div>
