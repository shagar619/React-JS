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
- **Usage:** Props are read-only and should not be modified by the component. They can be of any data type, including strings, numbers, arrays, and objects.

📌 Example:

```tsx
const Greeting = ({ name, role }) => {
  return <h1>Hello, {name} - {role}!</h1>;
};

//usages
<Greeting name="Alice" role="Admin" />
<Greeting name="Bob" role="Customer" />
```
- In this example, the `Greeting` component accepts a `name` and `role` prop and uses them to render a personalized greeting.


