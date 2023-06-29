# ReactJS Interview Questions

<div style="text-align: justify">

## React Intermediate:

---

**How to import and export components using React and ES6?**  
In React and ES6, you can import and export components using the *import* and *export* keywords.
To import a component, you can use the *import* keyword followed by the component name and file
path. To export a component, you can use the *export* keyword before component declaration. For
example:
```javascript
import React from "react";
export class MyComponent extends React.Component {}
export function MyOtherComponent() {}
```

---

**How to get history on React Router v4?**  
In React Router v4, you can get the history object by using the *this.props.history* object passed
to the component. This object contains the current history of the router, including the current
location, previous locations and navigation history. You can use this object to programmatically
navigate, access the current URL or manage the browser history.

**How to update the component every second?**  
You can do this by using *setInterval()* function in the *componentDidMount()* lifecycle method. This
will create a timer that update the component state every second, causing the component to re-render
with the new state value. For example:


</div>