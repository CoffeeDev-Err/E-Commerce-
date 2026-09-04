# Cellphone Shop E-Commerce Platform

A full-stack e-commerce application for selling new phones, pre-owned devices, and accessories. It combines a customer storefront with an administration area for products, orders, inventory, customers, and sales reports.

## Features

### Customer storefront

- Product search, filtering, sorting, and pagination
- New, second-hand, and accessory product categories
- Shopping cart and checkout workflow
- Pickup and delivery fulfillment options
- GCash, cash-on-delivery, and in-store payment options
- Customer registration, login, account, and order history

### Administration

- Sales dashboard and recent-order summaries
- Product and inventory management
- Order status and payment tracking
- Customer records
- Daily sales, best-seller, category, and payment reports
- Role-protected administrative routes

## Tech stack

- **Frontend:** React 19, Vite, React Router, Zustand, Axios
- **Backend:** Node.js, Express 5
- **Data:** Firebase Admin SDK and Cloud Firestore
- **Authentication:** JWT access tokens, rotating refresh sessions, bcrypt
- **Security:** Helmet, CORS, request validation, and rate limiting

## Project structure

```text
E-Commerce-/
├── frontend/    # Customer storefront and admin dashboard
└── backend/     # REST API, authentication, and Firestore access
```

## Local development

### 1. Clone the repository

```bash
git clone https://github.com/CoffeeDev-Err/E-Commerce-.git
cd E-Commerce-
```

### 2. Configure and start the backend

```bash
cd backend
npm install
```

Copy `.env.example` to `.env`, then configure the Firebase service-account fields and replace both JWT secrets. The main values are:

```env
FIREBASE_PROJECT_ID=your-project-id
FIREBASE_CLIENT_EMAIL=your-service-account-email
FIREBASE_PRIVATE_KEY="your-private-key"
JWT_SECRET=replace-with-a-long-random-secret
REFRESH_SECRET=replace-with-another-long-random-secret
FRONTEND_URL=http://localhost:5173
PORT=5000
```

Start the API:

```bash
npm run dev
```

To add the included sample catalog to Firestore:

```bash
node seed.js
```

### 3. Configure and start the frontend

From the repository root:

```bash
cd frontend
npm install
```

Create `frontend/.env`:

```env
VITE_API_URL=http://localhost:5000/api
```

Then start the development server:

```bash
npm run dev
```

The storefront is available at `http://localhost:5173` by default.

## Production build

```bash
cd frontend
npm run build
```

## Security

Never commit Firebase private keys, JWT secrets, or populated `.env` files. Use a dedicated service account with the minimum permissions required by the application.

