
# FutureBlogs

FutureBlogs is a modern, full-stack blogging platform built with React, Express.js, PostgreSQL, and Supabase. It features a beautiful UI, robust authentication, and a seamless writing and reading experience.

---

## Table of Contents

- [Features](#features)
- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [Getting Started](#getting-started)
- [Scripts](#scripts)
- [API Overview](#api-overview)
- [Database Schema](#database-schema)
- [Contributing](#contributing)
- [License](#license)

---

## Features

- User registration and login (Supabase Auth)
- Create, edit, and delete blog posts
- Browse, search, and filter posts by category
- Like and share posts
- Responsive, modern UI with dark mode
- Type-safe backend and frontend with shared Zod schemas
- Serverless PostgreSQL (Neon) and Drizzle ORM
- Real-time updates with React Query

---

## Tech Stack

**Frontend:**
- React 18 + TypeScript
- Vite (build tool)
- Wouter (routing)
- Zustand (state management)
- TanStack React Query (data fetching/caching)
- Tailwind CSS (styling)
- Shadcn/ui & Radix UI (UI components)
- Lucide React (icons)

**Backend:**
- Node.js + Express.js
- Drizzle ORM (PostgreSQL)
- Supabase (auth & database)
- Zod (validation)
- dotenv (env management)

**Other:**
- ESBuild (server bundling)
- PostCSS, Tailwind plugins
- Neon (serverless PostgreSQL)

---

## Project Structure

```
FutureBlogs/
│
├── server/           # Express server, API routes, storage logic
│   ├── index.ts
│   ├── routes.ts
│   ├── storage.ts
│   └── dotenv-loader.ts
│
├── src/              # Frontend React app
│   ├── components/   # UI and feature components
│   ├── hooks/        # Custom React hooks
│   ├── lib/          # API, auth, utilities
│   ├── pages/        # Page components (home, dashboard, auth, etc.)
│   └── assets/       # Static assets
│
├── shared/           # Shared types and Zod schemas
│   └── schema.ts
│
├── migrations/       # Drizzle migration files
│
├── index.html        # App entry point
├── package.json      # Project metadata and scripts
├── tsconfig.json     # TypeScript config
├── vite.config.ts    # Vite config
├── drizzle.config.ts # Drizzle ORM config
└── README.md
```

---

## API Overview

- `GET /api/posts` — List all published posts
- `GET /api/posts/:id` — Get a single post by ID
- `GET /api/posts/my` — List posts by the authenticated user
- `POST /api/posts` — Create a new post (auth required)
- `PUT /api/posts/:id` — Update a post (auth required)
- `DELETE /api/posts/:id` — Delete a post (auth required)

Authentication is handled via Supabase Auth. Pass the user's token in the `Authorization` header.

---

## Database Schema

See `shared/schema.ts` for the full Drizzle ORM schema and Zod validation.

**Blog Posts Table:**
- `id` (UUID, PK)
- `userId` (UUID, FK)
- `author` (string)
- `title` (string)
- `content` (string)
- `excerpt` (string)
- `category` (string)
- `imageUrl` (string, optional)
- `published` (boolean)
- `createdAt` (timestamp)
- `updatedAt` (timestamp)

---

## License

MIT

---
