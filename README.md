# National Cyber Security Protection Portal (NCSPP)

A high-end, premium, and professional full-stack web application designed for a government cybersecurity organization. 

## Project Architecture
This is a Full-Stack MERN (MongoDB, Express, React, Node.js) application.
- **Frontend**: React (Vite), React Router v6, Axios, Vanilla CSS (Dark Cyber Theme)
- **Backend**: Node.js, Express, MongoDB, Mongoose, JWT, Multer
- **Database**: MongoDB (Local or Atlas)

---

## Directory Structure
```text
NCSPP/
├── backend/                  # Node.js + Express API
│   ├── config/               # Database connection
│   ├── controllers/          # API Route controllers (Auth, Posts, Reports)
│   ├── middleware/           # JWT verification, Multer upload config
│   ├── models/               # Mongoose schemas (User, Report, AwarenessPost)
│   ├── routes/               # Express routes
│   ├── uploads/              # Local evidence file storage bucket
│   ├── .env                  # Environment Variables
│   ├── package.json          # Backend dependencies
│   └── server.js             # Express entry point
├── frontend/                 # React frontend
│   ├── public/         
│   ├── src/
│   │   ├── components/       # Reusable components (Navbar, Footer)
│   │   ├── pages/            # Home, About, Contact, Report, Awareness, Admin
│   │   ├── App.jsx           # Routing configuration
│   │   ├── index.css         # Global variables and dynamic CSS design system
│   │   └── main.jsx          # React DOM render
│   ├── package.json          # Frontend dependencies
│   └── vite.config.js        # Vite build tool config
└── README.md                 # You are here
```

---

## Installation & Setup Instructions

### Prerequisites
Make sure you have **Node.js** and **npm** installed on your system.
You will also need a running instance of **MongoDB** (either installed locally or via a MongoDB Atlas URI string).

### 1. Backend Setup

1. Open a terminal and navigate to the backend folder:
   ```bash
   cd NCSPP/backend
   ```
2. Install dependencies:
   ```bash
   npm install
   ```
3. Create/Edit the `.env` file (already created for you) in the `backend` folder. By default it uses local MongoDB:
   ```text
   PORT=5000
   MONGO_URI=mongodb://127.0.0.1:27017/ncspp
   JWT_SECRET=supersecretgovkey123
   ```
   *(Change the MONGO_URI if using MongoDB Atlas).*
4. Start the backend server:
   ```bash
   npm run dev
   # OR
   npm start
   ```
   *The server will run on http://localhost:5000*

### 2. Frontend Setup

1. Open a **new** terminal window and navigate to the frontend folder:
   ```bash
   cd NCSPP/frontend
   ```
2. Install dependencies:
   ```bash
   npm install
   ```
3. Start the Vite React development server:
   ```bash
   npm run dev
   ```
   *The frontend will run on http://localhost:3000 (or the port Vite issues).*

---

## Using the System

### 1. Public Portal
Navigate to the frontend port in your browser. Citizens can view the Home, About, Awareness, and Contact pages.
To report a cyber crime, click **Report Threat**. They can fill the complex form, and attach a dummy evidence `.pdf` or `.png`.

### 2. Admin Initialization
Before you can login as an Admin, you need to seed the database with the first Admin account.
Open a tool like **Postman** or **cURL** and make a `POST` request:

```bash
curl -X POST http://localhost:5000/api/auth/register-initial
```

This will automatically create the master admin user:
- **Email**: `admin@gov.in`
- **Password**: `Admin@123`

*(Note: If the terminal returns `Admin already initialized`, you can skip this step).*

### 3. Admin Dashboard
Navigate to `http://localhost:3000/admin/login` in your browser.
Login with the credentials above. 
You will have access to the dashboard to:
1. View submitted Cyber Threat Reports, update their statuses, and view uploaded evidence.
2. Publish, manage, and delete new Cybersecurity Awareness posts which show to the public on the Awareness page.

---
**Developed by Antigravity AI.**
