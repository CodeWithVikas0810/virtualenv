# AMA Session Questions and Answers

## 1. What are Controlled Components in React?

**Answer:**

Controlled components are form elements whose values are controlled by React state using the `useState` hook.

```jsx
const [name, setName] = useState("");

<input
  value={name}
  onChange={(e) => setName(e.target.value)}
/>
```

---

## 2. What are Deserializers?

**Answer:**

A deserializer converts incoming data (JSON/XML) into Python objects and validates the data.

---

## 3. How do you restore changes from the staging area to the working directory in Git?

**Answer:**

To unstage a file:

```bash
git restore --staged <file>
```

To discard working directory changes:

```bash
git restore <file>
```

---

## 4. What is a Hook in React?

**Answer:**

Hooks are special functions that let you use React features like state and lifecycle methods in functional components.

**Common Hooks:**
- `useState()`
- `useEffect()`
- `useContext()`
- `useRef()`
- `useMemo()`

---

## 5. What is Context API in React?

**Answer:**

Context API allows data to be shared across components without passing props manually (prop drilling).

**Example Uses:**
- Theme
- Authentication
- Language
- User information

---

## 6. What is Docker Hub?

**Answer:**

Docker Hub is a cloud-based repository for storing, sharing, and downloading Docker images.

**Common Commands:**

```bash
docker pull nginx
docker push username/image
```

---

## 7. Difference Between Method Overloading and Method Overriding (Python)

| Method Overloading | Method Overriding |
|--------------------|-------------------|
| Python does **not** support true method overloading. | Supported in Python using inheritance. |
| Multiple methods with the same name overwrite the previous one. | Child class provides its own implementation of a parent class method. |
| Similar behavior can be achieved using default arguments or `*args`. | Used to achieve runtime polymorphism. |
| Occurs within the same class. | Occurs between parent and child classes. |

### Method Overloading Example (using `*args`)

```python
class Calculator:
    def add(self, *args):
        return sum(args)

calc = Calculator()

print(calc.add(2, 3))
print(calc.add(2, 3, 4))
```

### Method Overriding Example

```python
class Animal:
    def sound(self):
        print("Animal sound")

class Dog(Animal):
    def sound(self):
        print("Bark")

dog = Dog()
dog.sound()
```

---

## 8. How do you create a new branch in Git?

**Answer:**

Create a new branch:

```bash
git branch feature-branch
```

Create and switch to it:

```bash
git checkout -b feature-branch
```

```
