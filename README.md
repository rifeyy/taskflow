# TaskFlow

A modern task and project management application built with React and Next.js. TaskFlow helps teams organize, track, and manage projects with an intuitive interface and real-time collaboration features.

## 📋 Project Overview

TaskFlow is a full-stack application with two implementations:

- **React + Vite**: Single-page application (SPA) with Redux state management and JSON Server backend
- **Next.js**: Server-side rendered application with Prisma ORM and SQLite/PostgreSQL support

Both implementations provide the same core functionality for task management, project organization, and team collaboration.

## 🚀 Features

- **Project Management**: Create, read, update, and delete projects with custom colors
- **Task Organization**: Organize tasks into kanban-style columns (To Do, In Progress, Done)
- **User Authentication**: Secure login with session management
- **Responsive Design**: Works seamlessly on desktop and mobile devices
- **Real-time Updates**: Instant feedback on task and project changes
- **Team Collaboration**: Manage multiple projects and assign team members

## 🏗️ Project Structure

```
taskflow/
├── React/
│   ├── taskflow/              # Vite + React SPA
│   ├── tp1/ - tp5/            # Practice/tutorial directories
│   └── README.md
│
├── NextJS/
│   ├── taskflow-next/         # Next.js Full-stack application
│   ├── tp1/ - tp3/            # Practice/tutorial directories
│   └── README.md
│
└── README.md (this file)
```

## 🛠️ Tech Stack

### React Implementation
- **Frontend Framework**: React 19.2
- **Build Tool**: Vite 7.3
- **State Management**: Redux Toolkit 2.11
- **Styling**: Bootstrap 5.3, Material-UI 7.3, Emotion
- **HTTP Client**: Axios
- **Routing**: React Router v7
- **Language**: TypeScript 5.9
- **Backend**: JSON Server (mock REST API)

### Next.js Implementation
- **Framework**: Next.js 16.2 (with Turbopack)
- **Database**: Prisma ORM with SQLite (development)
- **Styling**: Tailwind CSS 4
- **Language**: TypeScript 5
- **Build Tool**: Turbopack

## 📥 Installation

### Prerequisites
- Node.js 22+ and npm 10+
- For Next.js with PostgreSQL: PostgreSQL 12+ (optional, uses SQLite by default)

### Clone & Setup

```bash
# Navigate to project directory
cd taskflow

# Install dependencies for React app
cd React/taskflow
npm install

# Install dependencies for Next.js app
cd ../../NextJS/taskflow-next
npm install
```

## 🚀 Running the Applications

### React Application (Vite)

```bash
cd React/taskflow

# Start the development server
npm run dev
# Opens at http://localhost:5173

# In a separate terminal, start the JSON Server backend
npm run json-server
# Runs at http://localhost:4000
```

**Login Credentials:**
- Email: `admin@taskflow.com`
- Password: `admin123`

Alternative accounts: `ali@taskflow.com` (ali123), `sara@taskflow.com` (sara123)

### Next.js Application

```bash
cd NextJS/taskflow-next

# Start the development server
npm run dev
# Opens at http://localhost:3000
```

**Login Credentials:**
- Email: `admin@taskflow.com`
- Password: `password123`

## 📝 Available Scripts

### React App

```bash
npm run dev        # Start Vite dev server
npm run build      # Build for production
npm run preview    # Preview production build
npm run lint       # Run ESLint
npm run json-server # Start mock backend API
```

### Next.js App

```bash
npm run dev        # Start Next.js dev server
npm run build      # Build for production
npm run start      # Start production server
npm run lint       # Run ESLint
```

## 🗄️ Database Setup (Next.js)

The Next.js app uses SQLite by default for easy local development.

```bash
cd NextJS/taskflow-next

# Create/migrate database
npx prisma migrate dev --name init

# View database
npx prisma studio
```

To switch to PostgreSQL, update `.env`:
```env
DATABASE_URL="postgresql://user:password@localhost:5432/taskflow"
```

Then update `prisma/schema.prisma`:
```prisma
datasource db {
  provider = "postgresql"
  url      = env("DATABASE_URL")
}
```

## 🔐 Authentication

Both applications implement secure session-based authentication:

- **React**: Context API + localStorage tokens
- **Next.js**: HTTP-only cookies + server actions

Passwords are stored as plain text in development (for demo purposes). In production, use bcrypt or similar for password hashing.

## 📚 API Endpoints (React + JSON Server)

```
GET    /users              # List all users
GET    /users?email=...    # Find user by email
GET    /projects           # List all projects
POST   /projects           # Create project
PUT    /projects/:id       # Update project
DELETE /projects/:id       # Delete project
GET    /columns            # List kanban columns
```

## 🎨 Styling

The React app includes three design system implementations:
- **CSS Modules**: Custom styling with React Login
- **Bootstrap**: React Bootstrap components
- **Material-UI**: MUI components with custom theme

The Next.js app uses **Tailwind CSS** for utility-first styling.

## 🧪 Development

### Code Quality
- **Linting**: ESLint with TypeScript support
- **Type Checking**: TypeScript strict mode
- **Formatting**: Consistent code style across both apps

### Testing
Current setup includes TypeScript compilation tests. For unit/integration tests, consider adding:
- Jest (React)
- Vitest (Next.js)

## 📦 Dependencies Audit

Both applications have been audited for vulnerabilities:
```bash
npm audit
```

All critical vulnerabilities have been patched. Minor Node engine warnings may appear due to transitive dependencies requiring Node 22.13+.

## 🚀 Deployment

### React App
1. Build: `npm run build`
2. Deploy `dist/` folder to Vercel, Netlify, or static hosting
3. Update API endpoint from `localhost:4000` to production backend

### Next.js App
1. Build: `npm run build`
2. Deploy to Vercel (native support) or self-hosted Node environment
3. Set `DATABASE_URL` environment variable in production
4. Run migrations: `npx prisma migrate deploy`

## 🤝 Contributing

1. Create a feature branch: `git checkout -b feature/your-feature`
2. Commit changes: `git commit -m 'Add feature'`
3. Push to branch: `git push origin feature/your-feature`
4. Open a Pull Request

## 📄 License

This project is open source and available under the MIT License.

## 📞 Support

For issues, questions, or suggestions:
1. Check existing issues on GitHub
2. Create a new issue with clear description and steps to reproduce
3. Include your environment details (Node version, OS, browser)

## 🎯 Roadmap

- [ ] Real-time collaboration with WebSockets
- [ ] Dark mode support
- [ ] Advanced filtering and search
- [ ] Export to PDF/Excel
- [ ] Mobile native apps (React Native)
- [ ] Team/organization management
- [ ] Notification system

---

**Happy tasking! 🎯**
