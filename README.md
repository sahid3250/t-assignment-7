
##  What is JSX, and why is it used?

**JSX (JavaScript XML)** is a syntax extension for JavaScript that allows writing **HTML-like code** inside JavaScript.  
It makes React components easier to write and understand by combining UI structure with logic.  

 Example:
```jsx
const element = <h1>Hello, World!</h1>;
Why used?

Makes code more readable and expressive.

Helps visualize the UI structure directly inside JS.

Compiles into React’s createElement() calls.

 What is the difference between State and Props?
Aspect	State	Props
Definition	Internal data managed inside a component	External data passed to a component
Mutable?	Can be updated using setState / useState	 Read-only (immutable)
Where used?	Manages dynamic behavior (e.g., toggle, input fields)	Used to pass data from parent → child
Ownership	Belongs to the component itself	Controlled by the parent component

 What is the useState hook, and how does it work?
The useState hook lets you add state to functional components.

 Example:

jsx
Copy code
import { useState } from "react";

function Counter() {
  const [count, setCount] = useState(0); // initial state = 0

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={() => setCount(count + 1)}>Increase</button>
    </div>
  );
}
How it works:

useState(initialValue) returns an array with two elements:

Current state value.

Function to update that state.

When the setter function is called, React re-renders the component with the new state.

 How can you share state between components in React?
Ways to share state:

Lift State Up → Move state to the nearest common parent and pass via props.

Context API → Share global state without prop drilling.

State Management Libraries → (e.g., Redux, Zustand, Recoil) for larger apps.

 Example (Lift State Up):

jsx
Copy code
function Parent() {
  const [data, setData] = useState("Hello");

  return (
    <>
      <Child1 data={data} />
      <Child2 setData={setData} />
    </>
  );
}
 How is event handling done in React?
React handles events similarly to DOM events but uses camelCase syntax and passes functions instead of strings.

 Example:

jsx
Copy code
function Button() {
  function handleClick() {
    alert("Button Clicked!");
  }

  return <button onClick={handleClick}>Click Me</button>;
}
