# Fundamentals of REST API

# What is REST API?

* REST = Representational State Transfer.
* It's a set of rules for building web APIs.
* Uses HTTP methods: GET, POST, PUT, DELETE.
* Works with resources identified by URLs.

# Key Principles

* **Stateless**: Server does not remember client state.
* **Client-Server**: Separation of concerns.
* **Cacheable**: Responses should say if they can be cached.
* **Uniform Interface**: Same method of communication across APIs.

# HTTP Methods

* `GET`: Read data.
* `POST`: Create data.
* `PUT`: Update data.
* `DELETE`: Remove data.

# Status Codes

* `200`: OK
* `201`: Created
* `400`: Bad Request
* `404`: Not Found
* `500`: Server Error

# Example

```http
GET /users/1
```

Response:

```json
{
  "id": 1,
  "name": "Ali"
}
```

---

# Introduction to Node.js & NPM

# What is Node.js?

* Runtime to run JavaScript on server.
* Built on Chrome's V8 engine.
* Uses non-blocking (async) code.

# Features

* Fast and scalable.
* Uses event-driven architecture.
* Ideal for APIs, real-time apps.

# Node.js Architecture

* Single-threaded with Event Loop.
* Handles many connections using callbacks.

# Core Modules

* `fs` for file system
* `http` to create web servers
* `path`, `url`, etc.

# Example

```js
const http = require('http');
http.createServer((req, res) => {
  res.end('Hello World');
}).listen(3000);
```

# NPM

* Node Package Manager
* Used to install libraries

Commands:

```bash
npm init -y
npm install express
```

---

# What is MongoDB?

* NoSQL database.
* Stores data in JSON-like documents.
* Used for flexible, scalable apps.

# Basic Terms

* **Database**: Container for collections.
* **Collection**: Group of documents.
* **Document**: Data record (like JSON).

# CRUD Operations

* **Create**: `insertOne`, `insertMany`
* **Read**: `find`, `findOne`
* **Update**: `updateOne`, `updateMany`
* **Delete**: `deleteOne`, `deleteMany`

# Example:

```js
// Insert
await db.collection('users').insertOne({ name: 'Ali' });

// Find
const user = await db.collection('users').findOne({ name: 'Ali' });

// Update
await db.collection('users').updateOne({ name: 'Ali' }, { $set: { age: 25 } });

// Delete
await db.collection('users').deleteOne({ name: 'Ali' });
```

# Schema (with Mongoose)

```js
const mongoose = require('mongoose');
const userSchema = new mongoose.Schema({
  name: String,
  age: Number,
});
const User = mongoose.model('User', userSchema);
```

# Aggregation Pipeline

* Used to transform data

```js
User.aggregate([
  { $match: { age: { $gt: 20 } } },
  { $group: { _id: "$age", count: { $sum: 1 } } }
]);
```

# Indexing

* Speeds up search queries.

```js
collection.createIndex({ name: 1 });
```

# ACID Properties

* **Atomicity**: All or nothing.
* **Consistency**: Valid state.
* **Isolation**: No mixed results.
* **Durability**: Data is saved.

# Replication

* Copies data across multiple servers.
* Provides high availability.



