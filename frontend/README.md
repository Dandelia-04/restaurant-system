# Frontend - Chunchim Restaurant

Modern, responsive web application for Chunchim Thai Restaurant built with React.

## 🎨 Features

### Customer Pages
- 🏠 **Home/Menu Page** - Browse beautiful Thai menu
- 👤 **Authentication** - Login & Registration
- 🛒 **Order Page** - Select items, add special requests
- 📍 **Checkout** - Choose dine-in/takeaway, payment
- 📅 **Reservation** - Book table with date/time
- 🤖 **AI Assistant** - Get menu recommendations
- 📱 **User Profile** - View order history

### Admin Pages
- 🔐 **Admin Login**
- 📊 **Dashboard** - Overview & statistics
- 🍽️ **Menu Management**
  - Add new menu items
  - Upload images
  - Set prices & categories
  - Update availability
  - Delete items
- 📋 **Order Management**
  - View all orders
  - Update order status
  - Check order backlog
- 🤖 **AI Assistant** - Inventory insights

## 🛠️ Tech Stack

- **React 18** - UI library
- **React Router v6** - Navigation
- **Tailwind CSS** - Styling (or Material-UI)
- **Axios** - HTTP requests
- **Zustand/Redux** - State management
- **React Hook Form** - Form handling
- **React Toastify** - Notifications

## 📦 Installation

```bash
# Create React app
npm create vite@latest . -- --template react

# Or if using Create React App
npx create-react-app .

# Install dependencies
npm install

# Install additional packages
npm install axios react-router-dom zustand react-hook-form react-toastify tailwindcss
npm install -D nodemon
```

## 🗂️ Project Structure

```
frontend/
├── src/
│   ├── components/
│   │   ├── Layout/
│   │   │   ├── Navbar.jsx
│   │   │   ├── Sidebar.jsx
│   │   │   ├── Footer.jsx
│   │   │   └── Layout.jsx
│   │   │
│   │   ├── auth/
│   │   │   ├── LoginForm.jsx
│   │   │   ├── RegisterForm.jsx
│   │   │   └── ProtectedRoute.jsx
│   │   │
│   │   ├── menu/
│   │   │   ├── MenuCard.jsx
│   │   │   ├── MenuFilter.jsx
│   │   │   ├── MenuGrid.jsx
│   │   │   └── MenuDetail.jsx
│   │   │
│   │   ├── orders/
│   │   │   ├── CartItem.jsx
│   │   │   ├── Cart.jsx
│   │   │   ├── OrderForm.jsx
��   │   │   ├── OrderStatus.jsx
│   │   │   └── OrderHistory.jsx
│   │   │
│   │   ├── admin/
│   │   │   ├── AdminSidebar.jsx
│   │   │   ├── Dashboard.jsx
│   │   │   ├── MenuManager.jsx
│   │   │   ├── OrderManager.jsx
│   │   │   ├── AddMenuItem.jsx
│   │   │   └── EditMenuItem.jsx
│   │   │
│   │   ├── ai/
│   │   │   ├── AIAssistant.jsx
│   │   │   ├── ChatBox.jsx
│   │   │   └── Recommendations.jsx
│   │   │
│   │   └── common/
│   │       ├── Button.jsx
│   │       ├── Card.jsx
│   │       ├── Modal.jsx
│   │       ├── Loading.jsx
│   │       └── ErrorBoundary.jsx
│   │
│   ├── pages/
│   │   ├── HomePage.jsx
│   │   ├── MenuPage.jsx
│   │   ├── CartPage.jsx
│   │   ├── CheckoutPage.jsx
│   │   ├── ReservationPage.jsx
│   │   ├── OrderTrackingPage.jsx
│   │   ├── ProfilePage.jsx
│   │   ├── AdminDashboardPage.jsx
│   │   ├── AdminMenuPage.jsx
│   │   ├── AdminOrderPage.jsx
│   │   ├── LoginPage.jsx
│   │   ├── RegisterPage.jsx
│   │   └── NotFoundPage.jsx
│   │
│   ├── services/
│   │   ├── api.js              # Axios instance
│   │   ├── authService.js
│   │   ├── menuService.js
│   │   ├── orderService.js
│   │   ├── reservationService.js
│   │   └── aiService.js
│   │
│   ├── store/
│   │   ├── authStore.js        # Zustand auth store
│   │   ├── cartStore.js        # Cart state
│   │   └── uiStore.js          # UI state (theme, modals)
│   │
│   ├── styles/
│   │   ├── global.css
│   │   ├── variables.css
│   │   └── themes.css
│   │
│   ├── utils/
│   │   ├── formatters.js       # Format dates, prices
│   │   ├── validators.js       # Form validation
│   │   └── constants.js        # App constants
│   │
│   ├── hooks/
│   │   ├── useAuth.js
│   │   ├── useFetch.js
│   │   └── useForm.js
│   │
│   ├── App.jsx
│   └── main.jsx
│
├── public/
│   └── images/
│       └── (menu item images)
│
├── .env
├── .env.example
├── vite.config.js
├── tailwind.config.js
├── package.json
└── README.md
```

## 🚀 Getting Started

### 1. Environment Setup
```bash
cp .env.example .env
```

Update `.env`:
```
VITE_API_URL=http://localhost:5000/api
VITE_APP_NAME=Chunchim Restaurant
```

### 2. Start Development
```bash
npm run dev
```

### 3. Build for Production
```bash
npm run build
npm run preview
```

## 📝 Key Components

### Navbar
- Logo & restaurant name
- Menu links (Home, Menu, About)
- Cart icon with badge
- User profile dropdown
- Login/Register buttons

### Menu Display
- Filter by category
- Search functionality
- Star ratings
- Price display
- Add to cart button

### Cart & Checkout
- Cart items with quantity
- Special requests input
- Order type selection (dine-in/takeaway)
- Payment method selection
- Subtotal, tax, total

### Admin Menu Manager
- Add item form (name, category, price, image)
- Edit existing items
- Delete items
- Image upload

### Admin Order Manager
- View all orders
- Filter by status
- Update order status
- Customer details view

### AI Assistant
- Chat interface
- Menu recommendations
- Q&A about restaurant
- Admin: inventory insights

## 🎨 Design Guidelines

### Colors (Thai Theme)
- Primary: `#D4692E` (Warm Orange)
- Secondary: `#2D5016` (Thai Green)
- Accent: `#FFD700` (Gold)
- Background: `#FFF8F3` (Warm White)
- Text: `#333333` (Dark Gray)

### Typography
- Headings: Bold, Large
- Body: Regular, Medium
- Accent: Gold/Orange

### Layout
- Mobile-first responsive
- Padding: 16px
- Border-radius: 8px
- Shadows: Subtle

## 🔒 Protected Routes

```
/                    - Public (Home)
/menu                - Public (Browse menu)
/cart                - Private (Customer)
/checkout            - Private (Customer)
/orders              - Private (Customer)
/profile             - Private (Customer)
/admin/*             - Private (Admin only)
/login               - Public
/register            - Public
```

## 🔐 Authentication

1. Login/Register page
2. Store JWT token in localStorage
3. Include token in all API requests
4. Validate token on protected routes
5. Auto-logout on token expiration

## 📱 Responsive Breakpoints

```
Mobile:  < 640px
Tablet:  640px - 1024px
Desktop: > 1024px
```

## 🧪 Testing

```bash
# Component testing
npm test

# E2E testing
npm run test:e2e
```

## 🚀 Deployment

### Vercel
```bash
npm install -g vercel
vercel
```

### Netlify
```bash
npm run build
# Upload dist/ folder
```

## 📞 API Integration

See backend README for API endpoints.

Example API call:
```javascript
import api from './services/api';

const getMenu = async () => {
  const response = await api.get('/menu');
  return response.data;
};
```

## ⚠️ Common Issues

**CORS Error**: Check CORS_ORIGIN in backend .env

**Images not loading**: Ensure image URLs are correct

**Token expired**: Redirect to login page

## 📚 Resources

- [React Documentation](https://react.dev)
- [Tailwind CSS](https://tailwindcss.com)
- [Axios](https://axios-http.com)
- [Zustand](https://github.com/pmndrs/zustand)

---

**Status**: Ready for Development 🚀  
**Version**: 1.0.0
