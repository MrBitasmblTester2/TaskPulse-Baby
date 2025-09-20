# TaskPulse-Baby

Description
Create a web-based task management app where users can add, edit, and delete tasks. The app supports user authentication with JWT, categorizes tasks by project, and displays tasks with priority sorting. Front-end is handled by React and back-end by Node.js.

## Tech Stack
- React
- Node.js
- Express
- jsonwebtoken

## Requirements
- Authenticate users using JWT (Hint: Use jsonwebtoken in Express to sign and verify tokens)
- Implement CRUD for tasks (Hint: Use Express routers and in-memory store or database)
- Categorize tasks by project (Hint: Include projectId field in task object)
- Sort tasks by priority (Hint: Perform sorting in controller or in React before rendering)

## Installation
1. Clone the repository:
   bash
   git clone <repo-url>
   cd TaskPulse-Baby
   
2. Setup environment variables for the server (create a `.env` file in `/server`):
   bash
   JWT_SECRET=your_jwt_secret
   PORT=5000
   
3. Install server dependencies:
   bash
   cd server
   npm install
   
4. Install client dependencies:
   bash
   cd ../client
   npm install
   

## Usage
1. Start the backend server:
   bash
   cd server
   npm start
   
2. Start the frontend:
   bash
   cd client
   npm start
   
3. Open your browser and navigate to `http://localhost:3000` to access TaskPulse-Baby.

## Implementation Steps
1. Initialize the Node.js backend:
   - Run `npm init -y` in the `/server` directory.
   - Install Express and jsonwebtoken.
2. Configure the Express server:
   - Create `server.js` or `app.js`.
   - Set up middleware for JSON parsing and routing.
3. Implement JWT authentication:
   - Define routes for user registration and login.
   - Sign tokens with `jsonwebtoken` and protect task routes with middleware.
4. Create CRUD routes for tasks:
   - Define Express routers under `/api/tasks`.
   - Implement handlers for creating, reading, updating, and deleting tasks with `projectId` and `priority` fields.
5. Add project categorization:
   - Include a `projectId` attribute in the task model.
   - (Optional) Create a `/api/projects` router for managing projects.
6. Implement task sorting:
   - Sort tasks by `priority` in the controller or in React before rendering.
7. Initialize the React frontend:
   - Run `npx create-react-app client`.
   - Install Axios (or use Fetch) for API calls.
8. Build authentication in React:
   - Create login and registration components.
   - Store JWT in `localStorage` and attach it to Authorization headers.
9. Build task management components:
   - Create components for task listing, task form, and project filter.
   - Fetch tasks from the API, display them sorted by priority.
   - Implement inline editing and deletion of tasks.
10. Test end-to-end functionality:
   - Register a user, log in, create/read/update/delete tasks, and verify sorting and categorization.

## API Endpoints
### Auth
- POST /api/auth/register  – Register a new user.
- POST /api/auth/login     – Authenticate and receive a JWT.

### Tasks
- GET /api/tasks           – Get all tasks for the authenticated user.
- POST /api/tasks          – Create a new task.
- GET /api/tasks/:id       – Get a single task by ID.
- PUT /api/tasks/:id       – Update a task by ID.
- DELETE /api/tasks/:id    – Delete a task by ID.

### Projects (Optional)
- GET /api/projects        – List all projects.
- POST /api/projects       – Create a new project.