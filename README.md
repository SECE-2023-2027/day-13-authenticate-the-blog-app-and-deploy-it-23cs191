# Blog Application

A modern blog application built with MongoDB and Express.js.

## Features

- User Authentication (JWT)
- User Registration
- User Login
- Create blog posts
- Read blog posts
- Update blog posts
- Delete blog posts
- RESTful API endpoints
- MongoDB integration
- Input validation
- Error handling
- Protected routes

## API Endpoints

### Authentication

- `POST /api/auth/register` - Register new user
- `POST /api/auth/login` - Login user

### Posts

- `GET /api/posts` - Get all posts (public)
- `POST /api/posts` - Create a new post (requires auth)
- `GET /api/posts/:id` - Get a single post (public)
- `PUT /api/posts/:id` - Update a post (requires auth)
- `DELETE /api/posts/:id` - Delete a post (requires auth)

## Setup

1. Install dependencies:
```bash
npm install
```

2. Create a `.env` file with your MongoDB connection string:
```
MONGODB_URI=mongodb://localhost:27017/blog-app
PORT=3000
JWT_SECRET=your-secret-key
```

3. Start the server:
```bash
npm run dev
```

The server will start at `http://localhost:3000`

## Authentication

- Register a new user:
```bash
curl -X POST http://localhost:3000/api/auth/register \
-H "Content-Type: application/json" \
-d '{"name": "John Doe", "email": "john@example.com", "password": "password123"}'
```

- Login:
```bash
curl -X POST http://localhost:3000/api/auth/login \
-H "Content-Type: application/json" \
-d '{"email": "john@example.com", "password": "password123"}'
```

- Use the JWT token in the Authorization header for protected routes:
```bash
curl -X POST http://localhost:3000/api/posts \
-H "Content-Type: application/json" \
-H "x-auth-token: your-jwt-token-here" \
-d '{"title": "My Blog Post", "content": "This is my blog post content", "author": "John Doe"}'
```

## Tech Stack

- Express.js
- MongoDB
- Mongoose
- Node.js
- CORS
- dotenv
- express-validator
