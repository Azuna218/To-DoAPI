
Todo App API
This is a simple backend API for a Todo List application. It allows you to perform CRUD operations (Create, Read, Update, Delete) on tasks stored in a MySQL database.

Features
Create, read, update, and delete tasks.
Each task has a title, description, and completion status.
API documentation is available via Swagger UI.
Technologies Used
Node.js: JavaScript runtime for the server.
Express.js: Web framework for building the API.
MySQL: Database for storing tasks.
Swagger: API documentation and testing.
CORS: Enabling cross-origin requests.
Body-parser: Middleware for parsing JSON data.
Installation
Prerequisites
Node.js: Ensure that you have Node.js installed. You can download it from here.
MySQL (XAMPP): Ensure that MySQL is running. If you're using XAMPP, start the MySQL server.
Step 1: Clone the repository
Clone the repository to your local machine: git clone https://github.com/your-username/todo-app-api.git cd todo-app-api

Step 2: Install dependencies
Run the following command to install the required dependencies: npm install

This will install the necessary packages like express, mysql2, swagger-jsdoc, swagger-ui-express, body-parser, and cors.

Configuration
MySQL Database
Open XAMPP and start the MySQL server.
Access phpMyAdmin via http://localhost/phpmyadmin.
Create a new database named todo_db.
Create a table named tasks with the following schema:

CREATE TABLE tasks (
    id INT AUTO_INCREMENT PRIMARY KEY,
    title VARCHAR(255) NOT NULL,
    description TEXT NOT NULL,
    completed BOOLEAN DEFAULT false
);


Running the Server
Once everything is set up, you can start the server: node server.js

The server will run on http://localhost:5000.

API Documentation (Swagger)
Once the server is running, you can access the API documentation via Swagger UI by navigating to: http://localhost:5000/api-docs

The Swagger UI will display all available endpoints:

POST /tasks: Create a new task.
GET /tasks: Get all tasks.
PUT /tasks/{id}: Update a task by ID.
DELETE /tasks/{id}: Delete a task by ID.
You can interact with the API directly from the Swagger UI by providing the required input.

Example API Calls
Create a Task

POST /tasks
Request: {"title": "Buy groceries", "description": "Milk, eggs, bread"}
Response: {"id": 1, "title": "Buy groceries", "description": "Milk, eggs, bread"}
Get All Tasks

GET /tasks
Response: [{"id": 1, "title": "Buy groceries", "description": "Milk, eggs, bread", "completed": false}]
Update a Task

PUT /tasks/{id}
Request: {"title": "Buy groceries", "description": "Milk, eggs, bread, butter", "completed": true}
Response: {"message": "Task updated successfully"}
Delete a Task

DELETE /tasks/{id}
Response: {"message": "Task deleted successfully"}
Troubleshooting
If you encounter a 500 server error, check the MySQL connection in server.js. Make sure the database name, user, and password are correct.
If you see a 404 error when trying to update or delete a task, ensure that the task with the given ID exists.
