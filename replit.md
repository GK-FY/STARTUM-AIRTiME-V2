# FY WhatsApp Airtime Bot - Multi-Client Edition

## Overview
This project is a production-ready multi-client WhatsApp bot system designed for selling airtime in Kenya via M-Pesa. Its primary purpose is to enable multiple businesses or users to operate independent WhatsApp airtime vending bots from a single platform. The system features a comprehensive admin dashboard for managing client connections, configuring per-client settings, and monitoring operations. Key capabilities include unlimited client support, secure QR code generation, M-Pesa STK push payments, automatic airtime delivery, and robust administrative controls. The business vision is to provide a scalable, isolated, and easy-to-manage solution for individuals and small businesses to enter the airtime resale market efficiently.

## User Preferences
- Beautiful SweetAlert2 notifications instead of basic alerts
- Number-based confirmations (1=Yes, 2=No)
- Emoji-rich menus
- Modern gradient UI design
- Multi-client support with easy management
- Per-client API credentials for complete isolation
- User ban/unban system with custom messages
- Stop/Resume functionality for bot control
- Customizable app name
- All settings editable via UI
- No code changes needed for configuration

## System Architecture

### UI/UX Decisions
The system features a completely redesigned, modern, and responsive UI with a gradient design and smooth animations. SweetAlert2 is integrated for beautiful, professional pop-up notifications. The admin dashboard provides a centralized interface for managing all aspects of the system, including client management, global settings, and order tracking, with real-time status indicators and detailed modal dialogs.

### Technical Implementations
The bot uses `whatsapp-web.js` (Puppeteer-based) for multi-instance WhatsApp support, enabling independent sessions for each client. Real-time updates and client-specific events are handled using Socket.IO with dedicated rooms for each client, ensuring isolation. A file-based JSON storage (`clients.json`, `orders.json`, `settings.json`) is used for persistence. The system employs a robust credential resolution mechanism, checking for per-client credentials first and falling back to global settings if not specified, ensuring multi-tenant isolation and continued operation even when clients are offline.

### Feature Specifications
- **Multi-Client System**: Supports unlimited WhatsApp bot instances, each with a unique ID, isolated session, and configurable settings (bot name, admin number, API credentials, ban lists).
- **Admin Dashboard**: Provides a central interface for managing clients (view, edit, disconnect, stop/resume), configuring global and per-client settings, managing access codes, and tracking orders across all clients.
- **Access Code System**: Secures new client QR code generation with a configurable access code.
- **User Management**: Per-client user ban/unban system with customizable messages and reasons.
- **Bot Control**: Individual stop/resume functionality for pausing bot activity without logging out, and a disconnect option for complete logout.
- **Customizable App Name**: Allows changing the application title from admin settings.
- **Order Management**: Tracks orders from all clients, filterable by status, searchable, and includes client ID tracking.
- **WhatsApp User Interface**: Interactive menu-based interface for customers, offering airtime purchase, M-Pesa STK push payments, and automatic delivery.

### System Design Choices
- **Backend**: Node.js + Express for server-side logic.
- **WhatsApp Integration**: `whatsapp-web.js` (Puppeteer) for robust WhatsApp interaction.
- **Real-time Communication**: Socket.IO for efficient, isolated client updates.
- **Data Storage**: File-based JSON for simplicity and persistence of client data, orders, and settings.
- **Security**: Access code protection for QR generation, token-based admin authentication, environment variables for sensitive data (`ADMIN_UI_TOKEN`), input validation, and secure M-Pesa handling.
- **Scalability & Isolation**: Designed to handle multiple independent clients on a single server, ensuring data, sessions, and credentials are kept separate for each client.

## External Dependencies
- **WhatsApp**: `whatsapp-web.js` library for interacting with WhatsApp.
- **Payment Gateway**: Shadow Pay API for M-Pesa STK Push payments.
- **Airtime Delivery**: Statum API for automated airtime distribution.
- **Real-time Communication**: Socket.IO for bidirectional communication between server and clients.
- **UI Enhancements**: SweetAlert2 for interactive and attractive notifications.