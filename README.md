# 🎉 Eventify Platform

![Eventify Platform Banner](https://via.placeholder.com/1200x400/111827/ffffff?text=Eventify+-+Full+Stack+Event+Ticketing+%26+Management)

> A production-ready, SaaS-style Event Ticketing & Management Platform built with modern web technologies.

## 🚀 Overview

Eventify is a complete platform that bridges the gap between event organizers and attendees. It features a modern, responsive UI and a robust, scalable backend. 

### Roles
1. **User (Attendee)**: Can browse events, search, filter, book tickets, and manage their dashboard and ticket history.
2. **Organizer**: Can create, update, and manage events, set capacities and ticket prices, view analytics, and validate QR tickets.

---

## 🛠️ Tech Stack

### Frontend
- **Framework**: [React 19](https://react.dev/) + [Vite](https://vitejs.dev/)
- **Language**: TypeScript
- **Styling**: [Tailwind CSS](https://tailwindcss.com/) + [shadcn/ui](https://ui.shadcn.com/)
- **Routing**: React Router DOM
- **State Management & Fetching**: TanStack Query & Axios
- **Forms & Validation**: React Hook Form + Zod
- **Animations & Charts**: Framer Motion & Recharts

### Backend
- **Runtime**: [Node.js](https://nodejs.org/) + [Express.js](https://expressjs.com/)
- **Language**: TypeScript
- **Database**: PostgreSQL (via [Prisma ORM](https://www.prisma.io/))
- **Authentication**: JWT (JSON Web Tokens) & bcrypt
- **Real-time & Queues**: Socket.IO, Redis, and BullMQ

---

## ✨ Features

- **Authentication**: Secure JWT-based auth with Role-Based Access Control (RBAC).
- **Event Discovery**: Search, filter by category/location, and sort upcoming events.
- **Booking Engine**: Robust booking system with real-time seat locking and overbooking prevention.
- **QR Code Ticketing**: Generates unique QR codes for tickets that organizers can scan for validation.
- **Dashboards**: Dedicated dashboards for users and organizers with analytics and history.
- **Real-Time Updates**: Live ticket availability and booking updates powered by Socket.IO.
- **Background Jobs**: Asynchronous event reminders and booking confirmations via BullMQ and Redis.

---

## 📁 Project Structure

The repository is structured as a monorepo containing both the frontend and backend applications:

```
Eventify-Platform/
├── backend/                  # Node.js + Express API
│   ├── prisma/               # Database schema & migrations
│   ├── src/
│   │   ├── config/           # Environment variables & constants
│   │   ├── controllers/      # Route handlers
│   │   ├── middleware/       # Custom Express middlewares (e.g., Auth)
│   │   ├── queues/           # BullMQ job processors
│   │   ├── routes/           # API route definitions
│   │   ├── services/         # Core business logic
│   │   ├── socket/           # Socket.IO event handlers
│   │   ├── utils/            # Helper functions (Hash, JWT)
│   │   └── index.ts          # Application entry point
│   └── package.json
│
├── frontend/                 # React + Vite application
│   ├── src/
│   │   ├── api/              # Axios instances and API services
│   │   ├── components/       # Reusable UI components (shadcn/ui)
│   │   ├── context/          # React Contexts (e.g., AuthContext)
│   │   ├── hooks/            # Custom React hooks
│   │   ├── layouts/          # Page layouts (Navbar, Footer, Sidebar)
│   │   ├── pages/            # Application routes/pages
│   │   └── main.tsx          # React application entry point
│   ├── tailwind.config.js
│   └── package.json
│
└── docker-compose.yml        # Local PostgreSQL & Redis environment
```

---

## 💻 Getting Started

### Prerequisites
- Node.js (v18 or higher)
- Docker & Docker Compose (for the local database and Redis)

### 1. Start the Database
Spin up the local PostgreSQL and Redis instances:
```bash
docker-compose up -d
```

### 2. Setup the Backend
Navigate to the backend directory, install dependencies, and run Prisma migrations:
```bash
cd backend
npm install
npx prisma generate
npx prisma db push
```

Start the backend development server:
```bash
npm run dev
```

### 3. Setup the Frontend
In a new terminal, navigate to the frontend directory:
```bash
cd frontend
npm install
npm run dev
```

Visit `http://localhost:5173` to view the application!

---

## 📜 License

This project is licensed under the MIT License.
