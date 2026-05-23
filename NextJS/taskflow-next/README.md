# TaskFlow - Next.js Implementation

A modern full-stack task and project management application built with **Next.js 16**, **Prisma ORM**, and **Tailwind CSS**. This implementation features server-side rendering, API routes, and a SQLite database for development.

## 🎯 Features

- ✅ Server-side rendering with Next.js App Router
- ✅ Full-stack TypeScript implementation
- ✅ Prisma ORM for type-safe database access
- ✅ Server actions for secure data mutations
- ✅ Session-based authentication with HTTP-only cookies
- ✅ SQLite database (development) / PostgreSQL (production)
- ✅ Tailwind CSS for responsive design
- ✅ API routes for RESTful endpoints
- ✅ Protected routes with middleware
- ✅ Dark mode support ready

## 🛠️ Tech Stack

| Category | Technology |
|----------|------------|
| Framework | Next.js 16.2 (with Turbopack) |
| Language | TypeScript 5 |
| Database | Prisma ORM |
| Database (Dev) | SQLite |
| Database (Prod) | PostgreSQL |
| Styling | Tailwind CSS 4 |
| CSS Compiler | PostCSS 8.5+ |
| Auth | HTTP-only Cookies + Server Actions |
| Package Manager | npm |

## 📥 Installation

### Prerequisites
- Node.js 22+ and npm 10+

### Setup

```bash
# Navigate to the Next.js app directory
cd NextJS/taskflow-next

# Install dependencies
npm install

# Generate Prisma Client
npx prisma generate

# Create and seed the database
npx prisma migrate dev --name init
```

## 🚀 Running the Application

### Development Mode

```bash
npm run dev
```
- Frontend: http://localhost:3000
- Turbopack hot reload enabled

### Production Mode

```bash
npm run build
npm run start
```

## 🔐 Authentication

### Login Credentials

| Email | Password |
|-------|----------|
| admin@taskflow.com | password123 |

**Features:**
- Secure HTTP-only session cookies
- Server action-based authentication
- Automatic session expiration
- Protected dashboard routes with middleware

## 🔗 API Endpoints

### Projects API

```bash
# Get all projects
GET /api/projects

# Get single project
GET /api/projects/:id

# Create project
POST /api/projects

# Update project
PUT /api/projects/:id

# Delete project
DELETE /api/projects/:id
```

## 🗄️ Database Management

### Development (SQLite)

```bash
# View data with Prisma Studio
npx prisma studio

# Reset database
npx prisma migrate reset
```

### Production (PostgreSQL)

Update \.env\:
```env
DATABASE_URL="postgresql://username:password@host:5432/taskflow"
```

## 📝 Available Scripts

```bash
npm run dev          # Start Next.js dev server (port 3000)
npm run build        # Build for production
npm run start        # Start production server
npm run lint         # Run ESLint
```

## 🚀 Deployment

### Deploy to Vercel

1. Push code to GitHub
2. Import project on Vercel
3. Set environment variables: \DATABASE_URL=...\
4. Deploy

### Docker

```dockerfile
FROM node:22-alpine
WORKDIR /app
COPY package*.json ./
RUN npm ci
COPY . .
RUN npm run build
EXPOSE 3000
CMD ["npm", "start"]
```

## 🐛 Troubleshooting

### Prisma Client not initialized
```bash
npx prisma generate
```

### Database connection errors
- Check \.env\ DATABASE_URL
- Ensure PostgreSQL is running (if using PostgreSQL)
- SQLite automatically creates \dev.db\ file

## 📚 Learning Resources

- [Next.js Documentation](https://nextjs.org/docs)
- [Prisma Documentation](https://www.prisma.io/docs)
- [Tailwind CSS](https://tailwindcss.com/docs)
- [TypeScript](https://www.typescriptlang.org/docs)

## 📄 License

MIT License

---

**Built with ❤️ using Next.js and Prisma**
