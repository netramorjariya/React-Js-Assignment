
# 📚 React State Management — Theory Exercises

---

## 📖 Context API

### ❓ Question 1: What is the Context API in React? How is it used to manage global state across multiple components?

**Answer:**  
The Context API in React is a built-in feature that allows developers to share state or data globally across multiple components without having to pass props manually through each level of the component tree.

It is used to manage global state by:
- Creating a context using `createContext()`.
- Wrapping the component tree with a `Provider` component, which holds the shared state and makes it accessible to all child components.
- Accessing the shared data in any child component using `useContext()`.

This helps avoid **prop drilling** (passing data through many intermediate components) and makes state management simpler for smaller to medium-sized React applications.

---

### ❓ Question 2: Explain how `createContext()` and `useContext()` are used in React for sharing state.

**Answer:**  
- `createContext()` is a React function that creates a Context object. It returns a **Provider** and a **Consumer** component.
- The **Provider** component is used to pass down the data (state and functions) to all the nested components.
- `useContext()` is a React Hook that allows functional components to access the current context value.

**Example:**

```jsx
import React, { createContext, useContext, useState } from 'react';

// 1️⃣ Create a context
const UserContext = createContext();

// 2️⃣ Create a provider component
function UserProvider({ children }) {
  const [user, setUser] = useState("Netra");
  return (
    <UserContext.Provider value={{ user, setUser }}>
      {children}
    </UserContext.Provider>
  );
}

// 3️⃣ Access context value using useContext in any child component
function Profile() {
  const { user } = useContext(UserContext);
  return <h1>Hello, {user}</h1>;
}
```

---

## 📖 State Management (Redux, Redux Toolkit, Recoil)

### ❓ Question 1: What is Redux, and why is it used in React applications? Explain the core concepts of actions, reducers, and the store.

**Answer:**  
**Redux** is a predictable state container for JavaScript applications, commonly used with React to manage the application state in a centralized store.

It is used because:
- It maintains a single source of truth for the application's state.
- It makes state management predictable and easier to debug.
- It improves consistency when passing data between components.

**Core Concepts:**
- **Actions**: Plain JavaScript objects that describe an event or intention to change the state. Every action must have a `type` property.
- **Reducers**: Pure functions that take the current state and an action as arguments and return a new state based on the action type.
- **Store**: A centralized object that holds the entire application state. It allows access to state, dispatching actions, and registering listeners via `subscribe()`.

**Example:**

```javascript
// Action
const increment = () => ({ type: "INCREMENT" });

// Reducer
const counter = (state = 0, action) => {
  switch (action.type) {
    case "INCREMENT":
      return state + 1;
    default:
      return state;
  }
};

// Store
import { createStore } from "redux";
const store = createStore(counter);
```

---

### ❓ Question 2: How does Recoil simplify state management in React compared to Redux?

**Answer:**  
**Recoil** is a modern state management library for React that simplifies managing both global and shared component state.

**Advantages over Redux:**
- No need for actions or reducers — state can be updated directly using setters.
- Uses **atoms** (units of state) and **selectors** (derived/computed state) for a clean and modular state structure.
- Integrates seamlessly with React's functional components and hooks.
- Less boilerplate code compared to Redux.
- Fine-grained state management — only components that use a particular atom re-render when that atom's state changes.

**Example:**

```javascript
import { atom, useRecoilState } from 'recoil';

// Create atom
const countState = atom({
  key: 'countState',
  default: 0,
});

// Use in component
function Counter() {
  const [count, setCount] = useRecoilState(countState);
  return <button onClick={() => setCount(count + 1)}>{count}</button>;
}
```

---

✅ **Summary**:  
- **Context API** is built-in and best for small to medium projects.
- **Redux** provides structured, centralized state management with strict rules.
- **Recoil** simplifies state sharing with less boilerplate, closer to React’s native behavior.

