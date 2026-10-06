# 📰 Blog Application

A full-stack blogging platform developed using **React, Vite, Express.js, MongoDB, and Clerk Authentication**.

The application supports two different roles: **Users** and **Authors**. Users can discover and read published articles and participate through comments, while Authors can manage their own articles by creating, updating, and deleting them.

---

## 🎯 Main Capabilities

### 🔐 Login & Role Management

- Authentication is implemented using Clerk.
- New users can select their application role.
- The application supports **User** and **Author** roles.
- Features are made available according to the user's role.
- Backend APIs can be protected using authentication.
- Authorization is applied to restricted operations.

### 📖 For Users

Users are able to:

- Browse published articles
- Open and read individual articles
- See information about an article's author
- Add comments to articles

### 🖋️ For Authors

Authors can:

- Create articles
- View the articles they have written
- Edit their own articles
- Delete their own articles
- Access article management functionality through protected operations
- Pass article ownership checks when modifying content

---

## 🧱 Technologies

### Frontend Stack

- **React**
- **Vite**
- **React Router**
- **React Hook Form**
- **Bootstrap**
- **Clerk React**

### Backend Stack

- **Node.js**
- **Express.js**
- **MongoDB**
- **Mongoose**
- **Clerk**
- **dotenv**
- **CORS**

### Development Tools

- **ESLint**
- **Git**
- **npm**

---

## 🗂️ Folder Structure

```text
Blog-App/
│
├── backend/
│   ├── controllers/
│   ├── middleware/
│   ├── models/
│   ├── routes/
│   ├── .env.example
│   ├── package.json
│   └── server.js
│
├── frontend/
│   ├── public/
│   ├── src/
│   │   ├── components/
│   │   ├── contexts/
│   │   ├── App.jsx
│   │   └── main.jsx
│   ├── .env.example
│   ├── package.json
│   └── vite.config.js
│
├── req.http
├── .gitignore
└── README.md
```

---

## 💻 What You Need

Before setting up the project, ensure the following are available:

- **Node.js 20 or later**
- **npm**
- **MongoDB** running locally or a MongoDB connection URI
- A **Clerk application**
- Required Clerk publishable and secret keys

---

## 🔧 Environment Configuration

The project uses environment variables for database access, authentication credentials, and application URLs.

### Server Environment

First enter the backend directory:

```bash
cd backend
```

Create a `.env` file using `.env.example` as the reference.

```env
MONGODB_URI=your_mongodb_connection_string
PORT=4000
FRONTEND_URL=http://localhost:5173
CLERK_SECRET_KEY=your_clerk_secret_key
```

### Client Environment

Move into the frontend directory:

```bash
cd frontend
```

Create the `.env` file based on `.env.example`.

```env
VITE_CLERK_PUBLISHABLE_KEY=your_clerk_publishable_key
VITE_API_URL=http://localhost:4000
```

### 🚫 Protect Your Credentials

Do not commit the following to GitHub:

- `.env` files
- Database credentials
- Clerk keys
- Authentication tokens

The repository provides `.env.example` files containing placeholder values instead of actual secrets.

---

## ▶️ Launching the Application

The frontend and backend are started independently during development.

### Backend Setup

From the project root:

```bash
cd backend
npm install
npm run dev
```

The backend normally starts at:

```text
http://localhost:4000
```

### Frontend Setup

Open another terminal:

```bash
cd frontend
npm install
npm run dev
```

The frontend normally runs at:

```text
http://localhost:5173
```

If Vite chooses another port, use the address displayed in the terminal.

---

## 🔁 User Journey

The application follows this general flow:

```text
                    ┌───────────────┐
                    │     User      │
                    └───────┬───────┘
                            │
                            ▼
                    ┌───────────────┐
                    │ Clerk Login   │
                    └───────┬───────┘
                            │
                            ▼
                    ┌────────────────┐
                    │ First Login ?  │
                    └───────┬────────┘
                            │
                   ┌────────┴────────┐
                   │                 │
                  Yes                No
                   │                 │
                   ▼                 ▼
             ┌────────────┐    ┌──────────────┐
             │ Select Role│    │ Load Profile │
             └──────┬─────┘    └──────┬───────┘
                    │                 │
                    └────────┬────────┘
                             │
                    ┌────────┴────────┐
                    │                 │
                    ▼                 ▼
              ┌──────────┐      ┌──────────┐
              │   User   │      │  Author  │
              └────┬─────┘      └────┬─────┘
                   │                 │
                   ▼                 ▼
             Browse Articles    Manage Articles
                   │            ┌────┼────┐
                   ▼            │    │    │
                Comments      Create Edit Delete
```

---

## 🌐 Backend Interface

The backend exposes REST APIs for the application's primary operations.

| API Section | Function |
|---|---|
| User API | Article browsing, user operations, and comments |
| Author API | Creating and managing articles |
| Authentication | Protecting authenticated API requests |

Endpoints that require authentication must receive a valid Clerk authentication token.

---

## 🧪 API Request Testing

An HTTP request file is included with the project:

```text
req.http
```

It contains example requests for testing backend functionality, including:

- Listing articles
- Creating an article
- Adding a comment
- Other backend requests

For protected requests, use:

```http
Authorization: Bearer TOKEN
```

Replace `TOKEN` with a valid temporary Clerk session token.

The `req.http` file contains placeholders only and does not contain actual authentication tokens.

---

## 🔒 Security Measures

The application includes several mechanisms for protecting users and application data:

- Clerk is responsible for authentication.
- Protected backend routes require authentication.
- User roles control access to application functionality.
- Article ownership is verified before protected article operations.
- Sensitive configuration is stored through environment variables.
- `.env` files are excluded from Git.
- `req.http` does not contain real authentication tokens.
- `.env.example` files provide placeholder configuration.

---

## ✔️ Project Verification

The application was tested locally before submission.

### Frontend Linting

Run:

```bash
cd frontend
npm run lint
```

ESLint completed successfully without errors.

### Frontend Build

Run:

```bash
cd frontend
npm run build
```

The Vite production build completed successfully.

### Backend Check

Run:

```bash
cd backend
npm start
```

The backend successfully:

- Connected to MongoDB
- Started the Express API
- Listened on port `4000`

---

## 🛠️ Planned Improvements

The following improvements can be considered for future versions:

- Article search and filtering
- Pagination
- Categories and tags
- Rich-text article editor
- Comment editing and deletion
- User profile pages
- Image upload and cloud storage
- Article likes and bookmarks
- Better responsive UI
- Production deployment

---

## 👨‍💻 Project Overview

This project was developed as a full-stack web application using the **MERN stack with Clerk authentication**.

### Technologies

**MongoDB · Express.js · React · Node.js · Clerk · Vite**