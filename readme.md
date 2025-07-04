Here's a polished, slightly condensed version of your README that maintains all key information while improving scannability:

---

# 🔐 Reddit Clone with Next.js & Lucia Auth

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](https://github.com/yourusername/your-repo/pulls)

A full-stack Reddit clone featuring **custom authentication** with Lucia Auth, offering:

- Secure sessions with sliding expiration
- GitHub/Google OAuth integration
- Middleware-protected routes
- Subreddits, posts, and voting system

![App Screenshot](/path-to-screenshot.png) *Replace with actual screenshot*

## 🚀 Quick Start

```bash
git clone https://github.com/yourusername/your-repo.git
cd your-repo
npm install
cp .env.example .env # Configure your variables
npx prisma migrate dev --name init
npm run dev
```

## ✨ Key Features

### 🔒 Authentication
- Credential login with Argon2 hashing
- OAuth via GitHub/Google
- Database-backed sessions
- Route protection middleware
- `useSession` React hook

### 📝 Community Features
- Create/manage subreddits
- Text/image/link posts
- Nested comments
- Voting system

## 🛠️ Tech Stack

| Category       | Technologies                  |
|----------------|-------------------------------|
| Framework      | Next.js 14 (App Router)       |
| Auth           | Lucia + Arctic (OAuth)        |
| Database       | PostgreSQL + Prisma          |
| Security       | Argon2, HttpOnly cookies     |
| Styling        | Tailwind CSS                 |

## 🔍 Why Lucia Auth?

Chose Lucia over NextAuth.js for:
- **Full control** over session lifecycle
- **Transparent security** implementation
- **Customizable** database schema
- **No black boxes** in auth flow

```typescript
// Example: Session validation
export async function validateSession(token: string) {
  const session = await prisma.session.findUnique({
    where: { sessionToken: token },
    include: { user: true } // Efficient data fetching
  });
  // ... expiry checks
}
```

## 📚 Documentation

- [Medium git Article](https://medium.com/@ashekhar.1239/mastering-authentication-in-next-js-my-hands-on-journey-with-lucia-auth-868ec8172437) - Deep dive into the auth system
- [Lucia Docs](https://lucia-auth.com/) - Authentication framework

