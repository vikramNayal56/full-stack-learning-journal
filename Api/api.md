# Working with APIs & Fetch

## API

- API connects the client and server.
- Client sends a request, server sends a response.
- One request = One response.

---

## Request & Response

### Request

- Method
- URL
- Headers
- Body

### Response

- Status Code
- Headers
- Body

> Always check the **status code first**.

---

## JSON

- `response.json()` → Convert JSON to JavaScript object.
- `JSON.stringify()` → Convert JavaScript object to JSON.

---

## HTTP Methods

| Method | Purpose |
|---------|---------|
| GET | Read data |
| POST | Create data |
| PUT | Replace data |
| PATCH | Update data |
| DELETE | Remove data |

---

## Common Status Codes

| Code | Meaning |
|------|---------|
| 200 | OK |
| 201 | Created |
| 204 | No Content |
| 400 | Bad Request |
| 401 | Unauthorized |
| 403 | Forbidden |
| 404 | Not Found |
| 429 | Too Many Requests |
| 500 | Server Error |

---

## fetch()

```javascript
fetch(url)
```

### Using async/await

```javascript
const res = await fetch(url);
const data = await res.json();
```

---

## Sending Data

```javascript
fetch(url, {
  method: "POST",
  headers: {
    "Content-Type": "application/json"
  },
  body: JSON.stringify(data)
});
```

---

## Error Handling

- `fetch()` throws only for network errors.
- Check `res.ok` for HTTP errors.

---

## Authentication

- API Key → Identifies the application.
- Bearer Token → Identifies the user.
- Store secrets in `.env`.
- Never push API keys to GitHub.

---



---
## HTTP & REST APIs

HTTP (HyperText Transfer Protocol) is a communication protocol that allows a client (browser or mobile app) to communicate with a server. Whenever we visit a website, submit a form, or request data, HTTP is used.

REST (Representational State Transfer) is an architectural style used to build web APIs. REST APIs use HTTP methods to perform different operations on resources.

---

## How HTTP Works

```
Client (Browser)
       │
       │ HTTP Request
       ▼
     Server
       │
       │ HTTP Response
       ▼
Client (Browser)
```

### Example

When you open **https://github.com**:

1. Your browser sends an HTTP request.
2. GitHub's server receives the request.
3. The server processes it.
4. The webpage is sent back as an HTTP response.

---

# HTTP Request

An HTTP request is sent by the client to the server.

It contains:

- URL
- HTTP Method
- Headers
- Body (optional)

---

# HTTP Response

An HTTP response is sent by the server back to the client.

It contains:

- Status Code
- Headers
- Response Body

---

# HTTP Methods

### GET
Used to retrieve data from the server.

### POST
Used to create new data on the server.

### PUT
Used to replace an existing resource completely.

### PATCH
Used to update only specific fields of an existing resource.

### DELETE
Used to remove data from the server.

---

# Common HTTP Status Codes

| Status Code | Meaning |
|-------------|---------|
| 200 | Request Successful |
| 201 | Resource Created Successfully |
| 400 | Bad Request |
| 401 | Unauthorized |
| 403 | Forbidden |
| 404 | Resource Not Found |
| 500 | Internal Server Error |

---

# What is REST?

REST (Representational State Transfer) is a way of designing APIs. It uses HTTP methods to perform operations on resources.

A resource can be anything like:

- Users
- Products
- Orders
- Students

REST APIs use meaningful URLs to access these resources.

---

# REST API Example

| HTTP Method | Endpoint | Description |
|-------------|----------|-------------|
| GET | `/users` | Get all users |
| GET | `/users/1` | Get a specific user |
| POST | `/users` | Create a new user |
| PUT | `/users/1` | Replace user information |
| PATCH | `/users/1` | Update specific user details |
| DELETE | `/users/1` | Delete a user |

---

# JSON

JSON (JavaScript Object Notation) is the most common format used to exchange data between a client and a server.

Example:

```json
{
  "id": 1,
  "name": "Bhanu Joshi",
  "course": "Full Stack Development"
}
```

# Key Learnings

- Learned how clients and servers communicate using HTTP.
- Understood the difference between an HTTP request and an HTTP response.
- Learned the purpose of GET, POST, PUT, PATCH, and DELETE methods.
- Learned common HTTP status codes and their meanings.
- Understood how REST APIs organize resources using endpoints.
- Learned that JSON is the standard format for exchanging data in REST APIs.
---
## Quick Revision

- API → Client ↔ Server
- JSON → Data format
- GET → Read
- POST → Create
- PUT → Replace
- PATCH → Update
- DELETE → Remove
- `fetch()` → Send request
- `await res.json()` → Read response
- `res.ok` → Check success
- `.env` → Store secret keys
---
# Final Note