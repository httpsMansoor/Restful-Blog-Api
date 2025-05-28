# Blog API

A RESTful API for managing blog posts built with Django and Django REST Framework.

## Features

- CRUD operations for blog posts
- RESTful API endpoints
- Model Serialization
- ViewSet-based views
- Automatic API documentation (browsable API)

## Prerequisites

- Python 3.x
- pip (Python package installer)

## Installation

1. Clone the repository:
```bash
git clone <repository-url>
cd blog-api
```

2. Create and activate a virtual environment:
```bash
# Windows
python -m venv venv
.\venv\Scripts\activate

# Linux/Mac
python -m venv venv
source venv/bin/activate
```

3. Install the required packages:
```bash
pip install django djangorestframework
```

4. Run migrations:
```bash
python manage.py makemigrations
python manage.py migrate
```

5. Start the development server:
```bash
python manage.py runserver
```

The API will be available at `http://127.0.0.1:8000/api/`

## API Endpoints

### Blog Posts

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET    | `/api/posts/` | List all blog posts |
| POST   | `/api/posts/` | Create a new blog post |
| GET    | `/api/posts/{id}/` | Retrieve a specific blog post |
| PUT    | `/api/posts/{id}/` | Update a blog post (full update) |
| PATCH  | `/api/posts/{id}/` | Update a blog post (partial update) |
| DELETE | `/api/posts/{id}/` | Delete a blog post |

### Request/Response Examples

#### Create a Blog Post (POST /api/posts/)
```json
// Request Body
{
    "title": "My First Blog Post",
    "content": "This is the content of my first blog post."
}

// Response
{
    "id": 1,
    "title": "My First Blog Post",
    "content": "This is the content of my first blog post.",
    "created_at": "2024-03-14T12:00:00Z"
}
```

#### Update a Blog Post (PUT /api/posts/{id}/)
```json
// Request Body
{
    "title": "Updated Title",
    "content": "Updated content"
}

// Response
{
    "id": 1,
    "title": "Updated Title",
    "content": "Updated content",
    "created_at": "2024-03-14T12:00:00Z"
}
```

## Project Structure

```
blog_api/
├── blog/
│   ├── __init__.py
│   ├── admin.py
│   ├── apps.py
│   ├── models.py
│   ├── serializers.py
│   ├── urls.py
│   └── views.py
├── blog_api/
│   ├── __init__.py
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
├── manage.py
└── README.md
```

## Testing the API

You can test the API using:

1. **Web Browser**: Visit `http://127.0.0.1:8000/api/posts/` to access the browsable API interface
2. **Postman**: Use the endpoints mentioned above to test the API


## Technologies Used

- Django 5.2.1
- Django REST Framework 3.16.0
- SQLite (default database)

## Future Improvements

- Add user authentication
- Add permissions
- Add pagination
- Add filtering and searching
- Add categories/tags for blog posts
- Add comments functionality
- Add image upload support

## Contributing

1. Fork the repository
2. Create a new branch
3. Make your changes
4. Submit a pull request

## License

This project is licensed under the MIT License. 