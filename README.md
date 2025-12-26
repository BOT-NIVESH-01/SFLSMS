---

# 🎓 Smart Faculty Leave & Substitution Management System

![MERN](https://img.shields.io/badge/Stack-MERN-green)
![React](https://img.shields.io/badge/Frontend-React-blue)
![Node](https://img.shields.io/badge/Backend-Node.js-success)
![MongoDB](https://img.shields.io/badge/Database-MongoDB-brightgreen)
![JWT](https://img.shields.io/badge/Auth-JWT-orange)
![License](https://img.shields.io/badge/License-Open--Source-lightgrey)

A **MERN stack web application** that streamlines faculty leave management and automates substitute teacher allocation using an intelligent timetable analysis engine.

---

## 🚀 Features

### 🔄 Smart Substitution Engine

- Scans master timetable automatically
- Suggests available faculty per date & slot
- Prevents scheduling conflicts

### 👥 Role-Based Access

- **Faculty Dashboard**
- **HOD Dashboard**
- **Admin Dashboard**

### 📝 Leave Management

- Apply for **Casual**, **Medical**, or **Personal** leave
- **Medical Leave Rules**:

  - Minimum **10-day duration**
  - Can be submitted without substitutes
  - Admin can force-assign later

- **One Leave Per Day** validation

### ⚙️ Automated Workflow

1. Faculty applies for leave
2. System broadcasts substitution requests
3. First acceptance locks the slot
4. HOD/Admin approves after all slots are covered

### 🛠️ Admin Capabilities

- **Force Assign** faculty in emergencies
- Real-time faculty availability overview
- Leave approval & balance deduction

### 📅 Dynamic Timetable

- Visual class schedules
- Supports breaks and lunch periods

### 🔔 Notifications

- Real-time toast alerts for actions & errors

---

## 🛠️ Tech Stack

**Frontend**

- React.js
- Vite
- Axios
- Lucide React
- CSS3

**Backend**

- Node.js
- Express.js

**Database**

- MongoDB (Mongoose ODM)

**Authentication**

- JWT (JSON Web Tokens)

---

## 📂 Project Structure

```
smart-faculty-leave-system/
├── client/                 # React Frontend
│   ├── src/
│   │   ├── App.jsx
│   │   ├── App.css
│   │   └── ...
├── server/                 # Node/Express Backend
│   ├── config/             # Database config
│   ├── middleware/         # Auth middleware
│   ├── models/             # Mongoose schemas
│   ├── routes/             # API routes
│   └── server.js
└── README.md
```

---

## ⚙️ Installation & Setup

### 📌 Prerequisites

- Node.js **v14+**
- MongoDB (Local or Atlas)

---

### 1️⃣ Backend Setup

```bash
cd server
npm install
```

Create `.env` inside `server/`:

```env
MONGO_URI=mongodb://localhost:27017/faculty_leave_db
JWT_SECRET=your_super_secret_key_here
PORT=5000
```

Start backend server:

```bash
npm run dev
# or
node server.js
```

➡️ Backend runs at **[http://localhost:5000](http://localhost:5000)**

---

### 2️⃣ Frontend Setup

```bash
cd client
npm install
npm run dev
```

➡️ Frontend runs at **[http://localhost:5173](http://localhost:5173)**

---

### 🔁 Application Flow

#### 🧑‍🏫 Faculty – Request Leave

1. Login
2. Click **+ Apply Leave**
3. Select leave type, date & reason
4. View suggested substitutes
5. Submit request

#### 🔄 Faculty – Accept Substitution

1. Login
2. Open **Substitution Requests**
3. Click **Accept**
4. Slot is locked automatically

#### ✅ HOD/Admin – Approve Leave

1. Login as Admin
2. View **Pending Leave Approvals**
3. Review substitute status
4. Force assign if needed
5. Approve leave

---

## 📡 API Endpoints

### 🔐 Authentication

- `POST /api/auth/login` – Login & get token
- `GET /api/auth/me` – Get current user

### 📊 Data

- `GET /api/data/users` – All users
- `GET /api/data/timetable` – Master timetable (`?date=YYYY-MM-DD`)
- `GET /api/data/leaves` – Leave history
- `POST /api/data/leaves` – Apply leave
- `PATCH /api/data/leaves/:id/substitute` – Accept/Reject substitute
- `PATCH /api/data/leaves/:id/force-substitute` – Force assign (Admin)
- `PATCH /api/data/leaves/:id/status` – Final approval

## 🛡️ License

This project is **open-source** and intended for **educational use**.

---

### ⭐ If you like this project, give it a star!

---
