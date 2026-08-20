# AMA Questions & Answers

## 1. Adhikya Edammala — What is the use of `useRef` hook?

`useRef` is a React Hook used to **store a value that persists across renders without causing a re-render**.

### Common uses:

* Accessing DOM elements directly.
* Storing mutable values.
* Keeping previous values between renders.
* Storing values that should not trigger a re-render when changed.

---

## 2. Boorle Sowmya Sri Lakshmi — What are Portals in React?

**Portals** allow us to render a React component into a **different DOM node outside its normal parent DOM hierarchy**.

### Example:

```jsx
import { createPortal } from "react-dom";

function Modal() {
  return createPortal(
    <div className="modal">
      <h2>This is a Modal</h2>
    </div>,
    document.getElementById("modal-root")
  );
}
```


---

## 3. Md Musharaf — Why do we need keys in React?

**Keys** are used to uniquely identify elements in a list.

They help React determine **which items have been added, removed, or changed**, allowing React to update the UI efficiently.


---

## 4. Nayunipatruni Harsha Vardhan — What is Conditional Rendering?

**Conditional rendering** means displaying different UI elements or components based on a condition.

---

## 5. Rongala Vasu — What is Props Drilling and How to Overcome It?

**Props drilling** occurs when data is passed through multiple intermediate components using props, even though those intermediate components do not need the data themselves.


### How to overcome Props Drilling?


1. **React Context API**
2. **State management libraries** such as Redux or Zustand
3. **Better component structure** to keep shared state closer to where it is needed


