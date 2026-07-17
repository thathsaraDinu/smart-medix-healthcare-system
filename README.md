<h1 align="center" id="title">SMART MEDIX HEALTHCARE SYSTEM</h1>

<p align="center"><img src="https://socialify.git.ci/ShanelkaPramuditha/smart-healthcare-system/image?font=Source%20Code%20Pro&forks=1&issues=1&language=1&name=1&pattern=Plus&pulls=1&stargazers=1&theme=Auto" alt="smart-healthcare-system" width="640" height="320" />
<a href="https://github.com/ShanelkaPramuditha/smart-healthcare-system/graphs/contributors">
  <br><br>
  <img src="https://contrib.rocks/image?repo=ShanelkaPramuditha/smart-healthcare-system" />
</a>
</p>

## <b>📋 Table of Contents</b>

- [Overview](#overview)
- [Tech Stack](#tech-stack)
- [Architecture](#architecture)
- [Features](#features)
- [Installation](#installation)
- [Environment Variables](#environment-variables)
- [Project Structure](#project-structure)
- [API Endpoints](#api-endpoints)
- [User Roles](#user-roles)
- [Screenshots](#screenshots)
- [Contributing](#contributing)

## <b>🎯 Overview</b>

Smart Medix Healthcare System is a comprehensive healthcare management platform designed to streamline medical appointments, patient management, billing, and administrative tasks. The system provides a modern, user-friendly interface for patients, doctors, medical staff, and administrators to manage healthcare operations efficiently.

## <b>🛠 Tech Stack</b>

### Frontend
- **Framework**: React 18.3.1 with Vite
- **Styling**: TailwindCSS 3.4.10
- **UI Components**: Radix UI, shadcn/ui
- **State Management**: Zustand 4.5.5
- **Data Fetching**: TanStack Query 5.53.1
- **Routing**: React Router DOM 6.26.1
- **Forms**: React Hook Form 7.53.0 with Zod validation
- **Charts**: Chart.js 4.4.4, Recharts 2.13.0, React Chart.js 2
- **Calendar**: React Big Calendar, React Day Picker
- **PDF Generation**: jsPDF, jsPDF-autotable, html2canvas
- **Icons**: Lucide React, React Icons
- **Authentication**: Firebase 10.14.1
- **HTTP Client**: Axios 1.7.6

### Backend
- **Runtime**: Node.js with ES Modules
- **Framework**: Express 4.21.0
- **Database**: MongoDB with Mongoose 8.6.3
- **Authentication**: JWT (JSON Web Tokens) with bcrypt
- **Validation**: Zod 3.23.8
- **Logging**: Pino 9.4.0 with Pino HTTP
- **Security**: CORS, Express Rate Limiting, Cookie Parser
- **Testing**: Jest 29.7.0 with MongoDB Memory Server

### Development Tools
- **Package Manager**: pnpm
- **Code Formatting**: Prettier 3.3.3
- **Linting**: ESLint 8.57.0
- **Build Tool**: Vite 5.4.2
- **Hot Reload**: Nodemon 3.1.7

## <b>🏗 Architecture</b>

The system follows a client-server architecture with clear separation of concerns:

### Frontend Architecture
- **Component-based**: Modular React components organized by feature
- **Route-based Code Splitting**: Lazy loading for optimal performance
- **State Management**: Centralized state with Zustand
- **API Layer**: Axios-based API client with TanStack Query caching
- **Protected Routes**: Role-based access control with ProtectedRoute component

### Backend Architecture
- **MVC Pattern**: Models, Views (Controllers), and Routes separation
- **Middleware**: Authentication, authorization, validation, and logging
- **Service Layer**: Business logic separation from controllers
- **Repository Pattern**: Data access abstraction
- **Error Handling**: Centralized error handling with express-async-handler

### Database Design
- **User Collection**: Base user model with role-based extensions
- **Doctor Collection**: Extended user model with medical credentials
- **Patient Collection**: Extended user model with medical history
- **Appointment Collection**: Booking and scheduling data
- **Card Collection**: Payment card information

## <b>✨ Features</b>

### Patient Features
- **Appointment Management**
  - Search and filter doctors by specialization
  - View detailed doctor profiles
  - Book appointments with preferred doctors
  - View and manage personal appointments
  - Cancel or reschedule appointments
  - Appointment calendar view

- **Profile Management**
  - Personal information management
  - Medical history tracking
  - Treatment records
  - Payment history
  - Profile picture upload

- **Payment Processing**
  - Multiple payment methods (cash, card)
  - Save payment cards securely
  - View payment history
  - Receipt generation

### Doctor Features
- **Patient Management**
  - View assigned patients
  - Access patient medical history
  - Update patient records
  - View appointment schedules

### Medical Staff Features
- **Patient Care**
  - Manage patient information
  - Update medical history
  - Coordinate with doctors

### Admin Features
- **Dashboard Analytics**
  - Interactive charts and graphs
  - Appointment statistics
  - Doctor performance metrics
  - Patient demographics
  - Revenue tracking

- **User Management**
  - Manage all users (patients, doctors, staff)
  - Approve/reject doctor registrations
  - Activate/deactivate user accounts
  - View user statistics

- **Appointment Oversight**
  - View all system appointments
  - Generate appointment reports
  - Monitor booking trends

- **Report Generation**
  - PDF report generation
  - Export data for analysis
  - Custom date range reports

## <b>🚀 Installation</b>

### Prerequisites
- Node.js (v18 or higher)
- MongoDB (local instance or MongoDB Atlas)
- pnpm package manager

### Setup Steps

1. **Clone the repository**
```bash
git clone https://github.com/ShanelkaPramuditha/smart-healthcare-system.git
cd smartmedix
```

2. **Install dependencies**
```bash
# Install client dependencies
cd client
pnpm install

# Install server dependencies
cd ../server
pnpm install
```

3. **Configure environment variables**
Create `.env` files in both `client` and `server` directories (see Environment Variables section)

4. **Start the development servers**
```bash
# Option 1: Use the provided batch file (Windows)
start.bat

# Option 2: Start manually
# Terminal 1 - Client
cd client
pnpm run dev

# Terminal 2 - Server  
cd server
pnpm dev
```

5. **Access the application**
- Frontend: http://localhost:5173
- Backend: http://localhost:3001

### Production Build

```bash
# Build client
cd client
pnpm run build

# Start server in production mode
cd ../server
pnpm start
```

## <b>⚙️ Environment Variables</b>

### Server Environment Variables (`server/.env`)
```env
# Server Configuration
SERVER_PORT=3001

# Database Configuration
MONGODB_URI=mongodb://localhost:27017/smartmedix
DB_NAME=smartmedix

# JWT Configuration
ACCESS_TOKEN_SECRET=your_access_token_secret
REFRESH_TOKEN_SECRET=your_refresh_token_secret
ACCESS_TOKEN_EXPIRY=15m
REFRESH_TOKEN_EXPIRY=7d

# CORS Configuration
CORS_ORIGIN=http://localhost:5173

# Logging
LOG_LEVEL=info
```

### Client Environment Variables (`client/.env`)
```env
VITE_API_URL=http://localhost:3001/api
```

## <b>📁 Project Structure</b>

```
smartmedix/
├── client/                 # React frontend application
│   ├── src/
│   │   ├── api/           # API client and endpoints
│   │   ├── components/    # Reusable UI components
│   │   ├── constants/     # Application constants
│   │   ├── hooks/         # Custom React hooks
│   │   ├── layout/        # Layout components
│   │   ├── pages/         # Page components
│   │   ├── routes/        # Route configuration
│   │   ├── store/         # State management
│   │   ├── utils/         # Utility functions
│   │   └── validations/   # Form validation schemas
│   ├── public/            # Static assets
│   └── screenshots/       # Application screenshots
├── server/                # Express backend application
│   ├── src/
│   │   ├── constants/     # Server constants
│   │   ├── controllers/   # Request handlers
│   │   ├── factories/     # Factory functions
│   │   ├── middleware/    # Express middleware
│   │   ├── models/        # Mongoose models
│   │   ├── repositories/  # Data access layer
│   │   ├── routes/        # API routes
│   │   ├── services/      # Business logic
│   │   ├── utils/         # Utility functions
│   │   └── validations/   # Request validation schemas
│   └── __tests__/         # Server tests
├── start.bat              # Development startup script
└── README.md              # Project documentation
```

## <b>🔌 API Endpoints</b>

### Authentication
- `POST /api/auth/register` - User registration
- `POST /api/auth/login` - User login
- `POST /api/auth/logout` - User logout
- `POST /api/auth/refresh-token` - Refresh access token

### User Management
- `GET /api/users/profile` - Get user profile
- `PUT /api/users/profile` - Update user profile
- `GET /api/users/doctors` - Get all doctors
- `GET /api/users/patients` - Get all patients
- `PUT /api/users/status/:id` - Update user status

### Appointments
- `POST /api/appointments` - Create appointment
- `GET /api/appointments` - Get user appointments
- `GET /api/appointments/:id` - Get appointment details
- `PUT /api/appointments/:id` - Update appointment
- `DELETE /api/appointments/:id` - Cancel appointment
- `GET /api/appointments/all` - Get all appointments (admin)

### Payments
- `POST /api/cards` - Add payment card
- `GET /api/cards` - Get user cards
- `DELETE /api/cards/:id` - Delete card
- `PUT /api/appointments/pay/:id` - Process payment

### Reports
- `GET /api/reports/appointments` - Get appointment statistics
- `GET /api/reports/doctors` - Get doctor statistics

## <b>👥 User Roles</b>

The system implements role-based access control with four distinct roles:

### User (Patient)
- Can book, view, and cancel appointments
- Manage personal profile and medical history
- Process payments
- View payment history

### Doctor
- View assigned patients
- Access and update patient medical records
- View appointment schedules
- Manage patient treatments

### Medical Staff
- Manage patient information
- Update medical history
- Coordinate patient care

### Admin
- Full system access
- Manage all users and accounts
- View and approve doctor registrations
- Access comprehensive analytics and reports
- Monitor system performance

## <b>🖼 Logo</b>

<img src="client/screenshots/logo.webp" alt="Smart Medix Logo">

## <b>📸 Screenshots</b>

<div>
  <img src="client/screenshots/homepage.webp" alt="Homepage">
  <img src="client/screenshots/admin_dashboard.webp" alt="Admin Dashboard">
  <img src="client/screenshots/doctor_search.webp" alt="Doctor Search">
  <img src="client/screenshots/make_appointment.webp" alt="Make Appointment">
  <img src="client/screenshots/doc_profile.webp" alt="Doctor Profile">
  <img src="client/screenshots/profile.webp" alt="User Profile">
  <img src="client/screenshots/med_history.webp" alt="Medical History">
  <img src="client/screenshots/appointment_calender.webp" alt="Appointment Calendar">
  <img src="client/screenshots/payment_cards.webp" alt="Payment Cards">
  <img src="client/screenshots/payment_page.webp" alt="Payment Page">
  <img src="client/screenshots/appointments_reports.webp" alt="Appointments Reports">
  <img src="client/screenshots/doctors_reports.webp" alt="Doctors Reports">
  <img src="client/screenshots/login.webp" alt="Login Page">
  <img src="client/screenshots/sign_up.webp" alt="Sign Up Page">
</div>

## <b>🤝 Contributing</b>

Contributions are welcome! Please follow these guidelines:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

### Development Guidelines
- Follow existing code style and conventions
- Write meaningful commit messages
- Add tests for new features
- Update documentation as needed
- Ensure all tests pass before submitting

---

## <b>📄 License</b>

This project is licensed under the ISC License.
