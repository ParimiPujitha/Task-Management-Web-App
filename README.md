# Task-Management-Web-App

Same features as the original — rebuilt frontend with **plain HTML + CSS + JS**.  
Backend is unchanged: Django + DRF + JWT.

## Project Structure

```
task-app/
├── backend/          ← Django REST API (unchanged)
│   ├── app/
│   └── backend/
└── frontend/         ← Pure HTML/CSS/JS (no React, no npm)
    ├── login.html
    ├── register.html
    ├── dashboard.html
    ├── api.js        ← fetch() wrapper (replaces axios)
    └── style.css
```

## Backend Setup

```bash
cd backend
pip install django djangorestframework djangorestframework-simplejwt django-cors-headers psycopg2-binary

# Update settings.py with your DB credentials
python manage.py migrate
python manage.py runserver
```

> API runs at: http://127.0.0.1:8000/api/

## Frontend Setup

No npm, no build step needed.

Just open `login.html` in your browser — OR serve with any static server:

```bash
cd frontend
python -m http.server 5500
# Open: http://localhost:5500/login.html
```

## API Endpoints (unchanged)

| Method | Endpoint              | Description       |
|--------|-----------------------|-------------------|
| POST   | /api/register/        | Register user     |
| POST   | /api/token/           | Login (get JWT)   |
| GET    | /api/profile/         | Get user profile  |
| GET    | /api/tasks/           | List tasks        |
| POST   | /api/tasks/           | Create task       |
| PUT    | /api/tasks/{id}/      | Update task       |
| DELETE | /api/tasks/{id}/      | Delete task       |

## What Changed vs Original

| Original (React)              | New (Vanilla JS)               |
|-------------------------------|--------------------------------|
| React + react-router-dom      | Plain HTML pages               |
| axios for HTTP                | fetch() API                    |
| npm install + build required  | Open HTML directly             |
| JSX components                | DOM manipulation               |
| package.json / node_modules   | None needed                    |
