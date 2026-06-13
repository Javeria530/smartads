# SmartAds - AI-Powered Advertising Platform

> NOTE: Project updated with tests (login/signup & sentiment analysis).

An intelligent advertising platform that uses AI to generate logos, posters, videos, and marketing content.

## 🚀 Features

- **AI Logo Designer** - Generate professional logos using AI
- **Poster Creator** - Create stunning marketing posters
- **Video Generator** - Automated video content creation
- **Caption Writer** - AI-powered caption generation
- **Voiceover Maker** - Natural voiceover synthesis
- **Analytics Dashboard** - Track performance metrics
- **User Management** - Multi-user support with role-based access

## 📁 Project Structure

```
SMARTADS/
├── backend/                    # Flask API Backend
│   ├── config/                 # Configuration files
│   │   ├── settings.py         # App settings & env vars
│   │   └── database.py         # MongoDB connection
│   ├── controllers/            # Route handlers
│   │   ├── auth_controller.py  # Authentication routes
│   │   ├── design_controller.py # Design generation routes
│   │   └── product_controller.py # Product routes
│   ├── models/                 # Data models/schemas
│   │   ├── user_model.py       # User schema
│   │   └── product_model.py    # Product schema
│   ├── services/               # Business logic
│   │   ├── auth_service.py     # Auth operations
│   │   ├── design_service.py   # AI design generation
│   │   └── product_service.py  # Product operations
│   ├── middlewares/            # Custom middlewares
│   │   └── auth_middleware.py  # Auth middleware
│   ├── routes/                 # Legacy routes (deprecated)
│   ├── uploads/                # Local file uploads
│   ├── app.py                  # Main Flask application
│   └── requirements.txt        # Python dependencies
│
├── frontend/                   # React + Vite Frontend
│   ├── components/             # Reusable UI components
│   │   ├── common/             # Shared components
│   │   │   ├── Navbar.jsx
│   │   │   ├── ThemeToggle.jsx
│   │   │   └── ...
│   │   └── Dashboard/          # Dashboard-specific components
│   ├── views/                  # Page components
│   │   ├── Dashboard.jsx
│   │   ├── LandingPage.jsx
│   │   ├── LoginPage.jsx
│   │   ├── SignupPage.jsx
│   │   └── LogoDesigner.jsx
│   ├── context/                # React Context providers
│   │   ├── AuthContext.jsx
│   │   └── ThemeContext.jsx
│   ├── hooks/                  # Custom React hooks
│   ├── services/               # API communication
│   │   └── api.js
│   ├── utils/                  # Utility functions
│   │   ├── constants.js
│   │   └── validators.js
│   ├── styles/                 # CSS files
│   │   ├── App.css
│   │   └── index.css
│   ├── assets/                 # Static assets
│   ├── App.jsx                 # Main App component
│   ├── main.jsx                # Entry point
│   └── index.html              # HTML template
│
├── public/                     # Public static files
├── .env.example                # Environment variables template
├── .gitignore                  # Git ignore rules
├── eslint.config.js            # ESLint configuration
├── package.json                # NPM dependencies
├── vite.config.js              # Vite configuration
└── README.md                   # This file
```

## 🛠️ Tech Stack

### Frontend
- **React 19** - UI library
- **Vite 7** - Build tool
- **Lucide React** - Icons
- **Google OAuth** - Authentication

### Backend
- **Flask** - Python web framework
- **MongoDB** - Database
- **Cloudinary** - Image hosting
- **Google Gemini AI** - AI generation

## 📦 Installation

### Prerequisites
- Node.js 18+
- Python 3.9+
- MongoDB Atlas account
- Cloudinary account
- Google Cloud Console (for OAuth & Gemini)

### Setup

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/smartads.git
   cd smartads
   ```

2. **Install frontend dependencies**
   ```bash
   npm install
   ```

3. **Install backend dependencies**
   ```bash
   cd backend
   pip install -r requirements.txt
   cd ..
   ```

4. **Configure environment variables**
   ```bash
   cp .env.example .env
   # Edit .env with your credentials
   ```

5. **Run the backend**
   ```bash
   cd backend
   python app.py
   ```

6. **Run the frontend** (in a new terminal)
   ```bash
   npm run dev
   ```

7. **Open in browser**
   ```
   http://localhost:5173
   ```

## 🔧 API Endpoints

### Authentication
- `POST /api/signup` - Register new user
- `POST /api/login` - User login
- `POST /api/google-signup` - Google OAuth

### User Management
- `POST /api/add-subuser` - Add sub-user
- `GET /api/get-subusers/:id` - Get sub-users
- `PUT /api/update-subuser/:id` - Update sub-user
- `DELETE /api/delete-subuser/:id` - Delete sub-user

### Products & Designs
- `POST /api/add-product` - Add product
- `POST /api/upload-images` - Upload images
- `POST /api/generate-design` - Generate AI design
- `GET /api/designs` - List designs

## 📄 License

MIT License

## 👥 Contributors

- Your Name - Initial work
