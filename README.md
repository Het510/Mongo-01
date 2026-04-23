# 📒 Notes Management REST API

A production-ready REST API for managing notes — built with **Node.js**, **Express**, and **MongoDB**. Supports full CRUD, route/query parameters, pagination, sorting, and filtering with a clean MVC architecture.

[![Live Demo](https://img.shields.io/badge/Live%20Demo-Render-46E3B7?style=flat-square&logo=render)](https://advanced-routing-queries-assignment-8z9j.onrender.com)
[![API Docs](https://img.shields.io/badge/API%20Docs-Postman-FF6C37?style=flat-square&logo=postman)](https://documenter.getpostman.com/view/50839274/2sBXqGpMCY)

---

## ✨ Features

- Create, read, update, replace, and delete notes (single & bulk)
- Filter notes by category, pinned status, and date range
- Paginate result sets with configurable page sizes
- Sort notes by allowed fields
- Consistent JSON response format across all endpoints
- Clean MVC folder structure for easy extensibility

---

## 🛠 Tech Stack

| Layer | Technology |
|---|---|
| Runtime | Node.js |
| Framework | Express.js |
| Database | MongoDB |
| ODM | Mongoose |
| Config | dotenv |
| Dev Server | nodemon |

---

## 📁 Folder Structure

```
advanced-routing-queries-assignment/
├── src/
│   ├── config/
│   │   └── db.js
│   ├── controllers/
│   │   └── note.controller.js
│   ├── middlewares/
│   │   └── .gitkeep
│   ├── models/
│   │   └── note.model.js
│   ├── routes/
│   │   └── note.routes.js
│   ├── app.js
│   └── index.js
├── .env
├── .env.example
├── package.json
└── README.md
```

---

## 🔌 API Endpoints

### CRUD Operations

| Method | Endpoint | Description |
|---|---|---|
| `POST` | `/api/notes` | Create a single note |
| `POST` | `/api/notes/bulk` | Create multiple notes |
| `GET` | `/api/notes` | Get all notes |
| `GET` | `/api/notes/:id` | Get a note by ID |
| `PUT` | `/api/notes/:id` | Replace a note |
| `PATCH` | `/api/notes/:id` | Partially update a note |
| `DELETE` | `/api/notes/:id` | Delete a single note |
| `DELETE` | `/api/notes/bulk` | Delete multiple notes |

### Route Parameters

| Method | Endpoint | Description |
|---|---|---|
| `GET` | `/api/notes/category/:category` | Get notes by category |
| `GET` | `/api/notes/status/:isPinned` | Get notes by pinned status |
| `GET` | `/api/notes/:id/summary` | Get a note's summary |

### Query Parameters & Filtering

| Method | Endpoint | Description |
|---|---|---|
| `GET` | `/api/notes/filter` | General filtering |
| `GET` | `/api/notes/filter/pinned` | Get pinned notes |
| `GET` | `/api/notes/filter/category` | Filter by category |
| `GET` | `/api/notes/filter/date-range` | Filter by creation date range |

### Pagination

| Method | Endpoint | Description |
|---|---|---|
| `GET` | `/api/notes/paginate` | Paginate all notes |
| `GET` | `/api/notes/paginate/category/:category` | Paginate notes by category |

### Sorting

| Method | Endpoint | Description |
|---|---|---|
| `GET` | `/api/notes/sort` | Sort all notes |
| `GET` | `/api/notes/sort/pinned` | Sort pinned notes |

---

## 📦 Response Format

All endpoints return a consistent JSON structure:

```json
{
  "success": true,
  "message": "Notes fetched successfully",
  "data": {}
}
```

List endpoints include a `count` field. Paginated endpoints additionally include a `pagination` object:

```json
{
  "success": true,
  "message": "Notes fetched successfully",
  "count": 20,
  "pagination": {
    "page": 1,
    "limit": 10,
    "totalPages": 2,
    "totalItems": 20
  },
  "data": []
}
```

---

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/Priyankkhatri/advanced-routing-queries-assignment.git
cd advanced-routing-queries-assignment
```

### 2. Install dependencies

```bash
npm install
```

### 3. Configure environment variables

Create a `.env` file in the root of the project:

```env
MONGO_URI=mongodb+srv://<username>:<password>@cluster.mongodb.net/notes-db
PORT=5000
```

> Copy `.env.example` as a starting point.

### 4. Start the server

```bash
# Development (with hot reload)
npm run dev

# Production
npm start
```

The server will be running at `http://localhost:5000`.

---

## 🌐 Live Links

| Resource | URL |
|---|---|
| Live API | https://advanced-routing-queries-assignment-8z9j.onrender.com |
| API Documentation | https://documenter.getpostman.com/view/50839274/2sBXqGpMCY |

---

## 👤 Author

**Priyank Khatri**

---

> Built as a backend assignment project demonstrating REST API design, MVC architecture, and advanced Express.js routing patterns.
