# Notes Management REST API

This is my backend assignment project built with Node.js, Express, MongoDB, and Mongoose. It demonstrates CRUD operations, advanced routing, query handling, pagination, filtering, and sorting for a notes management API.

## Tech Stack

- Node.js
- Express.js
- MongoDB
- Mongoose
- dotenv
- nodemon

## Project Setup

```bash
git clone <your-repository-url>
cd advanced-routing-queries-assignment
npm install
```

Create a `.env` file from `.env.example` and add your own MongoDB connection string later:

```env
MONGO_URI=your_mongodb_connection_string_here
PORT=5000
NODE_ENV=development
```

Run the project:

```bash
npm run dev
```

Production start:

```bash
npm start
```

## Base URL

Local:

```text
http://localhost:5000
```

Render:

```text
https://your-render-service.onrender.com
```

## Health Endpoints

- `GET /`
- `GET /health`

## API Endpoints

### CRUD

- `POST /api/notes`
- `POST /api/notes/bulk`
- `GET /api/notes`
- `GET /api/notes/:id`
- `PUT /api/notes/:id`
- `PATCH /api/notes/:id`
- `DELETE /api/notes/:id`
- `DELETE /api/notes/bulk`

### Route Parameters

- `GET /api/notes/category/:category`
- `GET /api/notes/status/:isPinned`
- `GET /api/notes/:id/summary`

### Query and Filtering

- `GET /api/notes/filter`
- `GET /api/notes/filter/pinned`
- `GET /api/notes/filter/category`
- `GET /api/notes/filter/date-range`

### Pagination

- `GET /api/notes/paginate`
- `GET /api/notes/paginate/category/:category`

### Sorting

- `GET /api/notes/sort`
- `GET /api/notes/sort/pinned`

## Postman Documentation

The Postman collection for this assignment is included here:

- `docs/Notes-Management-API.postman_collection.json`

You can import that file into Postman and set the `baseUrl` collection variable to either your local server or your deployed Render URL.

Detailed endpoint notes are available in:

- `docs/POSTMAN_DOCUMENTATION.md`

## Render Deployment

A Render Blueprint file is included:

- `render.yaml`

Before deploying, add your MongoDB connection string in Render as the `MONGO_URI` environment variable.

Typical deployment flow:

```bash
git add .
git commit -m "Prepare assignment for deployment"
git push origin main
```

Then create the service on Render from your GitHub repository. Render will use:

- Build command: `npm ci`
- Start command: `npm start`

## Author

Het Rathod
