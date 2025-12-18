# JagaBook - Photoshoot Location Marketplace

## Overview

JagaBook is a comprehensive full-stack web application designed to serve as Pakistan's first online marketplace for photoshoot locations. The platform connects three key stakeholders: place providers who own photoshoot-worthy properties, customers seeking locations for various types of shoots, and photographers looking for unique venues. Built using the MERN stack (MongoDB, Express.js, React, Node.js), the application addresses critical challenges in the photography industry including lack of transparency, safety concerns, and the absence of a centralized platform for location discovery and booking.

### Problem Statement

The photography industry in Pakistan faces several critical challenges:

**For Customers and Photographers:**
- Difficulty in discovering verified, professional photoshoot locations with transparent pricing
- Risk of scams when booking through informal channels such as social media
- Lack of accountability and review systems to assess location quality
- No standardized booking and payment processes

**For Place Providers:**
- Absence of a centralized platform to showcase and monetize their properties
- Inability to reach a wider audience of potential customers
- Challenges in managing bookings and availability

**For the Industry:**
- High transaction friction and communication overhead
- Risk of external deals that bypass platform protection
- No verification system to ensure legitimacy of either party

### Solution

JagaBook provides a secure, transparent, and efficient marketplace that addresses these challenges through:

- A robust three-level verification system for place providers
- Integrated booking and payment processing
- In-platform communication system with contact protection
- Comprehensive review and rating mechanism
- Anti-bypass policies to maintain platform integrity
- Advanced search and filtering capabilities

## Table of Contents

- [Key Features](#key-features)
- [Technology Stack](#technology-stack)
- [System Architecture](#system-architecture)
- [Installation Guide](#installation-guide)
- [Project Structure](#project-structure)
- [API Documentation](#api-documentation)
- [User Roles and Permissions](#user-roles-and-permissions)
- [Security Implementation](#security-implementation)
- [Database Schema](#database-schema)
- [Future Enhancements](#future-enhancements)
- [Contributing](#contributing)
- [License](#license)

## Key Features

### Authentication and User Management

The application implements a comprehensive authentication system supporting three distinct user roles: customers, place providers, and photographers. The system utilizes JSON Web Tokens (JWT) for stateless authentication with secure password hashing using bcrypt. Key authentication features include:

- Role-based access control with granular permissions
- Email verification for new account registration
- Secure password reset functionality
- Session management and token refresh mechanisms

### Place Listing and Management

Place providers can create detailed listings for their photoshoot locations with the following capabilities:

- Upload multiple high-resolution images per location
- Specify comprehensive location details including address, amenities, and capacity
- Set dynamic pricing structures based on shoot type and seasonality
- Manage availability through an integrated calendar system
- Update listing information in real-time

### Advanced Search and Discovery

The platform provides sophisticated search and filtering mechanisms:

- Geographic filtering by city and area
- Price range specification with dynamic slider controls
- Shoot type categorization (wedding, fashion, commercial, portrait, event)
- Availability-based filtering
- Sorting options by price, rating, and popularity
- Full-text search across location names and descriptions

### Three-Level Verification System

A unique verification framework ensures platform security and trust:

**Level 3 - Unverified Status:**
- New providers without completed verification
- Limited visibility in search results
- Unable to receive bookings until verification completion
- Red badge indicator on listings

**Level 2 - Verified Status:**
- Identity documents successfully verified
- Digital signature or No Objection Certificate (NOC) submitted
- Ownership proof validated by platform administrators
- Eligible to receive bookings
- Blue badge indicator on listings

**Level 1 - Premium Verified Status:**
- All Level 2 requirements satisfied
- Minimum of two to three successfully completed bookings
- Positive customer reviews received
- Priority placement in search results
- Featured in homepage carousel
- Green badge indicator on listings

### Booking and Transaction System

The platform implements a comprehensive booking workflow:

1. Customer submits booking request for specific date
2. Provider reviews and accepts or rejects within 24-hour window
3. Upon acceptance, customer pays 5% advance payment through platform
4. Contact information unlocked for both parties after advance payment
5. Remaining 95% payment processed on shoot day
6. Booking marked as completed after successful shoot

**Cancellation Policy:**
- Full refund if cancelled 7+ days before shoot date
- 50% refund if cancelled 3-7 days before shoot date
- No refund if cancelled within 3 days of shoot date

### Secure Communication System

The platform features an integrated messaging system with the following security measures:

- End-to-end encrypted messaging between users
- Automatic detection of contact information sharing attempts
- Read receipt functionality
- Message history preservation
- Warning system for policy violations
- Account suspension mechanism for repeated offenses

**Contact Protection Policy:**
Users cannot exchange WhatsApp numbers, Instagram handles, Facebook profiles, or phone numbers until booking confirmation and advance payment completion. This policy ensures platform transaction integrity and user protection.

### Review and Rating System

Post-booking, customers can provide comprehensive feedback through:

**Multi-Category Rating System:**
- Location quality (1-5 stars)
- Provider responsiveness (1-5 stars)
- Value for money assessment (1-5 stars)
- Cleanliness and maintenance (1-5 stars)

**Additional Features:**
- Written review with 1000 character limit
- Photo upload capability
- Verified booking badge on reviews
- Provider response mechanism
- Review moderation system

### Payment Processing

The application includes a demonstration payment gateway with the following features:

**Platform Fee Structure:**
- 5-10% commission on each successful booking
- Transparent fee calculation displayed before payment
- Automatic fee deduction from total amount

**Payment Split:**
- 5% advance payment required for booking confirmation
- Triggers contact information unlock
- 95% balance paid directly to provider
- Escrow system for dispute resolution

**Payment Methods (Demo Mode):**
- Credit/Debit Card simulation
- Bank transfer simulation
- Digital wallet simulation

### Administrative Dashboard

Platform administrators have access to comprehensive management tools:

**User Management:**
- View all registered users with detailed profiles
- Edit user information and roles
- Suspend or ban accounts for policy violations
- Monitor user activity and engagement metrics

**Place Verification:**
- Review submitted verification documents
- Approve or reject place listings
- Upgrade verification levels based on performance
- Monitor listing quality and compliance

**Analytics and Reporting:**
- Total bookings and revenue metrics
- Active user statistics
- Popular locations and trending searches
- Geographic distribution analysis
- Revenue forecasting and trends

**Dispute Resolution:**
- Handle customer complaints efficiently
- Process refund requests
- Mediate provider-customer conflicts
- Maintain transaction logs for audit

### Additional Features

**Promotional System:**
- First-time user discount codes (5% default)
- Referral program with credit rewards
- Seasonal promotional campaigns
- Provider-specific discount offerings

**Multi-Language Support:**
- English and Urdu language options
- Right-to-left (RTL) text support for Urdu
- Expandable framework for additional languages
- Language-specific content management

**Responsive Design:**
- Mobile-first development approach
- Optimized for all screen sizes
- Progressive Web App (PWA) capabilities
- Cross-browser compatibility

## Technology Stack

### Frontend Technologies

**Core Framework:**
- React.js 18.2.0 - Component-based UI library
- React Router 6.16.0 - Client-side routing and navigation
- React Hook Form 7.46.2 - Form state management and validation

**Styling and UI:**
- Tailwind CSS 3.3.3 - Utility-first CSS framework
- Lucide React 0.279.0 - Icon component library
- Custom CSS animations and transitions

**State Management:**
- React Context API - Global state management
- Custom hooks - Reusable stateful logic

**HTTP Communication:**
- Axios 1.5.0 - Promise-based HTTP client
- API service layer architecture

**Utilities:**
- date-fns 2.30.0 - Date manipulation and formatting
- React Toastify 9.1.3 - Toast notification system

### Backend Technologies

**Runtime and Framework:**
- Node.js 18.x - JavaScript runtime environment
- Express.js 4.18.2 - Web application framework
- Middleware architecture for request processing

**Database:**
- MongoDB 6.0 - NoSQL document database
- Mongoose 7.5.0 - Object Data Modeling (ODM) library

**Authentication and Security:**
- jsonwebtoken 9.0.2 - JWT token generation and verification
- bcryptjs 2.4.3 - Password hashing with salt
- Helmet 7.0.0 - Security headers middleware
- Express Rate Limit 6.10.0 - Rate limiting for API endpoints

**File Handling:**
- Multer 1.4.5 - Multipart form data handling
- File type validation and size limits

**Communication:**
- Nodemailer 6.9.5 - Email service integration
- Socket.io (planned) - Real-time messaging

**Validation:**
- Express Validator 7.0.1 - Request validation middleware

**Performance:**
- Compression 1.7.4 - Response compression middleware

### Development Tools

**Code Quality:**
- ESLint 8.50.0 - Code linting and style enforcement
- Prettier 3.0.3 - Code formatting

**Testing:**
- Jest 29.7.0 - JavaScript testing framework (planned)

**Development Server:**
- Nodemon 3.0.1 - Automatic server restart on file changes

**API Testing:**
- Postman - API endpoint testing and documentation

**Database Management:**
- MongoDB Compass - Visual database management

**Version Control:**
- Git - Version control system
- GitHub - Repository hosting and collaboration

## System Architecture

### High-Level Architecture

The application follows a three-tier architecture pattern:

**Presentation Layer (Frontend):**
- React-based single-page application
- Component-based architecture with reusable UI elements
- Client-side routing and state management
- Responsive design implementation

**Application Layer (Backend):**
- RESTful API built with Express.js
- Middleware-based request processing
- Business logic implementation
- Authentication and authorization handling

**Data Layer (Database):**
- MongoDB document storage
- Mongoose schema definitions
- Data validation and relationships
- Index optimization for query performance

### Component Architecture

**Frontend Component Hierarchy:**

```
App
├── Layout Components
│   ├── Navbar
│   ├── Footer
│   └── Sidebar
├── Page Components
│   ├── Home
│   ├── Dashboard
│   ├── PlaceListing
│   ├── PlaceDetails
│   ├── Booking
│   └── Profile
├── Feature Components
│   ├── SearchBar
│   ├── PlaceCard
│   ├── BookingCard
│   └── ReviewCard
└── Common Components
    ├── Button
    ├── Input
    ├── Modal
    └── Loading
```

**Backend Service Architecture:**

```
Server
├── Routes Layer
│   ├── Authentication Routes
│   ├── Place Routes
│   ├── Booking Routes
│   └── Review Routes
├── Controller Layer
│   ├── Request validation
│   ├── Business logic coordination
│   └── Response formatting
├── Service Layer
│   ├── Database operations
│   ├── External API integration
│   └── Business logic implementation
└── Data Access Layer
    ├── Mongoose models
    └── Database queries
```

### Request Flow

1. Client sends HTTP request to backend API
2. Request passes through middleware chain (CORS, authentication, validation)
3. Router directs request to appropriate controller
4. Controller invokes service layer for business logic
5. Service layer interacts with database through Mongoose models
6. Response travels back through the layers to client
7. Client updates UI based on response data

## Installation Guide

### Prerequisites

Before beginning installation, ensure the following software is installed on your system:

- Node.js version 18.0.0 or higher
- npm (Node Package Manager) version 8.0.0 or higher
- MongoDB version 6.0 or higher
- Git version control system
- A modern code editor (Visual Studio Code recommended)

### Step 1: Repository Setup

Clone the repository and navigate to the project directory:

```bash
git clone https://github.com/yourusername/jagabook.git
cd jagabook
```

### Step 2: Backend Configuration

Navigate to the backend directory and install dependencies:

```bash
cd backend
npm install
```

Create environment configuration file:

```bash
cp .env.example .env
```

Configure environment variables in the .env file:

```env
# Server Configuration
PORT=5000
NODE_ENV=development

# Database Configuration
MONGODB_URI=mongodb://localhost:27017/jagabook

# JWT Configuration
JWT_SECRET=your_secure_jwt_secret_key_minimum_32_characters
JWT_EXPIRE=7d

# Email Configuration
EMAIL_HOST=smtp.gmail.com
EMAIL_PORT=587
EMAIL_USER=your_email@gmail.com
EMAIL_PASSWORD=your_app_specific_password
EMAIL_FROM=noreply@jagabook.com

# File Upload Configuration
MAX_FILE_SIZE=5242880
UPLOAD_PATH=./uploads

# Payment Gateway Configuration (Demo)
PAYMENT_API_KEY=demo_key
PAYMENT_SECRET=demo_secret

# Frontend URL
CLIENT_URL=http://localhost:3000

# Rate Limiting
RATE_LIMIT_WINDOW_MS=900000
RATE_LIMIT_MAX_REQUESTS=100
```

### Step 3: Database Setup

Ensure MongoDB is running on your system. Start the MongoDB service:

**Linux/Mac:**
```bash
sudo systemctl start mongod
```

**Windows:**
MongoDB should start automatically as a service. If not, start it manually from Services.

Optionally, seed the database with sample data:

```bash
npm run seed
```

### Step 4: Frontend Configuration

Open a new terminal window and navigate to the frontend directory:

```bash
cd frontend
npm install
```

Create environment configuration file:

```bash
cp .env.example .env
```

Configure frontend environment variables:

```env
# API Configuration
REACT_APP_API_URL=http://localhost:5000/api

# Application Configuration
REACT_APP_NAME=JagaBook
REACT_APP_VERSION=1.0.0

# Google Maps API (Optional)
REACT_APP_GOOGLE_MAPS_KEY=your_google_maps_api_key
```

### Step 5: Running the Application

**Start Backend Server:**

In the backend directory:

```bash
npm run dev
```

The server will start on http://localhost:5000

Verify the server is running by visiting: http://localhost:5000/api/health

**Start Frontend Development Server:**

In the frontend directory:

```bash
npm start
```

The application will open automatically in your default browser at http://localhost:3000

### Step 6: Verification

**Test Backend Endpoints:**

Use Postman or curl to test the health check endpoint:

```bash
curl http://localhost:5000/api/health
```

Expected response:
```json
{
  "success": true,
  "message": "JagaBook API is running",
  "timestamp": "2024-12-18T10:30:00.000Z"
}
```

**Test Frontend:**

Navigate to http://localhost:3000 and verify the landing page loads correctly.

### Default Demo Accounts

After seeding the database, the following demo accounts are available:

**Customer Account:**
```
Email: customer@jagabook.com
Password: demo123
```

**Place Provider Account (Level 1 Verified):**
```
Email: provider@jagabook.com
Password: demo123
```

**Administrator Account:**
```
Email: admin@jagabook.com
Password: admin123
```

### Troubleshooting

**Port Already in Use:**
```bash
# Find and kill process using port 5000
lsof -ti:5000 | xargs kill -9

# Or change PORT in .env file
PORT=5001
```

**MongoDB Connection Error:**
```bash
# Verify MongoDB is running
sudo systemctl status mongod

# Check MongoDB logs
tail -f /var/log/mongodb/mongod.log
```

**Module Not Found Error:**
```bash
# Delete node_modules and reinstall
rm -rf node_modules package-lock.json
npm install
```

## Project Structure

```
jagabook/
│
├── frontend/
│   ├── public/
│   │   ├── index.html
│   │   ├── favicon.ico
│   │   └── manifest.json
│   │
│   ├── src/
│   │   ├── components/
│   │   │   ├── layout/
│   │   │   │   ├── Navbar.jsx
│   │   │   │   ├── Footer.jsx
│   │   │   │   └── Sidebar.jsx
│   │   │   │
│   │   │   ├── common/
│   │   │   │   ├── Button.jsx
│   │   │   │   ├── Input.jsx
│   │   │   │   ├── Card.jsx
│   │   │   │   ├── Modal.jsx
│   │   │   │   └── Loading.jsx
│   │   │   │
│   │   │   └── features/
│   │   │       ├── PlaceCard.jsx
│   │   │       ├── SearchBar.jsx
│   │   │       ├── BookingCard.jsx
│   │   │       └── ReviewCard.jsx
│   │   │
│   │   ├── pages/
│   │   │   ├── Home.jsx
│   │   │   ├── Dashboard.jsx
│   │   │   ├── PlaceListing.jsx
│   │   │   ├── PlaceDetails.jsx
│   │   │   ├── Booking.jsx
│   │   │   ├── Profile.jsx
│   │   │   └── NotFound.jsx
│   │   │
│   │   ├── context/
│   │   │   ├── AuthContext.jsx
│   │   │   └── BookingContext.jsx
│   │   │
│   │   ├── hooks/
│   │   │   ├── useAuth.js
│   │   │   ├── useBooking.js
│   │   │   └── usePlaces.js
│   │   │
│   │   ├── services/
│   │   │   ├── api.js
│   │   │   ├── authService.js
│   │   │   ├── placeService.js
│   │   │   └── bookingService.js
│   │   │
│   │   ├── utils/
│   │   │   ├── validation.js
│   │   │   ├── formatters.js
│   │   │   └── constants.js
│   │   │
│   │   ├── App.jsx
│   │   ├── index.js
│   │   └── index.css
│   │
│   ├── package.json
│   ├── tailwind.config.js
│   └── .env.example
│
├── backend/
│   ├── src/
│   │   ├── config/
│   │   │   ├── database.js
│   │   │   └── constants.js
│   │   │
│   │   ├── models/
│   │   │   ├── User.js
│   │   │   ├── Place.js
│   │   │   ├── Booking.js
│   │   │   └── Review.js
│   │   │
│   │   ├── controllers/
│   │   │   ├── authController.js
│   │   │   ├── placeController.js
│   │   │   ├── bookingController.js
│   │   │   └── reviewController.js
│   │   │
│   │   ├── middleware/
│   │   │   ├── auth.js
│   │   │   ├── validation.js
│   │   │   ├── errorHandler.js
│   │   │   └── upload.js
│   │   │
│   │   ├── routes/
│   │   │   ├── authRoutes.js
│   │   │   ├── placeRoutes.js
│   │   │   ├── bookingRoutes.js
│   │   │   └── reviewRoutes.js
│   │   │
│   │   ├── services/
│   │   │   ├── emailService.js
│   │   │   ├── paymentService.js
│   │   │   └── notificationService.js
│   │   │
│   │   ├── utils/
│   │   │   ├── jwt.js
│   │   │   └── fileUpload.js
│   │   │
│   │   └── server.js
│   │
│   ├── uploads/
│   │   └── .gitkeep
│   │
│   ├── tests/
│   │   ├── unit/
│   │   └── integration/
│   │
│   ├── package.json
│   └── .env.example
│
├── docs/
│   ├── API.md
│   ├── DEPLOYMENT.md
│   └── CONTRIBUTING.md
│
├── .gitignore
├── README.md
└── LICENSE
```

## API Documentation

### Base URL

```
http://localhost:5000/api
```

### Authentication Endpoints

#### Register New User

**Endpoint:** `POST /api/auth/register`

**Request Body:**
```json
{
  "name": "John Doe",
  "email": "john@example.com",
  "password": "securePassword123",
  "role": "customer",
  "phone": "+923001234567"
}
```

**Response (201 Created):**
```json
{
  "success": true,
  "message": "Registration successful. Please verify your email.",
  "user": {
    "id": "64abc123def456789",
    "name": "John Doe",
    "email": "john@example.com",
    "role": "customer",
    "verified": false
  },
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9..."
}
```

#### User Login

**Endpoint:** `POST /api/auth/login`

**Request Body:**
```json
{
  "email": "john@example.com",
  "password": "securePassword123"
}
```

**Response (200 OK):**
```json
{
  "success": true,
  "user": {
    "id": "64abc123def456789",
    "name": "John Doe",
    "email": "john@example.com",
    "role": "customer",
    "verified": true
  },
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9..."
}
```

#### Get Current User

**Endpoint:** `GET /api/auth/me`

**Headers:**
```
Authorization: Bearer {token}
```

**Response (200 OK):**
```json
{
  "success": true,
  "user": {
    "id": "64abc123def456789",
    "name": "John Doe",
    "email": "john@example.com",
    "role": "customer",
    "verified": true,
    "createdAt": "2024-01-15T10:30:00.000Z"
  }
}
```

### Place Endpoints

#### Get All Places

**Endpoint:** `GET /api/places`

**Query Parameters:**
- `city` (optional): Filter by city
- `minPrice` (optional): Minimum price filter
- `maxPrice` (optional): Maximum price filter
- `shootType` (optional): Filter by shoot type
- `page` (optional): Page number for pagination
- `limit` (optional): Results per page

**Example Request:**
```
GET /api/places?city=Lahore&minPrice=10000&maxPrice=50000&shootType=wedding&page=1&limit=10
```

**Response (200 OK):**
```json
{
  "success": true,
  "count": 15,
  "pagination": {
    "page": 1,
    "limit": 10,
    "total": 15,
    "pages": 2
  },
  "data": [
    {
      "id": "64def789abc123456",
      "name": "Royal Garden Villa",
      "description": "Beautiful garden with fountain...",
      "location": {
        "city": "Lahore",
        "area": "DHA Phase 5",
        "address": "123 Main Boulevard"
      },
      "pricing": {
        "basePrice": 25000,
        "weekendPrice": 30000
      },
      "images": ["url1", "url2", "url3"],
      "verificationLevel": 1,
      "stats": {
        "averageRating": 4.8,
        "totalBookings": 45
      }
    }
  ]
}
```

#### Get Single Place

**Endpoint:** `GET /api/places/:id`

**Response (200 OK):**
```json
{
  "success": true,
  "data": {
    "id": "64def789abc123456",
    "name": "Royal Garden Villa",
    "description": "Beautiful garden with fountain...",
    "location": {
      "city": "Lahore",
      "area": "DHA Phase 5",
      "address": "123 Main Boulevard",
      "coordinates": {
        "lat": 31.4697,
        "lng": 74.2728
      }
    },
    "pricing": {
      "basePrice": 25000,
      "weekendPrice": 30000,
      "shootTypes": [
        {
          "type": "wedding",
          "price": 30000
        },
        {
          "type": "fashion",
          "price": 20000
        }
      ]
    },
    "amenities": ["parking", "wifi", "restroom", "ac"],
    "capacity": 50,
    "verificationLevel": 1,
    "status": "active"
  }
}
```

#### Create Place (Provider Only)

**Endpoint:** `POST /api/places`

**Headers:**
```
Authorization: Bearer {token}
Content-Type: multipart/form-data
```

**Request Body (FormData):**
```
name: Royal Garden Villa
description: Beautiful garden with fountain...
city: Lahore
area: DHA Phase 5
address: 123 Main Boulevard
basePrice: 25000
images: [file1, file2, file3]
amenities: ["parking", "wifi", "restroom"]
```

**Response (201 Created):**
```json
{
  "success": true,
  "message": "Place created successfully",
  "data": {
    "id": "64def789abc123456",
    "name": "Royal Garden Villa",
    "status": "pending"
  }
}
```

### Booking Endpoints

#### Create Booking

**Endpoint:** `POST /api/bookings`

**Headers:**
```
Authorization: Bearer {token}
Content-Type: application/json
```

**Request Body:**
```json
{
  "placeId": "64def789abc123456",
  "bookingDate": "2024-12-25",
  "shootType": "wedding",
  "specialRequests": "Need makeup room access"
}
```

**Response (201 Created):**
```json
{
  "success": true,
  "message": "Booking request sent successfully",
  "booking": {
    "id": "64xyz123abc456789",
    "placeId": "64def789abc123456",
    "bookingDate": "2024-12-25",
    "status": "pending",
    "pricing": {
      "baseAmount": 25000,
      "platformFee": 2500,
      "totalAmount": 27500,
      "advanceRequired": 1375
    }
  },
  "paymentUrl": "http://localhost:3000/payment/64xyz123abc456789"
}
```

#### Get My Bookings

**Endpoint:** `GET /api/bookings/my-bookings`

**Headers:**
```
Authorization: Bearer {token}
```

**Response (200 OK):**
```json
{
  "success": true,
  "bookings": [
    {
      "id": "64xyz123abc456789",
      "place": {
        "name": "Royal Garden Villa",
        "location": "Lahore, DHA Phase 5"
      },
      "bookingDate": "2024-12-25",
      "status": "confirmed",
      "totalAmount": 27500,
      "advancePaid": 1375
    }
  ]
}
```

### Review Endpoints

#### Create Review

**Endpoint:** `POST /api/reviews`

**Headers:**
```
Authorization: Bearer {token}
Content-Type: application/json
```

**Request Body:**
```json
{
  "bookingId": "64xyz123abc456789",
  "ratings": {
    "location": 5,
    "responsiveness": 4,
    "valueForMoney": 5,
    "cleanliness": 5
  },
  "comment": "Excellent location! Highly recommended for wedding shoots."
}
```

**Response (201 Created):**
```json
{
  "success": true,
  "message": "Review submitted successfully",
  "review": {
    "id": "64review123456789",
    "overallRating": 4.75,
    "verified": true,
    "createdAt": "2024-12-26T10:00:00.000Z"
  }
}
```

### Error Responses

All endpoints follow a consistent error response format:

**400 Bad Request:**
```json
{
  "success": false,
  "message": "Validation error",
  "errors": [
    "Email is required",
    "Password must be at least 6 characters"
  ]
}
```

**401 Unauthorized:**
```json
{
  "success": false,
  "message": "Not authorized to access this route"
}
```

**404 Not Found:**
```json
{
  "success": false,
  "message": "Resource not found"
}
```

**500 Internal Server Error:**
```json
{
  "success": false,
  "message": "Server error",
  "error": "Error details (only in development mode)"
}
```

## User Roles and Permissions

### Customer Role

**Allowed Operations:**
- Register and authenticate on the platform
- Search and browse available photoshoot locations
- Filter places by various criteria
- Save places to personal wishlist
- Create booking requests for desired locations
- Make advance and full payments through platform
- Communicate with providers after booking confirmation
- View complete booking history
- Write reviews after completed bookings
- Update personal profile information

**Restricted Operations:**
- Cannot list or manage places
- Cannot access provider-specific dashboard features
- Cannot view other customers' private information
- Cannot approve or reject bookings
- Cannot access administrative functions

### Place Provider Role

**Allowed Operations:**
- All customer role permissions
- Create and list multiple photoshoot locations
- Upload multiple images per location
- Set and update pricing structures
- Manage location availability calendar
- Accept or reject incoming booking requests
- View detailed booking information
- Communicate with customers through platform
- Access earnings and analytics dashboard
- Respond to customer reviews
- Update listing information in real-time
- Submit verification documents

**Restricted Operations:**
- Cannot modify other providers' listings
- Cannot delete verified customer reviews
- Cannot access administrative controls
- Cannot view other providers' financial information

### Photographer Role

Currently, photographers have the same permissions as customers. Future updates may include:

**Planned Features:**
- Access to photographer-specific search filters
- Ability to create photographer profiles
- Portfolio showcase capabilities