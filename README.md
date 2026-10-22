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
- A MongoDB database, either a local MongoDB server or a MongoDB Atlas cluster

The application reads its database URI and session secret from environment variables. It listens on port `8080` locally, or on the port provided by the hosting platform.

## Getting Started

1. Clone or download this project and open a terminal in its root directory.
2. Install dependencies:

   ```bash
   npm install
   ```

3. Copy `.env.example` to `.env`. For local development, the example uses `mongodb://127.0.0.1:27017/WanderLust`; update `SESSION_SECRET` to a long random value. For deployment, set `MONGODB_URI` to your MongoDB Atlas connection string and set `SESSION_SECRET` in the hosting provider's environment settings.
4. Start the application:

   ```bash
   npm start
   ```

5. Open [http://localhost:8080](http://localhost:8080) in your browser. Browse listings at [http://localhost:8080/listings](http://localhost:8080/listings).

For Render, set the build command to `npm install` and the start command to `npm start`. Add `MONGODB_URI` and `SESSION_SECRET` under the service's environment variables. In MongoDB Atlas, allow network access from Render (or configure an appropriate network access policy) and ensure the database user has access to the target database.

## Project Structure

```text
models/       Mongoose models for listings, reviews, and users
routes/       Express routes for listings, reviews, and authentication
views/        EJS page templates and shared layout components
public/       Static CSS and client-side JavaScript
init/         Sample listing data and database initialization script
middleware.js Request validation and authentication/ownership middleware
app.js        Express application setup and server entry point
.env.example  Example local environment configuration
```

## Development Notes

- Never commit `.env` or put database credentials in source code. If credentials were previously pushed to a public repository, rotate them in MongoDB Atlas and replace them in the hosting provider's environment settings.
- `npm test` is currently a placeholder; no automated test suite is configured yet.
- The optional sample-data initializer is `node init/index.js`. It deletes all existing listings before inserting sample listings, so do not run it against data you need to keep.
