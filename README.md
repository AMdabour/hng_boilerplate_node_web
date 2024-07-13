### Detailed README

---

# Organization and User Management API

This API provides endpoints for managing organizations, users, payments, admin operations, and comments.

## User Management

### Authentication

#### Register user

```
POST /register
```

- **Request Body**:
  - `username` (string, required)
  - `email` (string, required)
  - `password` (string, required)
- **Response**: 201 Created, 400 Bad Request

#### Login user

```
POST /login
```

- **Request Body**:
  - `email` (string, required)
  - `password` (string, required)
- **Response**: 200 OK, 401 Unauthorized

#### Logout user

```
POST /logout
```

- **Response**: 200 OK

#### Forgot password

```
POST /forgot-password
```

- **Request Body**:
  - `email` (string, required)
- **Response**: 200 OK

#### Reset password

```
POST /reset-password
```

- **Request Body**:
  - `token` (string, required)
  - `password` (string, required)
- **Response**: 200 OK, 400 Bad Request

### User Management

#### Get all users

```
GET /users
```

- **Response**: 200 OK

#### Get user by ID

```
GET /users/{id}
```

- **Parameters**:
  - `id` (string, required) - User ID
- **Response**: 200 OK, 404 Not Found

#### Update user

```
PUT /users/{id}
```

- **Parameters**:
  - `id` (string, required) - User ID
- **Request Body**:
  - Any user fields to update
- **Response**: 200 OK, 400 Bad Request, 404 Not Found

#### Delete user

```
DELETE /users/{id}
```

- **Parameters**:
  - `id` (string, required) - User ID
- **Response**: 204 No Content, 404 Not Found

#### Get user settings by ID

```
GET /users/{id}/settings
```

- **Parameters**:
  - `id` (string, required) - User ID
- **Response**: 200 OK, 404 Not Found

#### Update user settings by ID

```
PUT /users/{id}/settings
```

- **Parameters**:
  - `id` (string, required) - User ID
- **Request Body**:
  - Any user settings to update
- **Response**: 200 OK, 400 Bad Request, 404 Not Found

#### Get user profile by ID

```
GET /users/{id}/profile
```

- **Parameters**:
  - `id` (string, required) - User ID
- **Response**: 200 OK, 404 Not Found

#### Update user profile by ID

```
PUT /users/{id}/profile
```

- **Parameters**:
  - `id` (string, required) - User ID
- **Request Body**:
  - Any user profile fields to update
- **Response**: 200 OK, 400 Bad Request, 404 Not Found

## Organization Management

### Organizations

#### Get all organizations

```
GET /organizations
```

- **Response**: 200 OK, 404 Not Found

#### Get organization by ID

```
GET /organizations/{id}
```

- **Parameters**:
  - `id` (string, required) - Organization ID
- **Response**: 200 OK, 404 Not Found

#### Update organization by ID

```
PUT /organizations/{id}
```

- **Parameters**:
  - `id` (string, required) - Organization ID
- **Request Body**:
  - Any organization fields to update
- **Response**: 200 OK, 400 Bad Request, 404 Not Found

#### Delete organization by ID

```
DELETE /organizations/{id}
```

- **Parameters**:
  - `id` (string, required) - Organization ID
- **Response**: 204 No Content, 404 Not Found

### Organization Members

#### Add member to organization

```
POST /organizations/{id}/members
```

- **Parameters**:
  - `id` (string, required) - Organization ID
- **Request Body**:
  - `userId` (string, required)
- **Response**: 201 Created, 400 Bad Request, 404 Not Found

#### Invite member to organization

```
POST /organizations/{id}/invite
```

- **Parameters**:
  - `id` (string, required) - Organization ID
- **Request Body**:
  - `email` (string, required)
- **Response**: 201 Created, 400 Bad Request, 404 Not Found

#### Get organization member by ID

```
GET /organizations/{id}/members/{userId}
```

- **Parameters**:
  - `id` (string, required) - Organization ID
  - `userId` (string, required) - User ID
- **Response**: 200 OK, 404 Not Found

#### Remove member from organization

```
DELETE /organizations/{id}/members/{userId}
```

- **Parameters**:
  - `id` (string, required) - Organization ID
  - `userId` (string, required) - User ID
- **Response**: 204 No Content, 404 Not Found

### Payments

#### Get all payments

```
GET /payments
```

- **Response**: 200 OK, 404 Not Found

#### Get payment by ID

```
GET /payments/{id}
```

- **Parameters**:
  - `id` (string, required) - Payment ID
- **Response**: 200 OK, 404 Not Found

### Admin

#### Get admin information

```
GET /admin
```

- **Response**: 200 OK

#### Get all users by admin

```
GET /admin/users
```

- **Response**: 200 OK

#### Get all organizations by admin

```
GET /admin/organisations
```

- **Response**: 200 OK, 404 Not Found

### Comments

#### Get all comments

```
GET /comments
```

- **Response**: 200 OK

#### Get comment by ID

```
GET /comment/{id}
```

- **Parameters**:
  - `id` (string, required) - Comment ID
- **Response**: 200 OK, 404 Not Found
