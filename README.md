# SocketServer ⚡

**SocketServer** is a Node.js real-time server built with **Express** and **Socket.IO**, 
designed to work with the **NextShop** grocery app. It handles:

- Real-time geolocation updates for delivery boys  
- Chat messaging between users and delivery personnel  
- Room-based communication  
- Event notifications  

---

## Table of Contents

- [Features](#features)  
- [Tech Stack](#tech-stack)  
- [Installation](#installation)  
- [Environment Variables](#environment-variables)  
- [Available Scripts](#available-scripts)  
- [Usage](#usage)  

---

## Features

- **Real-time Updates**: Delivery boy & User location updates and broadcasting to all clients.  
- **Chat System**: Users and delivery boys can send messages in rooms.  
- **Notifications**: Emit events to a specific socket or all connected clients.  
- **Room-based Communication**: Users can join specific rooms for private messaging.  

---

## Tech Stack

- **Node.js** & **Express** – Backend server  
- **Socket.IO** – Real-time bi-directional communication  
- **Axios** – HTTP requests to Next.js API  
- **dotenv** – Environment variable management  
- **MongoDB** (via NextShop APIs) – Data persistence  

---

## Installation

1. Clone the repository:

```bash
git clone [https://github.com/jakaria2055/next_socket_server]
cd socketServer
````

2. Install dependencies:

```bash
npm install
```

3. Create a `.env` file in the root:

```env
NEXT_BASE_URL="http://localhost:3000"
PORT=4000
```

4. Start the development server:

```bash
npm run dev
```

Server will run on `http://localhost:4000` (or your custom port).

---

## Available Scripts

| Script        | Description                               |
| ------------- | ----------------------------------------- |
| `npm run dev` | Start server with nodemon for live reload |
| `npm test`    | Placeholder test script                   |

---

## Usage

The server exposes:

* **WebSocket Events**:

  * `identity` – Register a user with a socket ID
  * `update-location` – Send delivery boy location updates
  * `join-room` – Join a chat room
  * `send-message` – Send a chat message to a room
  * `disconnect` – Triggered when a user disconnects

* **HTTP POST Endpoint**:

  * `/notify` – Emit a custom event to a socket or all clients

  ```json
  {
    "event": "eventName",
    "data": { "example": "payload" },
    "socketId": "optionalSocketId"
  }
  ```

---

## Folder Structure

```text
socketServer/
├─ index.js           # Main server entry point
├─ package.json
├─ package-lock.json
└─ .gitignore
```

---

© 2026 Jakaria Ahmed

```
