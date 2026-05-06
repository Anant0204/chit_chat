# Chit Chat

A real-time chat application with React + Vite frontend and Express + MongoDB backend.

## Project Overview

This repository contains two main parts:

- `frontend/` — React application built with Vite, Tailwind CSS, Zustand, and Socket.IO client.
- `backend/` — Node.js + Express API server with MongoDB, authentication, messaging routes, email integration, and WebSocket support via Socket.IO.

## Features

- User signup, login, logout, and profile update
- Real-time chat messaging with Socket.IO
- Protected API routes using JWT authentication
- Persistent message storage in MongoDB
- Email and media integration support via Resend and Cloudinary
- Production-ready Express static serving of frontend assets

## Getting Started

### Prerequisites

- Node.js 18+ (or compatible)
- npm
- MongoDB database
- Cloudinary account (optional for file handling)
- Resend or email provider credentials (optional for email sending)

### Setup

1. Clone the repository.
2. Install dependencies for both backend and frontend.

```bash
cd backend
npm install

cd ../frontend
npm install
```

### Environment Variables

Create a `.env` file inside `backend/` with the following keys:

```env
PORT=3000
MONGO_URI=<your-mongodb-uri>
JWT_SECRET=<your-jwt-secret>
RESEND_API_KEY=<your-resend-api-key>
CLIENT_URL=http://localhost:5173
EMAIL_FROM=<sender-email-address>
EMAIL_FROM_NAME=<sender-name>
CLOUDINARY_CLOUD_NAME=<cloudinary-cloud-name>
CLOUDINARY_API_KEY=<cloudinary-api-key>
CLOUDINARY_API_SECRET=<cloudinary-api-secret>
ARCJET_API_KEY=<your-arcjet-api-key>
NODE_ENV=development
```

> `CLIENT_URL` should point to your frontend development server, typically `http://localhost:5173`.

### Run the App

Start the backend server:

```bash
cd backend
npm run dev
```

Start the frontend app:

```bash
cd frontend
npm run dev
```

Open the URL shown by Vite in your browser to use the app.

## Production Build

Build the frontend and serve it from the backend:

```bash
cd frontend
npm run build
```

Then start the backend server in production mode:

```bash
cd ../backend
npm run dev
```

The backend is configured to serve the `frontend/dist` files when `NODE_ENV=production`.

## Folder Structure

- `backend/src/app.js` — Express server entrypoint
- `backend/src/routes/` — API routing for auth and messages
- `backend/src/controllers/` — business logic for auth and messaging
- `backend/src/lib/` — environment, DB connection, socket setup, utilities
- `frontend/src/` — React components, pages, stores, and hooks

## Notes

- The backend uses `cookie-parser` and CORS to support authenticated requests from the frontend.
- Protected routes require a valid JWT token and user session.
- Socket.IO is initialized in the backend server to handle real-time messaging.

## License

This project is provided as-is.
