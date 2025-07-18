# Developer Task Manager

A full-stack MERN application for managing tasks with role-based access control.

---

## Live Demo

- **Frontend:** [frontend](https://devtaskmanager.vercel.app/)
- **Backend API:** [backend](https://dev-task-manager-1rs9.onrender.com) 

---

## Features

- **User Authentication** - JWT-based signup/login
- **Role-Based Dashboards** - Separate admin and developer views
- **Task Management** - Create, read, update, delete tasks
- **Admin Controls** - Admins can manage all users' tasks
- **Developer Access** - Developers can only manage their own tasks
- **Responsive UI** - Built with React and Tailwind CSS
- **Dark Mode** - Theme toggle support

---

## Tech Stack

- **Frontend:** React, Vite, Tailwind CSS, Radix UI
- **Backend:** Node.js, Express.js, MongoDB, Mongoose
- **Authentication:** JWT tokens with bcrypt
- **UI Components:** Shadcn/ui components

---

## Installation

### Prerequisites

- Node.js (v14+)
- MongoDB
- pnpm (recommended) or npm

### Setup

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd developer-task-manager
   ```

2. **Install dependencies**
   ```bash
   # Install server dependencies
   cd server
   pnpm install

   # Install client dependencies
   cd ../client
   pnpm install
   ```

3. **Environment Setup**
   Create a `.env` file in the server directory:
   ```
   PORT=5000
   MONGO_URI=mongodb://localhost:27017/devtaskdb
   JWT_SECRET=supersecretkey123
   ```

4. **Start MongoDB**
   ```bash
   sudo systemctl start mongod
   ```

5. **Start the application**
   ```bash
   # Start server (from server directory)
   pnpm dev
   # or
   pnpm start

   # Start client (from client directory, in a new terminal)
   pnpm dev
   ```

---

## Deployment Instructions

### Frontend (Vercel)

1. Push your code to GitHub.
2. Go to [Vercel](https://vercel.com/) and import your frontend repository.
3. Set the build command to `pnpm build` and output directory to `dist`.
4. Set environment variables if needed.
5. Deploy and note the provided URL.

### Backend (Vercel/Render/Other)

1. Push your backend code to GitHub.
2. Deploy to your chosen platform (e.g., [Render](https://render.com/), [Vercel](https://vercel.com/), [Heroku](https://heroku.com/)).
3. Set environment variables (`MONGO_URI`, `JWT_SECRET`, etc.).
4. Deploy and note the API URL.

---

## Usage

- **Client:** [https://devtaskmanager.vercel.app](https://devtaskmanager.vercel.app)
- **Server API:** [https://devtaskmanager-api.vercel.app](https://devtaskmanager-api.vercel.app)

### Default Admin Account

- **Username:** admin
- **Email:** admin@example.com
- **Password:** admin123

---

## Project Structure

```
├── client/          # React frontend
│   ├── src/
│   │   ├── components/  # Reusable UI components
│   │   ├── pages/       # Page components
│   │   ├── services/    # API services
│   │   └── utils/       # Utility functions
│   └── package.json
├── server/          # Express backend
│   ├── controllers/ # Route handlers
│   ├── middleware/  # Authentication middleware
│   ├── models/      # MongoDB models
│   ├── routes/      # API routes
│   └── package.json
└── README.md
```

---

## API Endpoints

### Authentication
- `POST /api/auth/signup` - User registration
- `POST /api/auth/login` - User login

### Tasks
- `GET /api/tasks/me` - Get user's tasks
- `GET /api/tasks/all` - Get all tasks (admin only)
- `POST /api/tasks` - Create task
- `PUT /api/tasks/:id` - Update task
- `DELETE /api/tasks/:id` - Delete task

---

## CI/CD Pipeline

The project uses GitHub Actions for continuous integration and deployment.

### Example Workflow

- On every push to `main`, the workflow:
  - Installs dependencies
  - Runs tests and linting
  - Builds the project
  - Deploys to Vercel/Render

### Screenshots

![CI/CD Build Passing](./docs/cicd-build.png)
![CI/CD Deploy Step](./docs/cicd-deploy.png)

---

## Monitoring Setup

- **Uptime Monitoring:** [UptimeRobot](https://uptimerobot.com/) monitors the backend API and frontend URLs.
- **Error Tracking:** [Sentry](https://sentry.io/) is integrated for frontend error monitoring.
- **Logging:** Backend logs are available via the deployment platform dashboard (e.g., Vercel/Render logs).

### Example Monitoring Dashboard

![UptimeRobot Dashboard](./docs/uptimerobot-dashboard.png)
![Sentry Issues](./docs/sentry-issues.png)

---

## License

MIT

---

> _Replace all placeholder URLs and image paths with your actual deployment and documentation links._