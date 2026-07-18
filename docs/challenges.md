# Technical Challenges

## Multi-Tenancy

Challenge:

The backend was originally built around a single-store architecture.

Impact:

Store isolation was inconsistent across APIs.

Solution:

Introduced Store Context on the frontend while collaborating with backend engineers on a complete multi-store architecture.

---

## API Contracts

Challenge:

Backend APIs evolved frequently during development.

Solution:

Maintained flexible API integration layers and updated frontend contracts without affecting reusable UI components.

---

## Large Dashboard

Challenge:

The dashboard contains dozens of pages and reusable modules.

Solution:

Adopted a modular component architecture and shared design system.

---

## Reusable Components

Challenge:

Avoid duplicating UI logic.

Solution:

Created reusable components for tables, forms, dialogs, badges, uploaders, and pagination.

---

## Responsive Dashboard

Challenge:

Large enterprise dashboard across desktop, tablet, and mobile.

Solution:

Designed responsive layouts with adaptive navigation and optimized spacing.

---

## Performance

Challenge:

Prevent unnecessary re-renders.

Solution:

- Memoization
- Lazy Loading
- Dynamic Imports
- Query Caching

---

## Forms

Challenge:

Large complex forms.

Solution:

React Hook Form + Zod validation with reusable form components.

---

## API Errors

Challenge:

Provide consistent UX during failures.

Solution:

Unified loading, empty, success, and error states across all pages.