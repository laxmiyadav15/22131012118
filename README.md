
# 22131012118 – Test Submission

This repository contains my submission for the *Afford Medical Technologies* hiring process under the *Frontend Development* track.  
Both the *Logging Middleware* and *Frontend Project* are included in this single folder.

---

## 📁 Contents

- 🌐 Frontend React App – URL Shortener built with Vite + React

---

## 🔹 Logging Middleware

A simple Express.js middleware that logs each HTTP request with:
- Method (GET, POST, etc.)
- Requested URL
- Timestamp

### Example Use in Express:
```js
const express = require('express');
const app = express();
const logger = require('./loggingMiddleware');

app.use(logger);
