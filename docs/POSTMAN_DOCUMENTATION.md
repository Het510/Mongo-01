# Postman Documentation

## Collection Setup

Import `docs/Notes-Management-API.postman_collection.json` into Postman.

Set the collection variable:

- `baseUrl` = `http://localhost:5000` for local testing
- `baseUrl` = `https://your-render-service.onrender.com` after deployment

## Sample Request Body

### Create note

```json
{
  "title": "Prepare backend submission",
  "content": "Finish routing, queries, deployment, and docs.",
  "category": "study",
  "isPinned": true
}
```

### Bulk create notes

```json
{
  "notes": [
    {
      "title": "DSA revision",
      "content": "Practice arrays and linked lists.",
      "category": "study",
      "isPinned": false
    },
    {
      "title": "Team sync",
      "content": "Prepare updates for the meeting.",
      "category": "work",
      "isPinned": true
    }
  ]
}
```

### Bulk delete notes

```json
{
  "ids": [
    "664f1a2b3c4d5e6f70819201",
    "664f1a2b3c4d5e6f70819202"
  ]
}
```

## Endpoints Included In Collection

- `GET /`
- `GET /health`
- `POST /api/notes`
- `POST /api/notes/bulk`
- `GET /api/notes`
- `GET /api/notes/:id`
- `GET /api/notes/:id/summary`
- `PUT /api/notes/:id`
- `PATCH /api/notes/:id`
- `DELETE /api/notes/:id`
- `DELETE /api/notes/bulk`
- `GET /api/notes/category/:category`
- `GET /api/notes/status/:isPinned`
- `GET /api/notes/filter`
- `GET /api/notes/filter/pinned`
- `GET /api/notes/filter/category`
- `GET /api/notes/filter/date-range`
- `GET /api/notes/paginate`
- `GET /api/notes/paginate/category/:category`
- `GET /api/notes/sort`
- `GET /api/notes/sort/pinned`

## Notes

- Replace `:id` values with real MongoDB document IDs from your database.
- Allowed categories are `work`, `personal`, and `study`.
- Allowed sort fields are `title`, `createdAt`, `updatedAt`, and `category`.
