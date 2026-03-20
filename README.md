# 🎨 Nexus Frontend

A modern, responsive, and real-time chat application built with React, Tailwind CSS, and Socket.io. It connects seamlessly with the Nexus Backend to deliver instant messaging, authentication, and rich user interactions.

---

## 📌 Introduction

Nexus Frontend is the client-side application for the Nexus chat platform. It provides a smooth and interactive user experience with real-time messaging, authentication, media sharing, and user presence indicators.

---

## 📚 Table of Contents

* [Introduction](#-introduction)
* [Features](#-features)
* [Tech Stack](#-tech-stack)
* [Project Structure](#-project-structure)
* [Installation](#-installation)
* [Usage](#-usage)
* [Environment Variables](#-environment-variables)
* [API Integration](#-api-integration)
* [Socket Integration](#-socket-integration)
* [State Management](#-state-management)
* [Styling](#-styling)
* [Examples](#-examples)
* [Troubleshooting](#-troubleshooting)
* [Contributors](#-contributors)
* [License](#-license)

---

## ✨ Features

* 🔐 User authentication (Login/Register)
* ⚡ Real-time messaging with Socket.io
* 🟢 Online/Offline user presence
* 💬 Typing indicators
* 🔔 Notification sounds (toggleable)
* 🖼️ Image sharing support
* 📱 Fully responsive UI
* 🎯 Clean and modern design with DaisyUI
* 🧠 Global state management using Zustand

---

## 🛠 Tech Stack

### Frontend

* React (Vite)
* JavaScript (ES6+)

### Styling

* Tailwind CSS
* DaisyUI

### State Management

* Zustand

### Networking

* Axios / Fetch API

### Real-Time

* Socket.io Client

---

## 📁 Project Structure

```id="xq8p0h"
src/
├── components/
│   ├── Chat/
│   ├── Sidebar/
│   ├── Navbar/
│   └── UI/
│
├── pages/
│   ├── Home.jsx
│   ├── Login.jsx
│   └── Register.jsx
│
├── store/
│   └── useAuthStore.js
│
├── services/
│   ├── api.js
│   └── socket.js
│
├── hooks/
│   └── useSocket.js
│
├── utils/
│   └── helpers.js
│
├── App.jsx
└── main.jsx
```

---

## ⚙️ Installation

### Prerequisites

* Node.js (v18+ recommended)

### Steps

```bash id="7hrh8s"
git clone https://github.com/YOUR_USERNAME/Nexus-frontend.git
cd Nexus-frontend
npm install
```

---

## ▶️ Usage

### Development Mode

```bash id="8s7qch"
npm run dev
```

### Build for Production

```bash id="k6y1kz"
npm run build
```

---

## 🔧 Environment Variables

Create a `.env` file:

```env id="u1m0s9"
VITE_API_URL=http://localhost:3000/api
VITE_SOCKET_URL=http://localhost:3000
```

---

## 🔗 API Integration

The frontend communicates with the backend via REST APIs.

### Example:

```js id="n7ttol"
const res = await fetch(`${import.meta.env.VITE_API_URL}/auth/login`, {
  method: "POST",
  credentials: "include",
  headers: { "Content-Type": "application/json" },
  body: JSON.stringify({ email, password })
});
```

---

## 🔌 Socket Integration

Socket.io is used for real-time messaging.

### Example:

```js id="3l0k2z"
import { io } from "socket.io-client";

const socket = io(import.meta.env.VITE_SOCKET_URL);

socket.emit("send_message", messageData);

socket.on("receive_message", (data) => {
  console.log(data);
});
```

---

## 🧠 State Management

Zustand is used for managing global state such as:

* Auth user
* Conversations
* Messages
* Online users

---

## 🎨 Styling

* Tailwind CSS for utility-first styling
* DaisyUI for prebuilt UI components
* Fully responsive design for all devices

---

## 💡 Examples

### Login Flow

1. User submits login form
2. API request sent to backend
3. JWT stored (cookies/local storage)
4. Redirect to chat dashboard

---

## 🛠 Troubleshooting

### API not connecting

* Check `VITE_API_URL`
* Ensure backend is running

### Socket not working

* Verify `VITE_SOCKET_URL`
* Check CORS configuration

### Styling issues

* Ensure Tailwind is properly configured
* Restart dev server

---

## 👥 Contributors

* Lakshya Saxena

---

## 📄 License

This project is licensed under the MIT License.

---

## 🌐 Related

Backend Repository:
👉 https://github.com/LakshyaSaxena49/Nexus-backend
