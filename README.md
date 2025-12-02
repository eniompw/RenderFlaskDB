# RenderFlaskDB

A simple Flask application demonstrating user authentication (login and signup) using SQLite. This project is configured for easy deployment on [Render](https://render.com).

## Features

- **User Signup**: Create a new account with a username and password.
- **User Login**: Authenticate with existing credentials.
- **Database**: Uses SQLite to store user information.
- **Deployment**: Includes `render.yaml` for Infrastructure as Code (IaC) deployment on Render.

## Project Structure

- `app.py`: The main Flask application containing routes for login, signup, and database interactions.
- `create_table.py`: A script to initialize the SQLite database and create the `users` table.
- `templates/`: HTML templates for the login and signup pages.
- `render.yaml`: Configuration file for deploying the web service on Render.
- `requirements.txt`: List of Python dependencies.

## Getting Started

### Prerequisites

- Python 3.x
- pip (Python package installer)

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/eniompw/RenderFlaskDB.git
   cd RenderFlaskDB
   ```

2. Install the dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Initialize the database:
   ```bash
   python create_table.py
   ```
   This will create a `login.db` file in your project directory.

### Running Locally

To run the application locally:

```bash
flask run
```

Open your browser and navigate to `http://127.0.0.1:5000`.

## Deployment on Render

You can deploy this application as a Web Service on Render.

1. Create a new **Web Service** on Render.
2. Connect this repository.
3. Configure the service with the following settings:
   - **Runtime**: Python 3
   - **Build Command**: `pip install -r requirements.txt && python create_table.py`
   - **Start Command**: `gunicorn app:app`
4. Click **Create Web Service**.

## License

This project is licensed under the terms of the LICENSE file.