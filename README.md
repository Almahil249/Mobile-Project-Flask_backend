# Mobile-Project-Flask_backend

This repository contains a Flask-based backend for a mobile application. It serves as a REST API for managing students, stores, and items, handling authentication, data storage, and image processing.

## Project Structure

The codebase is organized as follows:

- **`app.py`**: The application factory. It initializes the Flask app, configures the PostgreSQL database connection, and sets up extensions like SQLAlchemy and Migrate.
- **`run.py`**: The entry point for the application. It invokes the application factory and runs the Flask development server.
- **`routes.py`**: Defines the API endpoints. It contains the logic for:
  - **Authentication**: handling login and signup requests.
  - **Student Operations**: retrieving, updating, and deleting student account data.
  - **Store & Item Management**: CRUD operations for stores and products.
  - **Image Serving**: Endpoints for uploading and retrieving compressed images.
- **`models.py`**: Contains the database schema definitions (SQLAlchemy models) for:
  - `Student`: User account details.
  - `Store`: Store information and location.
  - `Item`: Product details.
  - `StoreItemRelation`: Manages the many-to-many relationship between stores and items.
- **`requirements.txt`**: Lists the Python dependencies required to run the project.
- **`vercel.json`**: Configuration settings for deployment on the Vercel platform.
- **`DEFAULT_PROFILE_IMAGE.jpg`**: A default image asset used when a user does not upload a profile picture.

## Features

- **Token-Based Authentication**: Secure login and signup processes returning authentication tokens.
- **Data Management**: Complete Create, Read, Update, and Delete (CRUD) capabilities for Stores and Items.
- **Image Compression**: Automatic compression of uploaded images to optimize storage and retrieval speed.
- **Relational Data**: Ability to link specific items to specific stores.

## Getting Started

### Prerequisites

- Python 3.10
- PostgreSQL (or a compatible SQL database configured in `app.py`)

### Installation

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/Almahil249/Mobile-Project-Flask_backend.git
    cd Mobile-Project-Flask_backend
    ```

2.  **Install dependencies:**
    ```bash
    pip install -r requirements.txt
    ```

### Running the Application

To start the development server:

```bash
python run.py
```

The API will be accessible at `http://localhost:5000`.

## API Endpoints

### Authentication
- `POST /signup/`: Register a new student.
- `POST /login/`: Authenticate an existing student.

### Student
- `GET /getstudentdata/`: Retrieve logged-in student details.
- `PUT /updatestudentdata/`: Update student profile.
- `DELETE /deletestudentaccount/`: Delete student account.

### Stores
- `GET /stores/`: List all stores.
- `POST /stores/`: Create a new store.
- `PUT /stores/<id>/`: Update store details.
- `DELETE /stores/<id>/`: Remove a store.

### Items
- `GET /items/`: List all items.
- `POST /items/`: Add a new item.
- `PUT /items/<id>/`: Update item details.
- `DELETE /items/<id>/`: Remove an item.
