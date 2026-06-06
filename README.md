# 🩸 BloodLink AI — Emergency Blood Donation Platform

Pakistan's most intelligent blood donation crisis response platform for Rawalpindi & Islamabad.

## ✨ Features
- **AI-Powered Matching** — Gemini-driven chatbot for triage & donor coordination
- **Live SOS Broadcasts** — Real-time emergency request broadcasting
- **Interactive Map** — Leaflet-powered hospital & camp locator
- **Blood Bank Inventory** — Live availability tracking across Twin Cities hospitals
- **ML Triage Lab** — Blood demand forecasting & camp clustering
- **Bilingual** — Full English & اردو support
- **MongoDB + Fallback** — Works with Atlas or in-memory mock data

## 🚀 Quick Deploy

### Option A — Single Deployment (Render only)
```bash
# 1. Push to GitHub
git init && git add . && git commit -m "BloodLink AI v1.0" && git push

# 2. Create Render Web Service
#    Build: npm install && npm run build
#    Start: npm start
#    Add env vars from .env.example
```

### Option B — Split Deployment (Render backend + Vercel frontend)
```bash
# Backend → Render (same as above, set FRONTEND_URL to Vercel URL)
# Frontend → Vercel (import repo, framework: Vite, add VITE_API_URL env var)
```

## 🔑 Environment Variables
See `.env.example` for all required variables.

| Variable | Required | Description |
|---|---|---|
| `MONGO_URI` | No | MongoDB Atlas URI. Falls back to in-memory if blank |
| `GEMINI_API_KEY` | No | Google Gemini key. Falls back to hardcoded responses |
| `FRONTEND_URL` | Yes (prod) | Vercel URL for CORS |
| `VITE_API_URL` | Split only | Render backend URL for frontend API calls |

## 🏗️ Tech Stack
- **Frontend:** React 19 + TypeScript + Vite + Tailwind CSS v4
- **Backend:** Node.js + Express + TypeScript + esbuild
- **Database:** MongoDB Atlas (with in-memory fallback)
- **AI:** Google Gemini 1.5 Flash
- **Maps:** Leaflet.js
- **Charts:** Recharts
- **Animations:** Framer Motion

## 📁 Structure
```
bloodlink-ai/
├── src/                  # React frontend
│   ├── components/       # UI components
│   ├── lib/api.ts        # API base URL config
│   ├── types.ts          # TypeScript types
│   ├── App.tsx           # Root component
│   └── main.tsx          # Vite entry
├── backend/              # Express API
│   ├── routes/           # API route handlers
│   ├── services/         # DB & Gemini services
│   ├── data/             # Seed data
│   └── server.ts         # Express server
├── index.html            # Vite HTML entry
├── server.ts             # Proxy entry (imports backend/server)
├── render.yaml           # Render deploy config
├── vercel.json           # Vercel deploy config
└── package.json          # Single package.json
```
