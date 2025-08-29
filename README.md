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

### 🔹What is virtual DOM in React?

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

### 🔹 What is React Router?
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

📌 Example of Prop Drilling:
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