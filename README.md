# 🎨 Collaborative Drawing Canvas

A **real-time collaborative drawing application** where multiple users can draw together on a shared canvas simultaneously — built with **Vanilla JavaScript**, **HTML5 Canvas**, and **Node.js WebSockets**.

![Demo Screenshot](https://github.com/UmedKumar/Collaborative-Drawing-Canvas/assets/your-image-link.png)

---

## 🚀 Project Overview

This project allows multiple users to collaborate on the same digital canvas in real-time.  
Each user can draw, erase, change colors and brush sizes, undo/redo their actions, and see updates from other users instantly.

🔗 **Live Demo:** _[coming soon]_  
📂 **GitHub Repo:** [Collaborative-Drawing-Canvas](https://github.com/UmedKumar/Collaborative-Drawing-Canvas)

---

## ✨ Features

### 🖌️ Drawing Tools
- Freehand drawing with customizable color and brush size  
- Eraser tool  
- Undo and redo support  

### ⚡ Real-Time Collaboration
- All strokes are synced instantly across users using WebSockets  
- Multi-user synchronization (each participant sees others’ drawings live)  

### 🧠 State Management
- Centralized drawing state tracking on the server  
- Smooth conflict resolution for overlapping strokes  
- Undo/Redo operations tracked across all connected users  

### 🧍 User Interaction
- Visual indicators for connected users  
- Each user’s color and actions reflected globally  

---

## 🧩 Tech Stack

| Layer | Technology |
|-------|-------------|
| **Frontend** | HTML5, CSS3, Vanilla JavaScript |
| **Backend** | Node.js, Native WebSocket API |
| **Communication** | WebSockets for real-time sync |
| **Version Control** | Git & GitHub |

---

## 🗂️ Project Structure


---

## ⚙️ Installation & Setup

### 🧾 Prerequisites
Make sure you have:
- Node.js (>= 16)
- npm (>= 8)

### 🧰 Setup Steps

```bash
# Clone the repository
git clone https://github.com/UmedKumar/Collaborative-Drawing-Canvas.git

# Navigate to the project
cd Collaborative-Drawing-Canvas

# Install dependencies
npm install

# Start the server
npm start
