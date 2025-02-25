## Question 1: What is React.js? How is it different from other JavaScript frameworks and libraries?

### Ans :

**React** :

- It is a JavaScript library created by FaceBook.
- Use for Building user interface, particularly for single page application.
- IT is component base and allows developers to create reusable UI component.
- React.js is faster as compare to JavaScript.
- React allows you to write HTML-like code in JavaScript, making it easier to design UIs directly in the logic.
- React create a virtual DOM in memory and reload a part that updated.

**Different from other JavaScript frameworks and libraries?**
React is a library not a full-fledged framework focused on building UI. Its flexibility, performance, and large ecosystem make it ideal for applications where you want complete control over how things work, unlike frameworks like Angular or Vue, which are more opinionated.

## Question 2: Explain the core principles of React such as the virtual DOM and component based architecture.

### Ans : **Core principle of React**

1. **Virtual DOM :** The Virtual DOM is a lightweight , in memory representation of the real DOM (Document Object Model). React uses this to optimize updates to the UI.
   **How it work**
   When the state or data of a React component changes React creates a new Virtual DOM tree.
   It compares this new Virtual DOM with the previous one using a process called reconciliation.
   React determines the minimal set of changes (called diffing) and updates only the affected parts of the real DOM.

2. **Component based Architecture :** React applications are built using components, which are reusable and self-contained pieces of UI.
   **How it work**
   Reusability: Components can be reused throughout the application, reducing redundancy.
   Encapsulation: Each component manages its own state and behavior, making the application modular.
   Hierarchical Structure: Components can be nested, creating a tree-like structure. For example, a "Header" component might contain a "Logo" and "Navigation" component.

## Question 3: What are the advantages of using React.js in web development?

### Ans :

React.js is a powerful library that has become one of the most popular tools for building modern, interactive, and scalable web applications. Its advantages make it a go-to choice for developers

1. Component-Based Architecture
2. Virtual DOM for High Performance
3. Declarative UI
4. Rich Ecosystem and Tooling
5. Easy Integration with Existing Projects
6. React Hooks
7. SEO-Friendliness
8. Strong Community and Ecosystem
9. JSX for Intuitive Development
10. Flexible and Scalable

# COMPONENT

## Question 1: What are components in React? Explain the difference between functional components and class components.

### Ans :

Components are independent and reusable bits of code. They serve the same purpose as JavaScript functions, but work in isolation and return HTML.
Components are in two types, Class components and Function components.

#### Difference between Class component & Function component

**Class component:**

- In class ES6 class based structure that extends React.component
- Use this.state and setState management.
- Slightly heavier because of (this) binding and more boilerplate

**Function component:**

- In function component we use simple js function.
- Use the useState and useReducer hooks for state management.
- Lightweight and more performant for pre-hooks and lack state

## Question 2: How do you pass data to a component using props?

### Ans:

Passing data to a component using props is one of the key concepts in react.

- Define Props in the parent component :
  When render a child component, pass the data as an attribute of the child component, these attributes are props (properties).
- Access Props in the child component:
  The child component receives the props object, which contain the data from the parent. You can access the specific values through this object.
  **Example**

```jsx
// Parent Component
function ParentComponent() {
  const message = "Hello everyone";
  return <ChildComponent greeting={message} />;
}

// Child Component
function ChildComponent(props) {
  return <h1>{props.greeting}</h1>;
}
```

## Question 3: What is the role of render() in class components?

### Ans:

React renders HTML to the web page by using a function called render(). The purpose of the function is to display the specified HTML code inside the specified HTML element. In the render() method, we can read props and state and return our JSX (JavaScript XML) code to the root component of our app.
**Example**

```jsx
import React, { Component } from "react";

class Welcome extends Component {
  render() {
    return (
      <div>
        <h1>Welcome, {this.props.name}!</h1>
      </div>
    );
  }
}

export default Welcome;
```

# JSX (JavaScript XML)

## Question 1: What is JSX in React.js? Why is it used?

### Ans :

JSX (JavaScript XML) is a syntax extension for JavaScript that looks similar to HTML. It allows developers to write HTML-like code directly within JavaScript files. JSX is then transformed into React.createElement() calls, which React uses to create Virtual DOM elements.

**Why is it used**
Improved Readability and Developer Experience: Writing UI components in a syntax that closely resembles HTML makes the code easier to understand and maintain.

Combines UI and Logic: JSX allows developers to describe how the UI should look (HTML-like structure) and include dynamic logic (JavaScript expressions) in one place.

Component-Based Architecture: JSX makes it easier to define and compose React components, enabling better modularity.

Better Integration with Tools: JSX integrates seamlessly with tools like linters and debuggers, improving developer productivity.

**Advantages of JSX**
Readable and Intuitive: Familiar HTML-like syntax.
Dynamic Rendering: Supports embedding JavaScript expressions.
Error Prevention: Catch errors early during development.

## Question 2: How is JSX different from regular JavaScript? Can you write JavaScript insideJSX?

### Ans :

**JSX different from regular JavaScript**
JSX is not regular JavaScript it's a syntax extension that lets you write HTML-like code within JavaScript.

1. Syntax
   JSX Looks like HTML but is written within JavaScript & JavaScript is Pure JavaScript uses functions or objects to represent elements.
2. Transpilation
   JSX is not executable by browsers directly. Tools like Babel transpile it into regular JavaScript using React.createElement() calls.
3. HTML-Like Syntax
   JSX allows mixing of JavaScript and HTML-like elements, which regular JavaScript doesn't.

**Can You Write JavaScript Inside JSX**
Yes, we can write JavaScript expressions inside JSX by enclosing them in curly braces {}. This is one of JSX's most powerful features!

## Question 3: Discuss the importance of using curly braces {} in JSX expressions.

### Ans :

Without {}, JSX would not support dynamic or reactive content. Curly braces allow you to insert live data, making UIs interactive.
Curly braces are used to insert JavaScript variables or expressions into JSX. Without {}, JSX would treat everything as plain text.
Curly braces allow you to include conditional logic in JSX using expressions like ternary operators
You can invoke JavaScript functions and insert the returned value into JSX.
Curly braces enable rendering lists dynamically by using .map() to iterate over an array.
You can pass JavaScript objects to style components dynamically using curly braces.

# PROPS & STATE

## Question 1: What are props in React.js? How are props different from state?

### Ans:

In react props are properties to pass data from parent component to child component. Props allow components to be dynamic and reusable by enabling the parent component to supply data that the child component can access.
**difference in Props & State**

_Props_ :

- immutable can't change the values
- Passed down from parent to child
- Can only updated by parent

_State_ :

- mutable can change the values
- managed within the component itself
- Can be updated by component itself

## Question 2: Explain the concept of state in React and how it is used to manage component data.

### Ans:

In React, state is an essential concept used to manage the data that changes over time within a component. Unlike props (which are passed from parent to child components), state is local to the component and can be changed by that component itself.

- Initialization: State is initialized using the useState() hook in functional components or within the constructor in class components.
- Updating State: State is updated using the setState() for class components or the function returned by useState() in functional components.
- Re-rendering: When state is updated, React automatically re-renders the component, ensuring that the UI reflects the new state values.

## Question 3: Why is this.setState() used in class components, and how does it work?

### Ans:

In React, this.setState() is used in class components to update the component's state. It is a built-in method that allows you to modify the state and trigger a re-render of the component to reflect the updated state in the UI.

You call this.setState() with an object or function that contains the updated state values. React then merges the updated values with the existing state. After the state is updated, React triggers a re-render of the component. The updated state is used to re-render the component’s UI with the new data. React batches multiple this.setState() calls and processes them together, ensuring that the component is not unnecessarily re-rendered multiple times.
**Example**

```jsx
this.setState({ key: value });
```

# Routing in React (React Router)

## Question 1: What is React Router? How does it handle routing in single-page applications?

### Ans :

React Router is a popular library in the React ecosystem used for handling routing in single-page applications. It enables you to define multiple routes in your application and navigate between them seamlessly without requiring a full page reload.

- How This Works :
- Navigation: Clicking on links updates the URL without a page reload from / to /about. Rendering: The Routes component matches the current path (/about) to the defined routes and renders the corresponding component
  (About).
- Seamless Experience: The application updates dynamically without refreshing the page, giving the illusion of moving between "pages."

## Question 2: Explain the difference between BrowserRouter, Route, Link, and Switch components in React Router.

### Ans :

- BrowserRouter : Wraps the app to enable routing
  Provides the context for routing using the History API. All routing components must be inside it.

- Route : Defines a route and its corresponding component
  Renders the specified component if the URL matches the route's path.

- Link : Creates navigation links
  Updates the URL without reloading the page, triggering the rendering of the associated route.

- Switch (or Routes) : Ensures only one matching route is rendered
  Renders the first route that matches the URL. Replaced by Routes in React Router v6.

# Conditional Rendering

## Question 1: What is conditional rendering in React? How can you conditionally render elements in a React component?

### Ans :

Conditional rendering in React means displaying elements or components based on certain conditions. You can achieve this in several ways:

- Using if Statements:

```jsx
if (condition) {
  return <ComponentA />;
} else {
  return <ComponentB />;
}
```

- Using switch Statements (for multiple conditions):

```jsx
switch (condition) {
  case "value1":
    return <ComponentA />;
  case "value2":
    return <ComponentB />;
  default:
    return <DefaultComponent />;
}
```

## Question 2: Explain how if-else, ternary operators, and && (logical AND) are used in JSXfor conditional rendering.

### Ans :

Conditional Rendering in JSX:

- Ternary Operator : Inline rendering for simpler conditions.

```jsx
function Example() {
  return isLoggedIn ? <h1>Welcome Back!</h1> : <h1>Please Log In</h1>;
}
```

- Using if Statements: Used outside JSX for handling conditional logic before returning the JSX.

```jsx
if (condition) {
  return <ComponentA />;
} else {
  return <ComponentB />;
}
```

- Logical && : Renders an element only when the condition is true.

```jsx
function Example() {
  return isLoggedIn && <h1>Welcome Back!</h1>;
}
```

- Using switch Statements (for multiple conditions):

```jsx
switch (condition) {
  case "value1":
    return <ComponentA />;
  case "value2":
    return <ComponentB />;
  default:
    return <DefaultComponent />;
}
```

# Lists and Keys

## Question 1: How do you render a list of items in React? Why is it important to use keys when rendering lists?

### Ans :

You can render a list using the map() method:

```jsx
const items = ["A", "B", "C"];
return (
  <ul>
    {items.map((item, index) => (
      <li key={index}>{item}</li>
    ))}
  </ul>
);
```

- Importance of Keys:
  1. Uniqueness: Keys help React identify and track items in the list.
  2. Efficient Updates: They allow React to optimize rendering by only updating the changed items instead of re-rendering the entire list.
  3. Avoid Bugs: Without unique keys, the app's behavior may be unpredictable.

## Question 2: What are keys in React, and what happens if you do not provide a unique key?

### Ans :

- Keys in React:
  Keys are unique identifiers used by React to track and manage list items during rendering. They help React efficiently update the DOM by identifying which items have changed, added, or removed.
  - What Happens Without Unique Keys

1. Performance Issues: React re-renders the entire list instead of only updating the necessary items.
2. Incorrect UI Behavior: Items may not be updated or reordered correctly, leading to bugs or unexpected behavior.
3. Warnings: React will show a warning in the console about missing or non-unique keys.

# Forms in React

## Question 1: How do you handle forms in React? Explain the concept of controlled components.

### Ans :

In React, forms are handled using state to manage input values. You update the state on every change in the input field.

- Controlled Components:
  A controlled component is a form element (like input or textarea) whose value is managed by React state.

Key Concept: The input’s value is tied to state (value prop) and changes using an event handler (onChange).

## Question 2: What is the difference between controlled and uncontrolled components in React?

### Ans :

**Controlled Components :**

- Form elements are controlled by React state.
- Value is set and updated via React state (value prop).
- React has full control over the input value.
- Use Case When you need form validation or data processing.
  **Uncontrolled Components :**

- Form elements manage their own state using the DOM.
- Value is accessed using refs (ref attribute).
- The DOM directly manages the input value.
- use case When quick implementation is needed with minimal logic.

# Lifecycle Methods (Class Components)

## Question 1: What are lifecycle methods in React class components? Describe the phases of a component’s lifecycle.

### Ans :

**Lifecycle Methods in React Class Components:**
React class components go through three main phases: Mounting, Updating, and Unmounting.

- Mounting:
  constructor(): Initializes state and binds methods.
  static getDerivedStateFromProps(): Updates state based on props.
  render(): Renders the UI.
  componentDidMount(): Executes after the component is mounted (e.g., data fetching).

- Updating:
  static getDerivedStateFromProps(): Updates state when props change.
  shouldComponentUpdate(): Decides if re-rendering is necessary.
  render(): Renders the updated UI.
  getSnapshotBeforeUpdate(): Captures the DOM state before updates.
  componentDidUpdate(): Runs after the component has re-rendered.

- Unmounting:
  componentWillUnmount(): Cleans up resources before the component is removed.
  These methods allow you to manage state, interact with the DOM, and perform side effects during the component’s lifecycle.

## Question 2: Explain the purpose of componentDidMount(), componentDidUpdate(),and componentWillUnmount().

### Ans :

**Purpose of Lifecycle Methods:**

- componentDidMount():
  Called once, after the component is mounted to the DOM.
  Ideal for initial data fetching or setting up subscriptions.

- componentDidUpdate():
  Called after the component updates due to changes in props or state.
  Used to perform actions after an update, like fetching new data based on updated props.

- componentWillUnmount():
  Called right before the component is removed from the DOM.
  Used for cleanup tasks, like removing event listeners or canceling network requests.

# Hooks

## Question 1: What are React hooks? How do useState() and useEffect() hooks work in functional components?

### Ans :

React Hooks are functions that let you use state and other React features in functional components without writing a class. They make it easier to manage component logic and lifecycle.

**useState()**

- Allows you to add state to functional component.
- Syntax : const [state, setState] = useState('defaultValue')
- State holds the current value and setState updates the value.

**useEffect**

- Handles side effects like fetching data, subscriptions or manually changing the DOM.
- Syntax : useEffect (()=>{} , [dependencies])
- the second parameter ([dependencies]) controls when the effect runs, An empty array means it runs only once when the component mounts.

## Question 2: What problems did hooks solve in React development? Why are hooks considered an important addition to React?

### Ans :

Hooks solved problems like complex state management, difficulty in reusing stateful logic, and reliance on class components. They allow functional components to manage state and side effects, making code cleaner, more reusable, and easier to maintain. Hooks modernized React development by simplifying the API, eliminating the need for classes in many cases, and improving developer experience.

## Question 3: What is useReducer ? How we use in react app?

### Ans :

useReducer is a React hook used to manage more complex state logic compared to useState. It works similarly to Redux by allowing you to handle state updates using a reducer function. A reducer function determines how the state should change based on an action.

- When to Use useReducer
  When your state has complex logic with multiple sub-values.
  When you need to manage state that depends on the previous state.
  When you want a more structured approach, especially in large-scale apps.

## Question 4: What is the purpose of useCallback & useMemo Hooks?

### Ans :

**Purpose of useCallback and useMemo**
Both useCallback and useMemo are React hooks used to optimize performance by memoizing values or functions to prevent unnecessary re-computation or re-creation.

- useCallback :
  useCallback memoizes a function so that it is not re-created on every render unless its dependencies change.

- useMemo :
  useMemo memoizes a computed value to avoid recalculating it on every render unless its dependencies change.

## Question 5: What’s the Difference between the useCallback & useMemo Hooks?

### Ans :

**useCallback**
Purpose: Memoizes a function so that it does not get recreated on every render.
Usage: Used when you need to pass the same callback function to child components or avoid unnecessary re-renders due to function re-creation.
Return Value: The memoized function.

**useMemo**
Purpose: Memoizes a computed value (the result of a function) to avoid recalculating it on every render.
Usage: Used for expensive calculations that depend on certain values.
Return Value: The memoized result of the function.

## Question 6 : What is useRef ? How to work in react app?

### Ans :

useRef is a React hook used to create a mutable reference that persists across renders. It provides a way to directly access and interact with DOM elements or store mutable values without triggering re-renders.

- useRef Works in a React App
  useRef creates an object with a single property, current, which you can use to hold a value or reference.
  Unlike state, updating the current value does not cause the component to re-render.

# React – JSON-server and Firebase Real Time Database

## Question 1: What do you mean by RESTful web services?

### Ans :

RESTful web services are web services that follow the principles of REST (Representational State Transfer), an architectural style used to design networked applications. These services communicate using HTTP and are widely used for building APIs.

## Question 2: What is Json-Server? How we use in React ?

### Ans :

JSON Server is a lightweight and simple tool that provides a fake REST API by serving a local JSON file as a RESTful backend. It is commonly used for prototyping, testing, and developing applications without the need for a full backend server.

## Question 3: How do you fetch data from a Json-server API in React? Explain the role of fetch() or axios() in making API requests.

### Ans :

To fetch data from a JSON Server API in a React app, you can use either the built-in JavaScript fetch() function or a library like axios(). Both are used to make HTTP requests, but they work slightly differently. Below is an explanation of how to fetch data using both approaches and their roles in making API requests.

**Using fetch()**
The fetch() function is a built-in browser API used to make HTTP requests. It returns a Promise that resolves to the Response object.

**Using axios()**
axios is a popular HTTP client library that simplifies making API requests. It provides a more concise and user-friendly syntax compared to fetch().

## Question 4: What is Firebase? What features does Firebase offer?

## Question 5: Discuss the importance of handling errors and loading states when working with APIs in React

# Context API

## Question 1: What is the Context API in React? How is it used to manage global state across multiple components?

## Question 2: Explain how createContext() and useContext() are used in React for sharing state.

# State Management

## Question 1: What is Redux, and why is it used in React applications? Explain the core concepts of actions, reducers, and the store.

## Question 2: How does Recoil simplify state management in React compared to Redux?
