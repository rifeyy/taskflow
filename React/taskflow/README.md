# TaskFlow - React Implementation

A responsive task management application built with **React 19**, **Vite**, and **Redux Toolkit**. This is the single-page application (SPA) version of TaskFlow, featuring a JSON Server backend for mock API calls.

## 🎯 Features

- ✅ Project management (CRUD operations)
- ✅ Kanban-style task boards with columns (To Do, In Progress, Done)
- ✅ User authentication with Redux state management
- ✅ Multiple design system implementations (CSS Modules, Bootstrap, Material-UI)
- ✅ Real-time API communication with Axios
- ✅ Responsive and mobile-friendly design
- ✅ Protected routes and role-based access

## 🛠️ Tech Stack

| Category | Technology |
|----------|------------|
| Framework | React 19.2 |
| Build Tool | Vite 7.3 |
| State Management | Redux Toolkit 2.11 |
| Styling | Bootstrap 5.3, Material-UI 7.3, Emotion, CSS Modules |
| HTTP Client | Axios 1.13 |
| Routing | React Router v7 |
| Language | TypeScript 5.9 |
| Backend | JSON Server (mocked REST API) |
| Package Manager | npm |

## 📥 Installation

### Prerequisites
- Node.js 22+ and npm 10+

### Setup

```bash
# Navigate to the React app directory
cd React/taskflow

# Install all dependencies
npm install
```

## 🚀 Running the Application

### Development Mode

Open two terminal windows:

**Terminal 1: Start the development server**
```bash
npm run dev
```
- Frontend: http://localhost:5173
- Hot Module Replacement (HMR) enabled for instant updates

**Terminal 2: Start the JSON Server backend**
```bash
npm run json-server
```
- Backend API: http://localhost:4000
- Watches \src/db.json\ for changes
- Auto-refresh on data modifications

### Production Build

```bash
# Compile TypeScript and build with Vite
npm run build

# Preview production build locally
npm run preview
```

## 🔐 Authentication

### Login Credentials

| Email | Password | Role |
|-------|----------|------|
| admin@taskflow.com | admin123 | Admin |
| ali@taskflow.com | ali123 | User |
| sara@taskflow.com | sara123 | User |

**Features:**
- Session stored in localStorage
- JWT-like token generation (base64 encoded)
- Protected routes redirect unauthenticated users to login
- Automatic logout with session expiration

## 🔗 API Endpoints

JSON Server automatically generates RESTful endpoints:

```bash
# Users
GET    /users
GET    /users?email=admin@taskflow.com

# Projects
GET    /projects
POST   /projects
PUT    /projects/:id
DELETE /projects/:id

# Columns (Kanban)
GET    /columns
PUT    /columns/:id
```

## 📝 Available Scripts

```bash
npm run dev          # Start Vite dev server (port 5173)
npm run build        # Build for production
npm run lint         # Run ESLint checks
npm run preview      # Preview production build
npm run json-server  # Start mock backend API (port 4000)
```

## 🚀 Deployment

### Deploy to Vercel

1. Push code to GitHub
2. Connect repository to Vercel
3. Build command: \
pm run build\
4. Output directory: \dist\
5. Deploy

### Deploy to Netlify

1. Connect GitHub repository
2. Build command: \
pm run build\
3. Publish directory: \dist\

## 📄 License

MIT License

---

**Built with ❤️ using React and Vite**
