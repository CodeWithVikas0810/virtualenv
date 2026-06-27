# AMA Session Questions and Answers

## 1. Arpit Yadav: Why do we create an app folder and a templates folder inside a Django app?

### App Folder
A Django project is divided into multiple apps, where each app handles a specific functionality.

**Example:**
- accounts -> User authentication
- profile -> Blog posts

### Templates Folder
The `templates` folder stores HTML files used to render web pages.

Keeping templates inside the app (app_name/templates/app_name/) provides:
- Better organization
- Avoids template name conflicts between apps

---

## 2. Boorle Sowmya Sri Lakshmi: Difference between Django and Flask

| Django | Flask |
|---------|-------|
| Full-stack framework | Micro framework |
| Batteries included | Minimal by default |
| Built-in ORM | No built-in ORM |
| Built-in Authentication | Need extensions |
| Admin Panel included | No admin panel |
| Suitable for large applications | Suitable for small APIs and microservices |
| More opinionated | Highly flexible |

**When to use Django**
- Large web applications
- Authentication
- Admin dashboard
- E-commerce

**When to use Flask**
- REST APIs
- Small applications
- Microservices
- Quick prototypes

---

## 3. M Harivardhan Reddy: What is Lazy Loading in Django?

Lazy loading means **data is not fetched from the database until it is actually needed.**

Django QuerySets are lazy.

```python
users = User.objects.filter(is_active=True)
```

At this point, **no SQL query is executed.**

The query executes only when:

```python
for user in users:
    print(user.username)
```

or

```python
list(users)
len(users)
users.first()
```

### Benefits
- Improves performance
- Reduces unnecessary database queries
- Saves memory

---

## 4. Md Musharaf: Difference between `AbstractUser` and `AbstractBaseUser`

| AbstractUser | AbstractBaseUser |
|---------------|------------------|
| Extends Django's default User model | Base class for custom authentication |
| Includes username, email, password, permissions, groups | Only password and authentication methods |
| Easy to customize | Full customization |
| Less code | More code |
| Recommended for most projects | Use only when you need complete control |

### Use `AbstractUser`
When adding fields like:

```python
phone
address
profile_picture
```

### Use `AbstractBaseUser`
When:
- Login with phone number
- Login with employee ID
- Completely custom authentication

---

## 5. Naman Sharma: Difference between `get()` and `filter()`

| get() | filter() |
|--------|----------|
| Returns one object | Returns a QuerySet |
| Raises exception if not found | Returns empty QuerySet |
| Raises exception if multiple objects found | Returns multiple objects if available |

### Example

```python
user = User.objects.get(id=1)
```

Returns:

```python
<User>
```

---

```python
users = User.objects.filter(is_active=True)
```

Returns:

```python
<QuerySet>
```

Use:
- `get()` → One object
- `filter()` → Multiple objects

---

## 6. Nayunipatruni Harsha Vardhan: When do we use `enctype="multipart/form-data"`?

It is used when an HTML form uploads files.

Example:

```html
<form method="POST" enctype="multipart/form-data">
```

### Required for: 
- Image upload
- PDF upload
- Resume upload
- Video upload


---

## 7. Parlapalli Sulochana: Difference between clean() and clean_<field>()

### clean_<field>()

Validates one specific field.

Example:

```python
def clean_email(self):
    email = self.cleaned_data['email']
    if email.endswith("@gmail.com"):
        return email
    raise ValidationError("Only Gmail allowed")
```

---

### `clean()`

Validates **multiple fields together**.

Example:

```python
def clean(self):
    cleaned_data = super().clean()
    password = cleaned_data.get("password")
    confirm = cleaned_data.get("confirm_password")

    if password != confirm:
        raise ValidationError("Passwords do not match")
```

### Difference

| clean_field() | clean() |
|---------------|----------|
| Validates one field | Validates multiple fields |
| Runs before `clean()` | Runs after all field validations |
| Field-level validation | Form-level validation |

---

## 8. Rongala Vasu: What is the `Meta` class?

The Meta class provides metadata about a Django model.

Example:

```python
class Student(models.Model):
    name = models.CharField(max_length=100)

    class Meta:
        ordering = ['name']
        db_table = 'student_table'
```

Common options:

```python
class Meta:
    ordering = ['name']
    db_table = 'students'
    verbose_name = 'Student'
    verbose_name_plural = 'Students'
    unique_together = ('email', 'phone')
```

Uses:
- Change database table name
- Default ordering
- Unique constraints
- Human-readable model names

---

## 9. Rovinpal Udupi: How do you make sure a post is liked only once?

The best approach is to enforce a unique constraint on the combination of user and post.

### Model

```python
class Like(models.Model):
    user = models.ForeignKey(User, on_delete=models.CASCADE)
    post = models.ForeignKey(Post, on_delete=models.CASCADE)

    class Meta:
        constraints = [
            models.UniqueConstraint(
                fields=['user', 'post'],
                name='unique_user_post_like'
            )
        ]
```
