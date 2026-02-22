# Lab: Contractors Lab

---

## Overview

Now it is time for you to build your own request responses!

You are working for a company that manages contracts between two parties. You need to manage sensitive data, and as such, you need to build two requests:

- One for **customer information**
- One for **contract information**

You will be using two new response codes:

- **204**: Successful response but no data to send (e.g., confirming a customer exists without sharing data).
- **404**: Not found — we cannot find the requested data.

---

## Tasks

### Task 1: Define the Problem

Build the following routes:

- `/contract/<id>`
- `/customer/<customer_name>`

---

### Task 2: Determine the Design

#### App Routes:

- `GET /contract/<id>`
  - **200**: Contract found — return contract information.
  - **404**: Contract not found.

- `GET /customer/<customer_name>`
  - **204**: Customer found — no information returned (sensitive).
  - **404**: Customer not found.

---

### Task 3: Develop the Code

- Initialize Flask
- Set up routes
- Configure responses

---

### Task 4: Test and Refine

- Debug and test during development using the provided test suite and Flask instance.

---

### Task 5: Document and Maintain

- Commit as you go with meaningful messages.
- Push commit history to GitHub periodically and when the lab is complete.

---

## API Endpoints

### `GET /contract/<id>`

Look up a contract by its numeric ID.

| Status Code | Description |
|-------------|-------------|
| **200** | Contract found — returns the contract information as plain text. |
| **404** | Contract not found. |

**Example:**

```
GET /contract/1  →  200  "This contract is for John and building a shed"
GET /contract/99 →  404  "Contract not found"
```

### `GET /customer/<customer_name>`

Verify whether a customer exists. No data is returned to protect sensitive information.

| Status Code | Description |
|-------------|-------------|
| **204** | Customer found — empty response body (sensitive data). |
| **404** | Customer not found. |

**Example:**

```
GET /customer/bob   →  204  (empty body)
GET /customer/mario →  404  "Customer not found"
```

---

## Setup

1. Fork and clone the repository.
2. Install dependencies:

```bash
pipenv install
pipenv shell
```

3. Run the server:

```bash
python server/app.py
```

4. Run tests:

```bash
python -m pytest server/testing/app_test.py -v
```

---

## Tools and Resources

- **Flask Quickstart**: [https://flask.palletsprojects.com/en/stable/quickstart/](https://flask.palletsprojects.com/en/stable/quickstart/)
