# BidBash - Online Auction System 🔨

A high-performance, real-time online auction platform built with the MERN stack. This system allows users to create auctions, place bids in real-time, and manage their auction history with a sleek, modern UI.

## 🚀 Features

- **Real-time Bidding**: Instant bid updates using Socket.io for a seamless auction experience.
- **Auction Management**: Create, view, and manage auctions with scheduled start and end times.
- **User Authentication**: Secure signup/login with JWT and bcrypt password hashing.
- **Admin Dashboard**: Comprehensive control over users and auctions for administrators.
- **Cloudinary Integration**: High-quality image uploads and optimization for auction items.
- **Responsive Design**: Modern UI built with Tailwind CSS v4, fully optimized for all devices.
- **Email Notifications**: Integration with Resend for transactional emails (e.g., bid confirmation).

---

## 🛠️ Tech Stack

### Frontend
- **Framework**: React 19
- **State Management**: Redux Toolkit & React Redux
- **Data Fetching**: TanStack React Query
- **Routing**: React Router 7
- **Styling**: Tailwind CSS v4
- **Real-time**: Socket.io Client
- **Icons**: React Icons
- **Toasts**: React Hot Toast

### Backend
- **Runtime**: Node.js
- **Framework**: Express.js
- **Database**: MongoDB with Mongoose ODM
- **Real-time**: Socket.io
- **File Storage**: Cloudinary
- **Email Service**: Resend
- **Compression**: Gzip compression for faster API responses

---

## 📂 Project Structure

```text
online-auction-system/
├── client/                 # Frontend React Application
│   ├── public/             # Static assets
│   ├── src/
│   │   ├── api/            # Axios API instances
│   │   ├── components/     # Reusable UI components
│   │   ├── config/         # Client-side configuration
│   │   ├── hooks/          # Custom React hooks (useSocket, useAuction, etc.)
│   │   ├── init/           # Initialization logic (Auth check)
│   │   ├── layout/         # Page layouts
│   │   ├── pages/          # Full page components
│   │   ├── routers/        # Route definitions
│   │   ├── store/          # Redux slices and store
│   │   └── utils/          # Helper functions
│   └── vite.config.js      # Vite configuration
│
└── server/                 # Backend Node.js Application
    ├── config/             # Database and Env configurations
    ├── controllers/        # Request handling logic
    ├── jobs/               # Cron jobs (Cleanup, Auction expiry)
    ├── middleware/         # Auth and Error middleware
    ├── models/             # Mongoose Schemas (User, Product, Bid)
    ├── routes/             # API Route definitions
    ├── services/           # External service logic (Cloudinary, Email)
    ├── socket/             # Socket.io event handlers
    ├── utils/              # Backend utility functions
    └── server.js           # Main entry point
```

---

## 🚦 API Endpoints

### Authentication
- `POST /api/auth/signup`: Register a new user
- `POST /api/auth/login`: Authenticate user & get token
- `POST /api/auth/logout`: Invalidate session

### Users
- `GET /api/user/`: Get current user profile
- `PATCH /api/user/`: Update password
- `GET /api/user/logins`: Get login history

### Auctions
- `GET /api/auction/`: List all active auctions
- `POST /api/auction/`: Create a new auction
- `GET /api/auction/stats`: Get dashboard statistics
- `GET /api/auction/:id`: Get specific auction details
- `POST /api/auction/:id/bid`: Place a bid on an auction
- `GET /api/auction/myauction`: Get auctions created by user
- `GET /api/auction/mybids`: Get auctions where user has bid

### Admin
- `GET /api/admin/dashboard`: Admin overview stats
- `GET /api/admin/users`: Manage all registered users

### Upload
- `GET /api/upload/signature`: Get secure Cloudinary upload signature

---

## ⚙️ Installation & Setup

### Prerequisites
- Node.js (v18+)
- MongoDB Atlas or Local instance
- Cloudinary Account
- Resend API Key

### Steps

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd online-auction-system
   ```

2. **Backend Setup**
   ```bash
   cd server
   npm install
   # Create a .env file based on the template below
   npm run dev
   ```

3. **Frontend Setup**
   ```bash
   cd ../client
   npm install
   # Create a .env file based on the template below
   npm run dev
   ```

---

## 🔑 Environment Variables

### Server (`server/.env`)
```env
PORT=3000
MONGO_URL=your_mongodb_uri
JWT_SECRET=your_secret_key
JWT_EXPIRES_IN=30d
ORIGIN=http://localhost:5173

# Cloudinary
CLOUDINARY_CLOUD_NAME=your_cloud_name
CLOUDINARY_API_KEY=your_api_key
CLOUDINARY_API_SECRET=your_api_secret

# Email
RESEND_API_KEY=your_resend_key
```

### Client (`client/.env`)
```env
VITE_API=http://localhost:3000/api
VITE_AUCTION_API=http://localhost:3000/auction
```

---

## 🤝 Authors
- **Devesh Ghadigaonkar**
- **Aditya Bhangare**

## 📄 License
This project is licensed under the MIT License.
