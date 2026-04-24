<div align="center">

# **Free-Cluely**

**An always-on-top desktop assistant** built with **Electron + React** that lets you capture on-screen context (screenshots) and get answers in real time using **Google Gemini** or **Ollama (local)**.

![Electron](https://img.shields.io/badge/Electron-2B2E3A?logo=electron&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?logo=typescript&logoColor=white)
![Vite](https://img.shields.io/badge/Vite-646CFF?logo=vite&logoColor=white)
![License](https://img.shields.io/badge/License-ISC-green)

</div>

## ✨ **Highlights**

- 🪟 **Always-on-top overlay** with quick hide/show
- 🧠 **AI provider switch**: **Gemini (cloud)** or **Ollama (local/private)**
- 📸 **Screenshot queue** with previews + one-key processing
- ⌨️ **Global hotkeys** for speed during work

## 🧩 **Tech Stack**

- **Electron**
- **Vite + React + TypeScript**
- **Tailwind CSS + Radix UI**

## 🚀 **Quick Start**

### ✅ **Prerequisites**

- **Node.js 18+**
- **Git**
- One of:
  - **Gemini API key** (Google AI Studio)
  - **Ollama** installed + running locally

### 📦 **Install**

```bash
git clone https://github.com/heyayushhh/Free-Cluely.git
cd free-cluely
npm install
```

If Sharp fails to install:

```bash
SHARP_IGNORE_GLOBAL_LIBVIPS=1 npm install --ignore-scripts
npm rebuild sharp
```

### 🔑 **Environment Variables**

Create a `.env` file in the project root.

**Option A — Gemini (cloud):**

```env
GEMINI_API_KEY=your_api_key_here
```

**Option B — Ollama (local/private):**

```env
USE_OLLAMA=true
OLLAMA_URL=http://localhost:11434
OLLAMA_MODEL=llama3.2
```

### ▶️ **Run (Development)**

```bash
npm start
```

Starts the Vite dev server on `127.0.0.1:5180` and launches the Electron app.

## ⌨️ **Keyboard Shortcuts**

| Shortcut | Action |
|---|---|
| **Ctrl/Cmd + Shift + Space** | Show + center window |
| **Ctrl/Cmd + B** | Toggle window visibility |
| **Ctrl/Cmd + H** | Take screenshot and add to queue |
| **Ctrl/Cmd + Enter** | Process screenshots |
| **Ctrl/Cmd + R** | Reset (cancel requests + clear queues) |
| **Ctrl/Cmd + Arrow Keys** | Move window |

## 🛠 **Scripts**

| Command | What it does |
|---|---|
| `npm start` | Dev app (Vite + Electron) |
| `npm run build` | Typecheck + build renderer + electron build output |
| `npm run dist` | Build + package installers (electron-builder) |

## 🧯 **Troubleshooting**

- 🔌 **Port `5180` in use**: stop the process using the port or update the port in `package.json` (`app:dev`).
- 🦙 **Ollama not connecting**: run `ollama serve` and confirm `OLLAMA_URL` matches.
- 🧱 **Sharp install errors**: use the Sharp workaround in the Install section.

## 🔒 **Security Notes**

- Never commit `.env` or API keys to GitHub.
- If you accidentally exposed a key, rotate it immediately and remove it from history.

## 📄 **License**

See [LICENSE](./LICENSE).
