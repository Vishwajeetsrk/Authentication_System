# Assignment Intern PrimeTrade – Secure MERN Stack Authentication System

PrimeTrade is a full-stack authentication system built with the **MERN stack** (MongoDB Atlas, Express.js, React + Vite, Node.js). It implements secure user registration, login, JWT-based authentication, protected routes, and a clean dashboard interface.

The project serves as a solid foundation for any MERN application requiring user authentication. It includes basic task management on the protected dashboard to demonstrate real-world usage of protected routes.


---

### 📸 Screenshots 
<img src="videotest.gif" alt="Alt text" width=""/>

- Login Page
- Registration Page
- Protected Dashboard with Tasks


---
## 🚀 Features

- **User Registration & Login** with form validation
- **Secure Password Hashing** using bcrypt
- **JWT Authentication** (access token stored in localStorage)
- **Protected Routes** (middleware + frontend wrapper)
- **Simple Task Management** on protected dashboard (CRUD demo)
- **Responsive UI** with Bootstrap
- **RESTful API** design
- **Environment-based configuration**

---

## 🛠 Tech Stack

### Frontend
- React 18 + Vite
- React Router DOM v6
- Axios for API calls
- Bootstrap 5
- localStorage for token persistence

### Backend
- Node.js + Express.js
- MongoDB Atlas + Mongoose ODM
- JSON Web Tokens (jwt)
- bcryptjs for password hashing
- dotenv for environment variables
- CORS configured

---

## 📁 Project Structure
```bash
Primetrade-Intern-Task
├── backend
│   ├── config
│   │   └── db.js              # MongoDB connection
│   ├── controllers
│   │   ├── authController.js  # Login/Register logic
│   │   └── taskController.js  # Task CRUD logic
│   ├── middleware
│   │   └── authMiddleware.js  # JWT verification
│   ├── models
│   │   ├── User.js
│   │   └── Task.js
│   ├── routes
│   │   ├── auth.js
│   │   └── tasks.js
│   ├── .env                   # (gitignored)
│   ├── package.json
│   └── server.js
│
├── frontend
│   ├── public
│   │   └── vite.svg
│   ├── src
│   │   ├── assets                 # Images/icons
│   │   ├── components
│   │   │   ├── Navbar.jsx
│   │   │   └── ProtectedRoute.jsx
│   │   ├── pages
│   │   │   ├── Login.jsx
│   │   │   ├── Register.jsx
│   │   │   ├── Dashboard.jsx
│   │   │   └── Tasks.jsx          # (if separate page)
│   │   ├── context                # Optional AuthContext
│   │   ├── services
│   │   │   └── api.js             # Axios instance
│   │   ├── App.jsx
│   │   ├── main.jsx
│   │   └── index.css
│   ├── index.html
│   ├── package.json
│   └── vite.config.js
│
├── README.md
└── .gitignore
```

---

## 🔐 Authentication Flow

1. User registers → password hashed with bcrypt → user saved in MongoDB
2. User logs in → credentials verified → JWT signed and returned
3. Token stored in `localStorage`
4. Every protected request includes token in Authorization header
5. Backend middleware verifies JWT → grants/denies access
6. Frontend `ProtectedRoute` component checks token presence

---

## ⚙️ Prerequisites

- Node.js v18 or higher
- MongoDB Atlas account (or local MongoDB)
- npm or yarn

---

## ▶️ Setup & Running Locally

### 1. Clone the Repository
bash
```
git clone https://github.com/yourusername/PrimeTrade.git
cd PrimeTrade
```
### 2. Backend Setup
bash
```
cd backend
node server.js
npm install
```
**Create .env file in /backend:**
env
```
PORT=5000
MONGO_URI=mongodb+srv://<username>:<password>@cluster0.mongodb.net/primetrade?retryWrites=true&w=majority
JWT_SECRET=your_strong_secret_here
JWT_EXPIRE=7d
```
**Start the server**:
# Development (with nodemon)
```
npm run dev
```
# Production
```
npm start
```
### 3. Frontend Setup
```
cd ../frontend
npm install
```
**Create proxy in vite.config.js (to avoid CORS issues):**
JavaScript
```
server: {
  proxy: {
    '/api': 'http://localhost:5000'
  }
}
```
**Start the frontend:**
App runs at 
```
http://localhost:5173
```
---
### 🧪 Sample Test Credentials
Email: test@prime.com
Password: 123456

### MangoDB (optional)
 clusters0--> Data Explorer --> primetrade -->user

/** 
* Paste one or more documents here
*/
{
  "email": "test@prime.com",
  "password": "$2a$10$ZxhkSdj7FN6CPk08Uwfmau9IJuc.Mj6GGMic2txg2V9YOWHzjYH/2",
  "__v": 0
}

---
### 🔒 Security Considerations

- Passwords hashed with bcrypt (salt rounds = 12 recommended)
- JWT signed with strong secret and expiration
- HTTP-only cookies can be added for enhanced security (future improvement)
- Input validation on both frontend and backend
- Environment variables never committed

---
### 🤝 Contributing
Contributions are welcome! Feel free to open issues or submit pull requests.

- Fork the repo
- Create your feature branch (git checkout -b feature/AmazingFeature)
- Commit your changes (git commit -m 'Add AmazingFeature')
- Push to the branch (git push origin feature/AmazingFeature)
- Open a Pull Request

---
### 📄 License
Distributed under the MIT License. See LICENSE for more information.

---

👤 Author
Vishwajeet
GitHub: [@vishwajeetsrk](https://github.com/Vishwajeetsrk)

