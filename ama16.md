# AMA Session Questions and Answers

## 1. Adhikya Edammala — What is Chain of Thought?

**Chain of Thought (CoT)** is a prompting technique where an AI model breaks a complex problem into multiple intermediate steps before reaching the final answer.

---

## 2. Allanki VV Manikanta Sai — What is Self-Consistency?

**Self-Consistency** is a prompting technique where an AI model generates multiple possible reasoning paths and chooses the answer that occurs most consistently.

### How It Works

1. Generate multiple solutions.
2. Each solution may follow a different reasoning path.
3. Compare the final answers.
4. Select the most frequently occurring answer.

---

## 3. Boorle Sowmya Sri Lakshmi — What is Generic API ListView?

In **Django REST Framework (DRF)**, `ListAPIView` is a generic API view used to retrieve and return a list of objects.

### Example

```python
from rest_framework.generics import ListAPIView
from .models import Product
from .serializers import ProductSerializer


class ProductListView(ListAPIView):
    queryset = Product.objects.all()
    serializer_class = ProductSerializer
```

This creates a **GET API** that returns a list of products.

### Advantages

* Requires less code
* Automatically works with serializers
* Supports pagination
* Can be combined with filtering
* Supports authentication and permissions
* Useful for building REST APIs quickly

### Common DRF Generic Views

```text
ListAPIView
CreateAPIView
RetrieveAPIView
UpdateAPIView
DestroyAPIView
ListCreateAPIView
RetrieveUpdateDestroyAPIView
```

---

## 4. Md Musharaf — What are Signals in Django?

**Django Signals** allow different parts of a Django application to respond automatically when a specific event occurs.

For example, when a new user is created, a signal can automatically create a profile for that user.

### Use Cases

* Automatically creating related objects
* Sending notifications
* Updating related data
* Performing actions after database changes

---

## 5. Nayunipatruni Harsha Vardhan — What are Decorators in Python?

A **decorator** is a function that modifies or extends the behavior of another function without changing its original code.

Decorators are commonly used with the `@decorator_name` syntax.

### Common Uses

* Logging
* Authentication and authorization
* Measuring execution time
* Caching
* Validation
* Django views and permissions

### Django Example

```python
from django.contrib.auth.decorators import login_required


@login_required
def dashboard(request):
    ...
```

The `login_required` decorator ensures that only authenticated users can access the view.

---

## 6. Rongala Vasu — What is Props Drilling in React?

**Props drilling** occurs when data is passed from a parent component to a deeply nested child component through intermediate components that do not actually need that data.

Example in React:

```jsx
function App() {
  const user = "Vikas";

  return <Parent user={user} />;
}

function Parent({ user }) {
  return <Child user={user} />;
}

function Child({ user }) {
  return <h1>Hello {user}</h1>;
}
```

Here, `Parent` does not use `user` itself. It only passes the prop to `Child`.

### Problems with Props Drilling

* Makes components harder to maintain
* Creates unnecessary prop passing
* Can become difficult with deeply nested components
* Makes component relationships more tightly coupled

### Solutions

For larger applications, you can use:

* **React Context API**
* **Redux**
* **Zustand**
* Other state-management solutions

### In Short

> **Props drilling means passing props through components that don't need them just to reach a deeply nested component.**
