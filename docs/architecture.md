# Vorder Frontend Architecture

## Overview

Vorder is a multi-tenant SaaS e-commerce platform built with Next.js and React.

The frontend consists of three major applications:

1. Marketing Website
2. Merchant Dashboard
3. Storefront

Each application shares a common design system while serving different user roles.

---

# Architecture Goals

The frontend architecture was designed around the following principles:

- Scalability
- Maintainability
- Reusability
- Type Safety
- Feature Isolation
- Performance
- Accessibility
- Responsive Design

---

# High-Level Architecture

```
                 +-----------------------+
                 |   Marketing Website   |
                 +-----------------------+
                           |
                           |
                Authentication
                           |
                           v
                +----------------------+
                | Merchant Dashboard   |
                +----------------------+
                           |
                    REST APIs
                           |
                           v
                    Backend Services
                           |
                           |
                     PostgreSQL
                           |
                           |
                 +----------------------+
                 |    Storefront        |
                 +----------------------+
```

---

# Project Structure

```
src/
│
├── app/
├── components/
├── features/
├── layouts/
├── hooks/
├── services/
├── lib/
├── providers/
├── types/
├── utils/
├── styles/
└── assets/
```

---

# Design Principles

The application follows a feature-first architecture.

Each feature owns:

- UI
- API calls
- validation
- hooks
- types
- business logic

instead of mixing everything together.

---

# Routing

The application contains three routing areas:

Marketing

```
/
```

Dashboard

```
/dashboard/*
```

Storefront

```
/store/*
```

---

# State Management

The application uses:

- TanStack Query
- React Hooks
- Context API
- Local Component State

Server state and UI state are separated.

---

# API Layer

Every API is isolated inside the services layer.

Example:

```
services/

auth.api.ts

products.api.ts

orders.api.ts

customers.api.ts
```

No page performs fetch requests directly.

---

# Authentication

Authentication uses JWT.

The frontend stores the access token securely and protects dashboard routes.

Authentication flow:

Register

↓

Login

↓

Receive JWT

↓

Store Token

↓

Protected Dashboard

↓

API Requests

---

# Store Context

Every dashboard operation is executed within a Store Context.

Current implementation:

- URL Parameter
- Local Storage

Future implementation:

- Global Store Context Provider
- Backend Validation
- Ownership Middleware

---

# Forms

Forms use:

- React Hook Form
- Zod

Validation is shared between components.

---

# Styling

UI Stack

- Tailwind CSS
- shadcn/ui

Reusable design tokens:

- Colors
- Typography
- Spacing
- Radius
- Shadows

---

# Internationalization

Languages:

- English
- Arabic

Features:

- RTL Support
- Dynamic Locale
- next-intl

---

# Performance

Implemented:

- Code Splitting
- Lazy Loading
- Dynamic Imports
- Image Optimization
- Skeleton Loading
- Memoization
- Responsive Images

---

# Future Improvements

- Micro Frontends
- Feature Flags
- Storybook
- Unit Testing
- E2E Testing
- S3 Media Storage
- Better Store Context