# postman
# Contact List API Test Project

This is a ready GitHub repository structure for your Contact List API assignment, including Postman collections, environment files, and documentation.

## Repository Structure

```
contact-list-api-tests/
│
├── collections/
│   ├── ContactList_SmokeTests.postman_collection.json
│   └── ContactList_NegativeTests.postman_collection.json
│
├── environments/
│   └── ContactListEnv.postman_environment.json
│
├── README.md
└── .gitignore
```

---

## File Descriptions

### 1. `collections/ContactList_SmokeTests.postman_collection.json`

* Contains positive API tests:

  * Login
  * Add contact (POST)
  * Get contacts (GET)
  * Update contact (PATCH)
  * Delete contact (DELETE)
* Includes test scripts for saving `token` and `contactId` in environment variables.

### 2. `collections/ContactList_NegativeTests.postman_collection.json`

* Contains negative API tests:

  * Login with wrong credentials
  * POST contact with missing fields
  * POST contact with invalid email
  * PATCH contact with invalid postal code
  * GET contacts without token
  * DELETE contact without token

### 3. `environments/ContactListEnv.postman_environment.json`

* Environment variables:

  * `baseUrl`: `https://thinking-tester-contact-list.herokuapp.com`
  * `token`: will be set after login
  * `contactId`: will be set after POST contact

### 4. `README.md`

* Explains how to run smoke and negative tests using Postman or Newman.

### 5. `.gitignore`

* Ignore local system files like `*.DS_Store` and Postman temporary files if needed.

---

## README.md Example

````markdown
# Contact List API Test Project

## Setup

1. Import the Postman collections:
   - `collections/ContactList_SmokeTests.postman_collection.json`
   - `collections/ContactList_NegativeTests.postman_collection.json`
2. Import the environment:
   - `environments/ContactListEnv.postman_environment.json`

## Running Tests

### Postman UI
1. Select the environment `ContactListEnv`.
2. Run collections using **Collection Runner**.

### Newman CLI

```bash
# Install Newman if not installed
npm install -g newman

# Run Smoke Tests
newman run collections/ContactList_SmokeTests.postman_collection.json -e environments/ContactListEnv.postman_environment.json

# Run Negative Tests
newman run collections/ContactList_NegativeTests.postman_collection.json -e environments/ContactListEnv.postman_environment.json
````

## Notes

* Ensure valid `email` and `password` exist in the login request.
* Smoke tests depend on environment variables `token` and `contactId`.
* Negative tests intentionally use invalid data to validate API error handling.

```

---

This structure allows you to push to GitHub immediately, and others can **import collections and run tests directly**. You can also extend it later with more UI or API tests.

```
