<div align="center">

# 🤖 AMC Assistant

### Where curiosity meets intelligent conversation.

A full-stack AI chat application powered by Google Gemini, with secure authentication, persistent chat history, and a clean, modern UI.

[![React](https://img.shields.io/badge/React-18.2-61DAFB?logo=react&logoColor=white)](https://react.dev/)
[![Node.js](https://img.shields.io/badge/Node.js-Express_5-339933?logo=node.js&logoColor=white)](https://nodejs.org/)
[![MongoDB](https://img.shields.io/badge/MongoDB-Mongoose-47A248?logo=mongodb&logoColor=white)](https://www.mongodb.com/)
[![Gemini](https://img.shields.io/badge/Google-Gemini_2.5-4285F4?logo=google&logoColor=white)](https://ai.google.dev/)
[![Clerk](https://img.shields.io/badge/Auth-Clerk-6C47FF?logo=clerk&logoColor=white)](https://clerk.com/)
[![Vercel](https://img.shields.io/badge/Deployed_on-Vercel-000000?logo=vercel&logoColor=white)](https://vercel.com/)

[Live Demo](https://rag-coral-nine.vercel.app) · [Report Bug](../../issues) · [Request Feature](../../issues)

</div>

---

## 📖 Overview

**AMC Assistant** is an AI-powered chat application built with the MERN stack. Users sign in securely with Clerk, start new conversations, and get intelligent responses from Google's Gemini model — with every conversation saved to MongoDB so users can revisit past chats anytime.

## ✨ Features

- 💬 **AI-Powered Chat** — Real-time conversational responses using Google Gemini (`gemini-2.5-flash`)
- 🔐 **Secure Authentication** — Sign up / sign in flows handled by Clerk
- 🗂️ **Persistent Chat History** — Every conversation and message is stored in MongoDB, organized per user
- 📱 **Responsive Dashboard** — Sidebar chat list with quick access to previous conversations
- 🛡️ **Content Safety** — Configurable safety thresholds on AI responses (harassment/hate-speech filtering)
- 🌐 **CORS-Protected API** — Backend restricts access to whitelisted origins
- ⚡ **Fast & Modern Frontend** — Built with Vite for instant HMR and optimized builds

## 🏗️ Tech Stack

| Layer          | Technology                                      |
|----------------|--------------------------------------------------|
| Frontend       | React 18, Vite, React Router, TanStack Query     |
| Backend        | Node.js, Express 5                               |
| Database       | MongoDB with Mongoose                            |
| Authentication | Clerk                                            |
| AI Model       | Google Gemini (`@google/genai`)                  |
| Deployment     | Vercel (frontend), Node hosting (backend)        |

## 🗂️ Project Structure

```
AMC-Assistant/
├── Frontend/
│   ├── backclient/          # Express + MongoDB API server
│   │   ├── models/          # Mongoose schemas (chat, userchat)
│   │   └── index.js         # Server entry point & routes
│   └── client/               # React + Vite frontend
│       ├── src/
│       │   ├── components/  # ChatList, Newprompt, etc.
│       │   ├── layout/      # Root & Dashboard layouts
│       │   ├── routes/      # Home, Sign in/up, Dashboard, Chat pages
│       │   └── lib/         # API helper & Gemini client
│       └── vercel.json
└── README.md
```

## 🚀 Getting Started

### Prerequisites

- Node.js (v18+ recommended)
- A MongoDB database (local or [MongoDB Atlas](https://www.mongodb.com/atlas))
- A [Clerk](https://clerk.com/) account (for auth keys)
- A [Google Gemini API key](https://ai.google.dev/)

### 1. Clone the repository

```bash
git clone https://github.com/<your-username>/<your-repo>.git
cd <your-repo>/Frontend
```

### 2. Backend setup

```bash
cd backclient
npm install
```

Create a `.env` file in `backclient/`:

```env
MONGO=your_mongodb_connection_string
CLERK_PUBLISHABLE_KEY=your_clerk_publishable_key
CLERK_SECRET_KEY=your_clerk_secret_key
CLIENT_URL=http://localhost:5173
CLIENT_URL_2=https://your-deployed-frontend-url.com
PORT=5000
```

Run the server:

```bash
npm run dev     # development (nodemon)
npm start        # production
```

### 3. Frontend setup

```bash
cd ../client
npm install
```

Create a `.env` file in `client/`:

```env
VITE_CLERK_PUBLISHABLE_KEY=your_clerk_publishable_key
VITE_GEMINI_PUBLIC_KEY=your_gemini_api_key
VITE_API_URL=http://localhost:5000
```

Run the app:

```bash
npm run dev
```

The app will be available at `http://localhost:5173`.

## 🔌 API Reference

| Method | Endpoint             | Description                          | Auth Required |
|--------|-----------------------|---------------------------------------|:--------------:|
| GET    | `/api/health`          | Check server & DB status              | ❌              |
| POST   | `/api/chats`           | Create a new chat                     | ✅              |
| GET    | `/api/userchats`       | Get all chats for the logged-in user  | ✅              |
| GET    | `/api/chats/:id`       | Get a specific chat by ID             | ✅              |
| PUT    | `/api/chats/:id`       | Append a Q&A pair to an existing chat | ✅              |

## 📦 Deployment

- **Frontend** is configured for [Vercel](https://vercel.com/) (see `vercel.json` with SPA rewrites).
- **Backend** can be deployed on any Node-friendly host (Render, Railway, Vercel Functions, etc.) — just set the environment variables listed above.

Update `CLIENT_URL` / `CLIENT_URL_2` on the backend and `VITE_API_URL` on the frontend to match your deployed URLs.

## 🤝 Contributing

Contributions are welcome! Feel free to open an issue or submit a pull request.

1. Fork the project
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

Distributed under the MIT License. See `LICENSE` for more information.

## 👤 Author

Built with ❤️ by riyascodeX — feel free to connect!

</div>
