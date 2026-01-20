# The Big Counter
The Big Counter is a full-stack web application for managing counters. It was built as a technical exercise with a Clojure (Pedestal) backend and a TypeScript/React frontend, then expanded with multi-counter management and shared usage across users.

## Frontend Preview
![Frontend screenshot](docs/frontend-screenshot.png)

## MVP (Original Challenge)
The test is to build a web app where:
- The backend is in Clojure using the Pedestal library.
- The application is a counter with two operations: increment and reset.
- Persistence can be:
  - Simple: in-memory state.
  - Complex: Datomic (local).
- The frontend is TypeScript/React, calls the backend API, shows the counter, and has buttons for the operations.

## What I Added (Differential)
- Counter management (create and delete counters).
- Multiple counters can exist simultaneously and be shared between users.
- Increment by more than 1 in a single operation.

## Tech Stack
- Backend: Clojure + Pedestal
- Database (optional): Datomic Local / Datomic in-memory
- Frontend: React + TypeScript
- Containerization: Docker / Docker Compose

## How to Run
### Backend (Clojure/Pedestal)
From `back-end`:

```sh
lein run
```

The API will be available at `http://localhost:3000`.

### Frontend (React/TypeScript)
From `front-end`:

```sh
npm install
npm run dev
```

The UI will be available at `http://localhost:5173`.

## Backend Routes
Document the API routes exposed by the Pedestal service here. Example structure:

- `GET /counters` - list available counters
- `POST /counters` - create a new counter
- `DELETE /counters/:id` - delete a counter
- `GET /counters/:id` - fetch a counter value
- `POST /counters/:id/increment` - increment by a value
- `POST /counters/:id/reset` - reset to zero
