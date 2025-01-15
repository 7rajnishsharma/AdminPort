# FlowManage (User Management System)

A full-stack User Management System that provides a seamless interface for user registration, profile updates, and administrative controls. Built with Node.js, Express, MongoDB, and React, this application includes robust authentication, CRUD operations, and an admin dashboard for user management.

---

## Features

### User Features
- **Registration**: Users can register with their username, email, and password.
- **Login**: Users can log in securely with their credentials.
- **Profile Management**: Users can upload profile pictures and manage their details.
- **Logout**: Secure session termination.

### Admin Features
- **Dashboard**: View all registered users.
- **User Management**: Add, update, or delete user details.
- **Search**: Quickly search for users using email or username.

### Technical Features
- **API**: CRUD operations for users via RESTful API.
- **Authentication**: JWT-based authentication for secure sessions.
- **State Management**: Managed with Redux Toolkit for consistent app behavior.
- **Error Handling**: Comprehensive error handling across the backend and frontend.
- **Responsive Design**: Fully responsive user interface.

---

## Technologies Used

### Backend
- **Node.js**
- **Express.js**
- **MongoDB**
- **JWT**
- **bcrypt**

### Frontend
- **React** 
- **Redux Toolkit**
- **React Router Dom**
- **Axios**
- **SweetAlert2**

---

## Setup Instructions

### Backend Setup
1. Clone the repository:
   ```bash
   git clone https://github.com/7rajnishsharma/FlowManage.git
   cd Backend
   ```
2. Install dependencies:
   ```bash
   npm install
   ```
3. Create a `.env` file in the backend root directory and add the following:

   ```env
   PORT=8000
   mongoDB_URL=mongodb://127.0.0.1:27017/User-Management-React-App
   JWT_SECRET=kjhsdkjfh23j4h2302343234dsfsd2d1f94385jkh34kj5h54687nbdmlfg
   ADMIN_MAIL=admin@gmail.com
   ADMIN_PASSWORD=admin@gmail.com
   ```
4. Start the backend server:
   ```bash
   nodemon app.js
   ```

### Frontend Setup
1. Navigate to the frontend directory:
   ```bash
   cd frontend
   ```
2. Install dependencies:
   ```bash
   npm install
   ```
3. Start the React development server:
   ```bash
   npm start
   ```

---

## API Endpoints

### API Endpoints

#### Admin Routes
The following routes are accessible by admin users:

1. **Login Admin**  
   - **Endpoint:** `/admin/login`  
   - **Method:** `POST`  
   - **Description:** Authenticates the admin using email and password.
   - **Request Body:**
     ```json
     {
       "email": "string",
       "password": "string"
     }
     ```
   - **Response:**
     - `200 OK` with JWT token on successful login.
     - `401 Unauthorized` if authentication fails.

2. **Get All Users**  
   - **Endpoint:** `/admin/allUsers`  
   - **Method:** `GET`  
   - **Middleware:** `checkAuth`
   - **Description:** Fetches all users from the database.
   - **Response:**
     - `200 OK` with an array of user objects.
     - `401 Unauthorized` if JWT token is invalid.

3. **Add New User**  
   - **Endpoint:** `/admin/addUser`  
   - **Method:** `POST`  
   - **Middleware:** `checkAuth`
   - **Description:** Adds a new user to the database.
  
     

4. **Edit User**  
   - **Endpoint:** `/admin/edituser/:_id`  
   - **Method:** `PUT`  
   - **Middleware:** `checkAuth`
   - **Description:** Updates user details based on their ID.

5. **Delete User**  
   - **Endpoint:** `/admin/deleteuser/:_id`  
   - **Method:** `DELETE`  
   - **Middleware:** `checkAuth`
   - **Description:** Deletes a user based on their ID.
   - **Request Params:**
     - `_id`: The unique ID of the user.
   - **Response:**
     - `204 No Content` on successful deletion.
     - `404 Not Found` if user ID does not exist.
     - `400 Bad Request` for invalid input.

#### User Routes
The following routes are accessible by regular users:

1. **Login User**  
   - **Endpoint:** `/user/login`  
   - **Method:** `POST`  
   - **Description:** Authenticates a user using email and password.
   - **Request Body:**
     ```json
     {
       "email": "string",
       "password": "string"
     }
     ```
   - **Response:**
     - `200 OK` with JWT token and user data on successful login.
     - `401 Unauthorized` if authentication fails.

2. **Sign Up User**  
   - **Endpoint:** `/user/signup`  
   - **Method:** `POST`  
   - **Description:** Registers a new user.
   - **Request Body:**
     ```json
     {
       "username": "string",
       "email": "string",
       "password": "string"
     }
     ```
   - **Response:**
     - `201 Created` on successful registration.
     - `400 Bad Request` if validation fails.

3. **Add Profile Image**  
   - **Endpoint:** `/user/addImage`  
   - **Method:** `POST`  
   - **Middleware:** `checkAuth`
   - **Description:** Allows a user to upload a profile image.
   - **Request Body:**
     - Multipart form-data with image file.
   - **Response:**
     - `200 OK` on successful upload.
     - `400 Bad Request` if file upload fails.


---

## Postman Testing

### 1. Register User
- **Method**: POST
- **URL**: `http://localhost:8000/api/users`
- **Body** (JSON):
  ```json
  {
    "username": "testuser",
    "email": "testuser@example.com",
    "password": "password123"
  }
  ```

### 2. Login User
- **Method**: POST
- **URL**: `http://localhost:8000/api/auth/login`
- **Body** (JSON):
  ```json
  {
    "email": "testuser@example.com",
    "password": "password123"
  }
  ```

### 3. Login Admin
- **Method**: POST
- **URL**: `http://localhost:8000/api/auth/login`
- **Body** (JSON):
  ```json
  {
    "email": "admin@gmail.com",
    "password": "admin@gmail.com"
  }
  ```

---

## Visual Representation

1. **User Interface**:
   - Demonstrates user registration, login, profile picture upload, and logout.
   ![user](https://github.com/user-attachments/assets/83a1ae4c-125b-4e7c-b6c2-67483264fde1)

2. **Admin Interface**:
   - Demonstrates admin login, searching users, updating user details, adding new users, and logout.
   ![admin](https://github.com/user-attachments/assets/e352df3e-60b4-4378-8c59-c92a50cfc03a)

3. MongoDB collections and documents showcasing user data.

   ![Screenshot 2025-01-15 163803](https://github.com/user-attachments/assets/ccfa50c7-f226-4586-8458-73ba7bb944c5)



---


