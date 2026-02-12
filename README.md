# SecOps Library

Complete full-stack bookstore project using:

- Backend: Node.js + Express + MongoDB
- Frontend: React + Tailwind CSS (Vite)
- Checkout: Razorpay test mode

## Project Structure

- `backend/` - REST API, authentication, cart, orders, admin endpoints
- `frontend/` - React client with public pages, dashboard, cart, and admin panel

## 1) Backend Setup

```bash
cd backend
cp .env.example .env
npm install
```

Update `.env` with your values:

- `MONGODB_URI`
- `JWT_ACCESS_SECRET`
- `JWT_REFRESH_SECRET`
- `CLIENT_URL`
- `SMTP_*` values for real email OTP delivery (or keep empty to use mock transport logs)
- `RAZORPAY_KEY_ID`
- `RAZORPAY_KEY_SECRET`
- `ADMIN_EMAIL`, `ADMIN_PASSWORD`, `ADMIN_NAME`

Run backend:

```bash
npm run dev
```

Optional seed commands:

```bash
npm run seed:admin
npm run seed:books
```

Backend runs on `http://localhost:5000`.

## 2) Frontend Setup

```bash
cd ../frontend
cp .env.example .env
npm install
```

Update `.env` values:

- `VITE_API_BASE_URL=http://localhost:5000/api`
- `VITE_RAZORPAY_KEY_ID=rzp_test_xxxxxxxxxx`

Run frontend:

```bash
npm run dev
```

Frontend runs on `http://localhost:5173`.

## Authentication Notes

- Signup requires valid email/password input validation
- OTP verification is required before login
- Passwords are encrypted with bcrypt
- Access token + refresh token flow is implemented

## API Modules

- `/api/auth`
- `/api/books`
- `/api/categories`
- `/api/users`
- `/api/cart`
- `/api/orders`
- `/api/admin`
