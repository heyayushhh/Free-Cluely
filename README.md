# Free-Cluely

A lightweight, always-on-top desktop assistant built with Electron + React that helps you capture on-screen context (screenshots) and get real-time answers using either a cloud model (Google Gemini) or a local model (Ollama).

![Free-Cluely screenshot](./image.png)

## Features

- Always-on-top, translucent overlay window
- Global hotkeys to toggle the assistant, capture screenshots, and process a queue
- Screenshot queue with previews
- Pluggable AI provider:
  - Google Gemini (requires an API key)
  - Ollama (local/private, requires Ollama running)

## Tech Stack

- Electron
- Vite + React + TypeScript
- Tailwind CSS + Radix UI

## Getting Started

### Prerequisites

- Node.js 18+ (recommended)
- Git
- One of:
  - Gemini API key (Google AI Studio)
  - Ollama installed and running locally

### Install

```bash
git clone https://github.com/heyayushhh/Free-Cluely.git
cd free-cluely
npm install
```

If you run into Sharp install issues:

```bash
SHARP_IGNORE_GLOBAL_LIBVIPS=1 npm install --ignore-scripts
npm rebuild sharp
```

### Configure Environment Variables

Create a `.env` file in the project root.

Gemini:

```env
GEMINI_API_KEY=your_api_key_here
```

Ollama (local):

```env
USE_OLLAMA=true
OLLAMA_URL=http://localhost:11434
OLLAMA_MODEL=llama3.2
```

### Run (Dev)

```bash
npm start
```

This starts the Vite dev server on `127.0.0.1:5180` and launches the Electron app.

## Keyboard Shortcuts

- Ctrl/Cmd + Shift + Space: Show and center window
- Ctrl/Cmd + B: Toggle window visibility
- Ctrl/Cmd + H: Take screenshot and add to queue
- Ctrl/Cmd + Enter: Process screenshots (generate solution)
- Ctrl/Cmd + R: Reset (cancel requests + clear queues)
- Ctrl/Cmd + Arrow Keys: Move window

## Build

```bash
npm run build
```

Packaged desktop builds:

```bash
npm run dist
```

## Troubleshooting

- Port `5180` in use: stop the process using the port or change the port in `package.json` (`app:dev`).
- Ollama not connecting: make sure `ollama serve` is running and `OLLAMA_URL` matches.
- Install failures (Sharp): use the Sharp workaround commands in the Install section.

## License

See [LICENSE](./LICENSE).
