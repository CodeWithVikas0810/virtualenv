# AMA Session Questions and Answers

## Adhikya Edammala - Difference between Functional Component and Class Component

### Functional Component
A Functional Component is a JavaScript function that returns JSX. It is the modern and recommended way to build React components.

**Example:**
```jsx
function Welcome() {
  return <h1>Hello, World!</h1>;
}
```

### Class Component
A Class Component is an ES6 class that extends `React.Component`.

**Example:**
```jsx
class Welcome extends React.Component {
  render() {
    return <h1>Hello, World!</h1>;
  }
}
```

### Key Differences

| Functional Component | Class Component |
|----------------------|-----------------|
| Uses functions | Uses ES6 classes |
| Uses Hooks for state and lifecycle | Uses lifecycle methods |
| Less code | More boilerplate |
| Easier to understand | More complex |
| Preferred in modern React | Mostly used in older React projects |

---

## Allanki VV Manikanta Sai - What is `flatMap()` in JavaScript?

`flatMap()` is an array method that first maps each element using a callback function and then flattens the result by one level.

### Syntax

```javascript
array.flatMap(callback)
```

### Example

```javascript
const numbers = [1, 2, 3];

const result = numbers.flatMap(num => [num, num * 2]);

console.log(result);
```

**Output:**

```javascript
[1, 2, 2, 4, 3, 6]
```

---

## Boorle Sowmya Sri Lakshmi - What is the use of Generic API View in Django?

A **Generic API View** in Django REST Framework (DRF) provides reusable functionality for building REST APIs with less code.

### Common Generic Views

- `ListAPIView` – Retrieve all records.
- `RetrieveAPIView` – Retrieve a single record.
- `CreateAPIView` – Create a new record.
- `UpdateAPIView` – Update an existing record.
- `DestroyAPIView` – Delete a record.
- `ListCreateAPIView` – List and create.
- `RetrieveUpdateDestroyAPIView` – Retrieve, update, and delete.

### Example

```python
from rest_framework.generics import ListCreateAPIView
from .models import Student
from .serializers import StudentSerializer

class StudentList(ListCreateAPIView):
    queryset = Student.objects.all()
    serializer_class = StudentSerializer
```

---

## Md Musharaf - What is Namespacing in Django?

**Namespacing** in Django is used to uniquely identify URL patterns when multiple apps have URL names that are the same.

It helps Django determine which URL should be used when calling the `url` template tag or the `reverse()` function.

### Example

**blog/urls.py**

```python
app_name = "blog"

urlpatterns = [
    path('', views.home, name='home'),
]
```

**shop/urls.py**

```python
app_name = "shop"

urlpatterns = [
    path('', views.home, name='home'),
]
```

---

## Nayunipatruni Harsha Vardhan - What is Hoisting?

**Hoisting** is JavaScript's behavior of moving declarations to the top of their scope before code execution.

Only declarations are hoisted, not initializations.
