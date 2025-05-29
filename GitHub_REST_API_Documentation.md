# 🛠 GitHub REST API Documentation

## Overview
This sample documentation demonstrates how I would approach documenting an authenticated REST API for developers. I selected the GitHub REST API to showcase scenarios involving token-based authentication, request payloads, and error handling within developer workflows.

The GitHub REST API allows developers to programmatically interact with repositories, issues, pull requests, and user profiles. It is often used to automate workflows, integrate external tools, and enhance development productivity. This documentation helps developers understand endpoint behavior, construct requests with authentication, interpret JSON responses, and manage errors.

---

## Base URL
```
https://api.github.com
```

---

## Authentication

GitHub's REST API uses token-based authentication.

### Personal Access Token
You can generate a token from your GitHub account settings under **Developer Settings > Personal Access Tokens**.

Include the token in your request headers:
```
Authorization: token YOUR_TOKEN
```

---

## Quick Start Example

**Retrieve your user profile with a token using Postman:**

1. Set the request type to `GET`
2. Use the following URL:
   ```
   https://api.github.com/user
   ```
3. Under the **Headers** tab, add:
   ```
   Key: Authorization
   Value: token YOUR_TOKEN
   ```
4. Click **Send** to view the authenticated user response.

---

## Endpoints

### `GET /user`
Retrieves the authenticated user’s profile.

**Request:**
```
GET https://api.github.com/user
```

**Headers:**
```
Authorization: token YOUR_TOKEN
```

**Response Example:**
```json
{
  "login": "yourusername",
  "id": 1234567,
  "email": "you@example.com",
  "public_repos": 42
}
```

---

### `GET /repos/{owner}/{repo}`
Retrieves details about a specific repository.

**Request:**
```
GET https://api.github.com/repos/octocat/Hello-World
```

**Response Example:**
```json
{
  "name": "Hello-World",
  "full_name": "octocat/Hello-World",
  "private": false,
  "owner": {
    "login": "octocat"
  },
  "html_url": "https://github.com/octocat/Hello-World"
}
```

---

### `POST /repos/{owner}/{repo}/issues`
Creates a new issue in a repository.

**Request:**
```http
POST https://api.github.com/repos/octocat/Hello-World/issues
```

**Headers:**
```
Authorization: token YOUR_TOKEN
Content-Type: application/json
```

**Body:**
```json
{
  "title": "Found a bug",
  "body": "I'm having a problem with this.",
  "assignees": ["octocat"],
  "labels": ["bug"]
}
```

**Response:**
Returns a JSON object representing the created issue.

---

## Status Codes

| Code | Meaning              |
|------|----------------------|
| 200  | Success              |
| 201  | Resource created     |
| 401  | Unauthorized         |
| 404  | Not found            |
| 422  | Validation failed    |
| 500  | Server error         |

---

## Common Use Cases

- Automating issue creation and assignment in GitHub repositories
- Integrating GitHub data into internal dashboards or reporting tools
- Retrieving repository metadata for analysis or archiving
- Syncing pull request or issue activity with external project management tools
- Authenticating users and retrieving their profile or contribution data

---

## Troubleshooting Tips
- Always include a valid token when accessing private data.
- If your request returns `401`, double-check your authentication header.
- For `POST` requests, make sure you’re using proper JSON and required fields.

---

## Tools Used
- Referenced official GitHub Developer Docs
- Formatted and previewed Markdown using **StackEdit**
- Tested API endpoints using **Postman**
- Validated JSON responses with **jsonlint.com**
- Published content via **GitHub Pages**
