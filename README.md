# API Documentation

## Setup Instructions

### 1. Install Dependencies
Run the following command in your project directory to install required dependencies:
```sh
npm install
```

### 2. Create an `.env` File
Create a `.env` file in the root directory and add your API keys and environment variables:
```
PORT=6000
JWT_SECRET=your_jwt_secret_key
DB_URI=your_database_connection_string
```

Ensure you replace `your_jwt_secret_key` and `your_database_connection_string` with actual values.

---

## Authentication Endpoints

### 1. User Sign-Up
**Method:** POST  
**Endpoint:** `http://localhost:6000/api/auth/signup`  
**Request Body:**  
```json
{
    "email": "bbc@gmail.com",
    "password": "Abcd@12345"
}
```
**Description:** Creates a new user account.

---

### 2. User Sign-In
**Method:** POST  
**Endpoint:** `http://localhost:6000/api/auth/signin`  
**Description:** Authenticates a user and returns a session token.

---

### 3. Change Password
**Method:** PATCH  
**Endpoint:** `http://localhost:6000/api/auth/change-password`  
**Headers:**  
- `client: not-browser`  
- `Authorization: Bearer {jwt_session_token}`  

**Description:** Allows authenticated users to change their password.

---

### 4. Sign Out
**Method:** POST  
**Endpoint:** `http://localhost:6000/api/auth/signout`  
**Description:** Logs out the user and clears authentication session.

---

## Post Management Endpoints

### 5. Create New Post
**Method:** POST  
**Endpoint:** `http://localhost:6000/api/posts/create-post`  
**Headers:**  
- `client: not-browser`  
- `Authorization: Bearer {jwt_session_token}`  

**Request Body:**  
```json
{
    "title": "something",
    "description": "moreeeee"
}
```
**Description:** Allows an authenticated user to create a new post.

---

### 6. Get All Posts
**Method:** GET  
**Endpoint:** `http://localhost:6000/api/posts/all-posts`  
**Description:** Retrieves all posts from the database.

---

### 7. Get Single Post
**Method:** GET  
**Endpoint:** `http://localhost:6000/api/posts/single-post?_id={post_id}`  
**Description:** Retrieves a single post based on its ID.

---

### 8. Update Post
**Method:** PUT  
**Endpoint:** `http://localhost:6000/api/posts/update-post?_id={post_id}`  
**Description:** Updates an existing post with new details.

---

### 9. Delete Post
**Method:** DELETE  
**Endpoint:** `http://localhost:6000/api/posts/delete-post?_id={post_id}`  
**Description:** Deletes a post based on its ID.

---

## Notes:
- All endpoints requiring authentication must include the **Authorization** header with a valid JWT token.
- Ensure the `client: not-browser` header is included where required.
- Passwords should always be encrypted before storage.
By - Bhavay

