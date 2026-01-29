Below is a **complete, production-style `README.md`** you can directly paste into your GitHub repository.
It is **practical, clean, and interview-ready**, matching your stack and real-world approach.

---

# 🚀 Next.js Firebase Auth + Edge Middleware App

A **modern full-stack authentication and user management system** built with **Next.js App Router**, **Firebase Authentication**, **Edge Middleware**, and **PostgreSQL (TypeORM)**.
This project demonstrates **real-world auth patterns**, **secure session handling**, and **high-performance route protection** using the **Edge Runtime**.

---

## ✨ Features

* 🔐 **Firebase Authentication** (Signup / Login / Logout)
* 🍪 **HttpOnly Cookie-based Sessions**
* ⚡ **Next.js Edge Middleware** (CDN-level auth protection)
* 🛡️ Protected routes (`/feed`)
* 🚫 Auth pages blocked for logged-in users
* 🧑‍💻 **PostgreSQL + TypeORM** user persistence
* 🔄 **React Query** for efficient data fetching
* 🌙 **Dark Mode Toggle**
* 🔍 **Search Bar (centered, responsive)**
* ➕ **Create Post Button**
* 🎨 Tailwind CSS + shadcn/ui
* 🧩 Clean, scalable architecture

---

## 🧠 Core Concept (High Level)

* **Firebase (Client)** handles user identity
* **Firebase Admin (Server)** verifies tokens
* **Backend** sets a secure HttpOnly cookie
* **Edge Middleware** reads cookies before page loads
* Unauthorized users are redirected instantly
* No client-side auth hacks or localStorage

---

## 🏗️ Tech Stack

### Frontend

* Next.js (App Router)
* React
* Tailwind CSS
* shadcn/ui
* React Query

### Backend

* Next.js API Routes
* Firebase Admin SDK
* Axios

### Database

* PostgreSQL
* TypeORM

### Security & Runtime

* Edge Middleware
* Edge Runtime (CDN)
* HttpOnly Cookies
* Firebase ID Tokens

---

## 📁 Project Structure

```txt
src/
├─ app/
│  ├─ auth/            # Login / Signup pages
│  ├─ feed/            # Protected feed page
│  ├─ api/             # Backend API routes
│  └─ middleware.ts    # Edge middleware
│
├─ components/         # UI components
├─ entities/           # TypeORM entities
├─ lib/                # Firebase, Axios, utils
├─ services/           # Auth & API services
└─ types/              # Shared DTOs
```

---

## 🔐 Authentication Flow

1. User logs in via **Firebase Auth (client)**
2. Firebase returns an **ID Token**
3. Token is sent to `/api/auth/login`
4. Backend verifies token using **Firebase Admin**
5. Backend sets **HttpOnly cookie**
6. Middleware checks cookie on every request
7. User can access `/feed`

---

## ⚡ Edge Middleware (Why It Matters)

* Runs **before page rendering**
* Executes at **CDN edge locations**
* No server or database hit
* Extremely fast redirects
* Perfect for auth & routing decisions

> ❌ Middleware does **NOT** handle database queries
> ✅ Only lightweight logic (cookies, headers, redirects)

---

## 🧪 How to Test Middleware

* Open `/feed` without login → redirected to `/auth/login`
* Login successfully → cookie is set
* Visit `/feed` → access granted
* Try `/auth/login` while logged in → redirected to `/feed`

---

## 🗄️ Database (TypeORM)

```ts
@Entity("users")
export class User {
  @PrimaryGeneratedColumn()
  id!: number;

  @Column({ unique: true })
  email!: string;

  @Column({ nullable: true })
  firstName?: string;

  @Column({ nullable: true })
  lastName?: string;

  @Column({ default: true })
  isActive!: boolean;

  @CreateDateColumn()
  createdAt!: Date;
}
```

---

## 🌙 UI Highlights

* Sticky Facebook-style Navbar
* Centered responsive search bar
* Dark mode toggle (Tailwind)
* User dropdown menu
* Clean & accessible UI components


## 📌 Why This Project Is Real-World Ready

* Uses **industry-standard auth flow**
* Secure against XSS (HttpOnly cookies)
* Works on refresh & hard reload
* Scales with CDN
* Clean separation of concerns
* Interview-ready architecture




## 👤 Author

**Ibrahim Amjad**
Web Developer – Next.js, Firebase, PostgreSQL

---

## 📄 License

MIT License
# Next-js-Social-App
# Next-js-Social-App
