# 🚌 Bus Booking System

A full-stack Bus Booking System built with **React + TypeScript** (frontend) and **Node.js + Express + MongoDB** (backend).

---

## Project Structure

```
bus-booking-system/
├── frontend/   # React + Vite + TypeScript
└── backend/    # Node.js + Express + MongoDB + TypeScript
```

---

## Quick Start

### Prerequisites
- Node.js >= 18
- MongoDB (local or Atlas)

### 1. Backend Setup

```bash
cd backend
cp .env.example .env          # Edit MONGODB_URI if needed
npm install
npm run dev                   # Starts on http://localhost:5000
```

The server will **auto-seed** 6 demo buses on first run.

### 2. Frontend Setup

```bash
cd frontend
cp .env.example .env          # Edit VITE_API_BASE_URL if needed
npm install
npm run dev                   # Starts on http://localhost:5173
```

---

## API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/buses` | Search buses with filters & pagination |
| GET | `/api/buses/:busId` | Get bus details + seat layout |
| POST | `/api/bookings` | Confirm a booking |
| POST | `/api/seats/lock` | Lock seats for 2 minutes (timer) |
| GET | `/health` | Health check |

### GET /api/buses — Query Parameters

| Param | Required | Description |
|-------|----------|-------------|
| `departureCity` | ✅ | e.g. `Bangalore` |
| `arrivalCity` | ✅ | e.g. `Chennai` |
| `date` | ✅ | `YYYY-MM-DD` |
| `seatType` | ❌ | `normal` / `semi-sleeper` / `sleeper` |
| `isAC` | ❌ | `true` / `false` |
| `departureSlot` | ❌ | `morning` / `afternoon` / `evening` / `night` |
| `page` | ❌ | default `1` |
| `pageSize` | ❌ | default `10` |

---

## Features

- 🔍 Search buses by city and date
- 🎛 Filter by seat type, AC/NON-AC, departure time slot
- 💺 Interactive seat selection grid
- ⏱ 2-minute seat reservation timer (bonus)
- 📋 Passenger details form
- ✅ Booking confirmation & success page
- 📱 Responsive design (mobile & desktop)
- ⚠️ Full error handling (invalid inputs, full buses, seat conflicts)
- 📄 Pagination

---

## Deployment

- **Frontend**: Deploy `/frontend` to [Vercel](https://vercel.com) or [Netlify](https://netlify.com). Set `VITE_API_BASE_URL` env var.
- **Backend**: Deploy `/backend` to [Render](https://render.com) or [Koyeb](https://koyeb.com). Set `MONGODB_URI`, `PORT`, `FRONTEND_URL` env vars.
- **Database**: Use [MongoDB Atlas](https://www.mongodb.com/cloud/atlas) free tier.

---

## Tech Stack

| Layer | Technology |
|-------|-----------|
| Frontend | React 18, TypeScript, React Router v6, Vite, Axios |
| Backend | Node.js, Express, TypeScript, Mongoose |
| Database | MongoDB |
