# AMA Session Questions and Answers

## 1. Adhikya Edammala - Some Methods of Console

Common console methods:

```js
console.log("Hello");
console.error("Error occurred");
console.warn("Warning");
console.table([{ name: "Vikas", age: 22 }]);
console.time("timer");
```

---

## 2. Allanki VV Manikanta Sai - What are Callback Functions?

A callback function is a function passed as an argument to another function.

---

## 3. Arpit Yadav - What Does the Transition Property Do?

The `transition` property creates smooth animations when CSS properties change.

```css
button {
    background-color: blue;
    transition: background-color 0.5s ease;
}

button:hover {
    background-color: red;
}
```

The button color changes smoothly from blue to red.

---

## 4. Boorle Sowmya Sri Lakshmi - What are Transpilers?

A transpiler converts code from one programming language version to another.

Example:

- Babel converts modern JavaScript (ES6+) into older JavaScript (ES5).

---

## 5. Injamuri Arun Kumar - What is Scope Chaining?

Scope chaining allows JavaScript to look for variables in outer scopes when they are not found in the current scope.

```js
let globalVar = "Global";

function outer() {
    let outerVar = "Outer";

    function inner() {
        console.log(globalVar);
        console.log(outerVar);
    }

    inner();
}

outer();
```

JavaScript searches:
Current Scope → Parent Scope → Global Scope

---

## 6. Kamparapu Lakshman - How Does the DOM Work?

DOM (Document Object Model) represents an HTML page as a tree structure of objects.

HTML:

```html
<h1 id="title">Hello</h1>
```

JavaScript:

```js
const element = document.getElementById("title");
element.textContent = "Welcome";
```

Browser updates the webpage when the DOM changes.

---

## 7. M Harivardhan Reddy - Some Common FS Module Commands

Node.js `fs` module is used for file operations.

```js
const fs = require("fs");

fs.readFileSync("file.txt", "utf8");
fs.writeFileSync("file.txt", "Hello");
fs.appendFileSync("file.txt", " World");
fs.unlinkSync("file.txt");
fs.mkdirSync("folder");
```

---

## 8. Md Musharaf - Difference Between Object Literals and Singleton Objects

### Object Literal

```js
const user = {
    name: "Vikas"
};
```

A new object is created every time.

### Singleton Object

```js
const user = new Object();
user.name = "Vikas";
```

Singleton means only one instance exists and is shared.

---

## 9. Naman Sharma - Difference Between Server-Side and Client-Side JavaScript

| Client-Side JS | Server-Side JS |
|---------------|---------------|
| Runs in browser | Runs on server |
| Manipulates DOM | Handles database/API |
| Uses Browser APIs | Uses Node.js APIs |
| Visible to users | Hidden from users |

---

## 10. Nayunipatruni Harsha Vardhan - Is Garbage Collection Automatic in JavaScript?

Yes.

JavaScript automatically removes objects that are no longer reachable.

JavaScript engines like V8 handle this automatically.

---

## 11. Parlapalli Sulochana - Difference Between package.json and package-lock.json

| package.json | package-lock.json |
|-------------|------------------|
| Project metadata | Exact dependency versions |
| Created manually | Generated automatically |
| Uses version ranges | Uses exact versions |
| Editable | Usually not edited manually |

Example:

```json
"express": "^4.18.2"
```

Lock file stores the exact installed version.

---

## 12. Rongala Vasu - How to Create HTML Elements Using DOM?

```js
const heading = document.createElement("h1");

heading.textContent = "Hello World";

document.body.appendChild(heading);
```

Steps:

1. Create element
2. Add content
3. Append to DOM

---

## 13. Rovinpal Udupi - Difference Between Promise.all() and Promise.race()

### Promise.all()

Waits for all promises to complete.

```js
Promise.all([p1, p2, p3]);
```

Returns results of all promises.

### Promise.race()

Returns the result of the first settled promise.

```js
Promise.race([p1, p2, p3]);
```

Whichever finishes first wins.

---

## 14. Tumma Haritha - What is Call Stack?

Call Stack is a data structure used by JavaScript to track function execution.

```js
function one() {
    two();
}

function two() {
    console.log("Hello");
}

one();
```

Execution:

```text
Push one()
Push two()
Execute console.log()
Pop two()
Pop one()
```

JavaScript executes functions using the Call Stack.

---

## 15. Yash Nitin Raut - Common Places to Write Script

### Inside HTML

Before closing body tag:

```html
<body>
    ...
    <script src="script.js"></script>
</body>
```

Recommended because HTML loads first.

### Inside Head

```html
<head>
    <script defer src="script.js"></script>
</head>
```

Using `defer` ensures the script runs after HTML parsing.

Best Practice:

```html
<script defer src="script.js"></script>
```

or place the script before the closing `</body>` tag.
