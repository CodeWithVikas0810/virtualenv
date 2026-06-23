# AMA Session Questions and Answers

## 1. Difference Between WSGI and ASGI

| Feature                | WSGI                         | ASGI                                  |
| ---------------------- | ---------------------------- | ------------------------------------- |
| Full Form              | Web Server Gateway Interface | Asynchronous Server Gateway Interface |
| Processing             | Synchronous                  | Asynchronous                          |
| Supports               | Traditional Django apps      | Async Django apps                     |

### Example

* **WSGI:** Handles HTTP requests only.
* **ASGI:** Handles HTTP requests, WebSockets, chat applications, notifications, etc.

---

## 2. Is `render()` a Class or Method?

`render()` is a **function** provided by Django in `django.shortcuts`.

---

## 3. What is `{% block content %}` Used For?

`block content` is used in **template inheritance**.

It allows child templates to replace specific sections of a parent template.

### Parent Template

```html
<!-- base.html -->

<html>
<body>
    {% block content %}
    {% endblock %}
</body>
</html>
```

### Child Template

```html
{% extends 'base.html' %}

{% block content %}
<h1>Home Page</h1>
{% endblock %}
```

---

## 4. What Are Middlewares?

Middleware is a layer that processes requests before they reach the view and responses before they are returned to the client.

### Uses

* Authentication
* Security checks
* Session management
* Logging
* CSRF protection

### Example

```python
MIDDLEWARE = [
    'django.middleware.security.SecurityMiddleware',
]
```

---

## 5. What Are Annotations?

Annotations add calculated fields to each object in a queryset.

---

## 6. What is the Use of `HttpResponseRedirect`?

`HttpResponseRedirect` redirects the user to another URL.

### Example

```python
from django.http import HttpResponseRedirect

def home(request):
    return HttpResponseRedirect('/dashboard/')
```

### Common Uses

* After form submission
* Login success
* Logout redirect
* Prevent duplicate submissions

---

## 7. What Are Django Built-in Apps?

Django provides several built-in applications.

### Common Built-in Apps

| App                           | Purpose                |
| ----------------------------- | ---------------------- |
| `django.contrib.admin`        | Admin panel            |
| `django.contrib.auth`         | Authentication         |
| `django.contrib.contenttypes` | Content type framework |
| `django.contrib.sessions`     | Session management     |
| `django.contrib.messages`     | Flash messages         |
| `django.contrib.staticfiles`  | Static file handling   |

---

## 8. How Do You Connect a Database to a Django App?

Database configuration is done in `settings.py`.

### SQLite Example

```python
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.sqlite3',
        'NAME': BASE_DIR / 'db.sqlite3',
    }
}
```

---

## 9. Explain Django Features

### 1. MVT Architecture

Django follows the Model-View-Template pattern.

### 2. ORM

Interact with databases using Python code instead of SQL.

```python
User.objects.all()
```

### 3. Admin Interface

Automatically generated admin panel.

### 4. Authentication System

Built-in login, logout, permissions, and user management.

### 5. Security Features

Protection against:

* CSRF
* SQL Injection
* XSS
* Clickjacking

### 6. URL Routing

```python
path('home/', views.home)
```

### 7. Template Engine

```html
{{ user.username }}
```

### 8. Middleware Support

Processes requests and responses globally.

### 9. Scalability

Suitable for both small and large applications.

### 10. Testing Framework

```bash
python manage.py test
```

---

## 10. What is ORM?

ORM stands for **Object Relational Mapping**.

It allows developers to interact with databases using Python objects instead of writing SQL queries.

### Example

#### SQL

```sql
SELECT * FROM users;
```

#### Django ORM

```python
User.objects.all()
```

### Benefits

* Less SQL code
* Database independence
* More secure
* Cleaner code
* Easier maintenance

---

## 11. Difference Between `null=True` and `blank=True`

| Feature        | `null=True`       | `blank=True`                 |
| -------------- | ----------------- | ---------------------------- |
| Affects        | Database          | Forms/Validation             |
| Meaning        | Stores NULL in DB | Allows empty form submission |

### Example

```python
name = models.CharField(
    max_length=100,
    blank=True
)
```

Users may leave this field empty in forms.

```python
age = models.IntegerField(
    null=True
)
```

Database can store:

```sql
NULL
```

### Using Both

```python
bio = models.TextField(
    null=True,
    blank=True
)
```

Meaning:

* Form allows empty value.
* Database stores NULL when no value is provided.

---
