# Test-Repo

### Flask Web Application
This is a basic Flask web application that demonstrates CRUD (Create, Read, Update, Delete) operations with SQLite as the database. It includes routes to create, read, update, and delete users, and it provides unit tests to verify functionality.

## Table of Contents
  * Setup Instructions
  * CRUD Operations
  * Running Tests


## Setup Instructions
# Prerequisites
Ensure you have Python installed on your machine. You can download it from python.org.

# Installation
  1. Clone the repository:

    ```shell
      git clone <repository_url>
      cd <repository_directory>
    ```
  
  2. Create a virtual environment:

    ```shell
      python -m venv venv
    ```
    
  3. Activate the virtual environment:
    * On Windows:

      ```shell
        venv\Scripts\activate
      ```
      
    * On macOS/Linux:
    
      ```bash
        source venv/bin/activate
      ```
      
  4. Install dependencies:

    ```shell
      pip install -r requirements.txt
    ```
  
  5. Set up the database:

    ```bash
      python setup_db.py
    ```

    This script will create the necessary tables in an in-memory SQLite database for testing purposes. For a persistent database, you can adjust the URI in config.py.

Configuration
The application uses a test_config.py for testing. This file should contain:

python
Copy code
class TestConfig:
    TESTING = True
    SQLALCHEMY_DATABASE_URI = 'sqlite:///:memory:'
    SQLALCHEMY_TRACK_MODIFICATIONS = False
For other configurations, adjust config.py as needed.

CRUD Operations
Create a New User
URL: /create
Method: GET, POST
Description: Displays a form to create a new user and handles form submission to add the user to the database.
Read All Users
URL: /users
Method: GET
Description: Displays a list of all users in the database.
Update a User
URL: /update/<int:id>
Method: GET, PUT
Description: Displays a form to update an existing user’s details and handles form submission to update the user.
Delete a User
URL: /delete/<int:id>
Method: POST
Description: Deletes a user by ID from the database.
Running Tests
Create a test configuration file: Ensure you have test_config.py with the following content:

python
Copy code
class TestConfig:
    TESTING = True
    SQLALCHEMY_DATABASE_URI = 'sqlite:///:memory:'
    SQLALCHEMY_TRACK_MODIFICATIONS = False
Run the tests:

bash
python -m unittest test_app.py
This will execute the unit tests defined in test_app.py, which include tests for retrieving all users.

Running the Application
To start the Flask application, use:

bash
Copy code
python run.py
The application will be accessible at http://127.0.0.1:5000.
