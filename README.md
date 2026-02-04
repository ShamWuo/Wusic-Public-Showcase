# Wusic - Smart Music Practice Companion

<div align="center">
  <img src="https://via.placeholder.com/150" alt="Wusic Logo" width="120" />
  <br/>
  <h3>Master Your Craft with AI-Powered Practice</h3>
</div>

Wusic is a modern, AI-enhanced music practice application designed to help musicians practice more effectively. Wusic also implements teacher-student interaction features, allowing teachers to assign pieces to students and monitor their progress. By combining traditional tools (Metronome, Tuner) with advanced AI analytics and structured practice plans, Wusic acts as a 24/7 pocket coach.

---

## 🚀 Key Features

### 🎧 Smart Practice Session
- **Integrated Tools**: Metronome (visual & audio), Tuner, and Audio Recorder all in one screen.
- **Distraction-Free Mode**: Minimalist interface to keep you focused on the music.
- **Session Tracking**: Automatically logs practice duration, sentiment, and struggle areas.

### 🤖 AI Coach (Maestro)
- **Practice Plans**: Generates custom practice routines based on your recent sessions and goals.
- **Vitality Score**: A 7-day rolling metric of your musical consistency.
- **Smart Feedback**: Analyzes your practice habits to suggest technical improvements.
- **Tiered Models**: Powered by Gemini 2.0 Flash (Free) and Gemini 2.5 Flash (Pro).

### 🎼 Repertoire Management
- **Piece Library**: Organize pieces by composer, status (Active, Maintenance, Learned), and difficulty.
- **Technique Tracker**: dedicated section for scales, arpeggios, and etudes.
- **Quick Focus**: "Pin" active pieces to your home screen for instant access.

### 📊 Analytics & Insights
- **Heatmaps**: GitHub-style practice streaks to visualize consistency.
- **Progress Charts**: Track specific metrics over time (BPM, accuracy, time spent).

---

## 🛠️ Technology Stack

Built with a focus on performance, offline-first reliability, and smooth UX.

- **Framework**: React Native + Expo (SDK 52)
- **Navigation**: Expo Router (File-based routing)
- **Language**: TypeScript (Strict typing)
- **Database**: Local-first architecture using **Expo SQLite** + **Drizzle ORM**.
- **State Management**: Zustand (for lightweight, performant global state).
- **AI Integration**: Google Gemini API via custom MCP-style caching layer.
- **Audio Engine**: `expo-av` for playback and custom audio processing for tuner analysis.

---

## 🏗️ Architecture Architecture

### Offline-First Design
Wusic is designed to work fully offline. All practice data, recordings, and statistics are stored locally on the device using SQLite. Syncing occurs opportunistically when online to back up data or fetch new AI insights.

### AI Caching Layer
To reduce API costs and latency, the app implements a robust caching strategy for AI responses. Practice plans and difficulty analyses are cached based on composite keys (User ID + Piece Context + Recent History), ensuring instant load times for frequent requests.

---

## 📸 Screenshots

| Screen 1 | Screen 2 |
|:---:|:---:|
| ![Screen 1](images/IMG_3322%20(1).PNG) | ![Screen 2](images/IMG_3326%20(1).PNG) |

---
