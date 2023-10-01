# ReactJS Interview Questions

<div style="text-align: justify">

## React State:

---

**Why shouldn't we update the state directly?**  
In React the state should not be updated directly because it can cause the component to re-render
improperly. Instead, the setState() method should be used to update state, which triggers a re-render
of the component and ensures that the updated state is properly reflected in the UI.

---

**What is state in React?**  
In React, state refers to a component's internal data that can change over time. State is managed using
the setState method, which allows developers to update the state of a component and trigger a re-render
of the UI. State is used to keep track of data that changes in response to user input or other events.

---

**What is the purpose of the callback function as an argument of setState?**  
The callback function as an argument of the setState method in React is used to update the state
asynchronously. When the setState() method is called, the state update may not happen immediately, which
can cause issues when trying to access to updated state. The callback function is called after the state
has been updated, ensuring that the updated state is available to use.
</div>
