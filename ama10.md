# AMA Session Questions and Answers

---

## 1. Why are functions called first-class citizens?

Functions are called first-class citizens because they can be treated like any other value.

They can:

* Be assigned to variables.
* Be passed as arguments to other functions.
* Be returned from functions.
* Be stored inside objects or arrays.

---

## 2. What are the different Promise states?

A Promise has **3 states**:

### Pending

Initial state.

```javascript
new Promise(() => {});
```

---

### Fulfilled

Operation completed successfully.

```javascript
Promise.resolve("Success");
```

---

### Rejected

Operation failed.

```javascript
Promise.reject("Error");
```

---

## 3. Difference between Promise.race() and Promise.any()

### Promise.race()

Returns the result of the **first settled promise** (fulfilled or rejected).

```javascript
Promise.race([
    Promise.reject("Error"),
    Promise.resolve("Success")
]);
```

Output:

```
Error
```

---

### Promise.any()

Returns the **first fulfilled promise**.

Ignores rejected promises.

```javascript
Promise.any([
    Promise.reject("Error"),
    Promise.resolve("Success")
]);
```

Output:

```
Success
```

If all promises reject, it throws an **AggregateError**.

| Promise.race                            | Promise.any                |
| --------------------------------------- | -------------------------- |
| First settled                           | First fulfilled            |
| Can reject immediately                  | Ignores rejected promises  |
| Rejects if first settles with rejection | Rejects only if all reject |

---

## 4. What is callback hell?

Callback hell occurs when callbacks are nested deeply, making code difficult to read and maintain.

```javascript
login(function () {
    getUser(function () {
        getPosts(function () {
            getComments(function () {

            });
        });
    });
});
```

---

## 5. What is lexical scope?

Lexical scope means a function can access variables from the scope where it was **defined**, not where it is called.

```javascript
let name = "Vikas";

function outer() {
    function inner() {
        console.log(name);
    }
    inner();
}

outer();
```

Output

```
Vikas
```

Lexical scope is the foundation of **closures**.

---

## 6. What is the spread operator?

Spread operator (`...`) expands an iterable into individual elements.

### Arrays

```javascript
const arr1 = [1,2];
const arr2 = [...arr1,3];
```

Output

```
[1,2,3]
```

---

### Objects

```javascript
const obj1 = {a:1};
const obj2 = {...obj1,b:2};
```

Output

```
{a:1,b:2}
```

Uses:

* Copy arrays
* Merge arrays
* Copy objects
* Merge objects

---

## 7. What is promise chaining?

Promise chaining means executing asynchronous operations one after another using `.then()`.

```javascript
fetchUser()
.then(user => getOrders(user.id))
.then(orders => getPayment(orders))
.then(result => console.log(result))
.catch(err => console.log(err));
```

---

## 8. What is Object.fromEntries()?

It converts an array of key-value pairs into an object.

```javascript
const arr = [
    ["name", "Vikas"],
    ["age", 23]
];

const obj = Object.fromEntries(arr);

console.log(obj);
```

Output

```javascript
{
    name: "Vikas",
    age: 23
}
```



---

## 9. Difference between var, let, and const in hoisting

All three are hoisted, but they behave differently.

### var

Hoisted and initialized with `undefined`.

```javascript
console.log(a);

var a = 10;
```

Output

```
undefined
```

---

### let

Hoisted but not initialized.

```javascript
console.log(a);

let a = 10;
```

Output

```
ReferenceError
```

---

### const

Also hoisted but not initialized.

```javascript
console.log(a);

const a = 10;
```

Output

```
ReferenceError
```



---

## 10. What does `null == undefined` and `null === undefined` return?

### Loose equality

```javascript
null == undefined
```

Output

```
true
```

Because JavaScript considers them equal only under loose equality.

---

### Strict equality

```javascript
null === undefined
```

Output

```
false
```

Because they are different types.

```javascript
typeof null       // "object"
typeof undefined  // "undefined"
```

---

## 11. Different ways to create functions in JavaScript

### Function Declaration

```javascript
function greet() {
    console.log("Hello");
}
```

---

### Function Expression

```javascript
const greet = function () {
    console.log("Hello");
};
```

---

### Arrow Function

```javascript
const greet = () => {
    console.log("Hello");
};
```

---

### Anonymous Function

```javascript
setTimeout(function () {
    console.log("Hello");
}, 1000);
```

---

### IIFE (Immediately Invoked Function Expression)

```javascript
(function () {
    console.log("Runs immediately");
})();
```

---

## 12. What is Temporal Dead Zone (TDZ)?

The Temporal Dead Zone is the period between entering a block and the point where a `let` or `const` variable is declared. During this time, the variable exists but cannot be accessed.

---
