# FastAPI Login Authentication

This project demonstrates user login/authentication using FastAPI and JWT tokens.

## Features
- User registration (optional)
- Login with username/password
- JWT token generation & validation
- Protected route


app/
├── auth/
│   ├── __init__.py
│   ├── models.py      # User model
│   ├── routes.py      # Auth endpoints
│   ├── services.py    # Auth logic
│   └── validators.py  # Pydantic models
├── config/
│   └── settings.py    # Configuration
└── main.py

