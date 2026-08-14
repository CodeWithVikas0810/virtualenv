# AMA Session Questions and Answers

## 1. Adhikya Edammala — What is `React.memo`?

`React.memo` is a React function used to prevent unnecessary re-rendering of a component.

It memoizes the component and re-renders it only when its props change.

```jsx
const User = React.memo(function User({ name }) {
  return <h1>Hello {name}</h1>;
});
```

### Key Point

* `React.memo` compares the previous and new props.
* If the props are the same, React can skip re-rendering the component.
* It is mainly used for performance optimization.

---

## 2. Allanki VV Manikanta Sai — Difference Between API and MCP

| API                                                           | MCP                                                                                                  |
| ------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- |
| API stands for **Application Programming Interface**.         | MCP stands for **Model Context Protocol**.                                                           |
| Allows software applications to communicate with each other.  | Allows AI models to communicate with external tools, data, and services through a standard protocol. |
| Usually designed for general software integration.            | Specifically designed for AI/LLM integrations.                                                       |
| Examples: REST API, GraphQL API.                              | Example: An MCP server providing database or file-system tools to an AI assistant.                   |
| Defines how applications request and exchange data/functions. | Defines a standardized way for AI applications to discover and use context/tools.                    |

---

## 3. Boorle Sowmya Sri Lakshmi — What are the Ways to Import in JavaScript?

JavaScript provides several ways to import modules using **ES Modules**.

### 1. Named Import

```javascript
import { add, subtract } from "./math.js";
```

### 2. Default Import

```javascript
import calculate from "./math.js";
```

### 3. Import with an Alias

```javascript
import { add as addition } from "./math.js";
```

### 4. Import Everything

```javascript
import * as math from "./math.js";

math.add();
math.subtract();
```

### 5. Import Only for Side Effects

```javascript
import "./styles.css";
```

This imports the module only to execute its side effects.

### 6. Dynamic Import

Dynamic imports load a module when it is needed.

```javascript
const module = await import("./math.js");

module.add();
```

---

## 4. Md Musharaf — What is `StrictMode` in React?

`React.StrictMode` is a development-only feature that helps developers find potential problems in their React applications.

### Example

```jsx
import { StrictMode } from "react";

<StrictMode>
  <App />
</StrictMode>;
```

### It Helps Identify

* Unsafe or outdated React patterns
* Unexpected side effects
* Deprecated APIs
* Components that are not resilient to React's development checks

In development, some functions or lifecycle-related logic may be invoked more than once to help detect side effects.

> This behavior is for development and does not mean your production app will execute the same logic twice.

---

## 5. Nayunipatruni Harsha Vardhan — Difference Between `useState` and `useRef`

| `useState`                                         | `useRef`                                                                         |
| -------------------------------------------------- | -------------------------------------------------------------------------------- |
| Stores state that affects the UI.                  | Stores a mutable value or reference.                                             |
| Updating state causes a re-render.                 | Changing `.current` does not cause a re-render.                                  |
| Used when UI needs to update when a value changes. | Used when a value needs to persist between renders without triggering rendering. |
| Accessed directly as the state value.              | Accessed using `.current`.                                                       |

### `useState` Example

```jsx
const [count, setCount] = useState(0);

setCount(count + 1);
```

The component re-renders when `count` changes.

### `useRef` Example

```jsx
const countRef = useRef(0);

countRef.current++;
```

Changing `countRef.current` does not re-render the component.

### Common Use of `useRef`

```jsx
const inputRef = useRef(null);

inputRef.current.focus();
```

It can be used to access a DOM element directly.

---

## 6. Rongala Vasu — Is the Claude API Stateful or Stateless?

The Claude API is generally **stateless**.

Each API request is independent. Claude does not automatically remember previous API requests.

If you want Claude to maintain a conversation, your application needs to send the relevant conversation history or context with subsequent requests.
