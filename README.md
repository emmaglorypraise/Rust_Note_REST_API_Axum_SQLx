# Rust Note REST API

A simple REST API built with Rust, Axum, and SQLx for managing notes with MySQL database. This service provides comprehensive CRUD (Create, Read, Update, Delete) operations for managing notes, along with paginated listing capabilities.

## 🚀 Quick Start

### Prerequisites
- Rust & Cargo
- Docker & Docker Compose
- MySQL (via Docker)

### Installation

1. **Clone the repository**
```bash
git clone https://github.com/emmaglorypraise/Rust_Note_REST_API_Axum_SQLx.git
```

2. Set up environment variables

```
cp .env.example .env
# Edit .env with your database credentials
```

3. Start MySQL with Docker
```bash
docker compose up -d
```

4. Run the application
```bash
cargo run
```

Server will start at http://localhost:8080

## 📋 API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/v1/healthcheck` | Health check |
| GET | `/api/v1/notes` | Get all notes |
| GET | `/api/v1/notes/:id` | Get note by ID |
| POST | `/api/v1/notes` | Create new note |
| PUT | `/api/v1/notes/:id` | Update note |
| DELETE | `/api/v1/notes/:id` | Delete note |


## 🧪 Testing the API
### Method 1: Browser Testing
Open your browser and navigate to:

```
http://localhost:8080/api/v1/healthcheck
```

### Method 2: VS Code REST Client Extension
Create requests.http file:
```
### Health Check
GET http://localhost:8080/api/v1/healthcheck

### Get All Notes
GET http://localhost:8080/api/v1/notes

### Get Note by ID
GET http://localhost:8080/api/v1/notes/1

### Create New Note
POST http://localhost:8080/api/v1/notes
Content-Type: application/json

{
    "title": "My First Note",
    "content": "This is my first note content",
    "category": "general"
}

### Update Note
PUT http://localhost:8080/api/v1/notes/1
Content-Type: application/json

{
    "title": "Updated Title",
    "content": "Updated content",
    "category": "updated"
}

### Delete Note
DELETE http://localhost:8080/api/v1/notes/1
```

Click "Send Request" above each endpoint to test.

### Method 3: curl Commands

# Health check
```
curl http://localhost:8080/api/v1/healthcheck
```

# Create note
```
curl -X POST http://localhost:8080/api/v1/notes \
  -H "Content-Type: application/json" \
  -d '{"title":"Test","content":"Test content","category":"test"}'
```

## 🛠️ Technology Stack
- Framework: Axum

- Database: MySQL with SQLx

- Environment: Dotenvy

- Async Runtime: Tokio

