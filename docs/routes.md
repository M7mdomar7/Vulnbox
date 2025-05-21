# 📌 VulnBox – Route Documentation

This document describes all available routes in the VulnBox project, including their purpose, expected behavior, and any intentional vulnerabilities for educational purposes.

---

## 🔹 GET `/`
### Description:
Returns the homepage. This may be a simple welcome page or basic HTML.

### Purpose:
- Confirms the server is running
- Entry point for users

### Notes:
- Could include links to login/register pages

---

## 🔹 GET `/login`
### Description:
Displays a login form for users.

### Purpose:
- Allows users to enter their credentials

### Vulnerability:
- No CSRF protection
- Could be susceptible to credential stuffing

---

## 🔸 POST `/login`
### Description:
Processes login credentials submitted by the user.

### Behavior:
- Compares entered username/password with DB
- Starts session if valid

### Vulnerabilities:
- Passwords may be stored as plaintext or weakly hashed (e.g. MD5)
- No rate limiting / brute force protection

---

## 🔹 GET `/register`
### Description:
Displays a user registration form.

### Purpose:
- Allows users to create new accounts

---

## 🔸 POST `/register`
### Description:
Accepts and stores new user data.

### Behavior:
- Saves new user to database
- Typically skips validation

### Vulnerabilities:
- No email verification
- May allow weak or duplicate usernames
- Insecure password storage (deliberate)

---

## 🔹 GET `/admin`
### Description:
Displays an admin-only page.

### Purpose:
- Simulates a protected resource

### Vulnerabilities:
- May lack proper authentication/authorization checks
- Users could access it by guessing the route or exploiting session flaws

---

## 🔹 GET `/upload`
### Description:
Returns a form to upload files.

### Purpose:
- Lets users upload files for testing

---

## 🔸 POST `/upload`
### Description:
Handles uploaded files.

### Behavior:
- Accepts file and saves it to disk (or server dir)

### Vulnerabilities:
- No file type/size validation
- May allow executable/script files
- Could be used for remote code execution

---

## 🔹 GET `/profile`
### Description:
Displays the current user's profile (if logged in).

### Purpose:
- Shows user info and account details

### Vulnerability:
- Profile data may be exposed without proper session checks

---

## 🔹 Catch-All `*`
### Description:
Handles undefined routes (404)

### Purpose:
- Improves UX and handles bad links
- May or may not be implemented intentionally for exploit opportunity

---

# 🛠 Notes

- This app is intentionally vulnerable for **educational use only**.
- Do not deploy it publicly without fixing security flaws.
