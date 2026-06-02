# Task API

Backend REST API with JWT Authentication and Role-Based Access Control (RBAC).

## Tech Stack
- Python, Django, Django REST Framework
- PostgreSQL
- JWT Authentication (SimpleJWT)
- Swagger API Docs (drf-spectacular)
- Vanilla JS Frontend

## Setup Instructions

```bash
git clone https://github.com/itesh-singh/taskapi.git
cd taskapi
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

Create `.env` file:
```
SECRET_KEY=your-secret-key
DEBUG=True
DB_NAME=taskapi
DB_USER=postgres
DB_PASSWORD=postgres
DB_HOST=localhost
DB_PORT=5432
```

```bash
python manage.py migrate
python manage.py createsuperuser
python manage.py runserver
```

## API Endpoints
| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | /api/v1/auth/register/ | Register |
| POST | /api/v1/auth/login/ | Login |
| GET | /api/v1/auth/profile/ | Profile |
| GET | /api/v1/tasks/ | List tasks |
| POST | /api/v1/tasks/ | Create task |
| PUT | /api/v1/tasks/{id}/ | Update task |
| DELETE | /api/v1/tasks/{id}/ | Delete task |

## API Docs
Visit `/api/docs/` for Swagger UI.

## Scalability Note
- Stateless JWT auth allows horizontal scaling
- PostgreSQL supports connection pooling (PgBouncer)
- Redis can be added for caching frequent queries
- Docker-ready structure for containerized deployment
- Can be split into microservices (auth, tasks) as traffic grows
