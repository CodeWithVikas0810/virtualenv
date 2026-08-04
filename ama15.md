# AMA Session Questions and Answers

## 1. Adhikya Edammala — What are retriable errors and terminal errors?

- **Retriable errors:** Temporary errors where the request can be tried again.
  - Example: `429`, `500`, `503`
- **Terminal errors:** Errors where retrying the same request will not fix the problem.
  - Example: Invalid API key, invalid parameters, permission denied.

---

## 2. Allanki VV Manikanta Sai — Name some retriable errors

- `429` — Too Many Requests
- `500` — Internal Server Error
- `502` — Bad Gateway
- `503` — Service Unavailable
- `504` — Gateway Timeout

---

## 3. Boorle Sowmya Sri Lakshmi — Why do we get `refusal` as a value for `stop_reason`?

`stop_reason: "refusal"` means the model refused to generate the requested response because the request violates safety policies or restrictions.

---

## 4. Md Musharaf — What are streaming responses?

**Streaming responses** allow the model's output to be received incrementally as it is generated, instead of waiting for the complete response.

---

## 5. Rongala Vasu — Length of `[,,,]` in js

```js
[,,,].length // 3