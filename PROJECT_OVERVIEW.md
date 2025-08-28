# MERN Blog App – Project Overview

## 1. Project Summary
This is a full-stack blog application built using the MERN stack (MongoDB, Express, React, Node.js). It allows users to sign up, log in, and create/view blog posts. The app features a modern, responsive UI using Material UI, and supports both light and dark themes.

---

## 2. Technologies Used
- **Frontend:** React, Material UI, CSS
- **Backend:** Node.js, Express
- **Database:** MongoDB (via Mongoose)
- **Authentication:** JWT (JSON Web Tokens)
- **Other:** dotenv for environment variables, bcryptjs for password hashing

---

## 3. Project Structure
```
blogapp/
  client/      # React frontend
    src/
      pages/   # Login, Signup, Dashboard pages
      components/ # AppBar and shared UI components
      App.js   # Main app logic and routing
      index.js # Entry point
    package.json
    ...
  server/      # Express backend
    models/    # Mongoose models (User, BlogPost)
    routes/    # Express routes (auth, blog)
    index.js   # Main server file
    .env       # Environment variables (MONGO_URI, JWT_SECRET)
    package.json
    ...
```

---

## 4. Features
### User Authentication
- **Sign Up:** Users register with name, email, and password. Passwords are hashed before storage.
- **Login:** Users log in with email and password. On success, a JWT token is returned and stored in the browser.
- **Protected Routes:** Only logged-in users can create blog posts.

### Blog Functionality
- **Create Post:** Authenticated users can create new blog posts (title, content).
- **View Posts:** All users can view all blog posts, including author and timestamp.
- **Modern UI:** Uses Material UI for a clean, responsive, and modern look. Includes dark mode toggle.

---

## 5. How It Works
### Backend (server/)
- **index.js:** Sets up Express, connects to MongoDB, loads routes.
- **models/User.js:** Mongoose schema for users (name, email, hashed password).
- **models/BlogPost.js:** Mongoose schema for blog posts (title, content, author, timestamps).
- **routes/auth.js:** Handles signup and login, returns JWT on success.
- **routes/blog.js:** CRUD for blog posts. Create/update/delete require JWT auth.
- **.env:** Stores sensitive info (MongoDB URI, JWT secret).

### Frontend (client/)
- **App.js:** Handles routing (login, signup, dashboard), manages auth state, theme, and layout.
- **components/AppBar.js:** Top navigation bar with app name, links, and dark mode toggle.
- **pages/Login.js:** Login form, error handling, redirects on success.
- **pages/Signup.js:** Signup form, error handling, redirects on success.
- **pages/Dashboard.js:** Shows user info, create post form, and all blog posts in cards.
- **Material UI:** Used throughout for consistent, modern design.

---

## 6. How to Run
1. **Backend:**
   - `cd server`
   - `npm install`
   - Create `.env` with your MongoDB URI and JWT secret
   - `node index.js`
2. **Frontend:**
   - `cd client`
   - `npm install`
   - `npm start`
3. **Access the app:**
   - Open [http://localhost:3000](http://localhost:3000) in your browser

---

## 7. API Endpoints
### Auth
- `POST /api/auth/signup` – Register new user
- `POST /api/auth/login` – Login user

### Blog
- `GET /api/blogs` – Get all blog posts
- `POST /api/blogs` – Create new post (auth required)
- `GET /api/blogs/:id` – Get single post
- `PUT /api/blogs/:id` – Update post (auth, owner only)
- `DELETE /api/blogs/:id` – Delete post (auth, owner only)

---

## 8. Security Notes
- Passwords are hashed before storage.
- JWT tokens are used for authentication and must be sent in the `Authorization` header as `Bearer <token>` for protected routes.
- Sensitive info is stored in `.env` and not committed to version control.

---

## 9. Customization
- You can easily change the theme, colors, or add new features (comments, likes, user profiles, etc.).
- The code is modular and follows best practices for easy extension.

---

## 10. For AI or Developers
This file explains the full structure, features, and flow of the MERN blog app. You can use it to:
- Understand the codebase quickly
- Continue development
- Add new features or refactor
- Use as a prompt for AI to generate new code or answer questions 