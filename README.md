# TBH — Anonymous Messaging App

A modern, fast, and privacy-focused anonymous messaging application built with Vanilla Web Technologies. Inspired by apps like NGL and TBH, this web app allows users to receive anonymous messages through a personal link, fully functional on the frontend.

## ✨ Features

- **P2P Messaging**: Powered by **WebRTC (PeerJS)** for real-time messaging directly between the sender and receiver—no database required for live delivery!
- **PWA Ready**: Installable as a native app on iOS and Android. Includes offline caching via Service Workers.
- **Dynamic Theming**: Choose between Light, Dark, and Midnight themes, along with multiple accent colors.
- **Privacy & Safety Controls**:
  - Filter out toxic words (Hidden Words list)
  - Block specific senders
  - Pause link at any time
- **Stunning UI/UX**: Features glassmorphism navigation, smooth micro-animations, and a highly responsive design.
- **Desktop Phone Frame**: Beautiful floating mobile layout when viewed on larger desktop screens.

## 🛠 Tech Stack

- **HTML5** & **Vanilla CSS** (No heavy CSS frameworks)
- **Vanilla JavaScript** (No React/Vue overhead)
- **PeerJS** (WebRTC library for Peer-to-Peer messaging)
- **Web Audio API** (Notification sounds)

## 🚀 How to Run Locally

Because the application uses Service Workers and WebRTC (PeerJS), it **must** be served over a local web server (using the `file://` protocol will break these features due to browser CORS and security rules).

1. Open your terminal in the project folder.
2. Start a local server. If you have Python installed, you can run:
   ```bash
   python -m http.server 8000
   ```
   *Alternatively, use VS Code's "Live Server" extension.*
3. Open your browser and go to `http://localhost:8000`.

## 📦 Deployment (Vercel)

This application is 100% static and requires zero build steps, making it perfect for instantaneous deployment on Vercel.

1. Go to [Vercel](https://vercel.com/)
2. Create a new project and import this folder (or link to your GitHub repository).
3. Vercel will automatically detect it as a static project.
4. Deploy!

## ⚠️ Important Note on P2P Architecture

This app currently operates purely on the frontend. While the WebRTC logic handles live messaging beautifully when both users are online, **offline messages** are currently cached locally in the sender's browser as a fallback. 

To enable true offline message delivery (where a sender can drop a message while the receiver's phone is off, and the receiver gets it later), you will need to integrate a lightweight backend database such as **Firebase**, **Supabase**, or **Vercel Postgres**.
