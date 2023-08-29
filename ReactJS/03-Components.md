# ReactJS Interview Questions

<div style="text-align: justify">

## React Components:

---

**How to create components in React?**  
There are two main ways to create components in React:
- **Function components**: Function components are simple JavaScript functions that accept props and return JSX
```jsx
function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}
```
- **Class components**: Class components are ES6 classes that extend React.Component and render JSX in their render method
```jsx
class Welcome extends React.Component {
  render() {
    return <h1>Hello, {this.props.name}</h1>;
  }
}
```

---

**When to use a class component over a function component?**  
Class components were used before React 16.8. They exist because they are necessary. Nowadays, most projects
done with React use Functional components as hooks have made everything easier, and the code is leaner and
more flexible. Yet, there are cases where we need to use Class components; for example when we’re required to
build an Error Boundary, or the team we joined has a project that has not migrated to React 16.8.
</div>
