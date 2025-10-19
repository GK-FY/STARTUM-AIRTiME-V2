
# 🎯 FY WHATSAPP AIRTIME BOT

<p align="center">
  <img src="https://iili.io/K8N5Jn4.png" alt="FY Bot" width="820" style="max-width:100%;border-radius:12px;"/>
</p>

A powerful, production-ready WhatsApp bot for selling airtime in Kenya via M-Pesa. Features a beautiful admin dashboard, automatic payment processing, and seamless airtime delivery.

<p align="center">
  <img src="https://img.shields.io/badge/license-MIT-blue.svg" alt="License" />
  <img src="https://img.shields.io/badge/node-%3E%3D16.0.0-brightgreen.svg" alt="Node" />
  <img src="https://img.shields.io/badge/WhatsApp-Web.js-25D366.svg" alt="WhatsApp" />
  <img src="https://img.shields.io/badge/status-Production%20Ready-success.svg" alt="Production Ready" />
</p>

---

## ✨ Quick overview

**FY WhatsApp Airtime Bot** makes selling airtime as easy as chatting — customers send a message, choose amount, pay with M-Pesa, and receive airtime instantly. Admins manage everything from a beautiful dashboard or directly via WhatsApp commands.

---

## 📚 Table of Contents

- [✨ Features](#-features)  
- [🚀 Quick Start](#-quick-start)  
- [📋 Requirements](#-requirements)  
- [🎮 How to Use](#-how-to-use)  
- [🎯 Admin Dashboard Features](#-admin-dashboard-features)  
- [🚀 Deployment](#-deployment)  
- [🔧 Configuration](#-configuration)  
- [📁 Project Structure](#-project-structure)  
- [🔒 Security](#-security)  
- [🛠️ Troubleshooting](#️-troubleshooting)  
- [📞 API Endpoints](#-api-endpoints)  
- [🤝 Contributing](#-contributing)  
- [📄 License](#-license)  
- [💡 Support](#-support)  
- [🎉 Credits](#-credits)

---

## ✨ Features

### For Customers
- 💸 **Easy Airtime Purchase** - Buy airtime for yourself or others via WhatsApp  
- 📱 **M-Pesa Integration** - Secure payments via Shadow Pay STK Push  
- 📦 **Order Tracking** - Track your orders with unique order numbers  
- ✅ **Instant Delivery** - Automatic airtime delivery via Statum API  
- 🎯 **User-Friendly** - Interactive menu system with clear instructions

### For Admins
- 🎨 **Beautiful Admin Dashboard** - Modern web interface for managing everything  
- ⚙️ **Easy Settings Management** - Change admin number, limits, discount, API keys - all from the dashboard  
- 📊 **Order Management** - View all orders, filter by status, search by order number  
- 👑 **WhatsApp Admin Panel** - Full admin control via WhatsApp commands  
- 🔐 **Secure** - Token-based authentication for admin access  
- 📱 **Real-time Updates** - Live connection status and QR code display  
- 💰 **Flexible Pricing** - Set min/max amounts and discount percentages

---

## 🚀 Quick Start

> Paste and run these commands to get started locally.

### 1. Clone and Install

```bash
git clone https://github.com/GK-FY/STARTUM-AIRTiME-V2.git
cd STARTUM-AIRTiME-V2
npm install
````

### 2. Configure Environment

Create a `.env` file:

```env
PORT=5000
ADMIN_WHATSAPP=254712345678
ADMIN_UI_TOKEN=your-strong-secret-token-here
```

### 3. Run the Bot

```bash
npm start
```

### 4. Scan QR Code

1. Open `http://localhost:5000` in your browser
2. Scan the QR code with WhatsApp (Settings → Linked Devices → Link a Device)
3. Wait for "WhatsApp Connected!" message

### 5. Configure Settings

1. Click "Admin Dashboard" on the homepage
2. Enter your `ADMIN_UI_TOKEN`
3. Go to Settings tab
4. Add your API credentials:

   * Shadow Pay API keys (for M-Pesa)
   * Statum API keys (for airtime delivery)
5. Set your pricing (min/max amounts, discount)
6. Click "Save All Settings"

---

## 📋 Requirements

* **Node.js** 16 or higher
* **WhatsApp Account** (for the bot)
* **Shadow Pay Account** ([shadow-pay.top](https://shadow-pay.top)) - For M-Pesa payments
* **Statum Account** ([statum.co.ke](https://statum.co.ke)) - For airtime delivery
* **Long-running server** (See deployment guide — persistent connection required)

---

## 🎮 How to Use

### For Customers

1. **Start conversation** - Send any message to the bot
2. **Type "menu"** - See available options
3. **Select option 1** - Buy Airtime
4. **Enter amount** - Input airtime amount in KES
5. **Choose recipient** - Self or someone else
6. **Enter phone number** - M-Pesa and recipient numbers
7. **Confirm order** - Type "1" to confirm
8. **Complete payment** - Enter M-Pesa PIN on your phone
9. **Receive airtime** - Automatic delivery after payment

### For Admins

#### Web Dashboard

1. Go to your bot URL
2. Click "Admin Dashboard"
3. Enter admin token
4. Manage orders, settings, and view system info

#### WhatsApp Commands

* Type `admin` or `9` from menu to access admin panel
* View orders, check status, update settings
* Get QR code, restart session, send test alerts

---

## 🎯 Admin Dashboard Features

### Orders Tab

* View all orders with filtering (all, paid, pending, failed)
* Search by order number, MPesa code, or phone number
* Real-time order status updates
* Detailed order information

### Settings Tab

* **Admin Configuration** - Change admin WhatsApp number
* **Pricing & Limits** - Min/max amounts, discount percentage
* **Shadow Pay Config** - M-Pesa payment API credentials
* **Statum Config** - Airtime delivery API credentials
* Save all settings with one click

### System Tab

* View system information
* Platform details and connection status
* Deployment guidance

---

## 🚀 Deployment

**⚠️ Important:** This bot **CANNOT** run on Vercel, Netlify, or other serverless platforms because it requires persistent connections.

### One-click Deploy (use this repo: `GK-FY/STARTUM-AIRTiME-V2`)

> Replace `main` in URLs below with your branch name if your default branch is different.

<p align="center">
  <a href="https://railway.app/new/template?template=https://github.com/GK-FY/STARTUM-AIRTiME-V2">
    <img src="https://railway.app/button.svg" alt="Deploy on Railway" style="margin:6px;height:40px;">
  </a>
  <a href="https://heroku.com/deploy?template=https://github.com/GK-FY/STARTUM-AIRTiME-V2">
    <img src="https://www.herokucdn.com/deploy/button.svg" alt="Deploy to Heroku" style="margin:6px;height:40px;">
  </a>
  <a href="https://app.koyeb.com/deploy?type=git&repository=GK-FY/STARTUM-AIRTiME-V2&branch=main">
    <img src="https://www.koyeb.com/static/images/deploy/button.svg" alt="Deploy to Koyeb" style="margin:6px;height:40px;">
  </a>
  <a href="https://cloud.digitalocean.com/apps/new?repo=https://github.com/GK-FY/STARTUM-AIRTiME-V2/tree/main">
    <img src="https://img.shields.io/badge/DigitalOcean-Deploy-blue.svg" alt="Deploy to DigitalOcean" style="margin:6px;height:40px;">
  </a>
  <a href="https://dashboard.render.com/new?repo=https://github.com/GK-FY/STARTUM-AIRTiME-V2">
    <img src="https://img.shields.io/badge/Render-Deploy-6CC24A.svg" alt="Deploy to Render" style="margin:6px;height:40px;">
  </a>
</p>

**Recommended Platforms (details)**

1. **Railway.app** ⭐ (Recommended)

   * Free tier available; easy one-click deploy
2. **Render.com**

   * Simple deployment; free tier available
3. **Heroku**

   * Reliable and tested; $5/month eco dynos (if you need always-on)
4. **DigitalOcean**

   * Full control; $5/month droplets or App Platform

**📖 See [DEPLOYMENT.md](DEPLOYMENT.md) for detailed deployment instructions.**

---

## 🔧 Configuration

### Environment Variables

| Variable         | Description                | Required | Default  |
| ---------------- | -------------------------- | -------- | -------- |
| `PORT`           | Server port                | No       | 5000     |
| `ADMIN_WHATSAPP` | Admin phone (254XXXXXXXXX) | Yes      | -        |
| `ADMIN_UI_TOKEN` | Admin dashboard password   | Yes      | changeme |

### Settings (via Admin Dashboard)

| Setting                  | Description            | Example     |
| ------------------------ | ---------------------- | ----------- |
| `bot_name`               | Bot display name       | FY Bot      |
| `min_amount`             | Minimum airtime (KES)  | 10          |
| `max_amount`             | Maximum airtime (KES)  | 1500        |
| `discount_percent`       | Discount percentage    | 0           |
| `shadow_api_key`         | Shadow Pay API key     | Your key    |
| `shadow_api_secret`      | Shadow Pay secret      | Your secret |
| `shadow_account_id`      | Shadow Pay account ID  | 17          |
| `statum_consumer_key`    | Statum consumer key    | Your key    |
| `statum_consumer_secret` | Statum consumer secret | Your secret |

---

## 📁 Project Structure

```
.
├── server.js              # Main application server
├── package.json           # Dependencies
├── public/
│   ├── index.html        # QR code dashboard
│   └── admin.html        # Admin dashboard
├── data/                 # Auto-created data directory
│   ├── orders.json       # Order records
│   └── settings.json     # Bot settings
├── session/              # WhatsApp session (auto-created)
├── railway.json          # Railway deployment config
├── render.yaml           # Render deployment config
├── Procfile              # Heroku deployment config
├── DEPLOYMENT.md         # Deployment guide
└── README.md             # This file
```

---

## 🔒 Security

* ✅ Admin dashboard protected by token authentication
* ✅ Admin WhatsApp number verification
* ✅ Environment variables for sensitive data
* ✅ Secure M-Pesa payment handling
* ✅ Session data isolated and persistent

---

## 🛠️ Troubleshooting

<details>
<summary><strong>Bot not connecting?</strong></summary>

1. Check server logs for errors
2. Ensure Chromium is installed (auto-handled on most platforms)
3. Use admin panel option 10 to restart session
4. Try re-scanning QR code

</details>

<details>
<summary><strong>Orders not processing?</strong></summary>

1. Verify Shadow Pay credentials in admin settings
2. Verify Statum credentials in admin settings
3. Check API account has sufficient credits
4. Review order details in admin dashboard

</details>

<details>
<summary><strong>Can't access admin dashboard?</strong></summary>

1. Ensure you're using the correct admin token
2. Check environment variable `ADMIN_UI_TOKEN`
3. Try clearing browser cache

</details>

---

## 📞 API Endpoints

### Public APIs

* `POST /api/initiate` - Create order and send STK push
* `POST /api/get_order` - Get order details
* `POST /api/check_status` - Check payment status
* `POST /api/deliver` - Manually deliver airtime

### Admin APIs (Token Required)

* `GET /admin/orders` - List all orders
* `GET /admin/order/:order_no` - Get specific order
* `GET /admin/settings` - Get all settings
* `POST /admin/settings` - Update settings
* `GET /admin/system-info` - System information
* `POST /admin/alert` - Send test WhatsApp alert

---

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request. Be sure to follow the code style and add tests for any significant behavior.

---

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

---

## 💡 Support

* 📖 Read the [Deployment Guide](DEPLOYMENT.md)
* 🐛 Report bugs via GitHub Issues
* ⭐ Star this repo if you find it useful!

---

## 🎉 Credits

Built with:

* [whatsapp-web.js](https://github.com/pedroslopez/whatsapp-web.js) - WhatsApp Web API
* [Express](https://expressjs.com/) - Web framework
* [Socket.IO](https://socket.io.com/) - Real-time updates
* [Shadow Pay](https://shadow-pay.top) - M-Pesa payments
* [Statum](https://statum.co.ke) - Airtime delivery

---

**Made with ❤️ for Kenyan entrepreneurs**

Need help? Open an issue or check the [Deployment Guide](DEPLOYMENT.md)!

```
```
