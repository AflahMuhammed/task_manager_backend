# Task Manager Backend

A full-stack task management application with a Node.js/Express backend and React frontend.

## Project Structure

```
.
├── backend/          # Node.js Express server
├── frontend/         # React application
├── package.json      # Backend dependencies
└── README.md        # This file
```

## Prerequisites

Before getting started, ensure you have the following installed:
- **Node.js** (v14 or higher)
- **npm** or **yarn** package manager
- **MongoDB** (local or MongoDB Atlas account)

## Backend Setup

### 1. Install Dependencies

Navigate to the backend directory and install dependencies:

```bash
npm install
```

### 2. Configure Environment Variables

Create a `.env` file in the root directory with the following configuration:

```env
# Database
MONGODB_URI=mongodb://localhost:27017/task_manager
# or for MongoDB Atlas:
# MONGODB_URI=mongodb+srv://username:password@cluster.mongodb.net/task_manager

# Server
PORT=5000

# JWT (Optional - if using authentication)
JWT_SECRET=your_jwt_secret_key_here
```

### 3. Database Connection

Ensure MongoDB is running:

```bash
# If using local MongoDB
mongod
```

For MongoDB Atlas, make sure your connection string is properly configured in the `.env` file.

## Running the Application

### Development Mode (with auto-reload)

```bash
npm run dev
```

The backend server will start on `http://localhost:5000` and automatically restart when you make changes.

### Production Mode

```bash
npm start
```

The server will start on `http://localhost:5000` (or the PORT specified in `.env`)

## API Endpoints

### Authentication Routes (`/api/auth`)
- `POST /api/auth/register` - Register a new user
- `POST /api/auth/login` - Login user

### Task Routes (`/api/tasks`)
- `GET /api/tasks` - Get all tasks
- `POST /api/tasks` - Create a new task
- `GET /api/tasks/:id` - Get task by ID
- `PUT /api/tasks/:id` - Update a task
- `DELETE /api/tasks/:id` - Delete a task

## Frontend Setup

### 1. Navigate to Frontend Directory

```bash
cd frontend
```

### 2. Install Dependencies

```bash
npm install
```

### 3. Development Mode

```bash
npm run dev
```

The frontend will be available at `http://localhost:5173` (Vite default port)

### 4. Build for Production

```bash
npm run build
```

### 5. Preview Production Build

```bash
npm run preview
```

## Technologies Used

### Backend
- **Express.js** - Web framework
- **Mongoose** - MongoDB ODM
- **bcryptjs** - Password hashing
- **jsonwebtoken** - JWT authentication
- **cors** - Cross-origin resource sharing
- **dotenv** - Environment configuration
- **nodemon** - Development auto-reload

### Frontend
- **React 19** - UI library
- **Vite** - Build tool and dev server
- **React DOM** - React rendering

## Troubleshooting

### Port Already in Use

If you get a "Port already in use" error:

```bash
# On Linux/macOS
lsof -i :5000
kill -9 <PID>

# On Windows
netstat -ano | findstr :5000
taskkill /PID <PID> /F
```

### MongoDB Connection Issues

- Verify MongoDB is running
- Check your connection string in `.env`
- For MongoDB Atlas, ensure your IP is whitelisted

### Dependencies Not Installing

```bash
# Clear npm cache
npm cache clean --force

# Remove node_modules and reinstall
rm -rf node_modules package-lock.json
npm install
```

## Additional Commands

### Linting (Frontend)

```bash
cd frontend
npm run lint
```

## License

ISC

## Support

For issues or questions, please create an issue in the repository.
