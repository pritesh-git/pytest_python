# API Testing with Pytest

This repository contains Pytest scripts for testing the ReqRes API (https://reqres.in/). The tests cover various endpoints, including user management, registration, login, and resource retrieval.

## Project Overview

This project demonstrates how to use Pytest for API testing. It includes tests for:

* **User Management:**
    * Creating users (POST).
    * Updating users (PUT and PATCH).
    * Deleting users (DELETE).
    * Retrieving single and multiple users (GET).
* **Authentication:**
    * User registration (POST).
    * User login (POST).
    * Handling incorrect registration attempts.
* **Resource Retrieval:**
    * Retrieving single and multiple resources (GET).
    * Handling wrong resource requests.

The tests also validate response status codes, JSON data, and data types.

## Technologies Used

* **Python:** 3.x
* **Requests:** For making HTTP requests.
* **Pytest:** For test execution and assertions.

## Getting Started

1.  **Clone the repository:**

    ```bash
    git clone <repository_url>
    cd <repository_directory>
    ```

2.  **Install dependencies:**

    ```bash
    pip install requests pytest
    ```

3.  **Run the tests:**

    ```bash
    pytest
    ```

4.  **View the HTML report (optional):**

    ```bash
    pytest --html=AutomationReport.html
    ```

    Open `AutomationReport.html` in your browser.

## Test Structure

The tests are organized into separate files for user management, authentication, and resource retrieval. Each test function is decorated with `pytest.mark` to categorize and filter tests.

* `test_users.py`: Contains tests for user management (GET, POST, PUT, PATCH, DELETE).
* `test_auth.py`: Contains tests for user registration and login.
* `test_resources.py`: Contains tests for resource retrieval.

## Test Execution and Configuration

* **Running Specific Tests:**
    * To run tests with a specific marker (e.g., `users`), use:
        ```bash
        pytest -m users
        ```
    * To run only login api tests:
        ```bash
        pytest -m login
        ```
    * To run only register api tests:
        ```bash
        pytest -m register
        ```
    * To run only resource api tests:
        ```bash
        pytest -m resource
        ```
* **Pytest Configuration (pytest.ini):**

    ```ini
    [pytest]
    addopts = -rA --html=AutomationReport.html
    markers =
        users: This is user marker
        login: This is login marker
        register: This is register marker
        resource: This is resource marker
    ```

    * `addopts`: Configures Pytest options, including generating an HTML report.
    * `markers`: Defines custom markers for test categorization.

## Test Cases

* **User Management:**
    * `test_create_user()`: Creates a new user and validates the response.
    * `test_put_request()`: Updates a user using PUT.
    * `test_patch_request()`: Updates a user using PATCH.
    * `test_delete_request()`: Deletes a user.
    * `test_user_list()`: Retrieves a list of users.
    * `test_single_user()`: Retrieves a single user.
    * `test_wrong_user()`: Tests retrieving a non-existent user.
* **Authentication:**
    * `test_register_user()`: Registers a new user.
    * `test_wrong_register()`: Tests an incorrect registration attempt.
    * `test_login_user()`: Logs in a user.
* **Resource Retrieval:**
    * `test_resource_list()`: Retrieves a list of resources.
    * `test_single_resource()`: Retrieves a single resource.
    * `test_wrong_resource()`: Tests retrieving a non-existent resource.

## Assertions

The tests use assertions to validate:

* Response status codes.
* JSON data structure and values.
* Data types.
* Presence of data.
* Absence of data.
* Cookie presence.
* Correct error messages.

## Contributing

Feel free to contribute to this project by submitting pull requests.

## License

This project is open-source and available under the MIT License.
