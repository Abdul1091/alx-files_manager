# Files Manager

## Description
The **Files Manager** is a simple web-based file management system built with Node.js, Express, and MongoDB. It provides a RESTful API for managing files and user authentication, with support for Redis for caching and background tasks using Bull. This project demonstrates key backend concepts, including:

- User authentication and session management.
- File upload and management.
- Background task processing.
- Integration with Redis and MongoDB.
- RESTful API design.

---

## Features
- **User Management**: Register, login, and logout.
- **File Operations**:
  - Upload files.
  - List user-specific files.
  - View file metadata.
  - Download files.
- **Redis Integration**:
  - Caching.
  - Session management.
- **Background Tasks**:
  - Generate thumbnails for uploaded image files.

---

## Technologies Used

- **Node.js**: Runtime environment for the backend.
- **Express**: Web framework for building the RESTful API.
- **MongoDB**: Database for storing user and file data.
- **Redis**: In-memory data store for caching and session management.
- **Bull**: Library for handling background jobs.
- **Multer**: Middleware for handling file uploads.
- **UUID**: Generate unique identifiers for files.
- **Mocha & Chai**: Testing framework and assertion library.
- **Supertest**: HTTP assertions for API testing.

---

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/files_manager.git
   cd files_manager
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Set up your environment variables:
   Create a `.env` file in the root directory with the following variables:
   ```env
   PORT=5000
   DB_HOST=localhost
   DB_PORT=27017
   DB_DATABASE=files_manager
   REDIS_HOST=localhost
   REDIS_PORT=6379
   ```

4. Start MongoDB and Redis:
   Ensure MongoDB and Redis are running on your system. Alternatively, use Docker:
   ```bash
   docker run -d -p 27017:27017 --name mongodb mongo
   docker run -d -p 6379:6379 --name redis redis
   ```

5. Start the server:
   ```bash
   npm start
   ```

6. Test the server:
   ```bash
   npm test
   ```

---

## API Endpoints

### **Status Endpoints**
- `GET /status`: Check if Redis and MongoDB are operational.
- `GET /stats`: Retrieve the number of users and files in the database.

### **User Endpoints**
- `POST /users`: Register a new user.
- `GET /connect`: Log in a user (return a token).
- `GET /disconnect`: Log out a user.

### **File Endpoints**
- `POST /files`: Upload a file.
- `GET /files`: List all user files.
- `GET /files/:id`: Retrieve metadata for a specific file.
- `GET /files/:id/data`: Download a file.

---

## Directory Structure
```
files_manager/
├── controllers/
│   ├── AppController.js
│   ├── UsersController.js
│   └── FilesController.js
├── middlewares/
│   └── auth.js
├── routes/
│   └── index.js
├── tests/
│   ├── utils.test.js
│   ├── users.test.js
│   └── files.test.js
├── utils/
│   ├── redis.js
│   └── db.js
├── .env
├── .gitignore
├── package.json
├── README.md
└── server.js
```

---

## Testing
To run the tests, execute:
```bash
npm test
```
Ensure MongoDB and Redis are running during testing.

---

## Contributing
Contributions are welcome! Follow these steps:
1. Fork the repository.
2. Create a new branch:
   ```bash
   git checkout -b feature-name
   ```
3. Commit your changes:
   ```bash
   git commit -m "Add feature description"
   ```
4. Push to your branch:
   ```bash
   git push origin feature-name
   ```
5. Open a pull request
