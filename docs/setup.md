### ✅ Installed: Express

- Purpose: Core web framework for handling routes, middleware, and requests/responses.
- Installed via: `npm install express`

### ✅ Installed: Mongoose

- Purpose: ODM (Object Data Modeling) library to manage MongoDB data with schemas and models.
- Benefits: Simplifies DB operations and adds structure to collections like users, files, etc.
- Installed via: `npm install mongoose`

### ✅ Installed: Multer

- Purpose: Middleware for handling file uploads via HTML forms.
- Use: Powers the `/upload` route to accept and store user-submitted files.
- Security Note: Improper config will allow insecure file types (intentionally).
- Installed via: `npm install multer`

### ✅ Installed: dotenv

- Purpose: Loads environment variables from a `.env` file into `process.env`.
- Use: Keeps sensitive info (like MongoDB URI, session secrets) out of source code.
- Installed via: `npm install dotenv`

### ✅ Installed: express-session

- Purpose: Manages user sessions on the server side.
- Behavior: Stores session data (e.g., login status) in memory or a store, while sending the user only a session ID via cookie.
- Why used here: Allows us to simulate insecure session handling (e.g., no expiration, no secure flags).
- Installed via: `npm install express-session`

#### 🆚 JWT vs express-session (for reference):

| Method             | Stored On      | Type       | Used in VulnBox? |
|--------------------|----------------|------------|------------------|
| `express-session`  | Server memory  | Stateful   | ✅ Yes            |
| `JWT`              | Client/browser | Stateless  | ❌ No             |

Note: JWT is great for APIs, but `express-session` fits better for server-rendered or vulnerable playground apps.


### ✅ Installed: EJS

- Purpose: Templating engine that lets us generate dynamic HTML using JavaScript variables.
- Use: Pages like login, upload, and admin can display different content based on user/session data.
- Example: `<%= username %>` inside HTML will render the actual logged-in username.
- Installed via: `npm install ejs`


