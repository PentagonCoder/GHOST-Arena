# Ghost-Arena

A browser-based 3D multiplayer game built with React, Vite, and Three.js (via React Three Fiber). Players join with a username, move around a shared map in real time, and attack nearby opponents.

## Features

- Real-time multiplayer state sync over WebSocket
- 3D scene rendering with React Three Fiber and Drei
- Pointer-lock camera controls for immersive gameplay
- Player movement with collision and map boundaries
- Basic melee attack system and death state UI
- Optimized GLB-based character/environment assets

## Tech Stack

- **Frontend:** React 19, Vite 8
- **3D Rendering:** three, @react-three/fiber, @react-three/drei
- **Networking:** Native WebSocket API
- **Linting:** ESLint 9

## Project Structure

```text
src/
  components/
    Game.jsx          # Main scene setup and game flow
    Player.jsx        # Local player movement/combat logic
    OtherPlayer.jsx   # Remote player rendering/interpolation
  hooks/
    useWebSocket.js   # Multiplayer connection and messaging
  assets/             # Generated React wrappers for 3D assets
public/               # GLB files used in the scene
```

## Prerequisites

- Node.js 18+ (Node.js 20 recommended)
- npm 9+

## Getting Started

1. Install dependencies:

   ```bash
   npm ci
   ```

2. Start the development server:

   ```bash
   npm run dev
   ```

3. Open the local URL printed by Vite (usually `http://localhost:5173`).

## Available Scripts

- `npm run dev` — start local development server
- `npm run build` — build production assets into `dist/`
- `npm run preview` — preview the production build locally
- `npm run lint` — run ESLint

## Gameplay Controls

- **W / A / S / D** or **Arrow Keys**: move
- **Mouse movement**: look around (after pointer lock)
- **Left click**: attack/swing
- **Esc**: release pointer lock

## Multiplayer Backend

The client connects to:

- `wss://game-server-websocket.onrender.com`

Make sure this backend is running and reachable for multiplayer features to work.

## Build Output Note

Current production builds can exceed Vite's default chunk-size warning threshold due to 3D dependencies and assets. This is expected for now and does not block builds.
