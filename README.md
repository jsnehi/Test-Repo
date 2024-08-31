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

   ```bash
   git clone <repository_url>
   cd <repository_directory>
   ```
  
  2. Create a virtual environment:

  ```bash
  python -m venv venv
  ```
    
  3. Activate the virtual environment:
  On Windows:

   ```bash
   venv\Scripts\activate
   ```
      
  On macOS/Linux:
    
   ```bash
   source venv/bin/activate
   ```
      
  4. Install dependencies:

   ```bash
   pip install -r requirements.txt
   ```
  
  5. Set up the database:

   ```bash
   python setup_db.py
   ```

   This script will create the necessary tables in an in-memory SQLite database for testing purposes. For a persistent database, you can adjust the URI in config.py.


## CRUD Operations

# Create a New User
* URL: /
* Method: GET, POST
* Description: Displays a form to create a new user and handles form submission to add the user to the database.
# Read All Users
* URL: /get_all_users
* Method: GET
* Description: Displays a list of all users in the database.
# Read Individual Users
* URL: /users/<int:id>
* Method: GET
* Description: Displays an individual users in the database.
# Update a User
* URL: /update_user/<int:id>
* Method: GET, PUT, POST
* Description: Displays a form to update an existing user’s details and handles form submission to update the user.
# Delete a User
* URL: /delete_user/<int:id>
* Method: POST
* Description: Deletes a user by ID from the database.
* Running Tests
# Create a test configuration file: 
```bash
python -m unittest test_app.py
```
This will execute the unit tests defined in test_app.py, which include tests for retrieving all users.

Running the Application
To start the Flask application, use:

```bash
python run.py
```
The application will be accessible at http://127.0.0.1:5000.
