# DRF_Project

# Django Task Management API

This is a simple REST API built with Django and Django REST Framework (DRF) that allows users to perform CRUD operations on a `Task` model.

## Features

- Create, Retrieve, Update, and Delete tasks.
- Use Django REST Framework's ModelSerializer for easy serialization.
- Endpoints for handling tasks.

---

## Setup Instructions

### 1. Clone the Repository

First, clone this repository to your local machine:

```bash
git clone https://github.com/Gayatribwagh/DRF_Project.git
cd DRF_Project
```

### 2. Create a Virtual Environment

Set up a virtual environment to isolate dependencies:

- On Windows:
  ```bash
  python -m venv venv
  venv\Scripts\activate
  ``  ```

### 3. Install Dependencies

Install the required packages using the `requirements.txt` file:

```bash
pip install -r requirements.txt
```

### 4. Apply Migrations

Run the following commands to create the necessary database tables for the `Task` model:

```bash
python manage.py makemigrations
python manage.py migrate
```

### 5. Run the Development Server

Start the development server to access the API:

```bash
python manage.py runserver
```

The API will be accessible at `http://127.0.0.1:8000/`.

---

## API Endpoints

The API supports the following CRUD operations for tasks:

| HTTP Method | Endpoint                 | Description                    |
|-------------|--------------------------|--------------------------------|
| **GET**     | `/api/tasks/`             | Retrieve the list of tasks     |
| **POST**    | `/api/tasks/`             | Create a new task              |
| **GET**     | `/api/tasks/<id>/`        | Retrieve a single task by ID   |
| **PUT**     | `/api/tasks/<id>/`        | Update an existing task        |
| **DELETE**  | `/api/tasks/<id>/`        | Delete a task by ID            |

---

## Example Requests

### 1. Get All Tasks (GET Request)

```bash
GET /api/tasks/
```

- **Response:**
  ```json
  [
      {
          "id": 1,
          "title": "First Task",
          "description": "This is the first task.",
          "due_date": "2024-10-25",
          "status": false
      },
      {
          "id": 2,
          "title": "Second Task",
          "description": "This is the second task.",
          "due_date": "2024-11-01",
          "status": true
      }
  ]
  ```

### 2. Create a New Task (POST Request)

```bash
POST /api/tasks/
```

- **Request Body:**
  ```json
  {
      "title": "New Task",
      "description": "Task description here.",
      "due_date": "2024-10-30",
      "status": false
  }
  ```

- **Response:**
  ```json
  {
      "id": 3,
      "title": "New Task",
      "description": "Task description here.",
      "due_date": "2024-10-30",
      "status": false
  }
  ```

### 3. Retrieve a Single Task (GET Request)

```bash
GET /api/tasks/1/
```

- **Response:**
  ```json
  {
      "id": 1,
      "title": "First Task",
      "description": "This is the first task.",
      "due_date": "2024-10-25",
      "status": false
  }
  ```

### 4. Update a Task (PUT Request)

```bash
PUT /api/tasks/1/
```

- **Request Body:**
  ```json
  {
      "title": "Updated Task Title",
      "description": "Updated task description.",
      "due_date": "2024-11-05",
      "status": true
  }
  ```

- **Response:**
  ```json
  {
      "id": 1,
      "title": "Updated Task Title",
      "description": "Updated task description.",
      "due_date": "2024-11-05",
      "status": true
  }
  ```

### 5. Delete a Task (DELETE Request)

```bash
DELETE /api/tasks/1/
```

- **Response:**

  HTTP 204 No Content (Task deleted successfully)



