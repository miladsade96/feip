# ReactJS Interview Questions

<div style="text-align: justify">

## React Arrays and Lists:

---

**What is *key* prop and what is the benefit of using it in arrays of elements?**  
The key prop is a special string attribute you need to include when rendering lists of elements in React.
Some benefits of using keys with arrays of elements:
- It helps React identify which items have changed, been added or removed.
- Keys should be given to the elements inside an array to give them a stable identity.
- Helps React optimize performance by recycling existing DOM elements rather than recreating them.
- Required when extracting list items as components to keep track of item identity.
```jsx
const todoItems = todos.map(item => 
  <TodoItem key={item.id} item={item}/>
)
```
</div>
