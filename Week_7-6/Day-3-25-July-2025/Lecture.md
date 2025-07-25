# Node Cron – Task Scheduling

# What is Node Cron?
- A Node.js module to run tasks at specific times.

# Install

npm install node-cron

# Example
```js
const cron = require('node-cron');

cron.schedule('*/2 * * * * *', () => {
  console.log('Runs every 2 seconds');
});
```

# Error Check

```js
if (error != 0) {
  console.log("Something went wrong");
}
```

---

# Node.js vs Express.js

* Node.js: Base for creating servers.
* Express.js: Framework to simplify Node.js with routing, responses, etc.

---

# Express Basics

```js
const express = require('express');
const app = express();

app.get('/', (req, res) => res.send('Home'));
app.listen(3000);
```

* Add more routes: `/profile`, `/contact`

# Middleware

```js
app.use((req, res, next) => {
  console.log("Middleware");
  next();
});
```

# req, res, next

* `req`: Request data
* `res`: Response to client
* `next`: Move to next middleware

# Dynamic Routes

```js
app.get('/user/:name', (req, res) => {
  res.send(req.params.name);
});
```

---

# EJS Template Engine

# Setup

```js
app.set('view engine', 'ejs');
```

# Render

```js
res.render('index', { age: 12 });
```

# In EJS

```html
<p>Age: <%= age %></p>
```

---

# Static Files

```js
app.use(express.static('./public'));
```

Use files like:

```html
<link href="/css/style.css" />
```

---

# Error Handling
```js
app.use((err, req, res, next) => {
  res.render('error', { message: err.message });
});
```

```js
next(new Error("Something went wrong"));
```

---

# Supabase – Firebase Alternative

* Uses PostgreSQL
* Offers auth, storage, real-time, database

# Start

* Go to [supabase.com](https://supabase.com)
* Create project

# Tables

* Add columns
* Enable Role Level Security (RLS)
* Use rules per role (anon, authenticated)

---

# Supabase + React

```bash
npm install @supabase/supabase-js
```

```js
import { createClient } from '@supabase/supabase-js';
const supabase = createClient(URL, ANON_KEY);
```

---

# CRUD

# Insert

```js
await supabase.from('tasks').insert({ title: 'Task' });
```

# Read

```js
await supabase.from('tasks').select('*');
```

# Update

```js
await supabase.from('tasks').update({ done: true }).eq('id', 1);
```

# Delete

```js
await supabase.from('tasks').delete().eq('id', 1);
```

---

# Auth

# Sign Up / In

```js
await supabase.auth.signUp({ email, password });
await supabase.auth.signInWithPassword({ email, password });
```

# Session

```js
const { data: { session } } = await supabase.auth.getSession();
```

# Auth Change

```js
supabase.auth.onAuthStateChange((event, session) => {
  setSession(session);
});
```

# Sign Out

```js
await supabase.auth.signOut();
```

---

# Real-Time

```js
supabase.channel('tasks_channel')
  .on('postgres_changes', {
    event: 'INSERT',
    schema: 'public',
    table: 'tasks'
  }, (payload) => {
    // handle payload
  })
  .subscribe();
```

---

# Storage

# Upload

```js
await supabase.storage.from('task_images').upload(filePath, file);
```

# Get URL

```js
const { data } = await supabase.storage.from('task_images').getPublicUrl(filePath);
```

# Show Image

```html
<img src={image_URL} />
```
