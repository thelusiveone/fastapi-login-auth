# FastAPI Login Authentication

This project demonstrates user login/authentication using FastAPI and JWT tokens.

## Features
- User registration (optional)
- Login with username/password
- JWT token generation & validation
- Protected route



## Authentication Flow Design

### Sequence Flow

```mermaid
sequenceDiagram
    actor Client
    participant Routes as auth/routes.py
    participant Validators as auth/validators.py
    participant Services as auth/services.py
    participant Models as auth/models.py
    participant Config as config/settings.py

    Client->>Routes: POST /login (credentials)
    Routes->>Validators: Validate payload
    Validators-->>Routes: Validated data
    Routes->>Services: Authenticate user
    Services->>Models: Fetch user & verify password
    Models-->>Services: User record
    Services->>Services: Verify credentials, issue token
    Services->>Config: Read token settings (expiry, secret)
    Services-->>Routes: Access token / refresh token
    Routes-->>Client: Return tokens

