# SmartAds - AI-Powered Advertising Platform

An intelligent advertising platform that uses AI to generate logos, posters, videos, and marketing content.

## 🚀 Features

- **AI Logo Designer** - Generate professional logos using AI
- **Poster Creator** - Create stunning marketing posters
- **Video Generator** - Automated video content creation
- **Caption Writer** - AI-powered caption generation
# SmartAds

SmartAds is an AI-assisted advertising workspace for creating and managing marketing content. It combines a React frontend with a Flask API and MongoDB-backed account and product data.

**Author:** Javeria Iqbal

## Features

- Create AI-assisted logos, designs, and reusable templates.
- Manage products, users, and marketing assets from the dashboard.
- Generate video ads and voiceovers, and use social publishing integrations.
- Sign in with email/password or Google OAuth.
- Review feedback and marketing analytics.

Some features require third-party credentials. Without them, the app can still be explored, but connected services such as AI generation, cloud uploads, OAuth, and social publishing will not be available.

## Tech Stack

- Frontend: React 19, Vite 7, Tailwind CSS, Lucide React.
- Backend: Python, Flask, MongoDB (PyMongo).
- Integrations: Google Gemini, Google OAuth, Cloudinary, ElevenLabs, LinkedIn, and Facebook.

## Project Layout

```text
backend/       Flask application, API controllers, services, and configuration
frontend/      React application, views, components, and styles
public/        Static assets served by Vite
package.json   Frontend scripts and dependencies
vite.config.js Vite configuration (frontend source is in frontend/)
```

## Requirements

- Node.js 20.19+ or 22.12+ and npm (required by Vite 7).
- Python 3.9 or newer.
- MongoDB running locally or a MongoDB connection string.
- Optional credentials for the external integrations you plan to use.

## Local Setup

1. Clone the repository and enter the project directory:

   ```bash
   git clone --branch smartads-complete-project https://github.com/Javeria530/smartads.git
   cd smartads
   ```

2. Install frontend dependencies and create your local environment file:

   ```bash
   npm install
   ```

   Copy `.env.example` to `.env`, then set the values needed for the services you use. `.env` is ignored by Git; do not commit real credentials.

3. Create and activate a Python virtual environment, then install the backend packages:

   ```bash
   python -m venv .venv
   ```

   Windows PowerShell:

   ```powershell
   .\.venv\Scripts\Activate.ps1
   ```

   macOS/Linux:

   ```bash
   source .venv/bin/activate
   ```

   Install dependencies:

   ```bash
   pip install -r backend/requirements.txt
   ```

4. Start the backend from the `backend` directory:

   ```bash
   cd backend
   python app.py
   ```

   The API runs at `http://127.0.0.1:5000` by default. Keep this terminal open.

5. In a second terminal, from the project root, start Vite:

   ```bash
   npm run dev
   ```

   Open the local URL printed by Vite (normally `http://localhost:5173`).

## Environment Variables

See `.env.example` for the complete list. The main settings are:

| Variable | Purpose |
| --- | --- |
| `MONGO_URI` | MongoDB connection string; defaults to local MongoDB. |
| `DATABASE_NAME` | MongoDB database name; defaults to `SmartAds`. |
| `FLASK_HOST`, `FLASK_PORT`, `FLASK_DEBUG` | Backend server settings. |
| `GEMINI_API_KEY` | Gemini access for backend AI features. |
| `CLOUD_NAME`, `CLOUD_API_KEY`, `CLOUD_API_SECRET` | Cloudinary uploads. |
| `ELEVENLABS_API_KEY`, `ELEVENLABS_VOICE_ID` | Voice generation. |
| `LINKEDIN_CLIENT_ID`, `LINKEDIN_CLIENT_SECRET` | LinkedIn integration. |
| `FACEBOOK_APP_ID`, `FACEBOOK_APP_SECRET` | Facebook integration. |
| `VITE_API_URL` | API base URL used by the frontend. |
| `VITE_GOOGLE_CLIENT_ID` | Google OAuth client ID for the frontend. |
| `VITE_GEMINI_API_KEY` | Optional browser-side Gemini integration. Treat `VITE_*` values as public; never put private credentials in them. |

## Development Commands

```bash
npm run dev       # Start the Vite development server
npm run build     # Create a production frontend build in dist/
npm run preview   # Preview the production build
npm run lint      # Run ESLint
npm test -- --run # Run frontend tests once
```

## API

The Flask API is served under `/api`. The root endpoint (`GET /`) returns a JSON overview of the available API groups. Configure `VITE_API_URL` when the backend is not running at `http://127.0.0.1:5000`.

## Security

Keep `.env` and all provider credentials private. Any credential that has previously been committed should be rotated with its provider; removing it from the latest source does not erase it from Git history.
