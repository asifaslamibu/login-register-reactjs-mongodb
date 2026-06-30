# Login & Registration — React + Node.js + MongoDB

A full-stack authentication system with a **React** frontend and a **Node.js/Express + MongoDB** backend. It supports user registration, login, JWT-based sessions, a protected user-details view, and password reset over email.

## Tech Stack

- **Frontend:** React 18, React Router DOM, Bootstrap 5
- **Backend:** Node.js, Express, Mongoose
- **Database:** MongoDB (MongoDB Atlas)
- **Auth & security:** JSON Web Tokens (jsonwebtoken), bcryptjs password hashing
- **Email:** Nodemailer (Gmail) for password-reset links
- **Views:** EJS (reset-password pages)

## Features

- User registration with hashed passwords (bcrypt)
- Login issuing a JWT token
- Token-verified "user details" endpoint to fetch the logged-in user
- Forgot / reset password flow with a time-limited email link
- CORS-enabled API consumed by the React client

### API Endpoints (Express, port 5000)

| Method | Route                        | Description                       |
|--------|------------------------------|-----------------------------------|
| POST   | `/register`                  | Create a new user                 |
| POST   | `/login-user`                | Authenticate and return a JWT     |
| POST   | `/userData`                  | Return user data for a valid token |
| POST   | `/forgot-password`           | Email a password-reset link       |
| GET/POST | `/reset-password/:id/:token` | Render & process password reset  |

## Prerequisites

- Node.js and npm
- A MongoDB connection string (e.g. MongoDB Atlas)

## Installation & Setup

### 1. Server

```bash
cd login-registration-server-node-main
npm install
node app.js      # runs on http://localhost:5000
```

Before running, set your own values in `app.js`:
- `mongoUrl` — your MongoDB connection string
- `JWT_SECRET` — a strong secret
- Nodemailer credentials for the password-reset email

> Note: the committed source contains example/demo credentials. Replace them with your own and keep secrets out of version control in real deployments.

### 2. Client

```bash
cd login-registration-main
npm install
npm start        # runs on http://localhost:3000
```

## Project Structure

```
login-registration-main/            # React frontend
└── src/components/
    ├── login_component.js
    ├── signup_component.js
    └── userDetails.js
login-registration-server-node-main/ # Express + MongoDB backend
└── app.js
```

## License

This project is for educational/portfolio purposes.
