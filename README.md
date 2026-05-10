# 🛒 ShopAPI — E-Commerce REST API

> **Status: 🚧 In active development** — This README is updated as the project progresses.

A production-ready e-commerce backend built with **Node.js**, **TypeScript**, **Express.js**, and **MongoDB**. This project is part of my portfolio, designed to demonstrate real-world backend architecture and serve as a foundation for freelance e-commerce projects.

---

## 🧱 Tech Stack

| Layer | Technology | Purpose |
|---|---|---|
| Runtime | Node.js + TypeScript | Type-safe server-side logic |
| Framework | Express.js | REST API routing & middleware |
| Database | MongoDB + Mongoose | Product catalog, orders, users |
| Auth | Supabase | JWT authentication & role management |
| Media | Cloudinary | Product image upload & optimization |
| Validation | express-validator | Request validation & sanitization |

---

## 📁 Project Structure

```
src/
├── config/         # DB connections, Supabase, Cloudinary, env validation
├── types/          # Global TypeScript interfaces & type declarations
├── models/         # Mongoose schemas (User, Product, Order, Cart, Review)
├── routes/         # URL definitions — no business logic
├── controllers/    # Request/response handling — calls services
├── services/       # Business logic & DB queries — reusable across controllers
├── middleware/     # Auth, validation, error handling, rate limiting
├── validators/     # express-validator rule sets per resource
├── utils/          # asyncHandler, ApiResponse, ApiError, pagination helpers
└── scripts/        # DB seed scripts
```

---

## ✅ Planned Features

> Items will be checked off as they are completed.

### 🔐 Authentication & Users
- [ ] User registration & login via Supabase Auth
- [ ] JWT verification middleware
- [ ] Role-based access control (customer / admin)
- [ ] User profile management
- [ ] Address book (multiple shipping addresses)

### 🛍️ Products & Catalog
- [ ] Full CRUD for products (admin only)
- [ ] Product image upload & optimization via Cloudinary
- [ ] Category & subcategory management
- [ ] Product variants (size, color, etc.)
- [ ] Product search with filters (price range, category, rating)
- [ ] MongoDB text search + aggregation-based sorting

### 🛒 Cart & Orders
- [ ] Persistent cart (linked to user)
- [ ] Add, update, remove cart items
- [ ] Order placement from cart
- [ ] Order status workflow: `pending → confirmed → shipped → delivered`
- [ ] Order history per user
- [ ] Admin order management dashboard

### 💳 Payments
- [ ] Stripe integration (cards, international)
- [ ] Paystack integration (Africa-focused payments)
- [ ] Payment status webhooks
- [ ] Invoice generation on order confirmation

### ⭐ Reviews & Ratings
- [ ] Verified-purchase reviews
- [ ] Star rating with average aggregation
- [ ] Admin moderation (approve / reject)

### 🔧 Admin Panel Support
- [ ] Product & inventory management endpoints
- [ ] Sales analytics (MongoDB aggregation pipelines)
- [ ] User management (ban, role change)
- [ ] Dashboard summary stats (revenue, orders, top products)

### 🚀 Infrastructure & Quality
- [ ] Centralized error handling with custom `ApiError` class
- [ ] Consistent API response shape with generic `ApiResponse<T>`
- [ ] Request validation on all write endpoints
- [ ] Rate limiting on auth routes
- [ ] Environment variable validation on startup
- [ ] DB seed script with realistic sample data
- [ ] API documentation (Postman collection)

---

## 🗺️ API Overview (in progress)

```
POST   /api/v1/auth/register
POST   /api/v1/auth/login

GET    /api/v1/products
GET    /api/v1/products/:id
POST   /api/v1/products          (admin)
PATCH  /api/v1/products/:id      (admin)
DELETE /api/v1/products/:id      (admin)

GET    /api/v1/cart
POST   /api/v1/cart
PATCH  /api/v1/cart/:itemId
DELETE /api/v1/cart/:itemId

POST   /api/v1/orders
GET    /api/v1/orders/me
GET    /api/v1/orders/:id

POST   /api/v1/upload/image      (admin)
```

> Full Postman collection will be added once core endpoints are complete.

---

## 🏗️ Architecture Decisions

**Why MongoDB + Supabase together?**
MongoDB handles the product catalog and orders — data that is document-shaped with varying attributes and nested structures. Supabase handles authentication cleanly without building a custom auth system, and provides real-time capabilities for cart sync.

**Why the 3-layer pattern (routes → controllers → services)?**
Routes define URLs only. Controllers handle HTTP concerns (read req, send res). Services contain all business logic and DB queries, making them reusable and independently testable. This keeps every file focused on one job.

**Why Cloudinary?**
Product images need resizing, format conversion (WebP), and CDN delivery. Cloudinary handles all of this via URL-based transformations, removing the need for a separate image processing pipeline.

---

## 🚦 Getting Started

> Full setup instructions will be added as the project stabilises.

### Prerequisites
- Node.js v18+
- MongoDB Atlas account (or local MongoDB)
- Supabase project
- Cloudinary account



**[Nyah Sabastine]**
Full-stack developer specialising in React, Next.js, React Native, and Node.js.
Available for freelance projects.

- Portfolio: *coming soon*
- GitHub: [github.com/ngambasty-tech]
- Email: [ngamsebastien@gmail.com]

---





