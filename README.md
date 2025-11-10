```markdown
#  Real-Time Collaborative Drawing Canvas

A multi-user drawing application where users can draw simultaneously on the same canvas with real-time synchronization. This project is built from scratch using vanilla JavaScript (HTML5 Canvas) and Node.js with WebSockets, focusing on efficient real-time state synchronization and core canvas operations.

##  Table of Contents

* [Features](#-features)
* [Technical-Stack](#-technical-stack)
* [Project-Structure](#-project-structure)
* [Setup-and-Installation](#-setup-and-installation)
* [How-to-Test](#-how-to-test)
* [Architecture-Overview](#-architecture-overview)
* [Known-Limitations](#-known-limitations)
* [Time-Spent](#-time-spent)

##  Features

* **Drawing Tools:**
    * **Brush:** Standard drawing tool.
    * **Eraser:** Erases content on the canvas.
    * **Color Picker:** Allows users to select any stroke color.
    * **Stroke Width:** Adjustable slider to change the size of the brush/eraser.
* **Real-Time Collaboration:**
    * **Live Sync:** Drawing actions (paths, strokes, erasures) are broadcast to all connected users in real time.
    * **State Synchronization:** New users joining the session receive the current, complete state of the canvas.
* **Advanced State Management:**
    * **Global Undo/Redo:** A shared operation history for the entire canvas. When one user clicks "Undo," it reverts the *last action* made by *any* user, and this change is synced across all clients.

##  Technical Stack

* **Frontend:**
    * **HTML5 Canvas:** Used for all rendering and drawing operations.
    * **Vanilla JavaScript (ES6+):** For all client-side logic, DOM manipulation, event handling, and canvas context management.
    * **CSS3:** For styling the toolbar, canvas, and layout.
* **Backend:**
    * **Node.js:** Runtime environment for the server.
    * **Express.js:** (or native `http` module) For serving static client files.
    * **WebSockets (Socket.io):** For bi-directional, real-time communication between the client and server.
* **Constraints:**
    * This project was built with **no frontend frameworks** (like React or Vue) and **no canvas libraries** (like Fabric.js or p5.js) to demonstrate mastery of the raw browser APIs.

##  Project Structure

Here is the high-level structure of the application, as required by the submission guidelines:

```

Collaborative-Drawing-Canvas/
├── client/
│   ├── index.html        \# Main HTML file with canvas and toolbar
│   ├── style.css         \# Styles for the application
│   ├── canvas.js         \# Core canvas drawing logic (handling paths, strokes, etc.)
│   ├── websocket.js      \# Client-side WebSocket connection and event handling
│   └── main.js           \# Initializes the app, wires up toolbar event listeners
├── server/
│   ├── server.js         \# Main backend file (Express + WebSocket server setup)
│   ├── rooms.js          \# Logic for managing user sessions and rooms
│   └── drawing-state.js  \# Server-side state management (canvas history, undo/redo stack)
├── ARCHITECTURE.md       \# In-depth documentation of the system architecture
├── package.json          \# Project dependencies and scripts
└── README.md             \# This file

````

##  Setup and Installation

Follow these steps to run the project locally.

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/UmedKumar/Collaborative-Drawing-Canvas.git](https://github.com/UmedKumar/Collaborative-Drawing-Canvas.git)
    cd Collaborative-Drawing-Canvas
    ```

2.  **Install server dependencies:**
    ```bash
    npm install
    ```

3.  **Start the server:**
    ```bash
    npm start
    ```
    (This will typically start the server on `http://localhost:3000`. Check your server console output for the exact port.)

4.  **Open the application:**
    Open your browser and navigate to `http://localhost:3000`.

##  How to Test

To test the real-time collaborative features, you must simulate multiple users.

1.  Start the server using `npm start`.
2.  Open `http://localhost:3000` in a new browser window.
3.  Open `http://localhost:3000` in a *second* browser window (or an incognito window) to create a separate client session.
4.  Place the windows side-by-side.
5.  Draw on one canvas. You should see the drawing appear instantly on the second canvas.
6.  Test the color picker, size picker, eraser, undo, and redo buttons on both clients to ensure the state is fully synchronized.

##  Architecture Overview

The application uses a client-server model with a central Node.js server acting as the single source of truth for the canvas state.

* **Client:** Captures user input (mouse events) and canvas settings (color, size). It serializes this data and sends it to the server via WebSockets. It also listens for "update" events from the server to re-draw the canvas based on the actions of other users.
* **Server:** Manages the global application state. It maintains a complete history of drawing operations (lines, erasures) in an array. When a client sends a drawing event, the server adds it to the history and then broadcasts that single event to all other connected clients. For the **global undo/redo** feature, the server maintains the operation stack.

> **For a detailed breakdown**, please see the [`ARCHITECTURE.md`](ARCHITECTURE.md) file, which includes:
> * Data Flow Diagram
> * WebSocket Protocol Definition (message types)
> * The Undo/Redo Strategy
> * Performance and Conflict Resolution Decisions

##  Known Limitations

* * * ##  Time Spent

* **Total Time:** Approx. 1.5 Days.

````
