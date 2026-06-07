# Chunchim Restaurant - Full Stack Application

A comprehensive restaurant management system with customer portal and admin dashboard, powered by AI Agent.

## 🎯 Project Overview

**Name**: Chunchim Restaurant Management System  
**Type**: Full-stack Web Application  
**Features**: Online ordering, table reservation, AI-powered recommendations, admin panel

### Key Features

#### 👥 Customer Side
- Browse Thai restaurant menu
- Reserve table with date/time
- Place orders (Dine-in / Takeaway)
- Special food requests (no spicy, extra salt, etc.)
- AI assistant for recommendations
- Order tracking
- Payment options
- User profile & history

#### 👨‍💼 Admin Side
- Login authentication
- Menu management (Add/Edit/Delete items)
- Upload menu item images
- Manage food categories
- Check order backlog
- Order status management
- View customer orders
- AI assistant for inventory insights

#### 🤖 AI Agent Features
- **Customer**: Menu recommendations based on preferences
- **Admin**: Inventory optimization suggestions
- **Both**: General Q&A about restaurant

---

## 🏗️ Architecture

### Technology Stack

**Backend**:
- Node.js + Express.js (REST API)
- MongoDB (Database)
- JWT (Authentication)
- OpenAI API (AI Agent)
- Mongoose (ODM)
- bcryptjs (Password hashing)

**Frontend**:
- React.js or Vue.js
- Tailwind CSS or Material-UI (Styling)
- Axios (HTTP client)
- React Router (Navigation)
- Zustand/Redux (State management)

---

## 📁 Project Structure

```
restaurant-system/
├── backend/
│   ├── config/
│   │   └── database.js          # MongoDB connection
│   ├── controllers/
│   │   ├── authController.js    # User auth logic
│   │   ├── menuController.js    # Menu CRUD
│   │   ├── orderController.js   # Order management
│   │   └── aiController.js      # AI interactions
│   ├── middleware/
│   │   ├── auth.js              # JWT verification
│   │   ├── errorHandler.js      # Error handling
│   │   └── validation.js        # Input validation
│   ├── models/
│   │   ├── User.js              # User schema
│   │   ├── MenuItem.js          # Menu items
│   │   ├── Order.js             # Orders
│   │   ├── Table.js             # Table management
│   │   └── Reservation.js       # Reservations
│   ├── routes/
│   │   ├── authRoutes.js        # Auth endpoints
│   │   ├── menuRoutes.js        # Menu endpoints
│   │   ├── orderRoutes.js       # Order endpoints
│   │   ├── aiRoutes.js          # AI endpoints
│   │   └── testRoutes.js        # Test endpoints
│   ├── services/
│   │   └── aiService.js         # OpenAI integration
│   ├── .env.example
│   ├── server.js                # Entry point
│   ├── package.json
│   └── README.md
│
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   │   ├── auth/            # Login, Register
│   │   │   ├── menu/            # Menu display
│   │   │   ├── orders/          # Order pages
│   │   │   ├── admin/           # Admin panel
│   │   │   └── common/          # Shared components
│   │   ├── pages/
│   │   │   ├── HomePage.jsx
│   │   │   ├── LoginPage.jsx
│   │   │   ├── MenuPage.jsx
│   │   │   ├── CheckoutPage.jsx
│   │   │   ├── AdminDashboard.jsx
│   ��   │   └── NotFound.jsx
│   │   ├── services/
│   │   │   └── api.js           # API calls
│   │   ├── store/
│   │   │   └── authStore.js     # State management
│   │   ├── App.jsx
│   │   └── index.css
│   ├── package.json
│   └── README.md
│
├── docs/
│   ├── requirements/
│   │   ├── DFD.md               # Data Flow Diagrams
│   │   ├── UseCase.md           # Use case diagrams
│   │   └── UserRequirements.md  # Requirements analysis
│   ├── feasibility/
│   │   ├── Technical.md
│   │   ├── Economic.md
│   │   ├── Operational.md
│   │   └── Legal.md
│   ├── design/
│   │   ├── Architecture.md
│   │   ├── Database.md
│   │   └── API.md
│   └── presentation/
│       └── slides.pptx          # PowerPoint presentation
│
├── README.md
└── .gitignore
```

---

## 🚀 Getting Started

### Prerequisites
- Node.js v18+
- MongoDB local or Atlas
- OpenAI API key
- Git

### Backend Setup

```bash
cd backend
npm install

# Create .env file
cp .env.example .env

# Update .env with:
# - OPENAI_API_KEY
# - DB_URL
# - JWT_SECRET

npm start           # or npm run dev
# Server runs on http://localhost:5000
```

### Frontend Setup

```bash
cd frontend
npm install

# Create .env file
REACT_APP_API_URL=http://localhost:5000/api

npm start
# App runs on http://localhost:3000
```

---

## 📊 Database Schema

### Users
- id, name, email, phone, password, role, preferences

### Menu Items
- id, name, description, category, price, image, spiceLevel, rating

### Orders
- id, orderNumber, customer, items[], orderType, status, totalAmount

### Tables
- id, tableNumber, capacity, status, currentOrder

### Reservations
- id, customer, table, reservationDate, status

---

## 🔐 Authentication Flow

1. User registers/logs in
2. Backend validates credentials
3. JWT token generated
4. Token stored in localStorage (frontend)
5. Token included in API requests (Authorization header)
6. Protected routes check token validity

---

## 🤖 AI Integration

### Menu Recommendations
**Request**:
```json
{
  "preferences": {
    "spiceLevel": "mild",
    "dietary": "vegetarian",
    "budget": "moderate"
  }
}
```

**Response**: AI recommends 3 suitable menu items

### Ask Question
**Request**:
```json
{
  "question": "Do you have vegetarian options?"
}
```

**Response**: AI answers about restaurant offerings

---

## ✅ API Testing

Use Postman or curl to test endpoints:

```bash
# Register
curl -X POST http://localhost:5000/api/auth/register \
  -H "Content-Type: application/json" \
  -d '{"name":"John","email":"john@test.com","phone":"0123456789","password":"pass123"}'

# Login
curl -X POST http://localhost:5000/api/auth/login \
  -H "Content-Type: application/json" \
  -d '{"email":"john@test.com","password":"pass123"}'

# Get Menu
curl http://localhost:5000/api/menu

# Create Order (requires token)
curl -X POST http://localhost:5000/api/orders \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -d '{"items":[{"menuItem":"id","quantity":2}],"orderType":"dine-in","tableNumber":5}'
```

---

## 📋 Deliverables

### Code
- ✅ Complete backend API
- ✅ Frontend web application
- ✅ Database models
- ✅ AI integration
- ✅ Authentication system

### Documentation (30+ pages)
- Project Overview & Requirements
- Feasibility Analysis
- Data Flow Diagrams (DFD)
- Use Case Diagrams
- System Architecture
- Database Schema
- API Documentation
- Implementation details
- Testing & Results

### Presentation
- PowerPoint slides
- Live demo
- System walkthrough

---

## 👥 Team Roles

- **Dandelia-04**: Backend Development + AI Integration
- **nicetymikety**: Frontend Development + Documentation + Presentation

---

## 🔗 Useful Links

- [Backend README](./backend/README.md)
- [Frontend README](./frontend/README.md)
- [API Documentation](./docs/design/API.md)
- [Database Design](./docs/design/Database.md)

---

**Status**: 🚀 In Development  
**Last Updated**: 2026-06-07  
**Version**: 1.0.0
