# Deployment Guide

## Prerequisites
- GitHub account
- Render account (for backend)
- Vercel account (for frontend)

## Backend Deployment (Render)

1. Push your code to GitHub
2. Go to [Render Dashboard](https://dashboard.render.com/)
3. Click "New +" → "Web Service"
4. Connect your GitHub repository
5. Configure:
   - **Name**: code-reviewer-backend
   - **Root Directory**: Backend
   - **Build Command**: `npm install`
   - **Start Command**: `npm start`
6. Add Environment Variable:
   - Key: `API_KEY`
   - Value: Your Gemini API key
7. Click "Create Web Service"
8. Copy your backend URL (e.g., `https://code-reviewer-backend.onrender.com`)

## Frontend Deployment (Vercel)

1. Go to [Vercel Dashboard](https://vercel.com/dashboard)
2. Click "Add New" → "Project"
3. Import your GitHub repository
4. Configure:
   - **Framework Preset**: Vite
   - **Root Directory**: Frontend
5. Add Environment Variable:
   - Key: `VITE_API_URL`
   - Value: Your Render backend URL (from step 8 above)
6. Click "Deploy"

## Important Notes

- Backend on Render free tier may sleep after inactivity (first request takes ~30s)
- Update frontend API URL to use environment variable: `import.meta.env.VITE_API_URL`
- Keep your API_KEY secret and never commit .env files

## Local Development

Backend:
```bash
cd Backend
npm install
npm start
```

Frontend:
```bash
cd Frontend
npm install
npm run dev
```
