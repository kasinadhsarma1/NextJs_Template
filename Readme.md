# NextJS Template

A modern full-stack Next.js 15 TypeScript + Radix Ui application template with FastAPI backend, featuring comprehensive UI components and security best practices. There is no secret recipe beyond all are one.

## 📋 Table of Contents

- [Overview](#overview)
- [Project Structure](#project-structure)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Running the Application](#running-the-application)
- [Technology Stack](#technology-stack)
- [Features](#features)
- [Development](#development)
- [API Documentation](#api-documentation)
- [Contributing](#contributing)
- [License](#license)

## 🎯 Overview

This is a cutting-edge full-stack TypeScript/Python template project that includes:
- **Next.js 15 Frontend**: Modern React 19 with App Router and TypeScript
- **FastAPI Backend**: High-performance Python backend with async support
- **MongoDB Integration**: NoSQL database for flexible data storage
- **shadcn/ui Components**: 50+ beautiful, accessible UI components
- **Turbopack**: Ultra-fast bundler for lightning-speed development
- **Security-First**: Comprehensive security measures and audit tools

This template is designed to help you quickly bootstrap production-ready full-stack applications with the latest technologies and best practices.

## 📁 Project Structure

```
NextJs_Template/
├── backend/                 # FastAPI backend service
│   ├── main.py             # Main FastAPI application
│   ├── main_secure.py      # Secure FastAPI configuration
│   ├── pyproject.toml      # Python project configuration
│   └── requirements.txt    # Python dependencies
├── frontend/               # Next.js 15 frontend application
│   ├── app/               # App Router directory (Next.js 13+)
│   │   ├── layout.tsx     # Root layout component
│   │   ├── page.tsx       # Home page component
│   │   ├── globals.css    # Global styles
│   │   └── favicon.ico    # App icon
│   ├── components/        # React components
│   │   └── ui/           # shadcn/ui component library (50+ components)
│   │       ├── button.tsx
│   │       ├── card.tsx
│   │       ├── dialog.tsx
│   │       ├── form.tsx
│   │       ├── input.tsx
│   │       ├── table.tsx
│   │       └── ... (40+ more components)
│   ├── hooks/            # Custom React hooks
│   │   ├── use-mobile.ts
│   │   └── use-toast.ts
│   ├── lib/              # Utility functions
│   │   └── utils.ts      # Tailwind utilities and helpers
│   ├── public/           # Static assets
│   │   ├── next.svg
│   │   ├── vercel.svg
│   │   └── ...
│   ├── components.json   # shadcn/ui configuration
│   ├── eslint.config.mjs # ESLint configuration
│   ├── next.config.ts    # Next.js configuration
│   ├── package.json      # Node.js dependencies
│   ├── postcss.config.mjs # PostCSS configuration
│   ├── tailwind.config.ts # Tailwind CSS configuration
│   ├── tsconfig.json     # TypeScript configuration
│   └── README.md         # Frontend documentation
├── scripts/              # Utility scripts
│   └── security-audit.sh # Security audit script
├── tests/                # Backend tests
├── CONTRIBUTING.md       # Contribution guidelines
├── LICENSE               # MIT License
├── SECURITY.md           # Security policy
├── SECURITY-CHECKLIST.md # Security checklist
└── README.md             # Project documentation
```

## 🔧 Prerequisites

Before you begin, ensure you have the following installed:

- **Node.js** (v18 or higher) - Required for Next.js 15
- **npm** (v9 or higher) or **yarn** (v1.22 or higher) or **pnpm** (v8 or higher)
- **Python** (v3.9 or higher)
- **pip** (Python package manager)
- **MongoDB** (v5.0 or higher) - Local or Atlas cloud instance

## 📦 Installation

### 1. Clone the Repository

```bash
git clone https://github.com/kasinadhsarma1/NextJs_Template.git
cd NextJs_Template
```

### 2. Backend Setup

```bash
cd backend

# Create a virtual environment
python -m venv venv

# Activate virtual environment
# On Linux/Mac:
source venv/bin/activate
# On Windows:
venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt
```

### 3. Frontend Setup

```bash
cd frontend

# Install dependencies (choose one)
npm install
# or
yarn install
# or (recommended for speed)
pnpm install
```

### 4. Environment Configuration

Create a `.env.local` file in the frontend directory:

```env
# API Configuration
NEXT_PUBLIC_API_URL=http://localhost:8000
NEXT_PUBLIC_APP_URL=http://localhost:3000

# Development settings
NODE_ENV=development
```

Create a `.env` file in the backend directory:

```env
# MongoDB Configuration
MONGODB_URL=mongodb://localhost:27017/nextjs_template
DATABASE_NAME=nextjs_template

# Security Configuration
SECRET_KEY=your_super_secure_secret_key_here
JWT_SECRET_KEY=your_jwt_secret_key_here
JWT_ALGORITHM=HS256
ACCESS_TOKEN_EXPIRE_MINUTES=30

# Server Configuration
PORT=8000
DEBUG=true
ENVIRONMENT=development

# CORS Configuration
ALLOWED_ORIGINS=["http://localhost:3000", "https://your-domain.com"]

# Rate Limiting
RATE_LIMIT_REQUESTS=100
RATE_LIMIT_WINDOW=60
```

⚠️ **Security Note**: Never commit `.env` files to version control. Always use strong, unique secrets in production.

## 🚀 Running the Application

### Start the Backend Server

```bash
cd backend
source venv/bin/activate  # Activate virtual environment

# Run with uvicorn
uvicorn main:app --reload --host 0.0.0.0 --port 8000

# Or run directly
python main.py
```

The backend API will be available at `http://localhost:8000`

### Start the Frontend Development Server

```bash
cd frontend

# Start Next.js development server with Turbopack (recommended)
npm run dev
# or
yarn dev
# or
pnpm dev

# Alternative: Start without Turbopack
npm run dev -- --no-turbopack
```

The frontend will automatically open at `http://localhost:3000`

**Note**: This template uses Turbopack for ultra-fast development builds. Turbopack can be up to 10x faster than traditional webpack.

## 🛠️ Technology Stack

### Frontend (TypeScript/Next.js)
- **Next.js 15** - React framework with App Router
- **React 19** - Latest React with Concurrent Features
- **TypeScript 5** - Type-safe JavaScript
- **Turbopack** - Ultra-fast bundler by Vercel
- **Tailwind CSS 4** - Utility-first CSS framework
- **shadcn/ui** - Accessible component library based on Radix UI
- **Lucide React** - Beautiful icon library
- **class-variance-authority** - Component variant utilities
- **ESLint 9** - Modern linting with flat config

### Backend (Python/FastAPI)
- **FastAPI** - Modern, fast web framework for building APIs
- **Python 3.9+** - Latest Python features
- **MongoDB** - NoSQL database
- **Motor** - Async MongoDB driver
- **Pydantic** - Data validation and settings management
- **uvicorn** - Lightning-fast ASGI server
- **JWT** - JSON Web Token authentication
- **Passlib** - Password hashing utilities

### Development & Security Tools
- **Black** - Code formatting
- **isort** - Import sorting
- **Flake8** - Code linting
- **MyPy** - Static type checking
- **Pytest** - Testing framework
- **Bandit** - Security linter
- **Safety** - Dependency vulnerability scanner

### UI Component Library (50+ Components)

The template includes a comprehensive set of shadcn/ui components:

**Layout & Navigation:**
- Accordion, Breadcrumb, Card, Carousel
- Navigation Menu, Menubar, Tabs, Sheet

**Forms & Inputs:**
- Button, Input, Checkbox, Radio Group
- Select, Textarea, Form, Label
- Calendar, Input OTP, Slider, Switch

**Feedback & Overlays:**
- Alert, Alert Dialog, Dialog, Drawer
- Toast, Sonner, Tooltip, Hover Card
- Progress, Skeleton

**Data Display:**
- Avatar, Badge, Table, Pagination
- Aspect Ratio, Separator

**Advanced:**
- Command, Context Menu, Dropdown Menu
- Collapsible, Popover, Resizable
- Scroll Area, Toggle, Toggle Group

## ✨ Features

- ✅ **Next.js 15** with App Router and React 19
- ✅ **TypeScript** for type-safe development
- ✅ **Turbopack** for lightning-fast development builds
- ✅ **FastAPI** backend with automatic API documentation
- ✅ **MongoDB** integration with async operations
- ✅ **50+ shadcn/ui Components** - Production-ready UI library
- ✅ **Tailwind CSS 4** with modern features
- ✅ **Responsive and Accessible** design out of the box
- ✅ **Hot Module Replacement** for instant development feedback
- ✅ **Type-safe APIs** with Pydantic models
- ✅ **Modern ESLint 9** with flat configuration
- ✅ **Production-ready** project structure
- ✅ **Security-first** approach with comprehensive auditing
- 🔒 **Enterprise-grade Security Features**
  - Rate limiting and DDoS protection
  - JWT authentication and authorization
  - Input validation and sanitization
  - Security headers and CORS configuration
  - Dependency vulnerability scanning
  - Environment variable protection
  - Automated security auditing
  - Password hashing with bcrypt
  - SQL injection prevention
  - XSS protection
  - Security linting with Bandit and ESLint security plugins

## 💻 Development

### Frontend Development

```bash
cd frontend

# Start development server with Turbopack (recommended)
npm run dev

# Build for production with Turbopack
npm run build

# Start production server
npm run start

# Run ESLint
npm run lint

# Install specific shadcn/ui component
npx shadcn@latest add button

# Install multiple components
npx shadcn@latest add card dialog form input
```

### Backend Development

```bash
cd backend

# Start with auto-reload
uvicorn main:app --reload

# Start secure version
uvicorn main_secure:app --reload

# Run tests
pytest

# Run tests with coverage
pytest --cov=.

# Format code
black .

# Sort imports
isort .

# Lint code
flake8 .

# Type checking
mypy .

# Security audit
bandit -r .
safety check
```

### Adding New shadcn/ui Components

The template includes 50+ pre-installed components. To add more:

```bash
cd frontend

# List all available components
npx shadcn@latest add

# Add specific components
npx shadcn@latest add data-table
npx shadcn@latest add command
npx shadcn@latest add date-picker
```

## 📚 API Documentation

FastAPI provides automatic interactive API documentation:

- **Swagger UI**: `http://localhost:8000/docs`
- **ReDoc**: `http://localhost:8000/redoc`
- **OpenAPI JSON**: `http://localhost:8000/openapi.json`

## 🔒 Security

This template includes comprehensive security measures:

### Security Features

- **Authentication & Authorization**: JWT-based authentication with secure password hashing
- **Rate Limiting**: API endpoints protected against brute force attacks
- **Input Validation**: Comprehensive validation using Pydantic models
- **Security Headers**: CORS, CSP, HSTS, and other security headers configured
- **Dependency Security**: Regular vulnerability scanning with Dependabot
- **Environment Protection**: Secure handling of sensitive configuration
- **Audit Logging**: Comprehensive logging for security monitoring

### Security Tools & Scripts

- `scripts/security-audit.sh` - Comprehensive security audit script
- `SECURITY.md` - Security policy and vulnerability reporting
- Automated dependency scanning with npm audit and safety
- Security linting with ESLint security plugin and Bandit

### Running Security Audits

```bash
# Run comprehensive security audit
./scripts/security-audit.sh

# Frontend security checks
cd frontend
npm audit
npm run security:check

# Backend security checks  
cd backend
bandit -r .
safety check
```

For more information, see our [Security Policy](SECURITY.md).

## 🧪 Testing

### Frontend Tests

```bash
cd frontend

# Next.js doesn't include testing by default
# Install testing dependencies first:
npm install --save-dev jest @testing-library/react @testing-library/jest-dom

# Create test files in __tests__ directory or alongside components
# Example: components/ui/__tests__/button.test.tsx
```

### Backend Tests

```bash
cd backend

# Run all tests
pytest

# Run with coverage
pytest --cov=.

# Run specific test file
pytest tests/test_main.py

# Run tests in watch mode
pytest --watch
```

Tests are located in:
- `tests/` directory for backend tests
- `__tests__/` or `*.test.tsx` files for frontend tests

## 🏗️ Building for Production

### Frontend

```bash
cd frontend

# Build with Turbopack (faster)
npm run build

# Or build with traditional webpack
npm run build -- --no-turbopack

# Test production build locally
npm run start
```

The optimized production build will be in the `frontend/.next/` directory.

### Backend

```bash
cd backend

# Install production dependencies
pip install -r requirements.txt

# Run with production settings (multiple workers)
uvicorn main:app --host 0.0.0.0 --port 8000 --workers 4

# Or run secure version
uvicorn main_secure:app --host 0.0.0.0 --port 8000 --workers 4
```

## 🚢 Deployment

### Frontend Deployment Options
- **Vercel** (recommended for Next.js) - Zero-config deployment
- **Netlify** - Easy static site deployment
- **AWS Amplify** - Full-stack serverless deployment
- **Railway** - Simple container deployment
- **Cloudflare Pages** - Edge deployment
- **GitHub Pages** - For static exports only

### Backend Deployment Options
- **Railway** - Simple Python deployment
- **Render** - Easy container deployment  
- **Heroku** - Classic PaaS platform
- **AWS ECS/Fargate** - Container orchestration
- **Google Cloud Run** - Serverless containers
- **DigitalOcean App Platform** - Simple app deployment

### Database
- **MongoDB Atlas** (recommended for production)
- **Railway MongoDB** - Integrated database
- **Self-hosted MongoDB** on VPS

## 🤝 Contributing

Contributions are welcome! Please read our [Contributing Guidelines](CONTRIBUTING.md) for details on how to submit pull requests, report issues, and contribute to the project.

## 📄 License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details.

## 👥 Author

**kasinadhsarma1**
- GitHub: [@kasinadhsarma1](https://github.com/kasinadhsarma1)

## 🙏 Acknowledgments

- [Next.js](https://nextjs.org/) - The React framework for production
- [React 19](https://react.dev/) - A JavaScript library for building user interfaces
- [FastAPI](https://fastapi.tiangolo.com/) - Modern, fast web framework for building APIs
- [shadcn/ui](https://ui.shadcn.com/) - Beautiful and accessible component library
- [Tailwind CSS](https://tailwindcss.com/) - Utility-first CSS framework
- [Turbopack](https://turbo.build/pack) - The successor to webpack
- [TypeScript](https://www.typescriptlang.org/) - Typed superset of JavaScript
- [MongoDB](https://www.mongodb.com/) - NoSQL database for modern applications
- [Vercel](https://vercel.com/) - Platform for frontend frameworks and static sites

## 📞 Support

If you have any questions or issues, please:
- Open an issue on GitHub
- Check existing issues and discussions
