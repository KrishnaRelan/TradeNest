# TradeNest

A full-stack web application for managing stock market holdings, positions, and orders. TradeNest provides traders with a comprehensive dashboard to track their investment portfolio and execute trades efficiently.

## 📋 Table of Contents

- [Features](#features)
- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Configuration](#configuration)
- [Running the Application](#running-the-application)
- [API Endpoints](#api-endpoints)
- [Project Components](#project-components)

## ✨ Features

- **Portfolio Management**: Track your stock holdings with real-time pricing information
- **Position Monitoring**: Monitor your current trading positions with product type tracking
- **Order Management**: Create and manage buy/sell orders efficiently
- **Interactive Dashboard**: React-based UI with interactive charts using Chart.js
- **Data Visualization**: Visualize portfolio performance and trends
- **RESTful API**: Express backend with MongoDB database for robust data management
- **Responsive Design**: Material-UI components for a modern, responsive interface

## 🛠️ Tech Stack

### Frontend
- **React** (v18.2.0) - UI library
- **React Router** (v6.22.2) - Routing and navigation
- **Material-UI** (v5.15.11) - Component library
- **Chart.js** & **React-ChartJS-2** - Data visualization
- **Axios** (v1.6.7) - HTTP client for API communication
- **Emotion** - CSS-in-JS styling

### Backend
- **Node.js** - Runtime environment
- **Express** (v4.18.3) - Web framework
- **MongoDB** - NoSQL database
- **Mongoose** (v8.2.1) - MongoDB ODM
- **Passport.js** - Authentication middleware
- **Passport-Local-Mongoose** - Local authentication strategy
- **CORS** - Cross-origin resource sharing
- **Body-Parser** - Request body parsing

## 📁 Project Structure

```
TradeNest/
├── Dashboard/                 # Main React dashboard application
│   ├── public/               # Static files
│   ├── src/
│   │   ├── components/       # React components
│   │   ├── data/            # Data utilities
│   │   ├── index.js         # React entry point
│   │   └── index.css        # Global styles
│   └── package.json
│
├── frontend/                  # Alternative frontend (placeholder)
│   ├── public/
│   ├── src/
│   └── package.json
│
├── backend/                   # Express server
│   ├── model/               # Mongoose models
│   ├── schemas/             # Database schemas
│   │   ├── HoldingsSchema.js   # Holdings schema
│   │   ├── PositionsSchema.js  # Positions schema
│   │   └── OrdersSchema.js     # Orders schema
│   ├── index.js             # Server entry point
│   ├── .env                 # Environment variables
│   └── package.json
│
└── README.md
```

## 📦 Prerequisites

- **Node.js** (v14 or higher)
- **npm** or **yarn** package manager
- **MongoDB** (local or cloud instance like MongoDB Atlas)

## 🚀 Installation

### 1. Clone the Repository

```bash
git clone https://github.com/KrishnaRelan/TradeNest.git
cd TradeNest
```

### 2. Install Backend Dependencies

```bash
cd backend
npm install
```

### 3. Install Dashboard Dependencies

```bash
cd ../Dashboard
npm install
```

## ⚙️ Configuration

### Backend Configuration

Create a `.env` file in the `backend/` directory with the following variables:

```env
PORT=3002
MONGO_URL=mongodb://localhost:27017/tradenest
```

**Environment Variables:**
- `PORT` - Server port (default: 3002)
- `MONGO_URL` - MongoDB connection string

For MongoDB Atlas:
```env
MONGO_URL=mongodb+srv://username:password@cluster.mongodb.net/tradenest?retryWrites=true&w=majority
```

## ▶️ Running the Application

### Start the Backend Server

```bash
cd backend
npm start
```

The backend will start on `http://localhost:3002` and connect to your MongoDB instance.

**Console Output:**
```
App started!
DB started!
```

### Start the Dashboard (in a new terminal)

```bash
cd Dashboard
npm start
```

The dashboard will open automatically at `http://localhost:3000`.

## 🔌 API Endpoints

### Holdings Endpoints

- **GET** `/allHoldings` - Retrieve all stock holdings
  - Response: Array of holdings with quantity, average price, current price, and performance metrics

### Positions Endpoints

- **GET** `/allPositions` - Retrieve all trading positions
  - Response: Array of positions with product type (CNC, MIS, etc.), quantity, and P&L information

### Orders Endpoints

- **POST** `/newOrder` - Create a new order
  - Body:
    ```json
    {
      "name": "STOCK_NAME",
      "qty": 10,
      "price": 2500.50,
      "mode": "BUY"
    }
    ```
  - Response: "Order saved!"

## 🏗️ Project Components

### Backend Models

**HoldingsSchema**: Stores stock holdings information
- Stock name
- Quantity
- Average purchase price
- Current market price
- Net return percentage
- Daily return percentage

**PositionsSchema**: Tracks active trading positions
- Product type (CNC/MIS)
- Stock name
- Quantity held
- Average price
- Current price
- Loss indicator

**OrdersSchema**: Records trading orders
- Stock name
- Order quantity
- Order price
- Buy/Sell mode

### Frontend Components

The Dashboard application includes:
- **Components**: Modular React components for UI elements
- **Data Utilities**: Data fetching and manipulation functions
- **Styling**: Material-UI theming and custom CSS

## 📝 Notes

- The backend includes commented example data for Holdings and Positions. Uncomment the `/addHoldings` and `/addPositions` routes to seed initial data.
- Authentication middleware (Passport.js) is set up but not currently active in the routes.
- The application uses CORS for cross-origin requests between frontend and backend.

## 🔐 Security Considerations

- Store sensitive credentials (database URLs, API keys) in `.env` files only
- Never commit `.env` files to the repository
- Use environment-specific configurations for development, staging, and production

## 📚 Dependencies Summary

| Package | Version | Purpose |
|---------|---------|---------|
| React | 18.2.0 | UI Framework |
| Express | 4.18.3 | Web Framework |
| MongoDB/Mongoose | 8.2.1 | Database |
| Material-UI | 5.15.11 | Component Library |
| Passport | 0.7.0 | Authentication |
| Chart.js | 4.4.2 | Data Visualization |

## 🤝 Contributing

Feel free to fork this repository and submit pull requests with improvements.

## 📄 License

This project is licensed under the ISC License.

## 💬 Support

For issues, questions, or suggestions, please open an issue on the GitHub repository.

---

**Happy Trading with TradeNest! 📈**
