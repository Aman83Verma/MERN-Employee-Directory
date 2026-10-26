# MERN Stack Employee Directory

A full-stack **Employee Directory Application** developed using the MERN stack — MongoDB, Express.js, React.js, and Node.js.

This project was built as part of my fourth Express.js class to practice connecting a React frontend with an Express.js backend and a cloud-hosted MongoDB Atlas database.

The application allows users to add employee information through a form and view the list of employees in a structured table. It uses Tailwind CSS for styling, React Router for navigation, and Mongoose for database operations.

## ✨ Features

- **Create Employee:** Add employee details through an interactive form.
- **Employee Listing:** Retrieve and display all saved employees.
- **Employee Information:** Store name, email, job title, department, and role.
- **Profile Avatars:** Generate employee avatars based on their names using DiceBear.
- **Form Handling:** Manage form submissions using React Hook Form.
- **Page Navigation:** Navigate between the employee list and employee creation page using React Router.
- **REST API Integration:** Connect the frontend and backend using HTTP requests.
- **Cloud Database:** Store employee records in MongoDB Atlas.
- **Responsive UI:** Build a modern interface using Tailwind CSS.
- **Environment Configuration:** Manage the backend port, database URL, and frontend API URL through environment variables.

## 🛠️ Technology Stack

### Frontend

| Technology | Purpose |
|---|---|
| React.js | Build the user interface |
| JavaScript | Application logic |
| HTML5 | Structure the web pages |
| Tailwind CSS | Styling and responsive layouts |
| React Router DOM | Client-side navigation |
| React Hook Form | Handle employee form input |
| React Icons | Display navigation icons |
| Create React App | Frontend development and build tooling |

### Backend

| Technology | Purpose |
|---|---|
| Node.js | JavaScript runtime |
| Express.js | Backend server and REST API routing |
| Mongoose | MongoDB connectivity and data modeling |
| MongoDB Atlas | Cloud-hosted database |
| dotenv | Load environment variables |
| CORS | Allow cross-origin frontend requests |
| Nodemon | Automatically restart the server during development |

## 📁 Project Structure

```text
MERN-Employee-Directory/
├── backend/
│   ├── config/
│   │   └── database.js
│   ├── controller/
│   │   ├── createUser.js
│   │   └── getUsers.js
│   ├── models/
│   │   └── User.js
│   ├── routes/
│   │   └── user.js
│   ├── .env
│   ├── .gitignore
│   ├── index.js
│   ├── package.json
│   └── package-lock.json
│
├── frontend/
│   ├── public/
│   ├── src/
│   │   ├── components/
│   │   │   └── EmployeeForm.js
│   │   ├── pages/
│   │   │   ├── CreateEmployeePage.js
│   │   │   └── HomePage.js
│   │   ├── App.js
│   │   ├── index.css
│   │   └── index.js
│   ├── .env
│   ├── package.json
│   ├── package-lock.json
│   └── tailwind.config.js
│
├── .gitignore
└── README.md
```

**File descriptions:**

- `backend/index.js` — Initializes Express, configures middleware, mounts routes, connects to MongoDB, and starts the server.
- `backend/config/database.js` — Establishes the MongoDB connection using Mongoose.
- `backend/controller/createUser.js` — Validates the required employee fields and creates an employee record.
- `backend/controller/getUsers.js` — Retrieves employee records from MongoDB.
- `backend/models/User.js` — Defines the employee schema.
- `backend/routes/user.js` — Defines the employee creation and retrieval endpoints.
- `frontend/src/components/EmployeeForm.js` — Contains the employee creation form.
- `frontend/src/pages/CreateEmployeePage.js` — Displays the employee creation page.
- `frontend/src/pages/HomePage.js` — Fetches and displays the employee list.
- `frontend/src/App.js` — Configures the application's frontend routes.
- `frontend/src/index.js` — Renders the React application inside `BrowserRouter`.

*Note: The controller filenames in the structure above follow the imports shown in your code. Ensure that the actual filename and import path match exactly, including capitalization.*

## ⚙️ Prerequisites

Install the following before running the application:

- [Node.js](https://nodejs.org/)
- npm, included with Node.js
- A [MongoDB Atlas](https://www.mongodb.com/atlas) account
- Git
- A code editor such as Visual Studio Code

## 🚀 Getting Started

### 1. Clone the Repository

```bash
git clone <YOUR_GITHUB_REPOSITORY_URL>
cd MERN-Employee-Directory
```

Replace `<YOUR_GITHUB_REPOSITORY_URL>` with your actual GitHub repository URL.

### 2. Configure MongoDB Atlas

1. Create a MongoDB Atlas cluster.
2. Create a database user with appropriate permissions.
3. Configure Network Access to allow connections from your development environment.
4. Copy your MongoDB connection string.
5. Replace the placeholders with your actual database username, password, and database name.

Your connection string will follow this format:

```text
mongodb+srv://<username>:<password>@<cluster-url>/<database-name>?retryWrites=true&w=majority
```

Keep your database credentials private. If your password contains special characters, URL-encode them in the connection string.

### 3. Configure the Backend

Navigate to the backend directory:

```bash
cd backend
```

Install dependencies:

```bash
npm install
or
npm i
```

Create a `.env` file inside `backend/`:

```env
PORT=4000
DATABASE_URL=mongodb+srv://<username>:<password>@<cluster-url>/<database-name>?retryWrites=true&w=majority
```

Replace the connection string with your actual MongoDB Atlas URI.

**Important:** Your backend reads `process.env.DATABASE_URL`. The environment variable must use this exact name.

### 4. Start the Backend Server

If your backend `package.json` includes the corresponding scripts, run and also if you install nodemon package:

```bash
npm run dev
```

Alternatively:

```bash
npm start
```

Or start the application directly:

```bash
node index.js
```

The backend should run on port `4000` when using the configuration above.

**Backend URL:**

```text
http://localhost:4000
```

**API base URL:**

```text
http://localhost:4000/api/v1
```

You can test the root endpoint in your browser:

```text
http://localhost:4000/
```

### 5. Configure the Frontend

Open a new terminal and navigate to the frontend directory:

```bash
cd frontend
```

Install dependencies:

```bash
npm install
```

Create a `.env` file inside `frontend/`:

```env
REACT_APP_BASE_URL=http://localhost:4000/api/v1
```

This matches the environment variable used in `EmployeeForm.js` and `HomePage.js`.

**Important:** Because this project uses Create React App, frontend environment variables must begin with `REACT_APP_`. Restart the frontend development server whenever you change this file.

### 6. Start the Frontend

Run:

```bash
npm start
```

The React development server will normally open at:

```text
http://localhost:3000
```

Make sure both the backend and frontend are running.

## 🔗 API Endpoints

All employee API routes are mounted under `/api/v1`.

**Base URL:** `http://localhost:4000/api/v1`

| Method | Endpoint | Description |
|---|---|---|
| POST | `/createUser` | Creates a new employee |
| GET | `/getallUsers` | Retrieves all employees |

### 1. Create Employee

**Method:** `POST`

**Endpoint:**

```text
http://localhost:4000/api/v1/createUser
```

**Request headers:**

```text
Content-Type: application/json
```

**Request body:**

```json
{
  "name": "Aman Verma",
  "email": "aman@example.com",
  "title": "Software Engineer",
  "department": "Engineering",
  "role": "Web Developer"
}
```

The backend validates the required fields, generates a profile avatar based on the employee's name, and stores the employee record in MongoDB.

**Example response:**

```json
{
  "status": 201,
  "message": "User created successfully",
  "data": {
    "_id": "GENERATED_EMPLOYEE_ID",
    "name": "Aman Verma",
    "email": "aman@example.com",
    "title": "Software Engineer",
    "department": "Engineering",
    "role": "Web Developer",
    "image": "GENERATED_AVATAR_URL"
  }
}
```

The generated ID and avatar URL will differ for each employee.

If a required field is missing, the backend returns a `400 Bad Request` response.

### 2. Retrieve All Employees

**Method:** `GET`

**Endpoint:**

```text
http://localhost:4000/api/v1/getallUsers
```

This endpoint retrieves all employee records from MongoDB.

**Example response:**

```json
{
  "success": true,
  "data": [
    {
      "_id": "GENERATED_EMPLOYEE_ID",
      "name": "Aman Verma",
      "email": "aman@example.com",
      "title": "Software Engineer",
      "department": "Engineering",
      "role": "Web Developer",
      "image": "GENERATED_AVATAR_URL"
    }
  ]
}
```

The frontend uses the `data` array to render the employee list.

## 🗄️ Employee Data Model

The employee schema is defined in `backend/models/User.js`.

| Field | Data Type | Description |
|---|---|---|
| `_id` | ObjectId | Automatically generated unique identifier |
| `name` | String | Employee's full name; required |
| `email` | String | Employee email; required and unique |
| `title` | String | Employee job title; required |
| `department` | String | Employee department; required, maximum 20 characters |
| `role` | String | Employee role; required |
| `image` | String | Generated profile avatar URL; required |

The model uses Mongoose to define the schema and interact with MongoDB.

## 🔄 Application Workflow

1. The user opens the employee directory in the React application.
2. `HomePage.js` sends a GET request to retrieve employees.
3. Express receives the request and routes it to the `getUser` controller.
4. Mongoose retrieves employee records from MongoDB Atlas.
5. The backend returns employee data as JSON.
6. React renders the employee records in a table.
7. The user selects **Add Employee** to open the creation form.
8. The form collects the employee's name, email, title, department, and role.
9. React Hook Form handles form submission.
10. The frontend sends a POST request to the Express API.
11. The backend validates the required fields and saves the employee.
12. After submission, the frontend navigates back to the employee list.

## 🧪 Testing with Postman

You can test the backend independently of the frontend.

**Test employee creation:**

- Method: `POST`
- URL: `http://localhost:4000/api/v1/createUser`
- Body: raw JSON containing all required employee fields.

**Test employee retrieval:**

- Method: `GET`
- URL: `http://localhost:4000/api/v1/getallUsers`

Verify the returned JSON and confirm that created records appear in MongoDB Atlas.

## 🔐 Environment Variables and Git

Add the following entries to your root `.gitignore` and any relevant project-level `.gitignore` files:

```gitignore
node_modules/
.env
.env.*
!.env.example
build/
coverage/
.DS_Store
```

Create separate `.env.example` files containing placeholder values for the frontend and backend configuration. Never upload real database credentials to GitHub.

For example, the backend example can contain:

```env
PORT=4000
DATABASE_URL=your_mongodb_atlas_connection_string
```

The frontend example can contain:

```env
REACT_APP_BASE_URL=http://localhost:4000/api/v1
```

## 🔮 Future Improvements

- Add employee update functionality.
- Add employee deletion functionality.
- Add search and filtering by name, department, or role.
- Add pagination for larger employee lists.
- Improve frontend loading states and error messages.
- Add stronger email validation and duplicate-email handling.
- Add authentication and authorization.
- Add automated backend and frontend tests.
- Deploy the frontend and backend to cloud hosting platforms.

## 👨‍💻 Author

**Aman Verma**

Java Full Stack Developer | MERN Stack Developer

**Skills demonstrated:** React.js, Tailwind CSS, React Router, React Hook Form, Node.js, Express.js, MongoDB Atlas, Mongoose, REST APIs, and environment configuration.

This project represents my fourth Express.js class project, focusing on integrating a React frontend with an Express.js backend and a cloud-hosted MongoDB database.

---

⭐ If you find this project useful, feel free to explore the code and follow my full-stack development journey.
