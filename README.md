# Sukoon – Mental Health Tracker

Sukoon is a **full-stack mental health tracking platform** built with **React.js**, **Node.js**, **Express.js**, and **MongoDB Atlas**.
It allows users to assess their mental well-being, read blogs, connect with professionals, and chat with a Gemini-powered assistant for support — all in one place.

---

## Features

* **Mental Health Assessments** – Take evidence-based assessments with AI-generated insights.
* **Chatbot Integration** – Gemini-powered chatbot for mental health guidance and check-ins.
* **Blogs & Articles** – Discover tips, coping strategies, and wellness guides.
* **Doctor Directory** – Connect with certified professionals.
* **User History** – View and track past assessments.
* **Authentication** – Secure registration & login using bcrypt.js and JWT.
* **Cloud-based Storage** – MongoDB Atlas for secure and scalable database management.

---

## Tech Stack

| Layer               | Technology                             |
| ------------------- | -------------------------------------- |
| **Frontend**        | React.js, Axios, React Router, CSS     |
| **Backend**         | Node.js, Express.js                    |
| **Database**        | MongoDB Atlas (Cloud)                  |
| **Auth & Security** | bcrypt.js, JSON Web Tokens (JWT), CORS |
| **AI Integration**  | Google Gemini API                      |
| **Hosting**         | Vercel (Frontend), Render (Backend)    |

---

##  Local Setup Instructions

### 1️ Clone the Repository

```bash
git clone https://github.com/<your-username>/Sukoon.git
cd Sukoon
```

---

### 2️ Install Dependencies

#### Backend:

```bash
cd server
npm install
```

#### Frontend:

```bash
cd ..
npm install
```

---

### 3️ Create a `.env` File inside `/server`

```
MONGO_URI=mongodb+srv://<username>:<encoded_password>@cluster0.mongodb.net/sukoonDB?retryWrites=true&w=majority
REACT_APP_API_KEY=<your-google-api-key>
```

 Replace `<encoded_password>` (for example `Nikhil%402025`) and `<your-google-api-key>` with your actual credentials.

`.env` is ignored via `.gitignore` — it should **not** be pushed to GitHub.

---

### 4️ Run Servers Locally

#### Backend:

```bash
cd server
node connection.js
```

#### Frontend:

```bash
npm start
```

Backend → [http://localhost:3001](http://localhost:3001)
Frontend → [http://localhost:3000](http://localhost:3000)

---

##  Deployment Guide

###  Backend (Render)

1. Push your code to GitHub.
2. Visit [https://render.com](https://render.com).
3. Click **New → Web Service → Build from GitHub**.
4. Fill in details:

   * **Name:** `sukoon-backend`
   * **Root Directory:** `server/`
   * **Build Command:** `npm install`
   * **Start Command:** `node connection.js`
5. Add environment variables under **Environment → Add Variable**:

   ```
   MONGO_URI=mongodb+srv://<username>:<encoded_password>@cluster0.mongodb.net/sukoonDB?retryWrites=true&w=majority
   REACT_APP_API_KEY=<your-google-api-key>
   ```
6. Deploy 
   Render will give you a live backend URL, e.g.:

   ```
   https://sukoon-backend.onrender.com
   ```

---

### Frontend (Vercel)

1. Go to [https://vercel.com](https://vercel.com).
2. Import your GitHub repository.
3. When asked:

   * **Framework Preset:** React
   * **Build Command:** `npm run build`
   * **Output Directory:** `build`
4. Add Environment Variables:

   ```
   REACT_APP_API_URL=https://sukoon-backend.onrender.com
   REACT_APP_API_KEY=<your-google-api-key>
   ```
5. Click **Deploy** 🚀
   After a few seconds, your site will be live at:

   ```
   https://sukoon-frontend.vercel.app
   ```

---

##  Folder Structure

```
Sukoon-master/
│
├── public/                   # React static assets
├── src/                      # React components and pages
│
├── server/
│   ├── connection.js         # MongoDB + Express configuration
│   ├── models/               # Mongoose schemas
│   ├── assessmentRouter.js   # Assessment routes
│   ├── .env                  # Environment variables (ignored)
│
├── package.json              # Frontend dependencies
└── README.md
```

---

##  Environment Variables Summary

| Variable            | Used In          | Description                            |
| ------------------- | ---------------- | -------------------------------------- |
| `MONGO_URI`         | Backend          | MongoDB Atlas connection string        |
| `REACT_APP_API_KEY` | Backend/Frontend | Google Gemini or other API integration |
| `REACT_APP_API_URL` | Frontend         | URL of deployed backend (Render)       |

---

## 🧪 API Endpoints

| Method | Endpoint       | Description           |
| ------ | -------------- | --------------------- |
| `POST` | `/register`    | Register a new user   |
| `POST` | `/login`       | Login existing user   |
| `GET`  | `/assessments` | Fetch all assessments |
| `POST` | `/assessments` | Submit new assessment |

---

## 🔐 Security

* Passwords hashed with **bcrypt.js**
* `.env` files excluded from Git tracking
* CORS enabled for cross-origin access
* JWT-based authentication for future expansion

---

