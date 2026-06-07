# Chunchim Restaurant - Backend API

Professional backend service for Chunchim Thai Restaurant Management System with AI Agent integration.

## 🚀 Quick Start

### Prerequisites
- Node.js (v18+)
- MongoDB
- OpenAI API Key

### Installation

1. Install dependencies:
```bash
npm install
```

2. Setup environment variables:
```bash
cp .env.example .env
```

3. Update `.env` with your values:
```
OPENAI_API_KEY=your_key_here
DB_URL=mongodb://localhost:27017/chunchim-restaurant
JWT_SECRET=your_secret_key
```

4. Start server:
```bash
npm start          # Production
npm run dev        # Development with nodemon
```

## 📚 API Endpoints

### Authentication
- `POST /api/auth/register` - Register new user
- `POST /api/auth/login` - User login
- `GET /api/auth/profile` - Get user profile

### Menu Management
- `GET /api/menu` - Get all menu items
- `GET /api/menu/:id` - Get menu item details
- `POST /api/menu` - Create menu item (Admin)
- `PUT /api/menu/:id` - Update menu item (Admin)
- `DELETE /api/menu/:id` - Delete menu item (Admin)
- `POST /api/menu/:id/reviews` - Add review to item

### Orders
- `POST /api/orders` - Create new order
- `GET /api/orders/my-orders` - Get customer's orders
- `GET /api/orders/:id` - Get order details
- `GET /api/orders` - Get all orders (Admin)
- `PUT /api/orders/:id/status` - Update order status (Admin)

### AI Agent
- `POST /api/ai/recommendation` - Get menu recommendations
- `POST /api/ai/ask` - Ask AI assistant
- `POST /api/ai/inventory-insights` - Get inventory suggestions (Admin)

## 📦 Project Structure

```
backend/
├── config/             # Database configuration
├── controllers/        # Business logic
├── middleware/         # Express middleware
├── models/            # MongoDB schemas
├── routes/            # API routes
├── services/          # External services (AI)
├── server.js          # Entry point
└── package.json
```

## 🤖 AI Agent Features

- **Menu Recommendations** - Personalized recommendations based on preferences
- **Customer Support** - Answer restaurant questions
- **Inventory Optimization** - Suggest stock management improvements

## 🔐 Authentication

Uses JWT tokens. Include in request headers:
```
Authorization: Bearer <token>
```

## 👥 User Roles

- **Customer** - Place orders, view menu, add reviews
- **Admin** - Manage menu, orders, view analytics

## 🚀 Development

### Environment Variables

See `.env.example` for all available options.

### Database Setup

Uses MongoDB with Mongoose ODM. Ensure MongoDB is running.

### Testing

```bash
# Manual testing with Postman/curl
# Or implement test suite
npm test
```

## 📝 Features

✅ User authentication (JWT)
✅ Menu management with categories
✅ Order tracking system
✅ Table management
✅ Reservation system
✅ AI Agent integration
✅ Review system
✅ Admin dashboard endpoints
✅ Order status updates
✅ Error handling & validation

## 🔧 Configuration

All configuration via environment variables in `.env`

## 📞 Support

For issues or questions, please check the documentation or contact the development team.

---

**Status**: ✅ Production Ready
**Version**: 1.0.0
