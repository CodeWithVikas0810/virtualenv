# AMA Session Questions and Answers

# Adhikya Edammala: What can be the data types for keys in JavaScript objects?

Object keys can only be:
- String
- Symbol

If you use a number, boolean, null, or object as a key, JavaScript converts it to a string.

---

# Allanki VV Manikanta Sai: What is a GET request in HTTP?

A GET request is used to fetch data from a server.

Characteristics:
- Retrieves data
- Should not modify data
- Parameters are sent in the URL
- Can be cached by browsers

---

# Arpit Yadav: What is a Common Table Expression (CTE)?

A CTE is a temporary named result set used inside an SQL query.

Syntax:

```sql
WITH ActiveUsers AS (
    SELECT * FROM users
    WHERE active = true
)
SELECT * FROM ActiveUsers;
```

---

# Boorle Sowmya Sri Lakshmi: How to get a popup window when we click on a card using DOM?

Using a modal:

```html
<div id="card">Click Me</div>

<div id="popup" style="display:none;">
  Hello User
</div>
```

```js
const card = document.getElementById("card");
const popup = document.getElementById("popup");

card.addEventListener("click", () => {
  popup.style.display = "block";
});
```

---

# Injamuri Arun Kumar: Tell some common real-world APIs

Popular APIs used in projects:

- REST Countries API
- OpenWeather API
- Google Maps API
- GitHub API
- Trello API
- Spotify API
- YouTube Data API
- Firebase APIs

---

# M Harivardhan Reddy: Does querySelector work with IDs?

Yes.

---

# Md Musharaf: Does DOM manipulation re-render the whole page or a particular element?

Generally, only the affected element and its related layout are re-rendered.

This is why DOM updates are much faster than a page refresh.

---

# Naman Sharma: What does `.finally()` return?

`.finally()` returns a new Promise.

---

# Nayunipatruni Harsha Vardhan: Tell some HTTP status codes

### Success

- 200 -> OK
- 201 -> Created
- 204 -> No Content

### Redirection

- 301 -> Moved Permanently
- 302 -> Found

### Client Errors

- 400 -> Bad Request
- 401 -> Unauthorized
- 403 -> Forbidden
- 404 -> Not Found
- 409 -> Conflict

### Server Errors

- 500 -> Internal Server Error
- 502 -> Bad Gateway
- 503 -> Service Unavailable

---

# Parlapalli Sulochana: Difference between JSON and JavaScript Object

| JSON | JavaScript Object |
|--------|--------|
| Data format | JavaScript data structure |
| Keys must be in double quotes | Quotes optional |
| Cannot contain functions | Can contain functions |
| Stored as string | Stored as object |
| Used for data transfer | Used inside code |

---

# Rongala Vasu: What is Shadowing in JavaScript?

When a variable in an inner scope has the same name as a variable in an outer scope.

```js
let name = "Vikas";

function test() {
  let name = "John";
  console.log(name);
}

test();
```

Output:

```
John
```

The inner variable shadows the outer variable.

---

# Rovinpal Udupi: What is Virtual DOM?

Virtual DOM is a lightweight JavaScript representation of the real DOM used by React.

Process:
1. State changes
2. New Virtual DOM created
3. React compares old and new Virtual DOM
4. Only changed nodes are updated in the real DOM

Benefits:
- Faster updates
- Fewer DOM operations
- Better performance

---

# Tumma Haritha: What is DNS?

DNS (Domain Name System) converts domain names into IP addresses.

Example:

```text
google.com
↓
142.250.183.14
```

Flow:

```text
Browser
  ↓
DNS Resolver
  ↓
DNS Server
  ↓
IP Address Returned
  ↓
Connection Established
```

Without DNS, we would have to remember IP addresses instead of domain names.

---

# Yash Nitin Raut: Difference between POST and PUT

| POST | PUT |
|--------|--------|
| Creates a new resource | Creates or updates a resource |
| Not idempotent | Idempotent |
| Multiple requests may create multiple records | Multiple requests give same result |
| Server decides resource ID | Client usually provides resource ID |

Example:

- POST → Create User
- PUT → Update User
