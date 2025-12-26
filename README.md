# Room Editor

## Overview

Room Editor is a browser-based 2.5D (isometric) editor for building rooms with tiles, walls, and stackable cubes. It focuses on fast interaction (drag/drop, right-click edits), clear visuals (depth sorting and previews), and persistence (rooms saved locally). Rendering runs on Pixi.js, with a lightweight Preact UI layer.

## Features

### Editor capabilities

- Isometric rendering with depth sorting for tiles, walls, and objects
- Drag-and-drop cube placement with stacking support
- Blueprint preview before confirming placement
- Per-face color customization (cubes, tiles, walls, avatar)
- Room layout editor (grid size, wall parameters, visibility)
- Multi-room management (create, rename, delete, switch)
- Door placement for room connections

### Interaction and navigation

- Click-to-move avatar with obstacle-aware pathfinding
- Camera zoom and panning for easier editing on large rooms

### Technical notes

- High-performance canvas rendering via Pixi.js (WebGL where available)
- Local persistence using browser localStorage
- Strong typing and validation-friendly patterns using TypeScript
- Modern tooling with Vite, plus a responsive UI styled with Tailwind CSS

## Tech stack

- Pixi.js (rendering)
- Preact (UI)
- TypeScript
- Vite
- Tailwind CSS
- @preact/signals (state)
- pixi-viewport (camera/viewport)
- heap-js (pathfinding support)
- gh-pages (deployment)

## Getting started

### Prerequisites

- Node.js 18+
- npm/yarn/pnpm
- A modern browser (Chrome, Firefox, Edge, Safari)

### Install and run

```bash
git clone https://github.com/username/room-editor.git
cd room-editor
npm install
npm run dev
```

Vite will print the local URL in your terminal (commonly `http://localhost:5173`). If your config uses a different port (e.g. `8080`), follow the URL shown in the console output.

### Production build

```bash
npm run build
```

Output is generated in `dist/`.

### Preview production build

```bash
npm run preview
```

## Usage

### Core controls

- Move the avatar by clicking a target tile; the avatar routes around obstacles automatically
- Move cubes via drag-and-drop; stack cubes to create platforms
- Open the color picker by right-clicking a face (cube, tile, wall, or avatar)
- Pan the camera by dragging the canvas; zoom using the on-screen controls

### Widgets

- Navigator: create/switch/rename/delete rooms
- Inventory: choose cube sizes and placement options
- Layout: edit grid dimensions, wall settings, tile thickness, and doors
- Settings: application options
- Zoom controls: zoom in/out

## Project structure

```
room-editor/
├── src/
│   ├── core/                 # Rendering + engine logic
│   │   ├── engine/
│   │   │   ├── game/          # Scene and client orchestration
│   │   │   └── pathfinding/   # Pathfinding algorithms/utilities
│   │   └── modules/           # Domain modules
│   │       ├── avatar/
│   │       ├── cube/
│   │       ├── tile/
│   │       └── wall/
│   ├── ui/                    # Preact UI
│   │   ├── components/
│   │   ├── hooks/
│   │   └── store/
│   └── index.ts
├── dist/
├── vite.config.ts
└── package.json
```

## Scripts

- `npm run dev` — Start the dev server
- `npm run build` — Build for production
- `npm run preview` — Preview the production build locally
- `npm run deploy` — Deploy to GitHub Pages
- `npm run lint` — Run ESLint
- `npm run lint:fix` — Fix lint issues
- `npm run format` — Format with Prettier
- `npm run format:check` — Check formatting

## Deployment (GitHub Pages)

```bash
npm run deploy
```
[1](https://img.shields.io/badge/Room%20Editor-2.5D%20Room%20Editor-blue)
[2](https://img.shields.io/badge/TypeScript-5.9-blue)
[3](https://img.shields.io/badge/Vite-7.1-646CFF)
