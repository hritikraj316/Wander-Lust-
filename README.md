# WanderLust

WanderLust is a travel-stay listing web application built with Node.js, Express, EJS, and MongoDB. Users can browse accommodation listings, create an account, and manage their own listings and reviews.

## Features

- Browse listings and view their details.
- Sign up, log in, and log out using Passport local authentication.
- Create, edit, and delete listings. Creating and managing listings requires authentication, and only the listing owner can edit or delete it.
- Add reviews to listings and delete reviews you authored.
- Validate listing and review submissions and show success or error messages.

## Requirements

- Node.js and npm
- MongoDB running locally at `mongodb://127.0.0.1:27017`

The application connects to the MongoDB database named `WanderLust` and listens on port `8080`.

## Getting Started

1. Clone or download this project and open a terminal in its root directory.
2. Install dependencies:

   ```bash
   npm install
   ```

3. Start MongoDB if it is not already running.
4. Start the application:

   ```bash
   node app.js
   ```

5. Open [http://localhost:8080](http://localhost:8080) in your browser. Browse listings at [http://localhost:8080/listings](http://localhost:8080/listings).

## Project Structure

```text
models/       Mongoose models for listings, reviews, and users
routes/       Express routes for listings, reviews, and authentication
views/        EJS page templates and shared layout components
public/       Static CSS and client-side JavaScript
init/         Sample listing data and database initialization script
middleware.js Request validation and authentication/ownership middleware
app.js        Express application setup and server entry point
```

## Development Notes

- The MongoDB connection string and Express session secret are currently defined directly in `app.js`. Replace the session secret and use environment variables before deploying the application.
- `npm test` is currently a placeholder; no automated test suite is configured yet.
- The optional sample-data initializer is `node init/index.js`. It deletes all existing listings before inserting sample listings, so do not run it against data you need to keep.
