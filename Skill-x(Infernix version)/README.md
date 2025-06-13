# 📚 Skill-X

A full-stack MERN (MongoDB, Express, React, Node.js) based E-learning platform with user authentication, email OTP verification, course subscription, and progress tracking.

---

## 🔧 Features

- ✅ User Registration with OTP Verification via Email  
- ✅ JWT-based Authentication & Authorization  
- ✅ Password Reset with Expiry Link  
- ✅ Course Subscription Tracking  
- ✅ Admin Dashboard (Expandable)  
- ✅ Progress Tracking for Enrolled Courses  
- ✅ RESTful API Design  
- ✅ Secure Password Hashing using bcrypt  
- ✅ Real-time Feedback with Loading UI

---

## 🛠 Tech Stack

### ⚙️ Backend
- Node.js
- Express
- MongoDB + Mongoose
- JWT (Authentication)
- bcrypt (Password Hashing)
- nodemailer (Email)
- dotenv (Environment Configs)

### 🎨 Frontend
- React
- React Router
- Context API
- CSS Modules / Custom Styling

---

## 🗂 Project Structure

```
📁 backend/
├── controllers/
├── routes/
├── models/
├── middlewares/
├── database/
├── .env
├── index.js
```

```
📁 frontend/
├── src/
│   ├── pages/
│   ├── context/
│   ├── components/
│   ├── App.js
│   ├── index.js
```

---

## 🚀 Getting Started

### 🧪 Prerequisites
- Node.js & npm
- MongoDB (local or Atlas)
- Gmail account (for nodemailer setup)

---

### 📦 Backend Setup

```bash
cd backend
npm install
```

#### 🌐 Configure `.env`:

```env
PORT=5000
MONGO_URI=your_mongodb_connection_string
Jwt_Sec=your_jwt_secret
Activation_Secret=your_otp_jwt_secret
Forgot_Secret=your_reset_jwt_secret
SMTP_HOST=smtp.gmail.com
SMTP_PORT=587
SMTP_USER=your_email@gmail.com
SMTP_PASS=your_email_app_password
```

#### ▶️ Start Backend:

```bash
npm start
```

---

### 💻 Frontend Setup

```bash
cd frontend
npm install
npm start
```

Update API URLs in your context or services if needed:

```js
const BASE_URL = "http://localhost:5000/api";
```

---

## 📫 API Endpoints Overview

### 👤 User Routes (`/api/user`)
- `POST /register` — Register user and send OTP
- `POST /verify` — Verify OTP and create user
- `POST /login` — Login and get JWT
- `GET /me` — Get profile (auth required)
- `POST /forgot` — Send reset email
- `POST /reset` — Reset password via token
- `POST /progress` — Update progress
- `GET /progress` — Get course progress

---

## 🔐 Authentication Flow

1. User registers with name/email/password
2. Backend generates OTP + activation token
3. Email is sent via nodemailer
4. User enters OTP → verified → stored in DB
5. Login → JWT returned → stored in localStorage/context

---

## 🐞 Troubleshooting

- **Duplicate email error**: Ensure email field is unique and not `null`.
- **OTP expired**: Check `.env` `Activation_Secret` and expiry time.
- **Email not sending?**
  - Check `SMTP_USER`, `SMTP_PASS`
  - Use an [App Password](https://myaccount.google.com/apppasswords)

---

## 📌 Notes

- For production, always:
  - Use HTTPS
  - Set proper CORS rules
  - Rate limit auth routes
  - Sanitize input
  - Encrypt secrets

---

## 🧑‍💻 Author

Made with ❤️ by [Infernix](https://github.com/The-Infernix)