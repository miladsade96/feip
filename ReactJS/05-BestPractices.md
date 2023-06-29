# ReactJS Interview Questions

<div style="text-align: justify">

## React Best Practices:

---

**What would be a common mistake of function being called every time the component renders?**  
A common mistake that can cause a function to be called every time the component renders is declaring the
function inside the component's render method. This can cause the function to be recreated every time the
component renders, even if the function's dependencies have not changed. To avoid this problem, function
should be declared outside the render method, or in a separate file if they are reused across multiple
components.

---

**What is the recommended way for naming the components?**  
This is to use a simple name that describes the components. The name should be a noun or noun phrase that accurately
represents component's purpose. This makes it easier to understand and maintain the code, as well as to reuse the
component in other parts of the application.

---

**What will happen if you use props in initial state?**  
Using props in initial state will cause initial state to ignore the props. Because the initial state is only set once,
when the component is first created. If you want to use props to initialize state, you should set the state in the
constructor instead.

---

**What is the impact of indexes as keys?**  
Using indexes as keys can cause issues with component's state, particularly if the order of items in the list changes.
It can also lead to issues with duplicate keys if items are added or removed from the list. It is generally recommended
to use a unique identifier as the key rather than an index.

---

**What is the recommended order of methods in component class?**  
The recommended ordering of methods in a React component class is as follows: constructor, render, lifecycle methods,
event handlers. This ordering groups related methods together and makes it easier to understand and maintain the code.

---

**Why should component names start with capital latter?**  
Because in order to distinguish them from regular HTML tags and make the code easier to read. This is a convention that
is widely used in the React community and helps developer to understand the purpose and scope of different parts of the
code.

---

**Why we need to be careful when spreading props on DOM elements?**  
It is important to be careful because it can spread invalid HTML attributes. This can cause the component to render
incorrectly or even create security vulnerabilities. It is recommended to only spread props on components that you
trust, or to manually whitelist the valid attributes.
</div>
