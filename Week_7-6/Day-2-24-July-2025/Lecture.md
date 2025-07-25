# Project Setup and Structure

- A Node.js REST API project is created using `npm init`.
- Installed Express with `npm install express`.
- Server listens on port `8000`.
- Created basic Express app.

# REST API Routes Overview

- `GET /users`: List all users.
- `GET /users/:id`: Get one user by ID.
- `POST /users`: Add new user.
- `PATCH /users/:id`: Update user by ID.
- `DELETE /users/:id`: Delete user by ID.

# Mock Data Generation

- Used **Mockaroo** to generate fake users data in JSON format.
- Fields: `id`, `first_name`, `last_name`, `email`, `gender`, `job_title`.
- Saved data to project folder.

# GET /api/users Route

- Returns all users in JSON.
- Visit `localhost:8000/api/users` to see JSON data.

# Hybrid Server Design

- Used `/api/*` for JSON (API clients).
- Used `/users` for HTML (browser clients).
- `/users` shows HTML list of users.

# Dynamic Route for Single User

- Route: `/api/users/:id`
- Uses `req.params.id` to get ID.
- Returns matching user object.

# POST, PATCH, DELETE Basics

- Used Postman for testing.
- Setup basic routes: POST, PATCH, DELETE.
- Used `app.route('/api/users/:id')` to group routes by path.
