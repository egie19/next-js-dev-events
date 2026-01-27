# 🚀 Next.js Advanced Integration Starter

A robust, type-safe web application architecture utilizing **Next.js 16**, **MongoDB**, and **PostHog** for data-driven decision making.

---

## 🛠 Tech Stack

| Tool           | Purpose                                      |
| :------------- | :------------------------------------------- |
| **Next.js**    | React Framework (App Router, Server Actions) |
| **TypeScript** | Static Typing & Developer Experience         |
| **MongoDB**    | NoSQL Database (via Mongoose)                |
| **Cloudinary** | Image Hosting & Optimization                 |
| **PostHog**    | Product Analytics & Event Tracking           |

---

## ✨ Features & Implementation

### 🗄️ Data Models & Connection

We use a **Singleton Pattern** for the MongoDB connection to prevent multiple active connections during hot reloads in development.

- **Mongoose Schemas:** Fully typed models to ensure data integrity between the application and MongoDB.
- **Connection Utility:** Centralized logic in `/lib/mongodb.ts`.

### ⚡ API Routes & Server Actions

This project utilizes a modern hybrid approach to data handling:

- **Server Actions:** Native Next.js functions for handling form submissions (e.g., creating bookings) without manual API boilerplate.
- **API Routes:** Dedicated `/api` endpoints for client-side fetching or third-party webhooks.

### 🖼️ Image Upload (Cloudinary)

Streamlined media management using the Cloudinary Upload API.

- Direct-to-cloud uploads to reduce server load.

### 🚀 Caching Strategy

- **Server-side Caching:** Leverages Next.js `cacheLife` cache and `revalidatePath` to ensure data freshness.

### 📈 PostHog: Booking Action & Tracking

Full-funnel analytics integration:

- **Event Tracking:** Captures specific user interactions, specifically the `Booking Action`.
- **Persistence:** Sessions are tracked across page reloads to understand user journeys.
- **Implementation:** Custom PostHog provider wrapping the root layout for global capture.

---

## 🚦 Getting Started

### 1. Environment Variables

Create a `.env.local` file and populate the following:

```env
# MongoDB
MONGODB_URI=your_mongodb_uri

# Cloudinary
CLOUDINARY_URL=your_cloudinary_url

# PostHog
NEXT_PUBLIC_POSTHOG_KEY=your_project_key
NEXT_PUBLIC_POSTHOG_HOST=[https://app.posthog.com](https://app.posthog.com)
```

# Install dependencies

```bash

npm install

npm run dev

```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

You can start editing the page by modifying `app/page.tsx`. The page auto-updates as you edit the file.
