# 🎧 SyncPlay — Shared Media Experience App

> A minimal, real-time synchronized media player that lets two people watch or listen together from anywhere.

---

## ✨ What is SyncPlay?

SyncPlay is a cross-platform application (Android + Windows) designed to recreate the feeling of **watching or listening together**, even when users are physically apart.

Instead of streaming media between users, SyncPlay synchronizes playback across devices where both users already have access to the same content.

---

## 🎯 Key Highlights

- 🔄 Real-time synced playback (play, pause, seek)
- 📁 Local file-based media support
- 💬 Lightweight, contextual messaging
- 🎙️ Built-in peer-to-peer voice communication
- 🎨 Interactive overlays (tap, draw, highlight)
- 🌙 Minimal, distraction-free UI (VLC-inspired)

---

## 🧠 How It Works

1. Both users join a shared room
2. Each loads the same media file (locally or via a shared source)
3. One user controls playback (or both)
4. The app synchronizes playback state across devices
5. Users interact via voice, messages, and visual overlays

> No media is transferred between users — only playback state and interactions are synced.

---

## 🚀 Features

### 🎬 Synced Playback

- Play / Pause / Seek synchronization
- Automatic drift correction
- Host-based or shared control

### 📁 Local Media Support

- Load media directly from device
- File integrity check using hash (MD5/SHA)
- Prevents mismatch between users

### 💬 Contextual Messaging

- Tap anywhere to send messages
- Messages appear as floating overlays
- Linked to playback timeline

### 🎙️ Voice Chat

- Peer-to-peer audio communication
- Low latency using WebRTC
- Simple controls (mute/unmute)

### 🎨 Interactive Overlay System

- Tap to highlight points
- Draw on screen (doodles, circles)
- Temporary visual annotations
- User-specific colors

### 👥 Presence & Sync Status

- See who is connected
- Playback state indicators
- Sync status feedback

### 🌙 UI & Experience

- VLC-inspired minimal interface
- Gesture-based controls
- Hidden UI (tap to reveal)
- “Date Mode” for immersive sessions

---

## 🧱 Architecture

```
Flutter Client (Android + Windows)
│
▼
Firebase (Realtime Sync & Signaling)
│
▼
WebRTC (Peer-to-Peer Voice)
```

---

## 🛠️ Tech Stack

| Layer              | Technology                         |
|-------------------|------------------------------------|
| Frontend          | Flutter                            |
| Realtime Backend  | Firebase (Firestore / RTDB)        |
| Sync Communication| Firebase (WebSocket-based updates) |
| Voice Chat        | WebRTC (`flutter_webrtc`)          |
| Media Playback    | Flutter video/audio plugins        |

---

## ⚙️ Core Concepts

### 🔄 Sync Engine

Playback state is shared using a simple model:

```json
{
  "state": "playing",
  "position": 42.5,
  "timestamp": 1713260000
}
```

Clients calculate expected playback position and correct drift using:

- Seek (for large differences)
- Playback speed adjustment (for small differences)

### 🎨 Overlay System

- Uses normalized coordinates (0–1) for cross-device consistency
- Rendered via `CustomPainter`
- Events are time-bound and auto-expire

### 🎙️ Voice System

- Peer-to-peer connection using WebRTC
- Signaling handled via Firebase
- No central audio server required

---

## ⚠️ Constraints

### Legal

- No redistribution or streaming of copyrighted content
- Media must be locally available or publicly accessible

### Network

- Internet required for long-distance sync
- Latency may affect synchronization accuracy

### Device

- Performance varies across devices
- Screen differences handled via normalized rendering

---

## 🚧 Challenges

- Maintaining accurate sync across variable networks
- Handling playback drift smoothly
- Reliable real-time communication
- UI layering without clutter
- WebRTC setup and NAT traversal

---

## 📶 Data Usage

| Component      | Usage    |
|---------------|----------|
| Sync events    | Minimal  |
| Messaging      | Minimal  |
| Voice chat     | Moderate |
| Media playback | None (local) |

---

## 🔒 Security

- Room-based access control
- Optional authentication
- Secure signaling for WebRTC
- No file transfer between users

---

## 🧪 Testing Strategy

- Multi-device testing (Android + Windows)
- Network latency simulation
- Reconnection handling
- Playback drift scenarios

---

## 📦 Deployment

- Android → APK via Flutter
- Windows → Desktop executable

---

## 🛣️ Roadmap

### MVP

- Room system
- Synced playback
- Local file support
- Basic messaging

### Phase 2

- Voice chat
- Reactions & overlays
- Improved sync engine

### Future

- Themes & personalization
- AI-based recommendations
- LAN/offline mode
- Advanced audio features

---

## 💡 Inspiration

- VLC Media Player — minimal UI
- Watch2Gether — shared experience
- Discord — lightweight communication

---

## 🏁 Philosophy

> SyncPlay is not just a media player — it’s a way to share moments.

---

## 📌 Status

🚧 In Development
