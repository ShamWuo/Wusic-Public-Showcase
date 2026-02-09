# System Architecture

## Overview
Prasic follows a **Local-First**, **Service-Oriented** architecture. The application is built on React Native (Expo) and utilizes a modular design to ensure maintainability and scalability.

## Core Layers

### 1. UI Layer (Presentation)
- **Components**: Atomic design methodology (Atoms -> Molecules -> Organisms).
- **Navigation**: File-based routing using `expo-router`.
- **Theming**: Context-based dynamic theming (Dark/Light modes).

### 2. State Management
- **Zustand Stores**:
  - `TimerStore`: Manages the active practice session, elapsed time, and background ticks.
  - `UserStore`: Handles user profile, preferences, and subscription status.
  - `ToastStore`: Global toast notification system.

### 3. Service Layer
Business logic is decoupled from UI components into dedicated singleton services:
- **`AIService`**: Handles interactions with the Gemini API, prompt engineering, and response parsing.
- **`CoachService`**: Aggregates data from sessions to generate "Vitality Scores" and practice feedback.
- **`AudioService`**: Manages recording sessions, file persistence, and playback.
- **`SubscriptionService`**: Gating logic for Pro features.

### 4. Data Layer (Persistence)
- **Drizzle ORM**: Provides a type-safe wrapper around SQLite.
- **SQLite**: On-device relational database storing:
  - Pieces / Repertoire
  - Practice Sessions
  - Journals / Logs
  - Application Settings

## Key Design Patterns

### The "Maestro" AI Engine
The AI Coach isn't just a chatbot; it's an integrated system context.
1. **Context Gathering**: When a user requests help, the app bundles the last 14 days of session data, current piece stats, and user goals.
2. **Prompt Optimization**: Context is formatted into a dense system prompt trained on music pedagogy.
3. **Structured Output**: The AI returns JSON-structured data that the app renders as interactive UI cards (not just Markdown text).

### Performance Optimization
- **Memoization**: Heavy computations (stats aggregation) are memoized.
- **Lazy Loading**: Lists use `FlatList` with optimization props.
- **Asset Caching**: Images and fonts are pre-cached at splash screen.

## Directory Structure (Public View)

```
/src
  /components    # UI Building Blocks
  /services      # Core Business Logic
  /database      # Schema & Migrations
  /hooks         # React Adapters
  /constants     # Design Tokens
  /utils         # Pure Functions
app/             # Router & Screens
```
