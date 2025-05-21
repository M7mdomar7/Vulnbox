# Vulnbox
A deliberately insecure web application built with Node.js and MongoDB. This is a learning project to explore web vulnerabilities and how to exploit/fix them.

# Basic Server setup
Using Express.js to build the server. Will listen on port 3000. 
This server will handle user routes, auth, and database calls later.
Decided on Express for simplicity and ecosystem support.

# Routes plan
`GET /` - Home page
`GET/POST /login` - User login
`GET/POST /register` - User registration
`GET /admin` - Fake admin panel
`GET/POST /upload` - File upload functionality
