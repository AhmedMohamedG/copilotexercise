# Mergington High School Activities API

A super simple FastAPI application that allows students to view and sign up for extracurricular activities.

## Features

- View all available extracurricular activities
- Sign up for activities

## Getting Started

1. Install the dependencies (recommended: from the repo virtual environment):

   ```sh
   # create a venv (if you don't have one already)
   python -m venv .venv
   # activate the venv on Linux/macOS
   source .venv/bin/activate
   # install pinned dependencies
   pip install -r ../requirements.txt
   ```

2. Run the application:

   ```sh
   # run with uvicorn for reload and proper ASGI support
   uvicorn src.app:app --reload
   ```

3. Open your browser and go to:
   - API documentation: http://localhost:8000/docs
   - Alternative documentation: http://localhost:8000/redoc

## API Endpoints

| Method | Endpoint                                                          | Description                                                         |
| ------ | ----------------------------------------------------------------- | ------------------------------------------------------------------- |
| GET    | `/activities`                                                     | Get all activities with their details and current participant count |
| POST   | `/activities/{activity_name}/signup?email=student@mergington.edu` | Sign up for an activity                                             |

## Data Model

The application uses a simple data model with meaningful identifiers:

1. **Activities** - Uses activity name as identifier:

   - Description
   - Schedule
   - Maximum number of participants allowed
   - List of student emails who are signed up

2. **Students** - Uses email as identifier:
   - Name
   - Grade level

All data is stored in memory, which means data will be reset when the server restarts.

Troubleshooting
---------------

- If you see an error like `ModuleNotFoundError: No module named 'uvicorn'`, make sure you activated the same Python environment you used to install dependencies. In the repository we use a local virtual environment (`.venv`) by default — run `source .venv/bin/activate` and then `pip install -r ../requirements.txt` if needed.

