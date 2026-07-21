# AMA Session Questions and Answers

## Adhikya Edammala: What is a Stateless Component?

A **stateless component** is a React component that **does not manage its own state**. It receives data through **props** and renders the UI based on those props.

### Example

```jsx
function Welcome({ name }) {
  return <h1>Hello, {name}</h1>;
}
```
---

## Arpit Yadav: Difference Between JSX and HTML

| JSX | HTML |
|------|------|
| Used in React | Used in web pages |
| Supports JavaScript expressions using `{}` | Does not support JavaScript expressions |
| Uses `className` instead of `class` | Uses `class` |
| Uses `htmlFor` instead of `for` | Uses `for` |
| Must return a single parent element | No such restriction |
| Compiled into JavaScript | Parsed directly by the browser |

### HTML Example

```html
<h1 class="title">Hello</h1>
```

### JSX Example

```jsx
<h1 className="title">Hello</h1>
```

---

## Md Musharaf: Why is React Called a Single Page Application (SPA)?

React applications are called **Single Page Applications (SPAs)** because the browser loads **one HTML page** initially.

After the initial load:

- React updates only the required parts of the page.
- The browser does not reload the entire page.
- Navigation is handled by **React Router** instead of requesting a new HTML page from the server.

### Benefits

- Faster navigation
- Better user experience
- Less server load
- Smooth page transitions

---

## Parlapalli Sulochana: Different Methods of Python Set

### Common Set Methods

```python
add()
update()
remove()
discard()
pop()
clear()
copy()
union()
intersection()
difference()
symmetric_difference()
issubset()
issuperset()
isdisjoint()
```

### Example

```python
a = {1, 2, 3}
b = {3, 4, 5}

print(a.union(b))                 # {1, 2, 3, 4, 5}
print(a.intersection(b))          # {3}
print(a.difference(b))            # {1, 2}
print(a.symmetric_difference(b))  # {1, 2, 4, 5}
```

---

## Rongala Vasu: Difference Between Library and Framework

| Library | Framework |
|----------|-----------|
| You control the flow of the program | The framework controls the flow |
| You call the library when needed | The framework calls your code |
| More flexibility | More structure and conventions |
| Used to perform specific tasks | Provides a complete application structure |

### Examples

**Libraries**
- React
- Lodash
- Axios

**Frameworks**
- Angular
- Django
- Spring Boot
- Ruby on Rails

---

