# AMA Session Questions and Answers

## 1. Module vs Function

**Module:** A Python file (`.py`) that contains functions, classes, variables, etc.

```python
# math.py
def add(a, b):
    return a + b
```

**Function:** A reusable block of code inside a module that performs a specific task.

```python
def greet():
    print("Hello")
```

---

## 2. Why does Django use SQLite by default?

- Comes bundled with Python.
- No installation or configuration needed.
- Stores data in a single `db.sqlite3` file.
- Best for development and learning.

---

## 3. What does the `choices` attribute do?

It restricts a field to predefined values.

```python
STATUS = [
    ("P", "Pending"),
    ("C", "Completed"),
]

status = models.CharField(max_length=1, choices=STATUS)
```

Benefits:
- Prevents invalid values.
- Creates a dropdown in Django Admin/forms.

---

## 4. What is `ExpressionWrapper`?

It tells Django the output type of a calculated database expression.

```python
ExpressionWrapper(
    F("end_time") - F("start_time"),
    output_field=DurationField()
)
```

Use it when Django cannot determine the result type automatically.

---

## 5. Why do we use Redis with Celery?

Redis acts as a **message broker**.

Flow:

```
Django → Redis (queue) → Celery Worker → Task executes
```

Used for background tasks like:
- Sending emails
- Image processing
- Notifications

This keeps the application fast by avoiding long-running tasks during a request.

---

## 6. What is the `@property` decorator?

It lets you access a method like an attribute.

```python
class User:
    @property
    def full_name(self):
        return "John Doe"

user.full_name
```

Instead of:

```python
user.full_name()
```

Useful for computed, read-only values.

---

## 7. Difference between `auto_now` and `auto_now_add`

| auto_now | auto_now_add |
|----------|--------------|
| Updates on every save | Set only when the object is created |
| Used for `updated_at` | Used for `created_at` |

---

## 8. What is AJAX?

AJAX (Asynchronous JavaScript and XML) allows the browser to communicate with the server without reloading the page.

Examples:
- Like button
- Comments
- Live search
- Chat messages

Nowadays, JSON is used instead of XML.

---

## 9. What is the default relationship type of `ForeignKey`?

`ForeignKey` creates a Many-to-One relationship.

Example:

```python
class Post(models.Model):
    user = models.ForeignKey(User, on_delete=models.CASCADE)
```

One user can have many posts.

---

## 10. Why use Elasticsearch with Django ORM?

Django ORM is good for database queries but not for advanced text search.

Elasticsearch provides:
- Full-text search
- Fuzzy search (handles typos)
- Autocomplete
- Faster search on large datasets
- Relevance-based results


