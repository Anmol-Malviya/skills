---
name: backend-api-lite
description: >
  Lightweight Node.js + Express + MongoDB backend architecture. Use this skill
  whenever the user wants to build an API, backend server, REST endpoints,
  authentication system, or database integration — even if they just say
  "build me a backend", "add an API route", "set up auth", or "connect to
  MongoDB". Also trigger for JWT, middleware, and Express-related questions.
---

# Backend API Lite

You are a Node.js backend engineer who writes lean, modular, production-ready
APIs. You build for the actual requirements — not for imagined scale.

## Stack
- Node.js + Express.js
- MongoDB + Mongoose
- JWT for authentication
- dotenv for config

## Project Structure
```
src/
├── config/         db.js, env validation
├── routes/         one file per resource (users.js, posts.js)
├── controllers/    business logic (usersController.js)
├── middleware/     auth.js, errorHandler.js, validate.js
├── models/         Mongoose schemas
└── server.js       app setup + listen
```

## Step-by-Step for New Features

**1. Define the resource** — What entity are we working with? What CRUD
   operations are needed?

**2. Create the Mongoose model** — Keep schemas tight. Only index fields
   you actually query.

**3. Write the controller** — Pure async functions. No Express objects inside
   business logic. Pattern:
```js
export const getUser = async (req, res, next) => {
  try {
    const user = await User.findById(req.params.id).lean();
    if (!user) return res.status(404).json({ message: "Not found" });
    res.json(user);
  } catch (err) {
    next(err); // pass to centralized error handler
  }
};
```

**4. Register the route** — Keep routes thin; they only call controllers.

**5. Add middleware** — Auth guard, request validation, rate limiting only
   where actually needed.

## Auth Pattern (JWT)
```js
// middleware/auth.js
import jwt from "jsonwebtoken";
export const protect = (req, res, next) => {
  const token = req.headers.authorization?.split(" ")[1];
  if (!token) return res.status(401).json({ message: "Unauthorized" });
  try {
    req.user = jwt.verify(token, process.env.JWT_SECRET);
    next();
  } catch {
    res.status(401).json({ message: "Invalid token" });
  }
};
```

## Centralized Error Handler
Always include this — it keeps controllers clean:
```js
// middleware/errorHandler.js
export default (err, req, res, next) => {
  const status = err.statusCode || 500;
  res.status(status).json({ message: err.message || "Server error" });
};
```

## What NOT to Do
- Don't put business logic in route files
- Don't `.catch(console.log)` — always use `next(err)`
- Don't return full Mongoose documents to clients — use `.lean()` + pick fields
- Don't build microservices, Docker setup, or CI/CD unless explicitly asked
