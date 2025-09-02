<!-- markdownlint-disable MD012 MD026 MD001 MD022 MD032 MD029 MD019 MD034 MD031 MD047 MD040 MD009 MD058 MD024 MD033 MD041 MD045 MD036 MD007  -->

<div>

 <img src="https://i.ibb.co.com/Swr7mbmJ/React.png" style="width:100%; height:auto;">

</div>

## 🔹What is ReactJS?
ReactJS is a popular JavaScript library for building user interfaces, particularly single-page applications where a responsive and dynamic user experience is essential. Developed and maintained by Facebook, React allows developers to create reusable UI components, manage the state of their applications efficiently, and optimize rendering performance through a virtual DOM.

### Key Features of ReactJS
1. **Component-Based Architecture**: React encourages the development of encapsulated components that manage their own state, making it easier to build and maintain complex UIs.
2. **Declarative Syntax**: React's declarative approach allows developers to describe what the UI should look like for a given state, and React takes care of updating the DOM when the state changes.
3. **Virtual DOM**: React uses a virtual representation of the DOM to optimize rendering performance. When the state of a component changes, React updates the virtual DOM first and then efficiently reconciles it with the actual DOM.
4. **Unidirectional Data Flow**: Data flows in one direction, from parent components to child components, making it easier to understand and debug the application state.
5. **Rich Ecosystem**: React has a vast ecosystem of libraries and tools, including React Router for routing, Redux for state management, and many others that enhance its capabilities.
6. **JSX Syntax**: React uses JSX, a syntax extension that allows developers to write HTML-like code within JavaScript, making it easier to visualize the structure of the UI.
7. **Hooks**: React introduced Hooks in version 16.8, allowing developers to use state and other React features without writing a class. Hooks enable a more functional approach to building components and managing state.
8. **Context API**: The Context API allows for easier state management and sharing of data between components without having to pass props down manually at every level. This is particularly useful for global state management and theming.
9. **React-Router**: React-Router is a popular library for handling routing in React applications. It enables developers to create single-page applications with dynamic routing, allowing for a seamless user experience as users navigate through different views.
10. **State Management**: React provides several options for state management, including local component state, Context API, and external libraries like Redux and MobX. This flexibility allows developers to choose the best approach for their application's needs.
11. **SSR & Full-Stack Development**: React can be used for server-side rendering (SSR) and full-stack development with frameworks like Next.js. SSR improves performance and SEO by rendering components on the server, while full-stack solutions enable developers to build complete applications with both front-end and back-end functionality.
12. **Testing**: React has a strong emphasis on testing, with tools like Jest and React Testing Library making it easier to write unit tests and integration tests for components. This focus on testing helps ensure the reliability and maintainability of React applications.





## ⚡ ReactJS Project Setup (Latest Version – 2025)

#### ✅ Prerequisites

Before starting, make sure you have installed:

- Node.js (LTS version ≥ 18 or 20) → Download here(https://nodejs.org/)
(Check version: `node -v`)
- npm (comes with Node) or yarn or pnpm
(Check version: `npm -v`)
- A code editor (e.g., Visual Studio Code)


#### 📦 Create a New React Project (with Vite)

Using npm:
```bash
npm create vite@latest my-app
```

Using yarn:
```bash
yarn create vite@latest my-app
```

Using pnpm (recommended for large projects):
```bash
pnpm create vite@latest my-app
```

#### 🛠 Setup Options

During setup, you’ll be asked:

- Project name → (e.g., `my-app`)
- Select a framework → `React`
- Variant → `JavaScript` or `TypeScript`

Example selection:
```yaml
✔ Project name: … my-app
✔ Select a framework: › React
✔ Select a variant: › JavaScript + SWC (or TypeScript + SWC)
```

#### 📂 Navigate & Install Dependencies

```bash
cd my-app
npm install
```

#### ▶️ Run Development Server

Start the local server:
```bash
npm run dev
```
- By default → runs at `http://localhost:5173/`


#### 🧩 Project Structure (Vite + React)

After setup, you’ll see:

```
my-app
├── node_modules
├── public
│   └── vite.svg
├── src
│   ├── App.css
│   ├── App.tsx
│   ├── main.tsx
│   └── assets
│       └── vite.svg
├── index.html
├── package.json
└── tsconfig.json
```

#### 🖼 Modify Your First Component

Open `src/App.tsx` and make the following changes:

1. Import the logo:
```tsx
import logo from './assets/vite.svg';
```

2. Open `src/App.jsx` and change:
```tsx
function App() {
  return (
    <div>
      <h1>Hello, React 2025! 🚀</h1>
      <img src={logo} alt="Vite logo" />
    </div>
  );
}
```
- Save → browser auto-refreshes.


#### 🎨 Adding Styling

**Option 1: Plain CSS**

Create `src/App.css` and import it:
```tsx
import './App.css';
```

**Option 2: TailwindCSS (modern styling)**

```bash
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
```

Update `tailwind.config.js`:
```js
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: ['./index.html', './src/**/*.{js,ts,jsx,tsx}'],
  theme: {
    extend: {},
  },
  plugins: [],
}
```

Add the Tailwind directives to your `src/App.css`:
```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

Now you can use classes like:

```html
<div class="flex items-center justify-center min-h-screen bg-gray-100">
  <h1 class="text-4xl font-bold">Hello, Tailwind CSS!</h1>
</div>
```

#### 📦 Build for Production

```bash
npm run build
```

This will create an optimized build of your application in the `dist` directory.

Preview locally:
```bash
npm run preview
```

## React Architecture

<div>

 <img src="https://i.ibb.co.com/23TRLq0Q/1-8vf-MJjm-H-Z3ux-EP-RGKTBg.png" style="width:100%; height:auto;">

</div>


## Building Blocks of React

### Components

- **Definition:** A component is a reusable piece of UI that can be composed to build complex user interfaces. Components can be functional or class-based.

#### 1. Functional Components

Functional components are modern, simple JavaScript functions that accept an object of properties (called props) and return a React element (JSX) that describes what should appear on the screen. They are the preferred way to write components in modern React, especially with the introduction of Hooks.

**Key Features:**

- **Simplicity:** Easy to read and test.
- **Stateless (traditionally):** Before hooks, they were primarily used for presenting UI without managing their own data.
- **Hooks:** With hooks like `useState` and `useEffect`, functional components can now manage state and side effects, making them as powerful as class components.
- **Performance:** Generally faster than class components due to less overhead.

`UserProfileCard.js`
```javascript
import React from 'react';
import './UserProfileCard.css'; // Assuming you have some CSS for styling

// This is a functional component.
// It receives 'props' as an argument, which is an object.
// We are destructuring the props object to get user directly.
const UserProfileCard = ({ user }) => {
  // If no user data is passed, we can return null or a placeholder.
  if (!user) {
    return <div>Loading user profile...</div>;
  }

  // The function returns JSX, which looks like HTML.
  return (
    <div className="user-profile-card">
      <img src={user.avatarUrl} alt={`${user.name}'s avatar`} className="profile-avatar" />
      <div className="profile-details">
        <h2>{user.name}</h2>
        <p className="profile-title">{user.title}</p>
        <a href={`mailto:${user.email}`} className="profile-email">Contact</a>
      </div>
    </div>
  );
};

export default UserProfileCard;
```

> **Note:** This component is highly reusable. You can use it anywhere in your application by passing different user objects as props.

#### 2. Class Components

Class components are ES6 classes that extend `React.Component` and must contain a `render()` method. They can hold and manage their own state, making them suitable for more complex components.

**Key Features:**

- **Stateful:** Can manage local state using `this.state` and `this.setState()`.
- **Lifecycle Methods:** Can use lifecycle methods like `componentDidMount` and `componentWillUnmount` to run code at specific points in the component's life.

`DataFetcher.js`
```javascript
import React, { Component } from 'react';

// This is a class component. It extends React.Component.
class DataFetcher extends Component {
  // The constructor is where you initialize state.
  constructor(props) {
    super(props);
    this.state = {
      items: [],
      isLoading: true,
      error: null,
    };
  }

  // componentDidMount is a lifecycle method.
  // It runs once after the component is first rendered to the DOM.
  // Perfect for API calls.
  componentDidMount() {
    fetch('https://jsonplaceholder.typicode.com/posts?_limit=5')
      .then(response => {
        if (response.ok) {
          return response.json();
        } else {
          throw new Error('Something went wrong ...');
        }
      })
      .then(data => this.setState({ items: data, isLoading: false }))
      .catch(error => this.setState({ error, isLoading: false }));
  }

  // The render() method is required and returns the component's UI.
  render() {
    const { items, isLoading, error } = this.state;

    if (error) {
      return <p>{error.message}</p>;
    }

    if (isLoading) {
      return <p>Loading data...</p>;
    }

    return (
      <div>
        <h2>Fetched Posts</h2>
        <ul>
          {items.map(item => (
            <li key={item.id}>{item.title}</li>
          ))}
        </ul>
      </div>
    );
  }
}

export default DataFetcher;
```




### JSX (JavaScript XML)

- **Definition:** JSX is a syntax extension for JavaScript that looks similar to HTML. It allows you to write HTML-like code within JavaScript, making it easier to create and visualize the structure of your UI.
- **Usage:** JSX is commonly used with React to describe what the UI should look like. Babel compiles JSX down to `React.createElement()` calls, which return plain JavaScript objects representing the DOM.

📌 Example:

```tsx
const element = <h1>Hello, JSX!</h1>;
```
- Allows dynamic rendering based on JS values.

> **Note:** In general, browsers are not capable of reading JSX and only can read pure JavaScript. The web browsers read JSX with the help of a transpiler. Transpilers are used to convert JSX into JavaScript. The transpiler used is called Babel.


### Props (Properties)

- **Definition:** Props are inputs to a React component. They are passed to the component as an object and can be used to customize the component's behavior and appearance.
- **Unidirectional Data Flow:** Data in React flows in one direction: from top to bottom (parent to child). A child component cannot directly change the props it receives from its parent. This makes the data flow predictable and easier to debug.
- **Read-Only (Immutable):** A component must never modify its own props. They are owned by the parent component. If a component needs to manage data that changes over time in response to user interaction, it should use state, not props.
- **Usage:** Props are read-only and should not be modified by the component. They can be of any data type, including strings, numbers, arrays, and objects.

📌 Example:

The Reusable Child Component: `StatCard.tsx`:

This component is designed to be a generic card for displaying a single statistic. It's highly reusable because its icon, label, and value are all passed in via props.

```tsx
import React from 'react';

const StatCard = ({ icon, label, value }) => {
  return (
    <div className="border p-4 rounded">
      <div className="flex items-center">
        <img src={icon} alt={label} className="w-8 h-8 mr-2" />
        <span className="font-bold">{label}:</span>
      </div>
      <p className="text-lg">{value}</p>
    </div>
  );
};

export default StatCard;
```

The Parent Component: `Dashboard.tsx`:

This is the main component that holds the data and orchestrates the child components. It passes the necessary data down to WelcomeBanner and StatCard using props.

```tsx
import React from 'react';
import WelcomeBanner from './WelcomeBanner';
import StatCard from './StatCard';
import './Dashboard.css';

const Dashboard = () => {
  // Data that lives in the parent component.
  const currentUser = 'Maria';
  const dashboardStats = [
    { id: 1, icon: '📈', label: 'Sales', value: '1,250' },
    { id: 2, icon: '👥', label: 'New Users', value: '82' },
    { id: 3, icon: '💬', label: 'Messages', value: '15' },
  ];

  return (
    <div className="dashboard">
      {/* Passing the 'currentUser' variable as the 'username' prop */}
      <WelcomeBanner username={currentUser} />

      <div className="stats-container">
        {/* Reusing the StatCard component with different props */}
        {dashboardStats.map(stat => (
          <StatCard
            key={stat.id} // 'key' is a special prop for lists
            icon={stat.icon}
            label={stat.label}
            value={stat.value}
          />
        ))}
      </div>
    </div>
  );
};

export default Dashboard;
```

> **Note:** The `Dashboard` component is responsible for managing the state and data of the dashboard, while the `StatCard` component is a presentational component that displays individual statistics. This separation of concerns makes the code more modular and easier to maintain.



### State

- **Definition:** State is a built-in object in React that allows components to manage their own data. Unlike props, which are passed from parent to child, state is managed within the component itself.
- **Internal and Private:** State is encapsulated within the component that owns and manages it. It cannot be accessed or modified directly by any other component. To share state, the owner component must pass it down as props to child components.
- **Mutable:** State is mutable, meaning it can be changed over time, typically in response to user actions or network responses.
- **Triggers Re-Renders:** When the state changes, React re-renders the component to reflect the new state.
- **Usage:** State is used to store data that a component needs to render. When the state changes, the component re-renders to reflect the new state.

📌 Example:

```tsx
import React, { useState } from 'react';

const Counter = () => {
  const [count, setCount] = useState(0);

  const increment = () => {
    setCount(count + 1);
  };

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={increment}>Increment</button>
    </div>
  );
};

export default Counter;
```

> **Note:** In this example, the `Counter` component uses the `useState` hook to manage its `count` state. When the button is clicked, the `increment` function updates the state, causing the component to re-render with the new count value.


### Events

- **Definition:** Events are actions or occurrences that happen in the application, usually as a result of user interactions (e.g., clicks, form submissions).
- **Handling Events:** In React, you can handle events using event handlers, which are functions that are called in response to specific events.

HTML: 
```html
<button onclick="handleClick()">Click Me</button>
```
React:
```tsx
<button onClick={handleClick}>Click Me</button>
```
- **Synthetic Events:** React creates a synthetic event system that wraps the browser's native events. This ensures consistent behavior across different browsers.
- **Preventing Default Behavior:** In React, you can prevent the default behavior of an event (e.g., form submission) by calling `event.preventDefault()` in your event handler.

📌 Example:

```tsx
import React, 'useState' from 'react';
import './ToggleSwitch.css'; // For styling

const ToggleSwitch = () => {
  // 1. State to keep track of whether the switch is on or off
  const [isOn, setIsOn] = useState(false);

  // 2. The event handler function
  // This function is called whenever the click event occurs.
  const handleToggle = () => {
    // We update the state to the opposite of its current value.
    // This will trigger a re-render.
    setIsOn(currentStatus => !currentStatus);
  };

  // Dynamically determine the CSS class based on the 'isOn' state
  const switchClassName = `switch-container ${isOn ? 'on' : 'off'}`;

  return (
    <div>
      {/* 3. The event listener 'onClick' is attached to this div */}
      {/* When clicked, it will execute the handleToggle function */}
      <div className={switchClassName} onClick={handleToggle}>
        <div className="switch-handle"></div>
      </div>
      <p>The switch is currently: <strong>{isOn ? 'ON' : 'OFF'}</strong></p>
    </div>
  );
};

export default ToggleSwitch;
```

> **Note:** In this example, the `ToggleSwitch` component uses the `onClick` event to toggle its state between "ON" and "OFF". The visual representation of the switch changes based on the state, demonstrating how events can drive UI updates in React.



### Conditional Rendering

- **Definition:** Conditional rendering in React allows you to render different UI elements or components based on certain conditions (e.g., user authentication status, form validation).
- **Techniques:** You can use JavaScript operators like `if`, `&&`, and `? :` (ternary operator) to implement conditional rendering.

📌 Example:

```tsx
import React, { useState } from 'react';

const UserProfile = () => {
  const [isLoggedIn, setIsLoggedIn] = useState(false);

  const handleLogin = () => {
    setIsLoggedIn(true);
  };

  const handleLogout = () => {
    setIsLoggedIn(false);
  };

  return (
    <div>
      {isLoggedIn ? (
        <div>
          <h2>Welcome back!</h2>
          <button onClick={handleLogout}>Logout</button>
        </div>
      ) : (
        <div>
          <h2>Please log in.</h2>
          <button onClick={handleLogin}>Login</button>
        </div>
      )}
    </div>
  );
};

export default UserProfile;
```

> **Note:** In this example, the `UserProfile` component uses conditional rendering to display different content based on the user's login status. When the user is logged in, a welcome message and logout button are shown; otherwise, a login prompt is displayed.




### Lists & Keys

- **Definition:** In React, you often work with lists of data. Rendering lists efficiently requires a unique "key" for each list item.
- **Keys:** Keys help React identify which items have changed, are added, or are removed. They should be unique among siblings.
- Render multiple items with `.map()`.
- Keys help React identify elements and update efficiently.

**Importance of keys -**

- Keys help react identify which elements were added, changed or removed.
- Keys should be given to array elements for providing a unique identity for each element.
- Without keys, React does not understand the order or uniqueness of each element.
- With keys, React has an idea of which particular element was deleted, edited, and added.
- Keys are generally used for displaying a list of data coming from an API.

📌 Example:

```jsx
import React from "react";
import ReactDOM from "react-dom/client";  // Import react-dom/client

const numbers = [1, 2, 3, 4, 5];

const updatedNums = numbers.map((number) => {
    return <li key={number}>{number}</li>;  // Add a unique "key" prop
});

const root = ReactDOM.createRoot(document.getElementById("root"));  // Create the root
root.render(<ul>{updatedNums}</ul>);  // Render the list into the root element
```

> Note- Keys used within arrays should be unique among siblings. They need not be globally unique.

### Lifecycle (Class) / Hooks (Function)

**React Component Lifecycle Overview:**
- **Mounting:** The component is created and inserted into the DOM.
- **Updating:** The component re-renders when its props or state change.
- **Unmounting:** The component is removed from the DOM.

**Class Component Lifecycle Methods:**
**Mounting Phase:**
- `constructor()`: Initialize state and bind methods
- `componentDidMount()`: Component has mounted, DOM is available
- `render()`: Returns JSX to render

**Updating Phase:**
- `componentDidUpdate()`: Invoked immediately after updating occurs.
- `render()`: Returns JSX to render
- `getSnapshotBeforeUpdate()`: Captures information from the DOM before changes are made

**Unmounting Phase:**
- `componentWillUnmount()`: Invoked immediately before a component is unmounted and destroyed

**Error Handling:**
- Use `ErrorBoundary` components to catch JavaScript errors in their child component tree.
- Implement `componentDidCatch()` lifecycle method to handle errors gracefully.



**Function Component Hooks**

**Core Hooks:**
- `useState()`: Manage local state in function components.
- `useEffect()`: Manage side effects in function components.
- `useContext()`: Access React context in function components.

**Additional Hooks:**
- `useReducer()`: Manage complex state logic in function components.
- `useCallback()`: Memoize callback functions to optimize performance.
- `useMemo()`: Memoize expensive calculations to optimize performance.
- `useRef()`: Access and interact with DOM elements directly.
- `useImperativeHandle()`: Allow a component to control its own imperative methods.
- `useLayoutEffect()`: Similar to `useEffect()`, but runs before the browser layout is updated.


📌 Example (Professional – Fetching API Data):
```tsx
function Users() {
  const [users, setUsers] = React.useState([]);

  React.useEffect(() => {
    fetch("/api/users")
      .then(res => res.json())
      .then(data => setUsers(data));
  }, []); // Runs once after component mounts

  return <div>{users.map(u => <p key={u.id}>{u.name}</p>)}</div>;
}
```



📌 Example Custom Hook for Data Fetching;
```tsx
function useUser(userId: number) {
  const [user, setUser] = useState<User | null>(null);
  const [loading, setLoading] = useState(false);
  const [error, setError] = useState<string | null>(null);

  useEffect(() => {
    let cancelled = false;
    
    async function fetchUser() {
      setLoading(true);
      setError(null);
      
      try {
        const response = await fetch(`/api/users/${userId}`);
        const userData = await response.json();
        
        if (!cancelled) {
          setUser(userData);
        }
      } catch (err: any) {
        if (!cancelled) {
          setError(err.message);
        }
      } finally {
        if (!cancelled) {
          setLoading(false);
        }
      }
    }

    fetchUser();

    return () => {
      cancelled = true;
    };
  }, [userId]);

  return { user, loading, error };
}

// Usage
function UserProfile({ userId }: { userId: number }) {
  const { user, loading, error } = useUser(userId);
  
  if (loading) return <div>Loading...</div>;
  if (error) return <div>Error: {error}</div>;
  if (!user) return <div>No user found</div>;
  
  return <div>{user.name}</div>;
}
```


### Context API

- Solves prop drilling (passing props too deep).
- Provides global state accessible by any component.

📌 Example (Professional – Dark Mode Theme):
```tsx
const ThemeContext = React.createContext();

function App() {
  return (
    <ThemeContext.Provider value="dark">
      <Navbar />
    </ThemeContext.Provider>
  );
}

function Navbar() {
  const theme = React.useContext(ThemeContext);
  return <nav className={theme}>Navbar</nav>;
}
```
> Used in multi-page apps (Google Docs, Notion) for global settings (theme, language).


### Fragments

- Allow grouping multiple elements without extra nodes.
- Use `<React.Fragment>` or shorthand `<>...</>`.

📌 Example (List without extra div):
```tsx
function Items() {
  return (
    <>
      <li>Item 1</li>
      <li>Item 2</li>
    </>
  );
}
```


### Refs

- Provide a way to access DOM nodes or React elements created in the render method.
- Created using `React.createRef()` or `useRef()` hook.

📌 Example (Professional – Accessing DOM Element):
```tsx
function TextInput() {
  const inputRef = React.useRef<HTMLInputElement>(null);

  function focusInput() {
    inputRef.current?.focus();
  }

  return (
    <>
      <input ref={inputRef} type="text" />
      <button onClick={focusInput}>Focus the input</button>
    </>
  );
}
```
> Used in form inputs, animations, and integrating with third-party DOM libraries.


### Higher-Order Components (HOC)

- A function that takes a component and returns a new component.
- Used for code reuse, logic, and bootstrap abstraction.

📌 Example (Logging Props):
```tsx
function withLogging(WrappedComponent) {
  return function WrappedWithLogging(props) {
    console.log("Rendering", WrappedComponent.name, "with props", props);
    return <WrappedComponent {...props} />;
  };
}

function MyComponent(props) {
  return <div>{props.message}</div>;
}

const MyComponentWithLogging = withLogging(MyComponent);
```

## 🔹What is virtual DOM in React?

The Virtual DOM is a lightweight, in-memory tree (plain JS objects) that describes what the UI should look like. When props/state change, React re-renders components to produce a new VDOM tree, diffs it against the previous one (“reconciliation”), computes the minimal set of real DOM mutations, and commits those updates to the browser DOM.

Mentally model in 3 phases:

1. **Render (pure, can be interrupted)**

    - run and return React elements → a new VDOM.
    - React compares (diffs) new vs. old VDOM.
2. **Reconcile (diffing rules)**
    - Same component type → compare props/children recursively.
    - Different type → unmount old subtree, mount new.
    - Lists → React uses keys to match children across renders. Stable keys = surgical updates.
3. **Commit (synchronous, cannot be interrupted)**
    - React applies the minimal DOM ops (insert/remove nodes, set attributes, update text).
    - Runs layout effects, ref updates, etc.


📌 Example (live order dashboard):

Scenario: A food-delivery ops dashboard shows 500+ active orders updating via WebSocket (status, ETA, courier location). We want only the changed rows to touch the DOM.
```tsx
// OrderRow.tsx
import React from "react";

const OrderRow = React.memo(function OrderRow({ order }) {
  return (
    <tr data-id={order.id}>
      <td>{order.id}</td>
      <td>{order.customer}</td>
      <td>{order.restaurant}</td>
      <td>{order.status}</td> {/* only this cell often changes */}
      <td>{order.eta} min</td>
    </tr>
  );
});

export default OrderRow;
```

```tsx
// OrdersTable.tsx
import React from "react";
import OrderRow from "./OrderRow";

export default function OrdersTable({ socket }) {
  const [orders, setOrders] = React.useState([]);

  // Load initial page
  React.useEffect(() => {
    fetch("/api/orders")
      .then(r => r.json())
      .then(setOrders);
  }, []);

  // Live updates
  React.useEffect(() => {
    const handler = (msg) => {
      const update = JSON.parse(msg.data); // {id, status, eta}
      setOrders(prev =>
        prev.map(o => (o.id === update.id ? { ...o, ...update } : o))
      );
    };
    socket.addEventListener("message", handler);
    return () => socket.removeEventListener("message", handler);
  }, [socket]);

  return (
    <table>
      <tbody>
        {orders.map(o => (
          <OrderRow key={o.id} order={o} />
        ))}
      </tbody>
    </table>
  );
}
```

## 🔹 What is React Router?
React Router is a popular library for handling routing in React applications. It provides a declarative way to define routes and navigate between different views or pages within an application. React Router is built on top of React and allows developers to create single-page applications with dynamic routing. In a SPA, the browser doesn’t reload for every page → React Router handles navigation by mapping URLs to components.
Maintained by the React Training team, it’s the de-facto standard for routing in React.

#### Key Features of React Router

- **Declarative Routing:** Define routes using JSX, making the code more readable and maintainable.
- **Dynamic Routing:** Routes can be added, removed, or changed dynamically based on application state.
- **Nested Routes:** Support for nested UI and layouts.
- **Route Parameters:** Capture values from the URL.
- **Programmatic Navigation:** Navigate using code (e.g., after form submission).
- **Route Guards:** Protect routes and redirect unauthorized users.
- **Lazy Loading:** Load route components lazily for better performance.



#### ⚡ Latest Version: react-router-dom v6 (2025)

- Introduced `Routes` replacing `Switch`.
- Route elements are now passed via `element` prop.
- Nested routes with `Outlet`.
- New hooks: `useNavigate`, `useParams`, `useLocation`.
- Improved route matching algorithm.
- Removed `withRouter` HOC.
- Better TypeScript support.
- Suspense support for data loading.

#### 🛠 Professional Application Setup with React Router (v6+)

**Install React Router**
```bash
npm install react-router-dom
```

**Setup Router in main.tsx**
```tsx
import React from "react";
import ReactDOM from "react-dom/client";
import { BrowserRouter } from "react-router-dom";
import App from "./App";

ReactDOM.createRoot(document.getElementById("root")!).render(
  <React.StrictMode>
    <BrowserRouter>
      <App />
    </BrowserRouter>
  </React.StrictMode>
);
```

**Routing**

`app/routes.tsx`
```tsx
import { createBrowserRouter } from "react-router-dom";
import { Home, About, AuthLayout, Login, Register, ConcertsHome, ConcertDetails } from "../app/pages";

export const router = createBrowserRouter([
  {
    path: "/",
    Component: Root,
    children: [
      { index: true, Component: Home },
      { path: "about", Component: About },
      {
        path: "auth",
        Component: AuthLayout,
        children: [
          { path: "login", Component: Login },
          { path: "register", Component: Register },
        ],
      },
      {
        path: "concerts",
        children: [
          { index: true, Component: ConcertsHome },
          { path: ":city", Component: ConcertsCity },
          { path: "trending", Component: ConcertsTrending },
        ],
      },
      { path: "concerts/:id", Component: ConcertDetails },
      { path: "*", Component: NotFound },
    ],
  },
]);
```

`Root.tsx`
```tsx
import { Outlet } from "react-router-dom";

export default function Root() {
  return (
    <>
      <header>
        <h1>My App</h1>
        <nav>
          <a href="/">Home</a> | <a href="/about">About</a> |{" "}
          <a href="/auth/login">Login</a>
        </nav>
      </header>
      <main>
        <Outlet />
      </main>
    </>
  );
}
```

**Features with React Router v6**

✅ Navigation state and GET forms (URL-driven search)
- useNavigation gives pending state; GET Forms update the URL and loaders respond to query changes.
```jsx
import { Form, useLoaderData, useNavigation, useSubmit } from "react-router-dom";

// loader reads query
export async function loader({ request }) {
  const url = new URL(request.url);
  const q = url.searchParams.get("q") ?? "";
  const results = await fetch(`/api/search?q=${encodeURIComponent(q)}`).then(r => r.json());
  return { q, results };
}

function SearchPage() {
  const { q, results } = useLoaderData();
  const nav = useNavigation();
  const submit = useSubmit();

  return (
    <>
      <Form role="search" method="get" onChange={(e) => submit(e.currentTarget)}>
        <input name="q" defaultValue={q} placeholder="Search…" />
      </Form>
      {nav.state === "loading" ? <p>Searching…</p> : <pre>{JSON.stringify(results, null, 2)}</pre>}
    </>
  );
}
```

✅ Nested Routes
```tsx
import { Outlet } from "react-router-dom";

function Dashboard() {
  return (
    <div>
      <h2>Dashboard</h2>
      <Outlet />
    </div>
  );
}

function Profile() {
  return <h3>Profile</h3>;
}

function Settings() {
  return <h3>Settings</h3>;
}

export default function App() {
  return (
    <Routes>
      <Route path="dashboard" element={<Dashboard />}>
        <Route path="profile" element={<Profile />} />
        <Route path="settings" element={<Settings />} />
      </Route>
    </Routes>
  );
}
```

✅ Route loaders: fetch data where the route is defined

- The loader runs before a route renders and returns the data for that route.
- It receives params, request, and an abort signal.
```jsx
// routes/post.jsx
import { useLoaderData } from "react-router-dom";

export async function loader({ params, signal }) {
  const res = await fetch(`/api/posts/${params.postId}`, { signal });
  if (!res.ok) throw res; // Will be caught by errorElement
  return res.json();
}

export default function Post() {
  const post = useLoaderData();
  return <article><h1>{post.title}</h1><p>{post.body}</p></article>;
}
```


✅ Route actions + <Form>: mutations with built‑in navigation and validation

- Actions handle non-GET submissions. Use Form to submit without manual event handlers.
- Return `redirect()` to navigate or `json()` with errors to show validation messages.
```jsx
// routes/post.jsx
import { Form, useActionData, useNavigation, json, redirect } from "react-router-dom";

export async function action({ request, params }) {
  const form = await request.formData();
  const body = form.get("body");
  if (!body?.trim()) {
    return json({ errors: { body: "Comment is required" } }, { status: 400 });
  }
  const res = await fetch(`/api/posts/${params.postId}/comments`, {
    method: "POST",
    headers: { "Content-Type": "application/json" },
    body: JSON.stringify({ body }),
  });
  if (!res.ok) throw res;
  return redirect(`/posts/${params.postId}`);
}

function CommentForm() {
  const errors = useActionData();
  const nav = useNavigation();
  const busy = nav.state === "submitting";
  return (
    <Form method="post">
      <textarea name="body" />
      {errors?.errors?.body && <p role="alert">{errors.errors.body}</p>}
      <button disabled={busy}>{busy ? "Saving..." : "Add comment"}</button>
    </Form>
  );
}
```



✅ Error boundaries for loaders/actions (errorElement)
- Throw Responses (or plain errors) in loaders/actions and render a route-specific error UI.
```jsx
// routes/post.jsx
import { useRouteError, isRouteErrorResponse } from "react-router-dom";

export function ErrorBoundary() {
  const error = useRouteError();
  if (isRouteErrorResponse(error)) {
    return <p>{error.status} {error.statusText}</p>;
  }
  return <p>Something went wrong.</p>;
}
```

✅ Deferred data + streaming UI (defer/Await)

- Render critical data immediately and stream the rest later with `Suspense/Await`.
```jsx
// routes/post.jsx
import { defer, Await } from "react-router-dom";
import { Suspense } from "react";

export async function loader({ params, signal }) {
  const post = fetch(`/api/posts/${params.postId}`, { signal }).then(r => r.json());
  const comments = fetch(`/api/posts/${params.postId}/comments`, { signal }).then(r => r.json());

  // Wait for post (critical), stream comments
  return defer({ post: await post, comments });
}

export default function Post() {
  const data = useLoaderData();
  return (
    <article>
      <h1>{data.post.title}</h1>
      <Suspense fallback={<p>Loading comments…</p>}>
        <Await resolve={data.comments} errorElement={<p>Failed to load comments</p>}>
          {(comments) => <ul>{comments.map(c => <li key={c.id}>{c.body}</li>)}</ul>}
        </Await>
      </Suspense>
    </article>
  );
}
```

✅ Fetchers: call loaders/actions without navigation

- Perfect for toggles, side panels, typeahead, etc.
```jsx
import { useFetcher } from "react-router-dom";

function FavoriteButton({ postId, initialFavorite }) {
  const fetcher = useFetcher();
  const optimistic = fetcher.formData
    ? fetcher.formData.get("favorite") === "true"
    : initialFavorite;

  return (
    <fetcher.Form method="post" action={`/posts/${postId}/favorite`}>
      <input type="hidden" name="favorite" value={(!optimistic).toString()} />
      <button disabled={fetcher.state !== "idle"}>
        {optimistic ? "★ Favorited" : "☆ Favorite"}
      </button>
    </fetcher.Form>
  );
}

// route config:
// { path: "posts/:postId/favorite", action: favoriteAction }
export async function favoriteAction({ request, params }) {
  const fd = await request.formData();
  const favorite = fd.get("favorite") === "true";
  await fetch(`/api/posts/${params.postId}/favorite`, {
    method: "POST",
    headers: { "Content-Type": "application/json" },
    body: JSON.stringify({ favorite }),
  });
  return null; // default: revalidate matching loaders
}
```

✅ Revalidation: automatic and controllable

- After actions or navigations, loaders re-run by default.
- Control it with `shouldRevalidate` or trigger manually with `useRevalidator`.
```jsx
// Only revalidate on non-GET mutations or when search changes
export const route = {
  loader: todosLoader,
  shouldRevalidate: ({ currentUrl, nextUrl, formMethod }) => {
    if (formMethod && formMethod.toLowerCase() !== "get") return true;
    return currentUrl.search !== nextUrl.search;
  },
};

// Manual revalidation
import { useRevalidator } from "react-router-dom";
function RefreshButton() {
  const { revalidate, state } = useRevalidator();
  return (
    <button onClick={() => revalidate()} disabled={state === "loading"}>
      {state === "loading" ? "Refreshing…" : "Refresh"}
    </button>
  );
}
```

✅ Route IDs + useRouteLoaderData: share parent data with children

- Give a route an id and read its loader data from any descendant.
```jsx
// router
{
  id: "root",
  path: "/",
  loader: async () => ({ user: await fetch("/api/me").then(r => r.json()) }),
  element: <RootLayout />,
  children: [/* ... */],
}

// anywhere below root:
import { useRouteLoaderData } from "react-router-dom";
function UserBadge() {
  const { user } = useRouteLoaderData("root");
  return <span>Signed in as {user.name}</span>;
}
```

✅ Progressive, lazy-loaded route modules (code-split loaders/actions/components)

- Load a route’s component, loader, and action only when navigated to.
```jsx
// route config
{
  path: "settings",
  lazy: () => import("./routes/settings"), // settings.jsx exports loader/action/default
}

// routes/settings.jsx
export async function loader() { /* ... */ }
export async function action() { /* ... */ }
export default function Settings() { return <h2>Settings</h2>; }
```

✅ Navigation state and GET forms (URL-driven search)

- useNavigation gives pending state; GET Forms update the URL and loaders respond to query changes.
```jsx
import { Form, useLoaderData, useNavigation, useSubmit } from "react-router-dom";

// loader reads query
export async function loader({ request }) {
  const url = new URL(request.url);
  const q = url.searchParams.get("q") ?? "";
  const results = await fetch(`/api/search?q=${encodeURIComponent(q)}`).then(r => r.json());
  return { q, results };
}

function SearchPage() {
  const { q, results } = useLoaderData();
  const nav = useNavigation();
  const submit = useSubmit();

  return (
    <>
      <Form role="search" method="get" onChange={(e) => submit(e.currentTarget)}>
        <input name="q" defaultValue={q} placeholder="Search…" />
      </Form>
      {nav.state === "loading" ? <p>Searching…</p> : <pre>{JSON.stringify(results, null, 2)}</pre>}
    </>
  );
}
```


✅ Data Loading (v6.4+)
```tsx
import { createBrowserRouter } from "react-router-dom";

export const router = createBrowserRouter([
  {
    path: "/",
    loader: async () => {
      // return data from here
      return { records: await getSomeRecords() };
    },
    Component: MyRoute,
  },
]);
```

Accessing Data
```tsx
import { useLoaderData } from "react-router-dom";

export function MyRoute() {
  const data = useLoaderData();
  return (
    <div>
      {data.records.map((record: any) => (
        <p key={record.id}>{record.name}</p>
      ))}
    </div>
  );
}
```




## 🔹What are hooks in React?

Hooks are special functions that let you “hook into” React features (like state, lifecycle, context) inside functional components.

- **Before hooks**: only class components had state & lifecycle methods.
- **After hooks**: functional components can do everything classes can do (and more).
- **Rules of Hooks**:
  1. Only call hooks at the top level (not inside loops, conditions, or nested functions).
  2. Only call hooks from React functions (components or custom hooks).


### 🔑 Types of Hooks in React

#### 1. useState
Manages state in a functional component.
- Returns a stateful value and a function to update it.
- Syntax: `const [state, setState] = useState(initialState);`

📌 Example (Counter Button – Professional Dashboard Widget):
```jsx
import { useState } from "react";

function Counter({ step = 1 }) {
  // Lazy init: expensive initial computation runs once
  const [count, setCount] = useState(() => {
    // e.g., read from localStorage or compute something heavy
    return 0;
  });

  const increment = () => {
    // Functional update form avoids stale state in async scenarios
    setCount(c => c + step);
  };

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={increment}>+{step}</button>
      <button onClick={() => setCount(0)}>Reset</button>
    </div>
  );
}
export default Counter;
```

#### 2. useEffect

Handles side effects (fetching data, subscriptions, DOM updates).
It’s the replacement for lifecycle methods `(componentDidMount`, `componentDidUpdate`, `componentWillUnmount`).
- Syntax: `useEffect(() => { /* effect */ return () => { /* cleanup */ }; }, [dependencies]);`

📌 Example (Fetch Users from API):
```jsx
import { useEffect, useState } from "react";

function User({ id }) {
  const [user, setUser] = useState(null);
  const [status, setStatus] = useState("idle");

  useEffect(() => {
    const ctrl = new AbortController();
    setStatus("loading");

    fetch(`/api/users/${id}`, { signal: ctrl.signal })
      .then(r => r.ok ? r.json() : Promise.reject(r))
      .then(data => {
        setUser(data);
        setStatus("success");
      })
      .catch(err => {
        if (err.name !== "AbortError") {
          setStatus("error");
        }
      });

    return () => ctrl.abort(); // cancel pending fetch on id change/unmount
  }, [id]);

  if (status === "loading") return <p>Loading…</p>;
  if (status === "error") return <p>Something went wrong.</p>;
  return <pre>{JSON.stringify(user, null, 2)}</pre>;
}
```


#### 3. useRef
Manages mutable values that persist across renders without causing re-renders.
- Returns a mutable ref object with a `.current` property.
- Commonly used to access DOM elements or store mutable variables.

📌 Example (Professional – Autofocus Input):
```jsx
import { useEffect, useRef } from "react";

function LoginForm() {
  const inputRef = useRef();

  useEffect(() => {
    inputRef.current.focus(); // focus input on mount
  }, []);

  return <input ref={inputRef} placeholder="Enter username" />;
}
```


#### 4. useContext

Allows you to access and share global data (like themes, user info) without prop drilling.
- Accepts a context object and returns the current context value.
- Components re-render when the context value changes.

📌 Example (Professional – Dark Mode Toggle):
```jsx
import { createContext, useContext, useState } from "react";

const ThemeContext = createContext();

function App() {
  const [theme, setTheme] = useState("light");

  return (
    <ThemeContext.Provider value={{ theme, setTheme }}>
      <Navbar />
    </ThemeContext.Provider>
  );
}

function Navbar() {
  const { theme, setTheme } = useContext(ThemeContext);

  return (
    <nav className={theme}>
      <button onClick={() => setTheme(theme === "light" ? "dark" : "light")}>
        Toggle Theme
      </button>
    </nav>
  );
}
```




#### 5. useReducer
An alternative to `useState` for complex state logic.
- Accepts a reducer function and initial state.
- Returns the current state and a dispatch function.

📌 Example (ToDo App with Reducer):
```jsx
import { useReducer } from "react";

function reducer(state, action) {
  switch (action.type) {
    case "add":
      return [...state, { id: crypto.randomUUID(), text: action.text, done: false }];
    case "toggle":
      return state.map(t => t.id === action.id ? { ...t, done: !t.done } : t);
    case "remove":
      return state.filter(t => t.id !== action.id);
    default:
      return state;
  }
}

function TodoApp() {
  const [todos, dispatch] = useReducer(reducer, []);

  return (
    <>
      <button onClick={() => dispatch({ type: "add", text: "Learn Hooks" })}>
        Add
      </button>
      <ul>
        {todos.map(t => (
          <li key={t.id}>
            <label>
              <input
                type="checkbox"
                checked={t.done}
                onChange={() => dispatch({ type: "toggle", id: t.id })}
              />
              {t.text}
            </label>
            <button onClick={() => dispatch({ type: "remove", id: t.id })}>
              ✕
            </button>
          </li>
        ))}
      </ul>
    </>
  );
}
```


#### 6. useMemo
Optimizes performance by memoizing expensive calculations.
- Accepts a function and dependency array.
- Recomputes the memoized value only when dependencies change.

📌 Example (Expensive Calculation):
```jsx
import { useMemo, useState } from "react";

function Fibonacci({ n }) {
  const [highlight, setHighlight] = useState(false);

  const value = useMemo(() => {
    function fib(x) {
      return x <= 1 ? x : fib(x - 1) + fib(x - 2);
    }
    return fib(n); // expensive
  }, [n]);

  return (
    <div style={{ background: highlight ? "#fffae6" : "white" }}>
      Fib({n}) = {value}
      <button onClick={() => setHighlight(h => !h)}>Toggle highlight</button>
    </div>
  );
}
```


#### 7. useCallback
Optimizes performance by memoizing function references.
- Accepts a function and dependency array.
- Recomputes the memoized function only when dependencies change.

📌 Example (Button with Memoized Click Handler):
```jsx
import { memo, useCallback, useState } from "react";

const Child = memo(function Child({ onAdd }) {
  console.log("Child re-render");
  return <button onClick={() => onAdd(1)}>Add 1</button>;
});

function Parent() {
  const [count, setCount] = useState(0);

  const handleAdd = useCallback((n) => {
    setCount(c => c + n);
  }, []); // stable reference

  return (
    <>
      <p>Count: {count}</p>
      <Child onAdd={handleAdd} />
    </>
  );
}
```

#### 8. useLayoutEffect
Synchronously fires after all DOM mutations.
- Useful for reading layout from the DOM and synchronously re-rendering.
- Blocks browser painting until the effect is run.

📌 Example (Measure DOM Element):
```jsx
import { useLayoutEffect, useRef, useState } from "react";

function Measure() {
  const ref = useRef(null);
  const [rect, setRect] = useState(null);

  useLayoutEffect(() => {
    if (ref.current) {
      setRect(ref.current.getBoundingClientRect());
    }
  });

  return (
    <>
      <div ref={ref}>Measure me</div>
      {rect && <pre>{JSON.stringify(rect, null, 2)}</pre>}
    </>
  );
}
```

#### 9. useId
Generates unique IDs for accessibility and server rendering.
- Ensures consistent IDs across server and client.
- Useful for linking labels and inputs.

📌 Example (Accessible Input):
```jsx
import { useId } from "react";

function Input() {
  const id = useId();
  return (
    <>
      <label htmlFor={id}>Name:</label>
      <input id={id} type="text" />
    </>
  );
}
```


#### 10. useTransition and useDeferredValue
- Helps manage concurrent rendering.
- useTransition: Defers state updates to keep UI responsive.
- useDeferredValue: Defers re-rendering non-urgent parts.

📌 Example (Deferred Search Input):
```jsx
import { useState, useTransition, useDeferredValue } from "react";

function Search() {
  const [text, setText] = useState("");
  const [isPending, startTransition] = useTransition();
  const deferredText = useDeferredValue(text);

  const handleChange = (e) => {
    const nextText = e.target.value;
    startTransition(() => {
      setText(nextText);
    });
  };

  const results = useMemo(() => {
    // simulate expensive search
    return deferredText ? ["Result 1", "Result 2"] : [];
  }, [deferredText]);

  return (
    <>
      <input type="text" onChange={handleChange} />
      {isPending && <div>Loading...</div>}
      <ul>
        {results.map(r => <li key={r}>{r}</li>)}
      </ul>
    </>
  );
}
```


### “All-In-One” example
```jsx
import React, {
  memo,
  useCallback,
  useContext,
  useDeferredValue,
  useEffect,
  useId,
  useMemo,
  useReducer,
  useRef,
  useState,
  useTransition,
  createContext
} from "react";

// Context + reducer
const TodosContext = createContext();

function todosReducer(state, action) {
  switch (action.type) {
    case "add":
      return [...state, { id: crypto.randomUUID(), text: action.text, done: false }];
    case "toggle":
      return state.map(t => t.id === action.id ? { ...t, done: !t.done } : t);
    default:
      return state;
  }
}

function TodosProvider({ children }) {
  const [todos, dispatch] = useReducer(todosReducer, []);
  const value = useMemo(() => ({ todos, dispatch }), [todos]);
  return <TodosContext.Provider value={value}>{children}</TodosContext.Provider>;
}

const TodoItem = memo(function TodoItem({ todo, onToggle }) {
  return (
    <li>
      <label>
        <input type="checkbox" checked={todo.done} onChange={() => onToggle(todo.id)} />
        {todo.text}
      </label>
    </li>
  );
});

function App() {
  const { todos, dispatch } = useContext(TodosContext);
  const [query, setQuery] = useState("");
  const deferredQuery = useDeferredValue(query);
  const [isPending, startTransition] = useTransition();
  const inputId = useId();
  const inputRef = useRef(null);

  const addTodo = useCallback((text) => {
    dispatch({ type: "add", text });
  }, [dispatch]);

  const onToggle = useCallback((id) => {
    dispatch({ type: "toggle", id });
  }, [dispatch]);

  const filtered = useMemo(() => {
    return todos.filter(t => t.text.toLowerCase().includes(deferredQuery.toLowerCase()));
  }, [todos, deferredQuery]);

  useEffect(() => {
    inputRef.current?.focus();
  }, []);

  function onAdd() {
    const text = inputRef.current.value.trim();
    if (!text) return;
    startTransition(() => addTodo(text)); // non-urgent update
    inputRef.current.value = "";
    setQuery("");
  }

  return (
    <div>
      <div>
        <label htmlFor={inputId}>New todo</label>
        <input id={inputId} ref={inputRef} />
        <button onClick={onAdd}>Add</button>
      </div>

      <div>
        <input
          placeholder="Filter…"
          value={query}
          onChange={(e) => setQuery(e.target.value)}
        />
        {isPending && <span> Updating…</span>}
      </div>

      <ul>
        {filtered.map(t => (
          <TodoItem key={t.id} todo={t} onToggle={onToggle} />
        ))}
      </ul>
    </div>
  );
}

// Usage
export default function Root() {
  return (
    <TodosProvider>
      <App />
    </TodosProvider>
  );
}
```

#### Custom Hook

📌 Example
```jsx
import { useState, useEffect } from "react";

function useFetch(url) {
  const [data, setData] = useState(null);

  useEffect(() => {
    fetch(url).then(res => res.json()).then(setData);
  }, [url]);

  return data;
}

// Usage
function Users() {
  const users = useFetch("/api/users");
  return <ul>{users?.map(u => <li key={u.id}>{u.name}</li>)}</ul>;
}
```


## 🔹What is Prop Drilling in React?

Prop Drilling in React refers to the process where you pass data from a parent component to a deeply nested child component through multiple layers of intermediate components that do not need the data themselves. This can make the code harder to maintain and understand.

#### 📌 Example of Prop Drilling:
Imagine you have an app with this component tree:

```nginx
App → Dashboard → Sidebar → UserProfile → UserName
```

Suppose the `App` component has user data (`name: "John Doe"`) that you need to display inside `UserName`.

Without Context (Prop Drilling):
```tsx
function App() {
  const user = { name: "John Doe" };
  return <Dashboard user={user} />;
}

function Dashboard({ user }) {
  return <Sidebar user={user} />;
}

function Sidebar({ user }) {
  return <UserProfile user={user} />;
}

function UserProfile({ user }) {
  return <UserName user={user} />;
}

function UserName({ user }) {
  return <div>{user.name}</div>;
}
```

**⚠️ Disadvantages of Prop Drilling**

**1. Unnecessary Passing of Data**
  - Components (`Dashboard`, `Sidebar`, `UserProfile`) get props they don’t use.

**2. Code Becomes Hard to Maintain**
  - If you add/remove props, you must update every intermediate component.

**3. Reduced Readability**
  - It’s harder to understand which component actually uses the prop.

**4. Scalability Issues**
  - As the app grows (more nested components), prop drilling becomes unmanageable.

**5. Performance Overhead**
  - Any prop change causes all intermediate components to re-render, even if they don’t use the data.


#### ✅ Solutions to Prop Drilling

**1. React Context API (built-in)**

Instead of drilling props, we can wrap components in a context provider and access data with useContext.
```tsx
const UserContext = React.createContext();

function App() {
  const user = { name: "John Doe" };
  return (
    <UserContext.Provider value={user}>
      <Dashboard />
    </UserContext.Provider>
  );
}

function UserName() {
  const user = React.useContext(UserContext);
  return <div>{user.name}</div>;
}
```

**2. State management libraries (Redux, Zustand, MobX, Jotai, Recoil)**

These libraries provide more powerful and scalable solutions for managing global state, avoiding prop drilling by connecting components directly to the state they need.

```tsx
// Redux example
import { createStore } from "redux";
import { Provider, useSelector, useDispatch } from "react-redux";

const initialState = { user: { name: "John Doe" } };

function reducer(state = initialState, action) {
  switch (action.type) {
    default:
      return state;
  }
}

const store = createStore(reducer);

function UserName() {
  const user = useSelector(state => state.user);
  return <div>{user.name}</div>;
}

function App() {
  return (
    <Provider store={store}>
      <UserName />
    </Provider>
  );
}
```

**3. Data fetching caches (React Query/SWR/Apollo)**

These libraries provide built-in caching and state management for server state, reducing the need for prop drilling.

```tsx
import { useQuery } from "react-query";

function fetchUser() {
  return fetch("/api/user").then(res => res.json());
}

function UserName() {
  const { data: user } = useQuery("user", fetchUser);
  return <div>{user?.name}</div>;
}
```


**4. Router/URL state (React Router)**

React Router allows you to store state in the URL, which components can read directly, avoiding prop drilling.

```tsx
function Leaf() {
  const [params, setParams] = useSearchParams();
  const theme = params.get('theme') ?? 'light';
  const toggle = () => setParams({ theme: theme === 'light' ? 'dark' : 'light' });
  return <button onClick={toggle}>Theme: {theme}</button>;
}
```


**5. Composition patterns (avoid passing through intermediates)**

Instead of passing props through many layers, use composition to directly provide the needed data to the component.

```tsx
function App() {
  const user = { name: "John Doe" };
  return (
    <Dashboard>
      <UserName user={user} />
    </Dashboard>
  );
}

function Dashboard({ children }) {
  return <div className="dashboard">{children}</div>;
}

function UserName({ user }) {
  return <div>{user.name}</div>;
}
```

**6. Pub/Sub (event bus)**

This pattern uses an event bus to publish and subscribe to events, allowing components to communicate without direct prop passing.

```tsx
const bus = (() => {
  const listeners = new Map();
  return {
    on: (type, fn) => (listeners.set(type, [...(listeners.get(type) || []), fn]), () => {
      listeners.set(type, (listeners.get(type) || []).filter(f => f !== fn));
    }),
    emit: (type, payload) => (listeners.get(type) || []).forEach(fn => fn(payload)),
  };
})();

function DeepToggleButton() {
  return <button onClick={() => bus.emit('theme/toggle')}>Toggle theme</button>;
}

function ThemeHolder() {
  const [theme, setTheme] = React.useState('light');
  React.useEffect(() => bus.on('theme/toggle', () => setTheme(t => t === 'light' ? 'dark' : 'light')), []);
  return <div>Theme: {theme}</div>;
}
```

**7. External store + useSyncExternalStore (built-in)**

```tsx
const store = {
  state: { theme: 'light' },
  listeners: new Set(),
  toggleTheme() {
    this.state.theme = this.state.theme === 'light' ? 'dark' : 'light';
    this.listeners.forEach((listener) => listener());
  },
  subscribe(listener) {
    this.listeners.add(listener);
    return () => this.listeners.delete(listener);
  },
  getSnapshot() {
    return this.state.theme;
  },
};

function useTheme() {
  return React.useSyncExternalStore(
    store.subscribe.bind(store),
    store.getSnapshot.bind(store)
  );
}

function ThemeToggle() {
  const theme = useTheme();
  return <button onClick={() => store.toggleTheme()}>Theme: {theme}</button>;
}
```

**8. Co-locate or lift state “just enough”**

This approach involves placing state as close as possible to where it's needed, or lifting it just enough to share between components, minimizing prop drilling.

```tsx
// Before (drilling theme + setter)
function App() {
  const [theme, setTheme] = React.useState('light');
  return <Parent theme={theme} setTheme={setTheme} />;
}
function Parent(props) { return <Middle {...props} />; }
function Middle(props) { return <Leaf {...props} />; }
function Leaf({ theme, setTheme }) { /* ... */ }

// After (co-located in Leaf)
function Parent() { return <Leaf />; }
function Leaf() {
  const [theme, setTheme] = React.useState('light');
  return <button onClick={() => setTheme(t => t === 'light' ? 'dark' : 'light')}>{theme}</button>;
}
```

**Notes:**

- Small apps or shallow trees: prefer co-location, composition, or Context.
- Large apps/shared state across unrelated parts: use a store (Redux/Zustand) or data cache (React Query/SWR).
- If you need to avoid threading callbacks: pub/sub or a store for actions works well.


## 🔹What are controlled components in React?

- A React component that controls the input form elements, maintaining their state within the component.
- The component's state is the "single source of truth" for the input values.
- Changes to the input are handled through event handlers that update the state.
- This allows validation, conditionally enabling/disabling buttons, and enforcing input formats.

Examples by control type:
- Text input: `onChange`, `value`.
- Checkbox: `onChange`, `checked`.
- Radio button: `onChange`, `checked`.
- Select: `onChange`, `value`.
- File input: `onChange`, `files`.
- Range input: `onChange`, `value`.
- Textarea: `onChange`, `value`.
- Button: `onClick`.
- Other form elements follow similar patterns.

#### 🏗 All-in-One Controlled Form Example:

```jsx
import { useState } from "react";

function AllInOneForm() {
  const [form, setForm] = useState({
    name: "",
    email: "",
    password: "",
    role: "user",
    gender: "",
    terms: false,
    bio: "",
  });

  // Handles input change for all fields
  const handleChange = (e) => {
    const { name, value, type, checked } = e.target;
    setForm({
      ...form,
      [name]: type === "checkbox" ? checked : value,
    });
  };

  const handleSubmit = (e) => {
    e.preventDefault();
    console.log("✅ Form Submitted:", form);
    alert(`Form Submitted:\n${JSON.stringify(form, null, 2)}`);
  };

  return (
    <form onSubmit={handleSubmit} style={{ maxWidth: "400px", margin: "auto" }}>
      <h2>All-in-One Controlled Form</h2>

      {/* Text Input */}
      <label>
        Name:
        <input
          type="text"
          name="name"
          value={form.name}
          onChange={handleChange}
          required
        />
      </label>
      <br />

      {/* Email Input */}
      <label>
        Email:
        <input
          type="email"
          name="email"
          value={form.email}
          onChange={handleChange}
          required
        />
      </label>
      <br />

      {/* Password Input */}
      <label>
        Password:
        <input
          type="password"
          name="password"
          value={form.password}
          onChange={handleChange}
          required
        />
      </label>
      <br />

      {/* Select Dropdown */}
      <label>
        Role:
        <select name="role" value={form.role} onChange={handleChange}>
          <option value="user">User</option>
          <option value="admin">Admin</option>
          <option value="moderator">Moderator</option>
        </select>
      </label>
      <br />

      {/* Radio Buttons */}
      <div>
        Gender:
        <label>
          <input
            type="radio"
            name="gender"
            value="male"
            checked={form.gender === "male"}
            onChange={handleChange}
          />
          Male
        </label>
        <label>
          <input
            type="radio"
            name="gender"
            value="female"
            checked={form.gender === "female"}
            onChange={handleChange}
          />
          Female
        </label>
      </div>

      {/* Checkbox */}
      <label>
        <input
          type="checkbox"
          name="terms"
          checked={form.terms}
          onChange={handleChange}
        />
        Accept Terms & Conditions
      </label>
      <br />

      {/* Textarea */}
      <label>
        Bio:
        <textarea
          name="bio"
          value={form.bio}
          onChange={handleChange}
          rows="4"
          placeholder="Tell us about yourself..."
        />
      </label>
      <br />

      <button type="submit" disabled={!form.terms}>
        Submit
      </button>
    </form>
  );
}

export default AllInOneForm;
```


## 🔹Explain CORS in React?

**CORS (Cross-Origin Resource Sharing)** is a security mechanism implemented by browsers to restrict web pages from making requests to a different domain (origin) unless the server explicitly allows it.

- An origin = `protocol + domain + port`
  Example:

    - `http://localhost:3000` (React app)
    - `https://api.example.com:443` (API server)

- Browsers block JS from calling a different origin (scheme+host+port) unless the server explicitly allows it via CORS headers.
- For many cross-origin requests, the browser first sends a preflight OPTIONS request to ask permission. If the server replies with the right headers, the actual request proceeds.
- CORS is enforced by the browser, not React. You fix it on the server (or via a proxy), not in React.

👉 Typical error you’ll see

“Access to fetch at `https://api.example.com` from origin `http://localhost:5173` has been blocked by CORS policy: No ‘Access-Control-Allow-Origin’ header is present…”


When does a preflight happen?

Methods other than GET/HEAD/POST
- Custom headers (e.g., Authorization, X-*)
- Content-Type is not one of: text/plain, application/x-www-form-urlencoded, multipart/form-data
- Using credentials (cookies) cross-site also has extra rules

Core CORS headers (cheat sheet)

- **Request**: Origin, Access-Control-Request-Method, Access-Control-Request-Headers
- **Response**: Access-Control-Allow-Origin, Access-Control-Allow-Methods, Access-Control-Allow-Headers, Access-Control-Allow-Credentials, Access-Control-Expose-Headers, Access-Control-Max-Age, Vary: Origin

#### ⚠️ Example of CORS Error in React Side

**1. Simple GET (no credentials)**

```javascript
fetch("https://api.example.com/data")
  .then((response) => response.json())
  .then((data) => console.log(data))
  .catch((error) => console.error("Error:", error));
```

**2. POST with JSON body**

```javascript
fetch("https://api.example.com/data", {
  method: "POST",
  headers: {
    "Content-Type": "application/json",
  },
  body: JSON.stringify({ key: "value" }),
})
  .then((response) => response.json())
  .then((data) => console.log(data))
  .catch((error) => console.error("Error:", error));
```

**3. Sending credentials (cookies)**

```javascript
fetch("https://api.example.com/data", {
  credentials: "include", // or "same-origin"
})
  .then((response) => response.json())
  .then((data) => console.log(data))
  .catch((error) => console.error("Error:", error));
```


#### ✅ How to Fix CORS in React Side

**1. Enable CORS on the Server (Best Practice)**

CORS must be allowed by the API server, not React.
Example (Node.js + Express backend):
```javascript
import express from "express";
import cors from "cors";

const app = express();
app.use(express.json());

app.use(cors({
  origin: ["http://localhost:5173"], // your React dev origin
  credentials: true, // if you need cookies
  allowedHeaders: ["Content-Type", "Authorization"],
  methods: ["GET", "POST", "PUT", "PATCH", "DELETE", "OPTIONS"],
}));

app.get("/api/users", (req, res) => res.json([{ id: 1, name: "Ada" }]));

app.post("/api/users", (req, res) => res.status(201).json(req.body));

app.listen(5000, () => console.log("API running on port 5000"));
```

**2. Using a Proxy in React (Development Only)**

React’s development server can proxy API requests to bypass CORS in local dev.

Add this to `package.json`:
```json
{
  "proxy": "http://localhost:5000"
}
```

Call fetch("/api/users") from React; CRA forwards to 5000 and keeps same origin.
- Vite (`vite.config.js`)
```javascript
import { defineConfig } from 'vite';
import react from '@vitejs/plugin-react';

export default defineConfig({
  plugins: [react()],
  server: {
    proxy: {
      '/api': 'http://localhost:5000',
    },
  },
});
```

- Next.js (`next.config.js` rewrites)
```javascriptmodule.exports = {
  async rewrites() {
    return [
      {
        source: '/api/:path*',
        destination: 'http://localhost:5000/api/:path*', // Proxy to Backend
      },
    ];
  },
};
```

#### 3. NGINX reverse proxy (production)

Make your frontend and API appear same-origin:
```nginx
server {
  listen 80;
  server_name myapp.com;

  location / {
    root /path/to/your/react/app;
    try_files $uri /index.html;
  }

  location /api/ {
    proxy_pass http://localhost:5000/api/;
    proxy_http_version 1.1;
    proxy_set_header Upgrade $http_upgrade;
    proxy_set_header Connection 'upgrade';
    proxy_set_header Host $host;
    proxy_cache_bypass $http_upgrade;
  }
}
```

👉 React calls `/api/data` → Nginx forwards to backend → no CORS needed.



#### 1️⃣ Using Axios with CORS

✅ Basic Axios Request
```javascript
import axios from "axios";
import { useEffect, useState } from "react";

function AxiosExample() {
  const [data, setData] = useState(null);

  useEffect(() => {
    axios
      .get("https://api.example.com/data", {
        headers: {
          "Content-Type": "application/json",
        },
        withCredentials: true, // required if API uses cookies/auth
      })
      .then((res) => setData(res.data))
      .catch((err) => console.error("CORS error:", err));
  }, []);

  return <pre>{JSON.stringify(data, null, 2)}</pre>;
}

export default AxiosExample;
```

- Server must respond with:
```http
Access-Control-Allow-Origin: http://localhost:5173
Access-Control-Allow-Credentials: true
Access-Control-Allow-Headers: Content-Type, Authorization
Access-Control-Allow-Methods: GET, POST, PUT, PATCH, DELETE, OPTIONS
```

**✅ Axios + Proxy (Development Trick)**

If your backend runs at `http://localhost:5000` and frontend at `http://localhost:3000`:

- Add in `package.json` of React app:
```json
{
  "proxy": "http://localhost:5000"
}
```

- Then in React code:
```javascript
axios.get("/api/users")
  .then((response) => console.log(response.data))
  .catch((error) => console.error("Error:", error));
```

2️⃣ Using Fetch API with CORS

✅ Basic Fetch Request
```javascript
import { useEffect, useState } from "react";

function FetchExample() {
  const [data, setData] = useState(null);

  useEffect(() => {
    fetch("https://api.example.com/data", {
      method: "GET",
      headers: {
        "Content-Type": "application/json",
      },
      credentials: "include", // include cookies/auth tokens
      mode: "cors",           // default, but explicit is clearer
    })
      .then((res) => res.json())
      .then((data) => setData(data))
      .catch((err) => console.error("CORS error:", err));
  }, []);

  return <pre>{JSON.stringify(data, null, 2)}</pre>;
}

export default FetchExample;
```

- Server must respond with:
```http
Access-Control-Allow-Origin: http://localhost:5173
Access-Control-Allow-Credentials: true
Access-Control-Allow-Headers: Content-Type, Authorization
Access-Control-Allow-Methods: GET, POST, PUT, PATCH, DELETE, OPTIONS
```



**✅ Fetch + Proxy (Development Trick)**

If your backend runs at `http://localhost:5000` and frontend at `http://localhost:3000`:

- Add in `package.json` of React app:
```json
{
  "proxy": "http://localhost:5000"
}
```

- Then in React code:
```javascript
fetch("/api/users")
  .then((response) => response.json())
  .then((data) => console.log(data))
  .catch((error) => console.error("Error:", error));
```



## 🔹What is axios and how to use it in React?

Axios is a popular JavaScript library used to make HTTP requests (GET, POST, PUT, DELETE) from node.js or XML Http Requests from the browser and it supports the Promise API that is native to JS ES6+. It is often used in React applications to communicate with backend services or APIs.

- Axios is a promise-based HTTP client for browsers and Node.js.
- It simplifies HTTP requests compared to fetch by offering:
  - Automatic JSON parsing/stringifying
  - Global config (baseURL, headers, timeouts)
  - Interceptors (e.g., attach auth tokens, handle refresh tokens)
  - Request cancellation (AbortController)
  - Upload/download progress
  - Consistent errors
  - Easy query params


#### 🛠 Setup Axios in React

1. **Installation**

First, you need to install Axios in your React project:

```bash
npm install axios
```

or

```bash
yarn add axios
```

#### 📌 Using Axios in React

GET with loading/error states and safe cancellation:
```javascript
// src/components/UsersList.jsx
import { useEffect, useState } from 'react';
import axios from 'axios';

const API_URL = import.meta.env.VITE_API_URL;

export default function UsersList() {
  const [users, setUsers] = useState([]);
  const [loading, setLoading] = useState(false);
  const [error, setError] = useState(null);

  useEffect(() => {
    const controller = new AbortController();
    setLoading(true);

    axios
      .get(`${API_URL}/users`, { signal: controller.signal })
      .then((res) => setUsers(res.data))
      .catch((err) => {
        if (axios.isCancel(err)) return; // request was canceled
        setError(err.response?.data?.message || err.message);
      })
      .finally(() => setLoading(false));

    return () => controller.abort(); // cancel on unmount
  }, []);

  if (loading) return <p>Loading…</p>;
  if (error) return <p style={{ color: 'crimson' }}>Error: {error}</p>;

  return (
    <ul>
      {users.map((u) => (
        <li key={u.id}>{u.name}</li>
      ))}
    </ul>
  );
}
```

POST Request (Submitting a Form):
```jsx
import { useState } from "react";
import axios from "axios";

function SignupForm() {
  const [form, setForm] = useState({ name: "", email: "" });

  const handleChange = (e) => {
    setForm({ ...form, [e.target.name]: e.target.value });
  };

  const handleSubmit = async (e) => {
    e.preventDefault();
    try {
      const res = await axios.post("https://jsonplaceholder.typicode.com/users", form);
      alert("User created: " + JSON.stringify(res.data));
    } catch (error) {
      console.error("Signup failed:", error);
    }
  };

  return (
    <form onSubmit={handleSubmit}>
      <input name="name" placeholder="Name" value={form.name} onChange={handleChange} />
      <input name="email" placeholder="Email" value={form.email} onChange={handleChange} />
      <button type="submit">Sign Up</button>
    </form>
  );
}

export default SignupForm;
```

PUT & DELETE Requests:
```jsx
import { useState } from "react";
import axios from "axios";

function UserManagement() {
  const [user, setUser] = useState(null);

  const updateUser = async (id, data) => {
    try {
      const response = await axios.put(`https://jsonplaceholder.typicode.com/users/${id}`, data);
      setUser(response.data);
      alert("User updated: " + JSON.stringify(response.data));
    } catch (error) {
      console.error("Update failed:", error);
    }
  };

  const deleteUser = async (id) => {
    try {
      await axios.delete(`https://jsonplaceholder.typicode.com/users/${id}`);
      setUser(null);
      alert("User deleted");
    } catch (error) {
      console.error("Delete failed:", error);
    }
  };

  return (
    <div>
      <button onClick={() => updateUser(1, { name: "New Name" })}>Update User</button>
      <button onClick={() => deleteUser(1)}>Delete User</button>
      {user && <pre>{JSON.stringify(user, null, 2)}</pre>}
    </div>
  );
}

export default UserManagement;
```


#### ⚙️ Axios Features

**🔄 Axios Instance (Reusable Configuration)**
```javascript
// src/api/axiosClient.js
import axios from 'axios';

export const api = axios.create({
  baseURL: import.meta.env.VITE_API_URL || 'http://localhost:5000/api',
  timeout: 10000,          // 10s timeout
  withCredentials: false,  // set true if you use cookie-based auth
  headers: { 'Content-Type': 'application/json' },
});
```

```javascript
// src/services/users.js
import { api } from '../api/axiosClient';

export const UsersApi = {
  list: (params) => api.get('/users', { params }).then((r) => r.data),
  create: (payload) => api.post('/users', payload).then((r) => r.data),
  remove: (id) => api.delete(`/users/${id}`).then((r) => r.data),
};
```

Use in a component:
```jsx
import { useEffect, useState } from 'react';
import { UsersApi } from '../services/users';

export default function UsersList() {
  const [data, setData] = useState([]);
  const [loading, setLoading] = useState(true);
  const [err, setErr] = useState(null);

  useEffect(() => {
    let active = true;
    UsersApi.list()
      .then((d) => active && setData(d))
      .catch((e) => active && setErr(e.response?.data?.message || e.message))
      .finally(() => active && setLoading(false));
    return () => { active = false };
  }, []);

  // render...
}
```

**Interceptors for auth and error handling**

Attach a JWT to every request:
```javascript
// src/api/axiosClient.js (continued)
api.interceptors.request.use(
  (config) => {
    const token = localStorage.getItem('accessToken');
    if (token) config.headers.Authorization = `Bearer ${token}`;
    return config;
  },
  (error) => Promise.reject(error)
);
```

```javascript
// src/api/axiosClient.js (continued)
api.interceptors.response.use(
  (res) => res,
  async (error) => {
    const config = error.config;
    const shouldRetry =
      (!error.response || error.response.status >= 500) &&
      (config.__retryCount || 0) < 3;

    if (shouldRetry) {
      config.__retryCount = (config.__retryCount || 0) + 1;
      const delay = 200 * 2 ** config.__retryCount; // 200ms, 400ms, 800ms
      await new Promise((r) => setTimeout(r, delay));
      return api(config);
    }
    return Promise.reject(error);
  }
);
```

**Refresh token flow (sketch)**

- When a 401 is returned, call a refresh endpoint, update the token, and retry original requests.
- Handle concurrency to avoid multiple refresh calls.

```javascript
// src/api/axiosClient.js (sketch)
let isRefreshing = false;
let queue = [];

const runQueue = (err, token) => {
  queue.forEach(({ resolve, reject }) => (token ? resolve(token) : reject(err)));
  queue = [];
};

api.interceptors.response.use(
  (res) => res,
  async (error) => {
    const original = error.config;
    if (error.response?.status === 401 && !original._retry) {
      original._retry = true;

      if (isRefreshing) {
        return new Promise((resolve, reject) => {
          queue.push({
            resolve: (token) => {
              original.headers.Authorization = `Bearer ${token}`;
              resolve(api(original));
            },
            reject,
          });
        });
      }

      isRefreshing = true;
      try {
        const refreshToken = localStorage.getItem('refreshToken');
        const { data } = await axios.post(
          '/auth/refresh',
          { refreshToken },
          { baseURL: api.defaults.baseURL }
        );
        localStorage.setItem('accessToken', data.accessToken);
        api.defaults.headers.common.Authorization = `Bearer ${data.accessToken}`;
        runQueue(null, data.accessToken);
        return api(original);
      } catch (err) {
        runQueue(err, null);
        localStorage.removeItem('accessToken');
        localStorage.removeItem('refreshToken');
        // e.g., redirect to login
        // window.location.href = '/login';
        return Promise.reject(err);
      } finally {
        isRefreshing = false;
      }
    }
    return Promise.reject(error);
  }
);
```


**A) Cancel and debounce (live search)**
```javascript
import { useEffect, useState } from 'react';
import axios from 'axios';
const API_URL = import.meta.env.VITE_API_URL;

export default function SearchBox() {
  const [q, setQ] = useState('');
  const [results, setResults] = useState([]);

  useEffect(() => {
    if (!q.trim()) {
      setResults([]);
      return;
    }
    const controller = new AbortController();
    const id = setTimeout(() => {
      axios
        .get(`${API_URL}/search`, { params: { q }, signal: controller.signal })
        .then((r) => setResults(r.data))
        .catch((e) => {
          if (!axios.isCancel(e)) console.error(e);
        });
    }, 300); // debounce 300ms

    return () => {
      clearTimeout(id);
      controller.abort();
    };
  }, [q]);

  return (
    <>
      <input value={q} onChange={(e) => setQ(e.target.value)} placeholder="Search…" />
      <pre>{JSON.stringify(results, null, 2)}</pre>
    </>
  );
}
```

**B) File upload with progress**
```javascript
import { useState } from 'react';
import { api } from '../api/axiosClient';

export default function FileUploader() {
  const [progress, setProgress] = useState(0);

  const upload = async (file) => {
    const formData = new FormData();
    formData.append('file', file);
    await api.post('/files', formData, {
      headers: { 'Content-Type': 'multipart/form-data' },
      onUploadProgress: (evt) => {
        if (!evt.total) return;
        setProgress(Math.round((evt.loaded * 100) / evt.total));
      },
    });
  };

  return (
    <div>
      <input type="file" onChange={(e) => e.target.files[0] && upload(e.target.files[0])} />
      {progress > 0 && <p>Uploading: {progress}%</p>}
    </div>
  );
}
```

**C) File download (e.g., PDF)**
```javascript
import { api } from '../api/axiosClient';

export async function downloadReport(id) {
  const res = await api.get(`/reports/${id}`, { responseType: 'blob' });
  const blob = new Blob([res.data], { type: 'application/pdf' });
  const url = URL.createObjectURL(blob);
  const a = document.createElement('a');
  a.href = url;
  a.download = `report-${id}.pdf`;
  document.body.appendChild(a);
  a.click();
  a.remove();
  URL.revokeObjectURL(url);
}
```

**D) Concurrency: load several resources in parallel**
```javascript
const [users, posts] = await Promise.all([api.get('/users'), api.get('/posts')]);
setUsers(users.data);
setPosts(posts.data);
```

**E) Timeouts and quick aborts**
```javascript
// Already set a global timeout in axiosClient (e.g., 10s).
// For special cases, override per request:
api.get('/slow', { timeout: 3000 }).catch((e) => console.log('Timed out', e.code));
```

**F) Query params**
```javascript
api.get('/search', { params: { q: 'laptops', page: 2, tags: ['gaming', '16gb'] } });
```

**G) Cookies and CSRF (when using cookie-based auth)**
```javascript
// axiosClient
export const api = axios.create({
  baseURL: import.meta.env.VITE_API_URL,
  withCredentials: true, // send cookies
  xsrfCookieName: 'XSRF-TOKEN', // optional, depends on backend
  xsrfHeaderName: 'X-XSRF-TOKEN',
});
```

**H) Integrate with React Query for caching, retries, dedup**

```bash
npm install @tanstack/react-query
```

```jsx
import { QueryClient, QueryClientProvider, useQuery } from '@tanstack/react-query';
import { UsersApi } from './services/users';

const qc = new QueryClient();

function Users() {
  const { data, isLoading, error } = useQuery({ queryKey: ['users'], queryFn: UsersApi.list });
  // ...
}

export default function App() {
  return (
    <QueryClientProvider client={qc}>
      <Users />
    </QueryClientProvider>
  );
}
```


## 🔹What is the Strict Mode in React?

**StrictMode** is a development-only feature in React.
It does not affect production builds and doesn’t render anything to the DOM.

Instead, it helps developers:

- Detect potential problems in their React code.
- Enforce best practices.
- Prepare apps for future versions of React.

#### 🛠 Enable Strict Mode

Wrap your app (or part of your app) in `<React.StrictMode>` inside `index.js`:
```jsx
import React from 'react';
import ReactDOM from 'react-dom/client';
import App from './App';

ReactDOM.createRoot(document.getElementById('root')).render(
  <React.StrictMode>
    <App />
  </React.StrictMode>
);
```

> 👉 It only applies in development mode.

#### 🔍 What Strict Mode Checks For

**1. Unsafe Lifecycles**
- Warns if you use deprecated lifecycle methods (`componentWillMount`, `componentWillReceiveProps`, etc.).

**2. Legacy String Refs**
- Warns if you use old ref syntax (`ref="myRef"`) instead of `React.createRef()` or `useRef()`.

**3. Unexpected Side Effects**
- Runs functions like `useEffect` twice in development to ensure code is side-effect free and resilient.

**4. Deprecated APIs**
- Warns about APIs that React plans to remove.

**5. Detects Missing Keys in Lists**
- Helps prevent rendering issues when using `.map()` for lists.


**📌 Example 1: Detecting Side Effects**
```jsx
import { useEffect } from "react";

function Example() {
  useEffect(() => {
    console.log("Effect executed!");
  }, []);

  return <h1>Hello Strict Mode</h1>;
}

export default Example;
```

> When wrapped in `StrictMode`, the log will appear twice in development because React is checking for side effects.

**📌 Example 2: Catching Deprecated Lifecycle Methods**
```jsx
import React from "react";

class OldComponent extends React.Component {
  componentWillMount() {
    console.log("This method is deprecated!");
  }

  render() {
    return <h2>Old Component</h2>;
  }
}

export default OldComponent;
```

> 👉 In **Strict Mode**, React will warn you in the console about using `componentWillMount`.


## 🔹How does React handle server-side rendering (SSR)?

By default, React is a client-side library → it runs in the browser, rendering UI after JavaScript loads.

**👉 Problem:** On first page load, users (and search engines like Google) see a blank screen until JS is downloaded & executed.

**👉 Solution:** Server-Side Rendering (SSR) → React components are rendered on the server into HTML, sent to the browser, and then React "hydrates" the page (attaches event listeners, making it interactive).

#### 🔄 How SSR Works in React

**1. Client Request:** User requests a page (`/products`).
**2. Server Render:** React on the server converts components → HTML string.
**3. Send HTML:** Browser immediately displays full HTML (fast, SEO-friendly).
**4. Hydration:** React loads JavaScript, attaches interactivity to that HTML.

#### 🛠 Implementing SSR in React

**1. Without Frameworks (using `react-dom/server`)**

React provides an API:

- `renderToString()` → Converts components to HTML string.
- `renderToPipeableStream()` (React 18+) → Supports streaming SSR (send HTML chunks before full render finishes).

👉 Example with Express.js:
```jsx
// server.js
import express from "express";
import React from "react";
import { renderToString } from "react-dom/server";
import App from "./src/App";

const app = express();

app.get("*", (req, res) => {
  const html = renderToString(<App />);
  res.send(`
    <!DOCTYPE html>
    <html>
      <head><title>SSR Example</title></head>
      <body>
        <div id="root">${html}</div>
        <script src="/client_bundle.js"></script>
      </body>
    </html>
  `);
});

app.listen(3000, () => console.log("Server running on http://localhost:3000"));
```

👉 On the browser, React hydrates the markup:
```jsx
import React from "react";
import { hydrateRoot } from "react-dom/client";
import App from "./App";

hydrateRoot(document.getElementById("root"), <App />);
```

**2. With Frameworks (Recommended in Professional Projects)**

Most teams don’t build SSR from scratch → they use frameworks like:

- **Next.js** → Most popular React SSR framework.
- **Remix** → SSR with data-loading focus.

👉 Example with **Next.js** (much simpler):

```jsx
// pages/index.js
export default function Home({ products }) {
  return (
    <div>
      <h1>Product List</h1>
      <ul>
        {products.map((p) => (
          <li key={p.id}>{p.name}</li>
        ))}
      </ul>
    </div>
  );
}

export async function getServerSideProps() {
  const res = await fetch("https://fakestoreapi.com/products");
  const products = await res.json();
  return { props: { products } };
}
```

> ✅ On every request, Next.js renders HTML on the server → SEO-friendly, faster first load.

**📊 Benefits of SSR in React**

**1. SEO Optimization** → Search engines see full HTML instead of blank divs.
(Important for blogs, e-commerce, landing pages.)
**2. Faster First Paint (TTFB)** → User sees UI quickly.
**3. Better Performance on Slow Devices** → Less work for client’s browser.
**4. Social Media Previews** → Sharing links (Twitter, LinkedIn, WhatsApp) shows meta tags correctly.

⚠️ **Challenges of SSR**

**1. Increased Server Load** → Server does rendering work.
**2. Complexity** → Managing hydration mismatches (server HTML ≠ client HTML).
**3. State Management** → Handling global state (Redux, Context) between server & client.
**4. Data Fetching** → Needs server + client coordination.



## React-Hook-Form

React Hook Form is a library that helps you manage form state and validation in React applications. It provides a simple and efficient way to handle forms with minimal re-renders and better performance.

Below is a complete, TypeScript, end-to-end example using React Hook Form + Zod (frontend) and Express + Mongoose (backend), with Axios for submission, strong password validation, Google reCAPTCHA v2, proper error handling, and saving to MongoDB.

- **Frontend**: React Hook Form + Zod validation, reCAPTCHA, error handling, Axios POST
- **Backend**: Express + Mongoose, zod input validation, reCAPTCHA verification, bcrypt password hashing, duplicate email checks, and robust error responses

#### 🧱 Folder Structure
```pgsql
/fullstack-signup
  /client  (React + Vite + TS)
    src/
      api/axios.ts
      validation/userSchema.ts
      types.ts
      App.tsx
      main.tsx
      index.css
    index.html
    package.json
    vite.config.ts
    .env        # REACT side (Vite prefix: VITE_)
  /server  (Express + TS + Mongoose)
    src/
      models/User.ts
      routes/auth.ts
      utils/validate.ts
      utils/password.ts
      server.ts
      types.ts
    package.json
    tsconfig.json
    .env        # SERVER secrets
```

#### ▶️ Quick Start

**1) Backend (server)**
```bash
mkdir -p fullstack-signup/server && cd fullstack-signup/server
npm init -y
npm i express mongoose dotenv zod bcrypt jsonwebtoken cors helmet express-rate-limit axios
npm i -D typescript ts-node-dev @types/express @types/cors @types/node
npx tsc --init
```

`server/.env`
```ts
import dotenv from "dotenv";
dotenv.config();

const get = (name: string, fallback?: string) => {
  const v = process.env[name] ?? fallback;
  if (v === undefined) {
    throw new Error(`Missing required env var: ${name}`);
  }
  return v;
};

export const env = {
  PORT: parseInt(get("PORT", "4000"), 10),
  MONGODB_URI: get("MONGODB_URI"),
  RECAPTCHA_SECRET: get("RECAPTCHA_SECRET"),
  CLIENT_ORIGIN: get("CLIENT_ORIGIN"),
  NODE_ENV: get("NODE_ENV", "production"),
};
```

`server/tsconfig.json (minimal)`
```json
{
  "compilerOptions": {
    "target": "ES2020",
    "module": "CommonJS",
    "outDir": "./dist",
    "rootDir": "./src",
    "strict": true,
    "esModuleInterop": true,
    "skipLibCheck": true,
    "forceConsistentCasingInFileNames": true
  }
}
```

`server/package.json (scripts)`
```json
{
  "name": "signup-server",
  "version": "1.0.0",
  "type": "commonjs",
  "scripts": {
    "dev": "ts-node-dev --respawn --transpile-only src/server.ts",
    "build": "tsc",
    "start": "node dist/server.js"
  }
}
```

### Server Code

`server/src/types.ts`
```ts
export type ApiResponse<T> = {
  success: boolean;
  message: string;
  data?: T;
  errors?: Record<string, string[]>;
};
```

`server/src/utils/password.ts`
```ts
export const STRONG_PASSWORD_REGEX =
  /^(?=.*[a-z])(?=.*[A-Z])(?=.*\d)(?=.*[ !"#$%&'()*+,\-./:;<=>?@[\\\]^_`{|}~]).{8,64}$/;
// At least 8 chars, 1 lowercase, 1 uppercase, 1 number, 1 special, up to 64, allows most symbols
```

`server/src/utils/validate.ts`
```ts
import { z } from "zod";
import { STRONG_PASSWORD_REGEX } from "./password";

export const registerSchema = z.object({
  firstName: z.string().min(2).max(50),
  lastName: z.string().min(2).max(50),
  email: z.string().email(),
  password: z.string().regex(STRONG_PASSWORD_REGEX, {
    message:
      "Password must be 8-64 chars and include upper, lower, number, and special.",
  }),
  confirmPassword: z.string(),
  role: z.enum(["user", "admin", "moderator"]),
  gender: z.enum(["male", "female", "other"]),
  terms: z.boolean().refine((v) => v === true, "You must accept the terms."),
  bio: z.string().max(500).optional(),
  recaptchaToken: z.string().min(10),
}).refine((data) => data.password === data.confirmPassword, {
  path: ["confirmPassword"],
  message: "Passwords do not match.",
});

export type RegisterInput = z.infer<typeof registerSchema>;
```

`server/src/models/User.ts`
```ts
import mongoose, { Schema, Document, Model } from "mongoose";
import bcrypt from "bcrypt";

export interface IUser extends Document {
  firstName: string;
  lastName: string;
  email: string;
  role: "user" | "admin" | "moderator";
  gender: "male" | "female" | "other";
  bio?: string;
  passwordHash: string;
  comparePassword(candidate: string): Promise<boolean>;
}

const UserSchema = new Schema<IUser>(
  {
    firstName: { type: String, required: true, trim: true },
    lastName:  { type: String, required: true, trim: true },
    email:     { type: String, required: true, unique: true, lowercase: true, trim: true },
    role:      { type: String, enum: ["user", "admin", "moderator"], default: "user" },
    gender:    { type: String, enum: ["male", "female"], required: true },
    bio:       { type: String },
    passwordHash: { type: String, required: true },
  },
  { timestamps: true }
);

UserSchema.methods.comparePassword = function (candidate: string) {
  return bcrypt.compare(candidate, this.passwordHash);
};

UserSchema.pre("save", async function (next) {
  const user = this as IUser;
  if (user.isModified("passwordHash")) {
    // Already hashed—do nothing
    return next();
  }
  next();
});

let User: Model<IUser>;
User = mongoose.models.User || mongoose.model<IUser>("User", UserSchema);

export default User;
```

`server/src/routes/auth.ts`
```ts
import { Router } from "express";
import { z } from "zod";
import bcrypt from "bcrypt";
import User from "../models/User";
import { registerSchema } from "../utils/validate";
import axios from "axios";
import type { ApiResponse } from "../types";

const router = Router();

router.post("/register", async (req, res) => {
  try {
    const parsed = registerSchema.safeParse(req.body);
    if (!parsed.success) {
      const errors: Record<string, string[]> = {};
      parsed.error.errors.forEach((e) => {
        const key = e.path.join(".") || "form";
        errors[key] = errors[key] || [];
        errors[key].push(e.message);
      });
      const payload: ApiResponse<null> = {
        success: false,
        message: "Validation failed",
        errors,
      };
      return res.status(400).json(payload);
    }

    const {
      firstName, lastName, email, password, role, gender, bio, recaptchaToken,
    } = parsed.data;

    // Verify reCAPTCHA with Google
    const secret = process.env.RECAPTCHA_SECRET!;
    const verificationURL = "https://www.google.com/recaptcha/api/siteverify";
    const verify = await axios.post(
      verificationURL,
      new URLSearchParams({
        secret,
        response: recaptchaToken,
        remoteip: req.ip || "",
      }),
      { headers: { "Content-Type": "application/x-www-form-urlencoded" } }
    );

    if (!verify.data.success) {
      return res.status(400).json({
        success: false,
        message: "Captcha verification failed.",
        errors: { recaptchaToken: ["Invalid captcha."] },
      } satisfies ApiResponse<null>);
    }

    const existing = await User.findOne({ email });
    if (existing) {
      return res.status(409).json({
        success: false,
        message: "Email already in use.",
        errors: { email: ["Email is already registered."] },
      } satisfies ApiResponse<null>);
    }

    const passwordHash = await bcrypt.hash(password, 12);
    const user = await User.create({
      firstName, lastName, email, role, gender, bio, passwordHash,
    });

    return res.status(201).json({
      success: true,
      message: "Registration successful",
      data: { id: user._id, email: user.email, firstName: user.firstName },
    } satisfies ApiResponse<{ id: string; email: string; firstName: string }>);
  } catch (err: any) {
    console.error(err);
    return res.status(500).json({
      success: false,
      message: "Internal server error",
    } satisfies ApiResponse<null>);
  }
});

export default router;
```

`server/src/server.ts`
```ts
import express from "express";
import dotenv from "dotenv";
import mongoose from "mongoose";
import cors from "cors";
import helmet from "helmet";
import rateLimit from "express-rate-limit";
import authRoutes from "./routes/auth";

dotenv.config();

const app = express();
app.use(express.json({ limit: "1mb" }));
app.use(helmet());

// CORS (allow your client)
app.use(
  cors({
    origin: process.env.CLIENT_ORIGIN,
    credentials: true,
  })
);

// Basic rate limiting for auth routes
const limiter = rateLimit({
  windowMs: 60_000,
  max: 60,
});
app.use("/api/", limiter);

app.use("/api", authRoutes);

// Health
app.get("/health", (_req, res) => res.send("OK"));

// Start
const PORT = process.env.PORT || 5000;

(async () => {
  try {
    await mongoose.connect(process.env.MONGODB_URI!);
    console.log("MongoDB connected");
    app.listen(PORT, () =>
      console.log(`Server running on http://localhost:${PORT}`)
    );
  } catch (e) {
    console.error("Failed to start server", e);
    process.exit(1);
  }
})();
```

**Run the backend:**
```bash
npm run dev
```




### Frontend (client)

```bash
cd ../
mkdir -p client && cd client
npm create vite@latest . -- --template react-ts
npm i axios react-hook-form zod @hookform/resolvers react-google-recaptcha
npm run dev
```

client/.env (Vite env vars must start with `VITE_`)
```ini
VITE_API_URL=http://localhost:5000/api
VITE_RECAPTCHA_SITE_KEY=your-site-key
```

`client/src/types.ts`
```ts
export type RegisterFormValues = {
  firstName: string;
  lastName: string;
  email: string;
  password: string;
  confirmPassword: string;
  role: "user" | "admin" | "moderator";
  gender: "male" | "female" | "other";
  terms: boolean;
  bio?: string;
  recaptchaToken: string;
};

export type ApiResponse<T> = {
  success: boolean;
  message: string;
  data?: T;
  errors?: Record<string, string[]>;
};
```

`client/src/api/axios.ts`
```ts
import axios from "axios";

const api = axios.create({
  baseURL: import.meta.env.VITE_API_BASE,
  withCredentials: true,
  headers: { "Content-Type": "application/json" },
});

// Optionally add interceptors for auth tokens/global errors
// api.interceptors.request.use(config => { ...; return config; });

export default api;
```

`client/src/validation/userSchema.ts`
```ts
import { z } from "zod";

export const STRONG_PASSWORD_REGEX =
  /^(?=.*[a-z])(?=.*[A-Z])(?=.*\d)(?=.*[ !"#$%&'()*+,\-./:;<=>?@[\\\]^_`{|}~]).{8,64}$/;

export const registerSchema = z.object({
  firstName: z.string().min(2, "Min 2 chars").max(50),
  lastName: z.string().min(2, "Min 2 chars").max(50),
  email: z.string().email("Invalid email"),
  password: z
    .string()
    .regex(STRONG_PASSWORD_REGEX, "8-64, upper/lower/number/special required"),
  confirmPassword: z.string(),
  role: z.enum(["user", "admin", "moderator"]),
  gender: z.enum(["male", "female", "other"]),
  terms: z.literal(true, { errorMap: () => ({ message: "Accept the terms" }) }),
  bio: z.string().max(500).optional(),
  recaptchaToken: z.string().min(10, "Captcha is required"),
}).refine((v) => v.password === v.confirmPassword, {
  message: "Passwords do not match",
  path: ["confirmPassword"],
});

export type RegisterSchema = z.infer<typeof registerSchema>;
```

`client/src/App.tsx`
```tsx
import { useRef, useState } from "react";
import { useForm } from "react-hook-form";
import { zodResolver } from "@hookform/resolvers/zod";
import ReCAPTCHA from "react-google-recaptcha";
import api from "./api/axios";
import { registerSchema, RegisterSchema } from "./validation/userSchema";
import type { ApiResponse } from "./types";

function App() {
  const [serverMessage, setServerMessage] = useState<string | null>(null);
  const [submitting, setSubmitting] = useState(false);
  const recaptchaRef = useRef<ReCAPTCHA>(null);

  const {
    register,
    handleSubmit,
    setValue,
    formState: { errors },
    reset,
  } = useForm<RegisterSchema>({
    resolver: zodResolver(registerSchema),
    defaultValues: {
      role: "user",
      gender: "other",
      terms: false,
    },
  });

  const onCaptchaChange = (token: string | null) => {
    setValue("recaptchaToken", token || "");
  };

  const onSubmit = async (values: RegisterSchema) => {
    try {
      setSubmitting(true);
      setServerMessage(null);

      const res = await api.post<ApiResponse<{ id: string; email: string }>>(
        "/register",
        values
      );

      if (res.data.success) {
        setServerMessage(`✅ Registered: ${res.data.data?.email}`);
        reset({ role: "user", gender: "other", terms: false, recaptchaToken: "" });
        recaptchaRef.current?.reset();
      } else {
        setServerMessage(res.data.message || "Registration failed.");
      }
    } catch (err: any) {
      if (err.response?.data?.errors) {
        const e = err.response.data as ApiResponse<null>;
        setServerMessage(
          "❌ " + (e.message || "Validation error. Check fields and try again.")
        );
      } else {
        setServerMessage("❌ Network/server error. Please try again.");
      }
    } finally {
      setSubmitting(false);
    }
  };

  return (
    <main style={{ maxWidth: 560, margin: "40px auto", padding: 16 }}>
      <h1>Full Signup (React Hook Form + Axios + Captcha)</h1>
      <p style={{ color: "#666" }}>
        Password: 8–64 chars, include upper, lower, number & special.
      </p>

      <form onSubmit={handleSubmit(onSubmit)} noValidate>
        <div style={{ display: "grid", gap: 12 }}>
          {/* First Name */}
          <label>
            First Name
            <input {...register("firstName")} placeholder="Jane" />
            {errors.firstName && (
              <small style={{ color: "crimson" }}>{errors.firstName.message}</small>
            )}
          </label>

          {/* Last Name */}
          <label>
            Last Name
            <input {...register("lastName")} placeholder="Doe" />
            {errors.lastName && (
              <small style={{ color: "crimson" }}>{errors.lastName.message}</small>
            )}
          </label>

          {/* Email */}
          <label>
            Email
            <input type="email" {...register("email")} placeholder="jane@acme.com" />
            {errors.email && (
              <small style={{ color: "crimson" }}>{errors.email.message}</small>
            )}
          </label>

          {/* Password */}
          <label>
            Password
            <input type="password" {...register("password")} />
            {errors.password && (
              <small style={{ color: "crimson" }}>{errors.password.message}</small>
            )}
          </label>

          {/* Confirm Password */}
          <label>
            Confirm Password
            <input type="password" {...register("confirmPassword")} />
            {errors.confirmPassword && (
              <small style={{ color: "crimson" }}>
                {errors.confirmPassword.message}
              </small>
            )}
          </label>

          {/* Role */}
          <label>
            Role
            <select {...register("role")}>
              <option value="user">User</option>
              <option value="admin">Admin</option>
              <option value="moderator">Moderator</option>
            </select>
            {errors.role && (
              <small style={{ color: "crimson" }}>{errors.role.message}</small>
            )}
          </label>

          {/* Gender */}
          <fieldset>
            <legend>Gender</legend>
            <label>
              <input type="radio" value="male" {...register("gender")} /> Male
            </label>
            <label>
              <input type="radio" value="female" {...register("gender")} /> Female
            </label>
            <label>
              <input type="radio" value="other" {...register("gender")} /> Other
            </label>
            {errors.gender && (
              <small style={{ color: "crimson" }}>{errors.gender.message}</small>
            )}
          </fieldset>

          {/* Bio */}
          <label>
            Bio (optional)
            <textarea rows={4} {...register("bio")} placeholder="Tell us about you..." />
            {errors.bio && (
              <small style={{ color: "crimson" }}>{errors.bio.message}</small>
            )}
          </label>

          {/* Terms */}
          <label>
            <input type="checkbox" {...register("terms")} /> I accept the Terms
            {errors.terms && (
              <small style={{ color: "crimson", display: "block" }}>
                {errors.terms.message}
              </small>
            )}
          </label>

          {/* Captcha */}
          <ReCAPTCHA
            sitekey={import.meta.env.VITE_RECAPTCHA_SITE_KEY}
            onChange={onCaptchaChange}
            ref={recaptchaRef}
          />
          {errors.recaptchaToken && (
            <small style={{ color: "crimson" }}>
              {errors.recaptchaToken.message}
            </small>
          )}

          {/* Submit */}
          <button type="submit" disabled={submitting}>
            {submitting ? "Submitting..." : "Create Account"}
          </button>
        </div>
      </form>

      {serverMessage && (
        <div
          style={{
            marginTop: 16,
            padding: 12,
            background: "#f7f7f7",
            borderRadius: 8,
          }}
        >
          {serverMessage}
        </div>
      )}
    </main>
  );
}

export default App;
```

`client/src/main.tsx`
```tsx
import React from "react";
import ReactDOM from "react-dom/client";
import App from "./App";
import "./index.css";

ReactDOM.createRoot(document.getElementById("root") as HTMLElement).render(
  <React.StrictMode>
    <App />
  </React.StrictMode>
);
```

**Run the frontend:**
```bash
npm run dev
```


### 🎨 Full UI Implementation (Frontend)

#### 🛠️ Setup

Install dependencies:
```bash
npm install @mui/material @mui/icons-material @emotion/react @emotion/styled
npm install react-hook-form yup @hookform/resolvers axios
npm install react-google-recaptcha
```

`src/components/RegisterForm.tsx`
```tsx
import React, { useState } from "react";
import {
  Box,
  Button,
  CircularProgress,
  Container,
  Grid,
  TextField,
  Typography,
  Alert,
  InputAdornment,
  IconButton,
} from "@mui/material";
import { Visibility, VisibilityOff } from "@mui/icons-material";
import { useForm, Controller } from "react-hook-form";
import { yupResolver } from "@hookform/resolvers/yup";
import * as yup from "yup";
import axios from "axios";
import ReCAPTCHA from "react-google-recaptcha";

// ✅ Validation Schema
const schema = yup.object().shape({
  name: yup.string().required("Full Name is required"),
  email: yup.string().email("Invalid email").required("Email is required"),
  password: yup
    .string()
    .required("Password is required")
    .min(8, "At least 8 characters")
    .matches(/[A-Z]/, "Must contain uppercase letter")
    .matches(/[a-z]/, "Must contain lowercase letter")
    .matches(/[0-9]/, "Must contain a number")
    .matches(/[@$!%*?&]/, "Must contain a special character"),
  confirmPassword: yup
    .string()
    .oneOf([yup.ref("password")], "Passwords must match"),
});

type FormData = yup.InferType<typeof schema>;

export default function RegisterForm() {
  const [loading, setLoading] = useState(false);
  const [showPassword, setShowPassword] = useState(false);
  const [captchaToken, setCaptchaToken] = useState<string | null>(null);
  const [error, setError] = useState<string | null>(null);
  const [success, setSuccess] = useState<string | null>(null);

  const {
    handleSubmit,
    control,
    reset,
    formState: { errors },
  } = useForm<FormData>({
    resolver: yupResolver(schema),
  });

  const onSubmit = async (data: FormData) => {
    if (!captchaToken) {
      setError("Please complete the captcha");
      return;
    }
    setError(null);
    setSuccess(null);
    setLoading(true);

    try {
      const res = await axios.post("http://localhost:5000/api/register", {
        ...data,
        captchaToken,
      });

      setSuccess(res.data.message || "Registration successful!");
      reset();
    } catch (err: any) {
      setError(err.response?.data?.message || "Something went wrong");
    } finally {
      setLoading(false);
    }
  };

  return (
    <Container maxWidth="sm">
      <Box
        sx={{
          mt: 5,
          p: 4,
          border: "1px solid #ddd",
          borderRadius: 3,
          boxShadow: 3,
          backgroundColor: "white",
        }}
      >
        <Typography variant="h4" textAlign="center" gutterBottom>
          Register
        </Typography>

        {error && <Alert severity="error">{error}</Alert>}
        {success && <Alert severity="success">{success}</Alert>}

        <form onSubmit={handleSubmit(onSubmit)} noValidate>
          <Grid container spacing={2} mt={1}>
            <Grid item xs={12}>
              <Controller
                name="name"
                control={control}
                defaultValue=""
                render={({ field }) => (
                  <TextField
                    {...field}
                    label="Full Name"
                    fullWidth
                    error={!!errors.name}
                    helperText={errors.name?.message}
                  />
                )}
              />
            </Grid>

            <Grid item xs={12}>
              <Controller
                name="email"
                control={control}
                defaultValue=""
                render={({ field }) => (
                  <TextField
                    {...field}
                    label="Email"
                    fullWidth
                    error={!!errors.email}
                    helperText={errors.email?.message}
                  />
                )}
              />
            </Grid>

            <Grid item xs={12}>
              <Controller
                name="password"
                control={control}
                defaultValue=""
                render={({ field }) => (
                  <TextField
                    {...field}
                    type={showPassword ? "text" : "password"}
                    label="Password"
                    fullWidth
                    error={!!errors.password}
                    helperText={errors.password?.message}
                    InputProps={{
                      endAdornment: (
                        <InputAdornment position="end">
                          <IconButton
                            onClick={() => setShowPassword((prev) => !prev)}
                          >
                            {showPassword ? <VisibilityOff /> : <Visibility />}
                          </IconButton>
                        </InputAdornment>
                      ),
                    }}
                  />
                )}
              />
            </Grid>

            <Grid item xs={12}>
              <Controller
                name="confirmPassword"
                control={control}
                defaultValue=""
                render={({ field }) => (
                  <TextField
                    {...field}
                    type="password"
                    label="Confirm Password"
                    fullWidth
                    error={!!errors.confirmPassword}
                    helperText={errors.confirmPassword?.message}
                  />
                )}
              />
            </Grid>

            <Grid item xs={12} display="flex" justifyContent="center">
              <ReCAPTCHA
                sitekey="YOUR_RECAPTCHA_SITE_KEY"
                onChange={(token) => setCaptchaToken(token)}
              />
            </Grid>

            <Grid item xs={12}>
              <Button
                type="submit"
                fullWidth
                variant="contained"
                color="primary"
                disabled={loading}
                startIcon={loading && <CircularProgress size={20} />}
              >
                {loading ? "Submitting..." : "Register"}
              </Button>
            </Grid>
          </Grid>
        </form>
      </Box>
    </Container>
  );
}
```


## What is Lazy Loading in React?

⚡Lazy loading (also called code splitting) means loading components only when they’re needed, instead of loading the entire app at once.

By default, React bundles the whole app into one large JavaScript file. For big applications, this increases initial load time.

Lazy Loading helps by splitting code into smaller chunks → React loads them on demand when the user visits that part of the app.


**🔑 How Lazy Loading Works in React**

React provides:

- `React.lazy()`: A function that lets you render a dynamic import as a regular component.
- `Suspense`: A component that wraps lazy components and allows you to show a fallback (e.g., loading spinner) while the lazy component is loading.

📝 Example: Without Lazy Loading
```tsx
import React from "react";
import Dashboard from "./components/Dashboard";
import Profile from "./components/Profile";

export default function App() {
  return (
    <div>
      <Dashboard />
      <Profile />
    </div>
  );
}
```
⚠️ Problem:
Both `Dashboard` and `Profile` are bundled and loaded on initial render, even if the user never visits Profile.


📝 Example: With Lazy Loading
```tsx
import React, { Suspense, lazy } from "react";

const Dashboard = lazy(() => import("./components/Dashboard"));
const Profile = lazy(() => import("./components/Profile"));

export default function App() {
  return (
    <div>
      <Suspense fallback={<div>Loading...</div>}>
        <Dashboard />
        <Profile />
      </Suspense>
    </div>
  );
}
```

✅ Now, React will only load Dashboard or Profile when they’re rendered.
✅ `<Suspense>` shows a loading spinner/loader until the component is ready.

🌍 Example: React Router + Lazy Loading
```tsx
import React, { Suspense, lazy } from "react";
import { BrowserRouter as Router, Routes, Route } from "react-router-dom";

const Home = lazy(() => import("./pages/Home"));
const About = lazy(() => import("./pages/About"));
const Contact = lazy(() => import("./pages/Contact"));

export default function App() {
  return (
    <Router>
      <Suspense fallback={<div>Loading page...</div>}>
        <Routes>
          <Route path="/" element={<Home />} />
          <Route path="/about" element={<About />} />
          <Route path="/contact" element={<Contact />} />
        </Routes>
      </Suspense>
    </Router>
  );
}
```

**📊 Benefits of Lazy Loading**

- **Faster Initial Load** → Loads only what’s needed.
- **Better Performance** → Reduces bundle size.
- **Improved User Experience** → Users don’t download unnecessary code.
- **Scalable Apps** → Essential for large apps with many pages/components.


### What is Memoization in React?

Memoization is an optimization technique that speeds up rendering by caching the result of a function call and returning the cached result when the same inputs occur again.

In React, memoization helps avoid expensive calculations or re-renders when component props/state haven't changed.


**🔑 React Tools for Memoization**

React provides 3 main tools:

**1. `React.memo()`**
   - Wraps a functional component to prevent re-renders if props haven’t changed.

**2. `useMemo()`**
   - Memoizes the result of a function to avoid expensive recalculations.

**3. `useCallback()`**
   - Returns a memoized callback function to prevent unnecessary re-renders.

📌 1. `React.memo()` Example:
```tsx
import React from "react";

type Props = { name: string };

const Child = React.memo(({ name }: Props) => {
  console.log("Child re-rendered");
  return <h2>Hello, {name}</h2>;
});

export default function App() {
  const [count, setCount] = React.useState(0);

  return (
    <div>
      <button onClick={() => setCount(count + 1)}>Increment: {count}</button>
      <Child name="Alice" />
    </div>
  );
}
```

📌 2. `useMemo()` Example (Caching Expensive Calculations)
```tsx
import React, { useState, useMemo } from "react";

function ExpensiveComponent({ num }: { num: number }) {
  const expensiveCalculation = (n: number) => {
    console.log("Calculating...");
    return n * 1000; // Imagine this is expensive
  };

  const result = useMemo(() => expensiveCalculation(num), [num]);

  return <h3>Result: {result}</h3>;
}

export default function App() {
  const [count, setCount] = useState(0);
  const [value, setValue] = useState(5);

  return (
    <div>
      <button onClick={() => setCount(count + 1)}>Increment: {count}</button>
      <ExpensiveComponent num={value} />
      <button onClick={() => setValue(value + 1)}>Change Value</button>
    </div>
  );
}
```

📌 3. `useCallback()` Example (Stabilizing Function References)
```tsx
import React, { useState, useCallback } from "react";

type ChildProps = { onClick: () => void };

const Child = React.memo(({ onClick }: ChildProps) => {
  console.log("Child re-rendered");
  return <button onClick={onClick}>Click Me</button>;
});

export default function App() {
  const [count, setCount] = useState(0);

  // Without useCallback, new function is created on every render
  const handleClick = useCallback(() => {
    console.log("Clicked!");
  }, []);

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={() => setCount(count + 1)}>Increment</button>
      <Child onClick={handleClick} />
    </div>
  );
}
```

## What is Reoncillation in React?

**Reconciliation** is the process React uses to decide:
👉 “How should I update the DOM when the application’s state or props change?”

Instead of re-rendering the whole UI, React compares the **Virtual DOM** (new tree) with the previous **Virtual DOM** (old tree) and efficiently updates only what has changed.

This algorithm is called the **Diffing Algorithm**.

#### 🔄 The Reconciliation Process

**1. Trigger:** A component’s state or props change.
**2. Re-render Virtual DOM:** React creates a new Virtual DOM tree.
**3. Diffing:** React compares the new tree with the previous one.
**4. Minimal DOM Updates:** React updates only the nodes that changed.

🏗️ Example (Todo App):
```jsx
function TodoList({ todos }) {
  return (
    <ul>
      {todos.map((t) => (
        <li key={t.id}>{t.task}</li>
      ))}
    </ul>
  );
}
```

**Why `key` is Important in Reconciliation**

- React uses the `key` prop to identify list items.
- If keys are stable, React reuses existing DOM elements instead of deleting and re-creating them.

**🔴 Bad Example (No keys)**
```jsx
<ul>
  <li>Buy Milk</li>
  <li>Read Book</li>
</ul>
```

> If "Buy Milk" is removed → React might re-render all <li> elements.


**🟢 Good Example (Using keys)**
```jsx
<ul>
  <li key="1">Buy Milk</li>
  <li key="2">Read Book</li>
</ul>
```

> If "Buy Milk" is removed → React knows only key="1" is gone and updates efficiently.

**📌 Key Rules of Reconciliation**

1. Different Element Types → Replace DOM Node
   - `<div>` → `<p>` → React destroys `<div>` and creates `<p>`.

2. Same Element Type → Update Attributes
   - `<input type="text" />` → `<input type="password" />` → React updates type.

3. Children with Keys → Optimized Updates
   - Helps React reorder, add, or remove efficiently.

