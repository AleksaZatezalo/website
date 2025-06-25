# Phantom Security Website

A full-stack web application for Phantom Security built with the MERN stack, featuring a modern design with black, purple, and gold theming.

## 🏗️ Architecture Overview

```
phantom-security-website/
├── client/                 # React frontend
│   ├── public/
│   ├── src/
│   │   ├── components/     # Reusable UI components
│   │   ├── pages/          # Main application pages
│   │   ├── contexts/       # React contexts (Auth, Theme)
│   │   ├── hooks/          # Custom React hooks
│   │   ├── services/       # API service layer
│   │   ├── utils/          # Utility functions
│   │   └── styles/         # Global styles and theme
│   └── package.json
├── server/                 # Express.js backend
│   ├── controllers/        # Route controllers
│   ├── middleware/         # Custom middleware
│   ├── models/             # MongoDB schemas
│   ├── routes/             # API routes
│   ├── config/             # Database and environment config
│   ├── utils/              # Server utilities
│   └── package.json
├── shared/                 # Shared types and utilities
├── docs/                   # Additional documentation
└── README.md
```

## 🚀 Features

### Core Pages
- **Landing Page** - Company overview and mission statement
- **Blog** - Research articles and industry insights
- **Services** - Detailed service offerings
- **Contact** - Contact form with email integration

### Admin Features
- **Secure Authentication** - JWT-based admin login system
- **Content Management** - Edit all pages through admin dashboard
- **Blog Management** - Create, edit, and delete blog posts
- **Contact Management** - View and respond to contact submissions

### Technical Features
- **Responsive Design** - Mobile-first approach with purple/black/gold theme
- **RESTful API** - Clean API design with proper error handling
- **Security** - Input validation, rate limiting, and secure headers
- **Performance** - Optimized builds and lazy loading

## 🛠️ Tech Stack

**Frontend**
- React 18+ with TypeScript
- React Router for navigation
- Styled Components / CSS Modules for styling
- Axios for API communication
- React Hook Form for form management

**Backend**
- Node.js with Express.js
- MongoDB with Mongoose ODM
- JWT for authentication
- Bcrypt for password hashing
- Nodemailer for email functionality
- Express Validator for input validation

**Development Tools**
- Vite for frontend build tooling
- ESLint + Prettier for code formatting
- Husky for git hooks
- Jest for testing
- Docker for containerization

## 📦 Package Structure

### Client Package (`/client`)
```json
{
  "name": "@phantom-security/client",
  "dependencies": {
    "react": "^18.2.0",
    "react-router-dom": "^6.8.0",
    "styled-components": "^5.3.0",
    "axios": "^1.3.0",
    "react-hook-form": "^7.43.0"
  }
}
```

### Server Package (`/server`)
```json
{
  "name": "@phantom-security/server",
  "dependencies": {
    "express": "^4.18.0",
    "mongoose": "^7.0.0",
    "jsonwebtoken": "^9.0.0",
    "bcryptjs": "^2.4.3",
    "nodemailer": "^6.9.0",
    "express-validator": "^6.15.0"
  }
}
```

## 🚦 Getting Started

### Prerequisites
- Node.js 18+ and npm
- MongoDB instance (local or Atlas)
- Email service credentials (for contact form)

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/your-username/phantom-security-website.git
   cd phantom-security-website
   ```

2. **Install dependencies**
   ```bash
   # Install root dependencies
   npm install
   
   # Install client dependencies
   cd client && npm install
   
   # Install server dependencies
   cd ../server && npm install
   ```

3. **Environment Configuration**
   ```bash
   # Server environment (.env in /server)
   cp server/.env.example server/.env
   
   # Configure variables:
   MONGODB_URI=mongodb://localhost:27017/phantom-security
   JWT_SECRET=your-super-secure-jwt-secret
   EMAIL_HOST=smtp.your-email-provider.com
   EMAIL_USER=your-email@domain.com
   EMAIL_PASS=your-email-password
   PORT=5000
   ```

4. **Start Development Servers**
   ```bash
   # Start both client and server concurrently
   npm run dev
   
   # Or start individually:
   npm run server    # Backend on :5000
   npm run client    # Frontend on :3000
   ```

## 📝 API Endpoints

### Public Routes
```
GET    /api/pages/about      # Get About Us content
GET    /api/pages/services   # Get Services content
GET    /api/blog             # Get all blog posts
GET    /api/blog/:id         # Get specific blog post
POST   /api/contact          # Submit contact form
```

### Protected Admin Routes
```
POST   /api/auth/login       # Admin authentication
GET    /api/auth/verify      # Verify JWT token

PUT    /api/admin/pages/about    # Update About Us content
PUT    /api/admin/pages/services # Update Services content
POST   /api/admin/blog           # Create new blog post
PUT    /api/admin/blog/:id       # Update blog post
DELETE /api/admin/blog/:id       # Delete blog post
GET    /api/admin/contacts       # Get contact submissions
```

## 🎨 Design System

### Color Palette
```css
:root {
  --primary-black: #000000;
  --primary-purple: #6B46C1;
  --accent-gold: #F59E0B;
  --dark-purple: #4C1D95;
  --light-purple: #A78BFA;
  --background-dark: #111827;
  --text-light: #F9FAFB;
}
```

### Component Architecture
- **Atomic Design** - Components organized as atoms, molecules, organisms
- **Theme Provider** - Centralized theme management
- **Responsive Breakpoints** - Mobile-first responsive design
- **Animation System** - Consistent motion design

## 🔒 Security Features

- **Authentication** - JWT-based admin authentication
- **Input Validation** - Server-side validation for all inputs
- **Rate Limiting** - API endpoint protection
- **CORS Configuration** - Proper cross-origin setup
- **Helmet.js** - Security headers
- **Environment Variables** - Sensitive data protection

## 🧪 Testing Strategy

```bash
# Run all tests
npm test

# Client tests
npm run test:client

# Server tests  
npm run test:server

# Coverage report
npm run test:coverage
```

## 🚀 Deployment

### Production Build
```bash
# Build client for production
npm run build:client

# Start production server
npm run start:prod
```

### Docker Deployment
```bash
# Build and run with Docker Compose
docker-compose up --build

# Production deployment
docker-compose -f docker-compose.prod.yml up -d
```

### Environment Variables (Production)
```env
NODE_ENV=production
MONGODB_URI=mongodb+srv://user:pass@cluster.mongodb.net/phantom-security
JWT_SECRET=your-production-jwt-secret
CLIENT_URL=https://phantomsecurity.com
EMAIL_HOST=smtp.gmail.com
EMAIL_USER=contact@phantomsecurity.com
EMAIL_PASS=app-specific-password
```

## 📚 Development Guidelines

### Code Style
- **TypeScript** for type safety
- **ESLint + Prettier** for consistent formatting
- **Conventional Commits** for clear git history
- **Component Documentation** with JSDoc comments

### Git Workflow
```bash
# Feature development
git checkout -b feature/admin-dashboard
git commit -m "feat: add admin dashboard component"
git push origin feature/admin-dashboard

# Create pull request for review
```

### Project Scripts
```json
{
  "scripts": {
    "dev": "concurrently \"npm run server\" \"npm run client\"",
    "client": "cd client && npm start",
    "server": "cd server && npm run dev",
    "build": "cd client && npm run build",
    "test": "npm run test:client && npm run test:server",
    "lint": "eslint . --ext .js,.jsx,.ts,.tsx",
    "format": "prettier --write ."
  }
}
```

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'feat: add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🔗 Links

- **Live Site**: https://phantomsecurity.com
- **Documentation**: [docs/](./docs/)
- **API Docs**: [docs/api.md](./docs/api.md)
- **Deployment Guide**: [docs/deployment.md](./docs/deployment.md)

---

**Phantom Security** - Protecting your digital assets with cutting-edge security solutions.
