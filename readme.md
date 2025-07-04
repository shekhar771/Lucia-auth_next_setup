

  **custom authentication** with Lucia Auth, offering:

- Secure sessions with sliding expiration
- GitHub/Google OAuth integration
- Middleware-protected routes



## 🚀 Quick Start

```bash
git clone https://github.com/shekhar771/Lucia-auth_next_setup
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

