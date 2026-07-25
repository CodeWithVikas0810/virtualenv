# AMA Session Questions and Answers

### Adhikya Edammala: What is `useRef`?
`useRef` is a React Hook used to store a mutable value that persists across renders without causing a re-render. It is also used to access DOM elements directly.

**Example:**
```jsx
const inputRef = useRef();

<button onClick={() => inputRef.current.focus()}>
  Focus Input
</button>

<input ref={inputRef} />
```

---

### Allanki VV Manikanta Sai: What is a component?
A component is a reusable piece of UI in React. It accepts props and returns JSX.

**Example:**
```jsx
function Welcome() {
  return <h1>Hello, World!</h1>;
}
```

---

### Arpit Yadav: Difference between `useState` and `useEffect`

| `useState` | `useEffect` |
|------------|-------------|
| Stores component state. | Runs side effects after rendering. |
| Causes re-render when state changes. | Used for API calls, timers, event listeners, etc. |

**Example:**
```jsx
const [count, setCount] = useState(0);

useEffect(() => {
  console.log("Count changed:", count);
}, [count]);
```

---

---

### Md Musharaf: What is `useMemo`?
`useMemo` memoizes the result of an expensive calculation and recalculates it only when dependencies change.

**Example:**
```jsx
const squared = useMemo(() => number * number, [number]);
```

---

### Nayunipatruni Harsha Vardhan: What is Vite?
Vite is a fast frontend build tool and development server. It provides instant startup, fast HMR (Hot Module Replacement), and optimized production builds.

---

### Parlapalli Sulochana: What is React Router?
React Router is a library used for navigation in React applications without reloading the page.

**Example:**
```jsx
<Route path="/about" element={<About />} />
```

---

### Rongala Vasu: Difference between `Link` and `navigate()`

| `Link` | `navigate()` |
|--------|--------------|
| Used in JSX for user navigation. | Used in JavaScript to navigate programmatically. |
| Example: `<Link to="/home">Home</Link>` | Example: `navigate("/home")` |

