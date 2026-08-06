# AMA Session Questions and Answers

---

# 1. Why do we use JSON response instead of HTML response in DRF?

**Answer:**

Django REST Framework (DRF) is designed to build **REST APIs**, where the backend communicates with different clients such as web applications, mobile apps, and third-party services.

Instead of returning HTML pages, DRF returns **JSON (JavaScript Object Notation)** because it is:

- Lightweight
- Easy for machines to read and parse
- Language-independent
- Supported by almost every programming language

### Example

```http
GET /api/users/1
```

Response:

```json
{
    "id": 1,
    "name": "Vikas",
    "email": "vikas@gmail.com"
}
```

A frontend application (React, Flutter, Angular, etc.) would have difficulty extracting structured data.

---

# 2. What is Just-In-Time (JIT) Compilation?

**Answer:**

Just-In-Time (JIT) Compilation is a technique where code is compiled during program execution rather than before execution.

Instead of interpreting code line by line every time, frequently executed code is compiled into machine code, making execution faster.

Examples:
- Java JVM
- JavaScript V8 Engine (Chrome)
- .NET CLR

**Advantages**
- Faster execution
- Better runtime optimization
- Improved performance

---

# 3. Difference between Function-Based Views (FBV) and Class-Based Views (CBV) in DRF

| Function-Based Views | Class-Based Views |
|----------------------|------------------|
| Written as functions | Written as classes |
| Simple and easy to understand | More reusable and organized |
| Suitable for small APIs | Suitable for larger projects |
| Less reusable | Supports inheritance and code reuse |
| More code for CRUD | Generic views reduce boilerplate |

### FBV Example

```python
@api_view(['GET'])
def player_list(request):
    players = Player.objects.all()
    serializer = PlayerSerializer(players, many=True)
    return Response(serializer.data)
```

### CBV Example

```python
class PlayerList(ListAPIView):
    queryset = Player.objects.all()
    serializer_class = PlayerSerializer
```

---

# 4. Difference between Serialization and Deserialization

## Serialization

Converts a Python object (or Django model) into JSON.

```text
Python Object
      ↓
     JSON
```

## Deserialization

Converts JSON received from a client into a Python object.

```text
JSON
 ↓
Python Object
```

**Example**

Serialization:

```python
serializer = PlayerSerializer(player)
serializer.data
```

Deserialization:

```python
serializer = PlayerSerializer(data=request.data)

if serializer.is_valid():
    serializer.save()
```

---

# 5. What is ModelSerializer?

**Answer:**

`ModelSerializer` is a DRF serializer that automatically generates serializer fields based on a Django model.

Instead of manually defining every field, DRF reads them directly from the model.

Example:

```python
class PlayerSerializer(serializers.ModelSerializer):

    class Meta:
        model = Player
        fields = "__all__"
```

---

# 6. Why do we use the Meta class in `models.py`?

**Answer:**

The `Meta` class is used to define **metadata** about a Django model.

It does not define model fields but controls model behavior.

Common uses:

- Database table name
- Default ordering
- Verbose names
- Constraints
- Permissions

Example:

```python
class Player(models.Model):
    name = models.CharField(max_length=100)

    class Meta:
        db_table = "players"
        ordering = ["name"]
```

---

# 7. What is `partial=True`?

**Answer:**

`partial=True` allows **partial updates** during serialization.

Without it, all required fields must be provided.

Example:

```python
serializer = PlayerSerializer(
    player,
    data=request.data,
    partial=True
)
```

---

# 8. What are Mixins in DRF?

**Answer:**

Mixins are reusable classes that provide common CRUD functionality.

Examples:

- CreateModelMixin
- ListModelMixin
- RetrieveModelMixin
- UpdateModelMixin
- DestroyModelMixin

Example:

```python
class PlayerView(
    mixins.ListModelMixin,
    mixins.CreateModelMixin,
    GenericAPIView
):
    queryset = Player.objects.all()
    serializer_class = PlayerSerializer
```

Instead of writing GET and POST manually, mixins provide these operations.

---

# 9. What is a Router in DRF?

**Answer:**

A Router automatically generates URL patterns for a ViewSet.

Instead of manually writing URLs, you register the ViewSet with a router.

Example:

```python
from rest_framework.routers import DefaultRouter

router = DefaultRouter()
router.register("players", PlayerViewSet)

urlpatterns = router.urls
```

Automatically generated URLs:

```text
GET     /players/
POST    /players/
GET     /players/1/
PUT     /players/1/
PATCH   /players/1/
DELETE  /players/1/
```