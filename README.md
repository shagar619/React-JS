<!-- markdownlint-disable MD012 MD026 MD001 MD022 MD032 MD029 MD019 MD034 MD031 MD047 MD040 MD009 MD058 MD024 MD033 MD041 MD045 MD036  -->

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

> **Note:** JSX must be transpiled to JavaScript before it can be executed in the browser.


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

```tsx
import React from 'react';

const TodoList = ({ todos }) => {
  return (
    <ul>
      {todos.map(todo => (
        <li key={todo.id}>{todo.text}</li>
      ))}
    </ul>
  );
};

export default TodoList;
```

> **Note:** In this example, the `TodoList` component renders a list of todo items. Each item has a unique `key` prop, which is essential for efficient updates and re-renders.


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


📌 Example:

Class Component Version:
```tsx
import React, { Component } from 'react';

interface User {
  id: number;
  name: string;
  email: string;
  avatar: string;
}

interface UserProfileProps {
  userId: number;
}

interface UserProfileState {
  user: User | null;
  loading: boolean;
  error: string | null;
  editMode: boolean;
  formData: Partial<User>;
}

class UserProfileClass extends Component<UserProfileProps, UserProfileState> {
  private abortController: AbortController | null = null;
  private intervalId: number | null = null;

  constructor(props: UserProfileProps) {
    super(props);
    
    // Initialize state
    this.state = {
      user: null,
      loading: false,
      error: null,
      editMode: false,
      formData: {}
    };

    // Bind methods (or use arrow functions)
    this.handleEdit = this.handleEdit.bind(this);
    this.handleSave = this.handleSave.bind(this);
  }

  async componentDidMount() {
    // Component has mounted - fetch initial data
    console.log('Component mounted, fetching user data');
    await this.fetchUser();
    
    // Set up polling for real-time updates
    this.intervalId = window.setInterval(() => {
      if (!this.state.editMode) {
        this.fetchUser();
      }
    }, 30000); // Poll every 30 seconds
  }

  async componentDidUpdate(prevProps: UserProfileProps, prevState: UserProfileState) {
    // Component updated - check if we need to fetch new data
    if (prevProps.userId !== this.props.userId) {
      console.log('User ID changed, fetching new user');
      await this.fetchUser();
    }

    // Log state changes for debugging
    if (prevState.editMode !== this.state.editMode) {
      console.log(`Edit mode ${this.state.editMode ? 'enabled' : 'disabled'}`);
    }
  }

  componentWillUnmount() {
    // Cleanup before component is destroyed
    console.log('Component unmounting, cleaning up');
    
    // Cancel any pending requests
    if (this.abortController) {
      this.abortController.abort();
    }
    
    // Clear intervals
    if (this.intervalId) {
      clearInterval(this.intervalId);
    }
  }

  componentDidCatch(error: Error, errorInfo: React.ErrorInfo) {
    // Handle errors in child components
    console.error('Error caught in UserProfile:', error, errorInfo);
    this.setState({ error: 'Something went wrong loading the user profile' });
  }

  private async fetchUser() {
    // Cancel previous request if still pending
    if (this.abortController) {
      this.abortController.abort();
    }
    
    this.abortController = new AbortController();
    
    this.setState({ loading: true, error: null });
    
    try {
      const response = await fetch(`/api/users/${this.props.userId}`, {
        signal: this.abortController.signal
      });
      
      if (!response.ok) {
        throw new Error(`Failed to fetch user: ${response.status}`);
      }
      
      const user = await response.json();
      this.setState({ user, loading: false });
    } catch (error: any) {
      if (error.name !== 'AbortError') {
        this.setState({ 
          error: error.message || 'Failed to load user', 
          loading: false 
        });
      }
    }
  }

  private handleEdit() {
    this.setState({ 
      editMode: true, 
      formData: { ...this.state.user } 
    });
  }

  private async handleSave() {
    if (!this.state.user) return;

    try {
      const response = await fetch(`/api/users/${this.state.user.id}`, {
        method: 'PUT',
        headers: { 'Content-Type': 'application/json' },
        body: JSON.stringify(this.state.formData)
      });

      if (!response.ok) {
        throw new Error('Failed to update user');
      }

      const updatedUser = await response.json();
      this.setState({ 
        user: updatedUser, 
        editMode: false, 
        formData: {} 
      });
    } catch (error: any) {
      this.setState({ error: error.message });
    }
  }

  render() {
    const { user, loading, error, editMode, formData } = this.state;

    if (loading) return <div>Loading user profile...</div>;
    if (error) return <div>Error: {error}</div>;
    if (!user) return <div>No user found</div>;

    return (
      <div className="user-profile">
        <img src={user.avatar} alt={`${user.name}'s avatar`} />
        
        {editMode ? (
          <div>
            <input
              value={formData.name || ''}
              onChange={e => this.setState({
                formData: { ...formData, name: e.target.value }
              })}
              placeholder="Name"
            />
            <input
              value={formData.email || ''}
              onChange={e => this.setState({
                formData: { ...formData, email: e.target.value }
              })}
              placeholder="Email"
            />
            <button onClick={this.handleSave}>Save</button>
            <button onClick={() => this.setState({ editMode: false })}>
              Cancel
            </button>
          </div>
        ) : (
          <div>
            <h2>{user.name}</h2>
            <p>{user.email}</p>
            <button onClick={this.handleEdit}>Edit</button>
          </div>
        )}
      </div>
    );
  }
}
```

Function Component with Hooks Version:
```tsx
import React, { useState, useEffect, useCallback, useRef } from 'react';

interface User {
  id: number;
  name: string;
  email: string;
  avatar: string;
}

interface UserProfileProps {
  userId: number;
}

function UserProfileHooks({ userId }: UserProfileProps) {
  // useState replaces this.state
  const [user, setUser] = useState<User | null>(null);
  const [loading, setLoading] = useState(false);
  const [error, setError] = useState<string | null>(null);
  const [editMode, setEditMode] = useState(false);
  const [formData, setFormData] = useState<Partial<User>>({});

  // useRef for mutable values that don't trigger re-renders
  const abortControllerRef = useRef<AbortController | null>(null);
  const intervalRef = useRef<number | null>(null);

  // useCallback to memoize functions (prevents unnecessary re-renders)
  const fetchUser = useCallback(async () => {
    // Cancel previous request
    if (abortControllerRef.current) {
      abortControllerRef.current.abort();
    }
    
    abortControllerRef.current = new AbortController();
    
    setLoading(true);
    setError(null);
    
    try {
      const response = await fetch(`/api/users/${userId}`, {
        signal: abortControllerRef.current.signal
      });
      
      if (!response.ok) {
        throw new Error(`Failed to fetch user: ${response.status}`);
      }
      
      const userData = await response.json();
      setUser(userData);
    } catch (err: any) {
      if (err.name !== 'AbortError') {
        setError(err.message || 'Failed to load user');
      }
    } finally {
      setLoading(false);
    }
  }, [userId]); // Dependency array - recreate when userId changes

  // useEffect replaces componentDidMount, componentDidUpdate, componentWillUnmount
  useEffect(() => {
    console.log('Effect: Fetching user data');
    fetchUser();

    // Set up polling (like componentDidMount)
    intervalRef.current = window.setInterval(() => {
      if (!editMode) {
        fetchUser();
      }
    }, 30000);

    // Cleanup function (like componentWillUnmount)
    return () => {
      console.log('Effect cleanup: Canceling requests and clearing interval');
      
      if (abortControllerRef.current) {
        abortControllerRef.current.abort();
      }
      
      if (intervalRef.current) {
        clearInterval(intervalRef.current);
      }
    };
  }, [fetchUser, editMode]); // Re-run when fetchUser or editMode changes

  // Separate useEffect for logging edit mode changes (like componentDidUpdate)
  useEffect(() => {
    console.log(`Edit mode ${editMode ? 'enabled' : 'disabled'}`);
  }, [editMode]);

  const handleEdit = useCallback(() => {
    setEditMode(true);
    setFormData({ ...user });
  }, [user]);

  const handleSave = useCallback(async () => {
    if (!user) return;

    try {
      const response = await fetch(`/api/users/${user.id}`, {
        method: 'PUT',
        headers: { 'Content-Type': 'application/json' },
        body: JSON.stringify(formData)
      });

      if (!response.ok) {
        throw new Error('Failed to update user');
      }

      const updatedUser = await response.json();
      setUser(updatedUser);
      setEditMode(false);
      setFormData({});
    } catch (err: any) {
      setError(err.message);
    }
  }, [user, formData]);

  const handleCancel = useCallback(() => {
    setEditMode(false);
    setFormData({});
  }, []);

  // Render logic (same as class component render method)
  if (loading) return <div>Loading user profile...</div>;
  if (error) return <div>Error: {error}</div>;
  if (!user) return <div>No user found</div>;

  return (
    <div className="user-profile">
      <img src={user.avatar} alt={`${user.name}'s avatar`} />
      
      {editMode ? (
        <div>
          <input
            value={formData.name || ''}
            onChange={e => setFormData(prev => ({ ...prev, name: e.target.value }))}
            placeholder="Name"
          />
          <input
            value={formData.email || ''}
            onChange={e => setFormData(prev => ({ ...prev, email: e.target.value }))}
            placeholder="Email"
          />
          <button onClick={handleSave}>Save</button>
          <button onClick={handleCancel}>Cancel</button>
        </div>
      ) : (
        <div>
          <h2>{user.name}</h2>
          <p>{user.email}</p>
          <button onClick={handleEdit}>Edit</button>
        </div>
      )}
    </div>
  );
}
```

Custom Hook for Data Fetching;
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


