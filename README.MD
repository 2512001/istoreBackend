# 📦 iPhone Store — Backend (Node.js + Express + MongoDB)

This is the **backend REST API** for the iPhone Store E-commerce application.  
It provides **authentication, product management, cart, orders, payments, reviews, and admin analytics**.

Built using **Node.js, Express, MongoDB, Cloudinary & Razorpay**.

---

# 🚀 Features

### 👤 Authentication
- Register, Login, Logout
- JWT-based authentication (Access & Refresh Tokens)
- User profile fetch & update

### 📱 Product Management
- Get all products with filtering & pagination
- Get single product details
- Admin-protected: Create, Update & Delete products
- Cloudinary image uploads

### 🛒 Cart
- Add to cart
- Update quantity
- Remove cart items
- Fetch user cart

### 🧾 Orders & Payments
- Create order
- Razorpay payment integration
- Server-side payment signature verification
- Cancel orders

### 📊 Admin Panel APIs
- Revenue analytics
- Recent orders
- Low-stock alerts
- Top-selling products

---

# 🧭 Getting Started (Beginner-Friendly)

## 1️⃣ Prerequisites
Before running backend, install:

- **Node.js** v14 or higher  
- **npm** or **yarn**
- **MongoDB** (Local or Atlas)
- **Cloudinary Account**
- **Razorpay Test Account** (optional for development)

---

# 2️⃣ Installation & Setup

### 👉 Step 1: Clone Backend Repo
```bash
git https://github.com/2512001/istoreBackend.git
cd iphone-store-backend

👉 Step 2: Install dependencies
npm install

👉 Step 3: Create .env

Create .env file in root of backend folder and paste:

# Server
PORT=3000
NODE_ENV=development

# MongoDB
MONGODB_URI=mongodb://127.0.0.1:27017/iphone-store

# JWT Secrets
JWT_SECRET=your_jwt_secret
JWT_REFRESH_SECRET=your_refresh_jwt_secret
JWT_EXPIRES_IN=5h

# Cloudinary
CLOUDINARY_NAME=your_cloud_name
CLOUDINARY_API_KEY=your_api_key
CLOUDINARY_API_SECRET=your_api_secret

# Razorpay (Optional but recommended)
RAZORPAY_KEY_ID=rzp_test_xxxxxx
RAZORPAY_KEY_SECRET=your_razorpay_secret

# Admin Setup (optional)
ADMIN_SECRET=super_secret_key


📌 Do NOT commit .env file to GitHub!

👉 Step 4: Start Backend Server
Development (auto restart with nodemon)
npm run dev

Production
npm start

🌐 API Base URL
http://localhost:3000/api

📁 Backend Folder Structure
backend/
├── app.js              # Entry point
├── package.json
├── .env                # Environment vars (gitignored)
├── config/
│   ├── db.js           # MongoDB connection
│   └── cloudinary.js   # Cloudinary setup
├── controllers/        # Logic for auth, products, orders, cart, admin
├── middleware/         # Auth middleware, validators, error handler
├── models/             # Mongoose models (User, Product, Cart, Order)
├── routes/             # All API routes
├── utils/              # Helpers (JWT, payment verify)
└── scripts/            # Seed scripts / create admin

🔌 API Endpoints (Important)
🔐 Auth Routes
Method	Endpoint	Description
POST	/api/auth/register	Register
POST	/api/auth/login	Login
GET	/api/auth/profile	User profile (protected)
POST	/api/auth/logout	Logout
PUT	/api/auth/:id	Update user
📱 Product Routes
Method	Endpoint	Description
GET	/api/products	Get all products
GET	/api/products/:id	Product details
GET	/api/products/pageCount	Total pages
POST	/api/products	Create product (admin)
PUT	/api/products/:id	Update product (admin)
DELETE	/api/products/:id	Delete (admin)
🛒 Cart Routes
Method	Endpoint	Description
POST	/api/cart/	Add to cart
PATCH	/api/cart/:cartId	Update quantity/remove
GET	/api/cart/user/:userId	User cart
🧾 Order Routes
Method	Endpoint	Description
GET	/api/orders	Fetch user orders
POST	/api/orders	Create order (starts Razorpay)
POST	/api/orders/payment/verify	Verify payment
GET	/api/orders/:id	Get order by ID
PATCH	/api/orders/:id/cancel	Cancel order
🛠️ Admin Routes
Method	Endpoint	Description
GET	/api/admin/analytics	Revenue, stats
GET	/api/admin/low-stock	Low stock items
GET	/api/admin/recent-orders	Last orders
GET	/api/admin/topSellproduct	Top selling products
🧪 Create Sample Admin (Optional)

Add the script in scripts/ folder:

node scripts/createAdmin.js

🪲 Troubleshooting Guide
❌ MongoDB not connecting?

Check MONGODB_URI

Make sure MongoDB service is running or Atlas IP is whitelisted

❌ Cloudinary upload fails?

Wrong CLOUDINARY_* keys

Missing multer upload logic

❌ Razorpay signature invalid?

Ensure you're using correct RAZORPAY_KEY_SECRET

❌ CORS issue with frontend?

Add in app.js:

const cors = require("cors");
app.use(cors({ origin: "*" }));

❌ JWT errors?

Tokens expired → requires re-login

Missing Authorization: Bearer <token>

🤝 Contributing

Fork the repository

Create a feature branch

Commit changes

Push & create PR

📝 License

MIT License. See LICENSE for more details.

If you want, I can also generate:
✅ .env.example file
✅ Postman Collection for all APIs
✅ Seed Script (createAdmin.js, seedProducts.js)
Just tell me!


---

✔️ **This is now your complete backend README — clean, professional, beginner-friendly, ready to use.**
