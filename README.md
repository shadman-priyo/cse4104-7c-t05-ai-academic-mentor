# AI Academic Mentor

CSE4104-7C-T05 | Northern University of Business & Technology, Khulna (NUBTK)
Software Development III 

An AI-assisted study platform: authentication, an AI chatbot, quiz
generation, note summarization, a study planner, progress tracking, and an
admin dashboard.

> **Team:** Shadman Sadequeen Priyo (Lead) · Musabbir Hossain Chayon (Frontend) ·
> SK. Nadirul Haque Nadir (Backend) · Shafin Kabir (AI Integration)
> Instructor: Md. Riaz Mahmud

Repository: `<PASTE YOUR GITHUB REPO URL HERE — replace before submission>`

## Structure

```
AI-Academic-Mentor/
├── frontend/     React 19 + Vite SPA
├── backend/      Express + MongoDB (Mongoose) API
└── README.md     This file
```

`frontend/` and `backend/` are two independent npm projects — install and
run them separately.

## Running it

**Backend**
```
cd backend
cp .env.example .env      # fill in your real MongoDB URI, JWT secret, AI keys
npm install
npm start                 # http://localhost:5000
```

**Frontend**
```
cd frontend
npm install
npm run dev                # http://localhost:5173
```

## Before you submit / demo — known open issues

- `frontend/src/services/api.js` still points `PRODUCTION_API_BASE` at a
  placeholder (`YOUR-BACKEND.onrender.com`). Set it to your real deployed
  backend URL, or set `VITE_API_BASE` in a `frontend/.env`.
- The Gemini and HuggingFace keys shipped in earlier submissions were
  invalid/empty, which silently drops every AI feature (chat, quiz
  generation, summarizer, planner) to a static canned-text fallback. Put
  working keys in `backend/.env` and actually test a live AI response
  before submitting — don't assume it's using the "AI" it's supposed to.
- Admin **Announcements** and **Bulk Clear / Wipe Data** are intentionally
  non-functional stubs (no backing Mongo model / disabled to avoid
  destructive actions). If your rubric expects a working admin panel,
  decide whether that's acceptable or needs a real implementation.
- `.env` files are never committed or submitted — only `.env.example`. See
  `CHANGELOG.md` for why this matters here specifically.

## Tech stack

- **Frontend:** React 19, Vite, React Router, Axios
- **Backend:** Node.js, Express, Mongoose/MongoDB Atlas, JWT auth, bcrypt,
  Helmet, express-rate-limit
- **AI:** Google Gemini (primary), HuggingFace Inference (fallback)
