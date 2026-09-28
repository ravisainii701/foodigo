🍔 Foodigo: Real-Time Food Ordering & Delivery Platform
📌 Overview
Foodigo is a full-stack MERN food ordering and delivery platform that connects customers, shop owners, and delivery partners in one system. Customers can browse shops by city, order food, and track deliveries live on a map, while shop owners manage menus and orders and delivery boys accept and fulfill deliveries in real time.

🚀 Why It Matters
🛵 On-Demand Delivery is a Multi-Billion Dollar Market
→ Online food delivery continues to grow rapidly worldwide, driven by convenience, real-time tracking, and digital payments.

📍 Real-Time Location Tracking Improves Trust
→ Live delivery tracking with sockets and maps keeps customers informed and reduces support overhead.

💳 Seamless Payments Drive Conversions
→ Integrated online payments (Razorpay) alongside Cash on Delivery give customers flexibility and reduce checkout friction.

🏗 Project Structure
```text
📂 Foodigo
├── 📂 backend  (Node.js, Express & MongoDB API)
│   ├── index.js  (Express server entry point & Socket.IO setup)
│   ├── socket.js  (Real-time delivery tracking & order events)
│   ├── package.json  (Backend dependencies)
│   ├── .gitignore
│   ├── 📂 config
│   │   ├── db.js  (MongoDB connection)
│   ├── 📂 controllers
│   │   ├── auth.controllers.js  (Signup, signin, OTP, Google auth)
│   │   ├── user.controllers.js  (User profile & location)
│   │   ├── shop.controllers.js  (Shop creation & management)
│   │   ├── item.controllers.js  (Menu item CRUD, search & ratings)
│   │   ├── order.controllers.js  (Cart checkout, payments & delivery flow)
│   ├── 📂 middlewares
│   │   ├── isAuth.js  (JWT authentication middleware)
│   │   ├── multer.js  (Image upload handling)
│   ├── 📂 models
│   │   ├── user.model.js  (User schema: role, location, OTP fields)
│   │   ├── shop.model.js  (Shop schema)
│   │   ├── item.model.js  (Menu item schema)
│   │   ├── order.model.js  (Order & shop-order sub-schema)
│   │   ├── deliveryAssignment.model.js  (Delivery assignment schema)
│   ├── 📂 routes
│   │   ├── auth.routes.js  (Auth endpoints)
│   │   ├── user.routes.js  (User endpoints)
│   │   ├── shop.routes.js  (Shop endpoints)
│   │   ├── item.routes.js  (Item endpoints)
│   │   ├── order.routes.js  (Order & delivery endpoints)
│   ├── 📂 utils
│   │   ├── cloudinary.js  (Image hosting)
│   │   ├── mail.js  (OTP & transactional emails)
│   │   ├── token.js  (JWT helpers)
│   ├── 📂 public
│   │   ├── .gitkeep  (Placeholder for uploaded/static files)
│
├── 📂 frontend  (React.js + Redux + TailwindCSS + Vite)
│   ├── index.html  (Base HTML file)
│   ├── package.json  (Frontend dependencies)
│   ├── vite.config.js  (Vite configuration & proxy setup)
│   ├── eslint.config.js  (ESLint configuration)
│   ├── firebase.js  (Firebase Google Auth config)
│   ├── .env  (Frontend environment variables)
│   ├── .gitignore
│   ├── README.md  (Default Vite/CRA readme)
│   ├── 📂 public
│   │   ├── vite.svg  (Favicon)
│   ├── 📂 src
│   │   ├── App.jsx  (Main component, routing & Socket.IO client setup)
│   │   ├── main.jsx  (React entry point)
│   │   ├── index.css  (Global TailwindCSS styling)
│   │   ├── category.js  (Food category definitions)
│   │   ├── 📂 assets  (App images: home, shop, scooter, food banners)
│   │   ├── 📂 components
│   │   │   ├── Nav.jsx  (Navigation bar)
│   │   │   ├── FoodCard.jsx  (Menu item card)
│   │   │   ├── CategoryCard.jsx  (Food category card)
│   │   │   ├── CartItemCard.jsx  (Cart line item)
│   │   │   ├── OwnerDashboard.jsx  (Shop owner dashboard)
│   │   │   ├── OwnerItemCard.jsx  (Owner's menu item card)
│   │   │   ├── OwnerOrderCard.jsx  (Owner's incoming order card)
│   │   │   ├── UserDashboard.jsx  (Customer dashboard)
│   │   │   ├── UserOrderCard.jsx  (Customer order card)
│   │   │   ├── DeliveryBoy.jsx  (Delivery partner dashboard)
│   │   │   ├── DeliveryBoyTracking.jsx  (Live map tracking view)
│   │   ├── 📂 pages
│   │   │   ├── SignUp.jsx  (Registration page)
│   │   │   ├── SignIn.jsx  (Login page)
│   │   │   ├── ForgotPassword.jsx  (OTP-based password reset)
│   │   │   ├── Home.jsx  (Landing page, role-based views)
│   │   │   ├── Shop.jsx  (Shop storefront & menu)
│   │   │   ├── CreateEditShop.jsx  (Owner: create/edit shop)
│   │   │   ├── AddItem.jsx  (Owner: add menu item)
│   │   │   ├── EditItem.jsx  (Owner: edit menu item)
│   │   │   ├── CartPage.jsx  (Shopping cart)
│   │   │   ├── CheckOut.jsx  (Checkout & payment)
│   │   │   ├── OrderPlaced.jsx  (Order confirmation)
│   │   │   ├── MyOrders.jsx  (Customer order history)
│   │   │   ├── TrackOrderPage.jsx  (Live order tracking map)
│   │   ├── 📂 hooks
│   │   │   ├── useGetCurrentUser.jsx  (Fetch logged-in user)
│   │   │   ├── useGetCity.jsx  (Detect current city)
│   │   │   ├── useGetShopByCity.jsx  (Fetch shops in city)
│   │   │   ├── useGetItemsByCity.jsx  (Fetch items in city)
│   │   │   ├── useGetMyShop.jsx  (Fetch owner's shop)
│   │   │   ├── useGetMyOrders.jsx  (Fetch customer orders)
│   │   │   ├── useUpdateLocation.jsx  (Push live location updates)
│   │   ├── 📂 redux
│   │   │   ├── store.js  (Redux store configuration)
│   │   │   ├── userSlice.js  (User/auth state & socket instance)
│   │   │   ├── ownerSlice.js  (Shop owner state)
│   │   │   ├── mapSlice.js  (Map/location state)
│
└── 📖 README.md  (Project documentation)
```

🚀 Features
✅ Multi-Role Platform: Separate experiences for Customers, Shop Owners, and Delivery Boys.
✅ Authentication: Email/password signup with OTP verification, password reset, and Google sign-in.
✅ Shop & Menu Management: Owners can create/edit their shop and add, edit, or delete menu items with images.
✅ City-Based Discovery: Customers browse shops and items filtered by their current city.
✅ Cart & Checkout: Add items to cart, place orders with Cash on Delivery or online payment via Razorpay.
✅ Real-Time Order Tracking: Live delivery boy location tracking on a map using Socket.IO and Leaflet.
✅ Delivery Assignment Flow: Delivery boys receive, accept, and fulfill assignments with OTP-verified handoff.
✅ Ratings: Customers can rate ordered items.

🔧 Tech Stack
• Frontend: React.js, Redux Toolkit, React Router, TailwindCSS, Vite
• Backend: Node.js, Express.js, Socket.IO
• Database: MongoDB with Mongoose (geospatial queries for location-based search)
• Authentication: JWT, bcrypt.js, Firebase (Google Auth)
• Payments: Razorpay
• Maps & Real-Time: Leaflet, React-Leaflet, Socket.IO Client
• Media Storage: Cloudinary
• Notifications: Nodemailer (OTP & transactional email)

📥 Installation & Setup
1️⃣ 📝 Clone the Repository
git clone https://github.com/ravisainii701/foodigo.git
cd foodigo

2️⃣ Backend Setup
cd backend
npm install

3️⃣ Frontend Setup
cd frontend
npm install

4️⃣ Set Environment Variables
Create a .env file in the backend directory and add your credentials:

PORT=5000
MONGODB_URL=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret
CLOUDINARY_CLOUD_NAME=your_cloudinary_cloud_name
CLOUDINARY_API_KEY=your_cloudinary_api_key
CLOUDINARY_API_SECRET=your_cloudinary_api_secret
RAZORPAY_KEY_ID=your_razorpay_key_id
RAZORPAY_KEY_SECRET=your_razorpay_key_secret
EMAIL=your_email_address
EMAIL_PASSWORD=your_email_app_password

Create a .env file in the frontend directory with your Firebase config for Google Auth.

📌 Steps to Run the Project
5️⃣ Run the Backend Server
cd backend
npm run dev
The API will be available at: http://localhost:5000

6️⃣ Run the Frontend
cd frontend
npm run dev
Frontend will be available at: http://localhost:5173

📡 API Endpoints
Method	Endpoint	Description
POST	/api/auth/signup	Register a new user
POST	/api/auth/signin	Log in a user
GET	/api/auth/signout	Log out a user
POST	/api/auth/send-otp	Send OTP for verification
POST	/api/auth/verify-otp	Verify OTP
POST	/api/auth/reset-password	Reset password
POST	/api/auth/google-auth	Google sign-in
GET	/api/user/current	Get current logged-in user
POST	/api/user/update-location	Update user's live location
POST	/api/shop/create-edit	Create or edit a shop
GET	/api/shop/get-my	Get the owner's shop
GET	/api/shop/get-by-city/:city	Get shops in a city
POST	/api/item/add-item	Add a new menu item
POST	/api/item/edit-item/:itemId	Edit a menu item
GET	/api/item/get-by-city/:city	Get items available in a city
GET	/api/item/search-items	Search menu items
POST	/api/item/rating	Rate a menu item
POST	/api/order/place-order	Place a new order
POST	/api/order/verify-payment	Verify Razorpay payment
GET	/api/order/my-orders	Get the customer's orders
GET	/api/order/get-assignments	Get delivery assignments for a delivery boy
GET	/api/order/accept-order/:assignmentId	Accept a delivery assignment
POST	/api/order/send-delivery-otp	Send OTP to confirm delivery
POST	/api/order/verify-delivery-otp	Verify delivery OTP
POST	/api/order/update-status/:orderId/:shopId	Update order status
WS	Socket.IO	Real-time delivery boy location & order status updates

🚀 Deployment
🌍 Backend Deployment (Node.js/Express)
⚡ Deploy on Render, Railway, or a VM
cd backend
npm start

🔹 Use Render, Railway, AWS EC2, or DigitalOcean to host the backend.
🔹 Set all required environment variables in your hosting provider's dashboard.
🔹 Ensure MongoDB Atlas (or your MongoDB instance) allows connections from your server's IP.

🖥 Frontend Deployment (React + Vite)
⚡ Deploy on Vercel
cd frontend
vercel deploy

🔹 📦 Install Vercel CLI if not already installed:
npm install -g vercel

🔹 Run vercel login to authenticate.
🔹 Deploy the project using vercel deploy.

⚡ Deploy on Netlify
cd frontend
netlify deploy --prod

🔹 📦 Install Netlify CLI:
npm install -g netlify-cli

🔹 Authenticate using netlify login.
🔹 Deploy the frontend with netlify deploy --prod.

🌱 How It Works
1️⃣ A customer signs up, verifies their account, and sets their delivery location.
2️⃣ They browse nearby shops and menu items filtered by city.
3️⃣ Items are added to the cart and an order is placed via Cash on Delivery or Razorpay.
4️⃣ The shop owner updates order status as it's prepared and a delivery boy is assigned.
5️⃣ The customer tracks the delivery boy's live location on the map until an OTP confirms delivery.

🛠 Future Roadmap
📱 Mobile App (React Native) for customers and delivery partners.
🌍 Multi-language & multi-currency support for global reach.
📊 Analytics Dashboard for shop owners to track sales trends.
🔔 Push Notifications for order status updates.

🤝 Real-World Use Cases
🍽️ Local Restaurants & Cloud Kitchens: Manage menus and receive orders online.
🛵 Delivery Partners: Accept and fulfill nearby delivery assignments in real time.
🧑‍🤝‍🧑 Customers: Discover local food options and track deliveries live.

🤝 Contributing
We welcome contributions from the community! Feel free to:
• Fork the repository
• Create a pull request with your changes
• Report issues or suggest improvements

📜 License
This project currently has no license file. Add a LICENSE file (e.g. MIT) to clarify usage terms.

🍕 Powering Local Food, in Real Time! 🛵
