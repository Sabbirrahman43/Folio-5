# Folio-5
<div align="center">

```
███████╗ ██████╗ ██╗     ██╗ ██████╗ 
██╔════╝██╔═══██╗██║     ██║██╔═══██╗
█████╗  ██║   ██║██║     ██║██║   ██║
██╔══╝  ██║   ██║██║     ██║██║   ██║
██║     ╚██████╔╝███████╗██║╚██████╔╝
╚═╝      ╚═════╝ ╚══════╝╚═╝ ╚═════╝ 
```

**A reader that thinks with you.**

*PDF & comic reader with a local AI companion who actually has a personality.*

<br/>

[![Windows](https://img.shields.io/badge/Windows-0078D4?style=for-the-badge&logo=windows&logoColor=white)](https://github.com/Sabbirrahman43/folio/releases)
[![Electron](https://img.shields.io/badge/Electron-47848F?style=for-the-badge&logo=electron&logoColor=white)](https://electronjs.org)
[![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)](https://react.dev)
[![License](https://img.shields.io/badge/license-MIT-c4902a?style=for-the-badge)](LICENSE)

<br/>

[**Download**](https://github.com/Sabbirrahman43/folio/releases) · [**Features**](#features) · [**AI Setup**](#ai-setup) · [**Build it yourself**](#build)

<br/>

---

</div>

<br/>

## What is Folio?

Most PDF readers treat you like a filing cabinet. Open file. Read. Close.

Folio is different. It's a **desktop reading environment** built around the idea that reading shouldn't be a passive, lonely activity. You have a resident AI companion — **Lyra** — who reads alongside you. She can see the page you're on, discuss what you're reading, and she actually has opinions. Not the corporate hedging kind. Real ones.

It runs on your machine. Your books stay on your machine. Nothing phones home.

<br/>

```
┌─────────────────────────────────────────────────────────────────┐
│  𝔉 Folio          [Open PDF]  [🌿 Focus]  [⚙ Settings]  [✦ Lyra] │
├──────────────────────────────────────────┬──────────────────────┤
│                                          │  ✦  Lyra             │
│                                          │  ● Local · llama3.2  │
│   Chapter IV                             │                      │
│                                          │  "What's this book   │
│   The man who reads much and             │   actually about?"   │
│   walks little acquires a heavy          │                      │
│   body and a dull mind, yet still        │  [Break down what    │
│   believes himself to be wise.           │   I just read]       │
│                                          │                      │
│   ████████████████░░░░░░ · page 4        │  [Give me the real   │
│                                          │   context here]      │
│   [Highlight: ● ● ● ● ●]                 │                      │
│                                          │  ┌──────────────┐    │
│                                          │  │ Ask Lyra...  │ →  │
└──────────────────────────────────────────┴──────────────────────┘
```

<br/>

---

<br/>

## Features

<br/>

### ✦ Lyra — an AI that reads with you

> *"No corporate AI energy. No 'As an AI...' garbage. Just sharp, direct, and actually useful."*

Lyra is your AI companion. She's not a chatbot bolted onto a PDF viewer. She's built into the reading experience:

- **She can see what you're reading** — send her the current page as an image (works with comics, diagrams, charts, anything visual)
- **Select any text → Ask Lyra** — highlight a sentence, click, and she's already on it
- **She has a real voice** — powered by ElevenLabs neural TTS, not robotic browser speech
- **Fully customizable persona** — rename her, rewrite her personality, make her whoever you need

<br/>

### 🖥 Runs completely local (or cloud — your choice)

| Provider | Models | Private | Cost |
|----------|--------|---------|------|
| **Ollama** | Llama 3.2, Mistral, DeepSeek R1, Phi-3... | ✅ 100% local | Free |
| **OpenAI** | GPT-4o, GPT-4o Mini | ☁ API | Pay-per-use |
| **Anthropic** | Claude Opus, Sonnet, Haiku | ☁ API | Pay-per-use |

No internet required if you use Ollama. Your books, your conversations, your data — all stay on your machine.

<br/>

### 📖 Reading experience

- **Eye-safe dark mode** — warm amber-toned dark themes, no harsh blue light
- **5 highlight colors** — paint text, click to remove, persists per book
- **Remembers where you left off** — opens to your exact scroll position, every time
- **Comic/manga mode** — lazy-loads pages so it never lags, even on 400-page volumes
- **Focus mode** — strips every distraction, just text and Lyra
- **Fonts** — Lora, Georgia, system serif, monospace — pick your reading style
- **Column width** — Narrow / Normal / Wide / Full

<br/>

### 🔊 Voice — ElevenLabs

Lyra can read her responses aloud. Neural voices, not the robotic browser fallback. Two voices built in, switchable in settings.

<br/>

---

<br/>

## AI Setup

### Option A — Ollama (Recommended, fully free)

```bash
# 1. Install Ollama
# Windows: winget install Ollama.Ollama
# Or download from https://ollama.com

# 2. Start it
ollama serve

# 3. In Folio → Settings → Models → pick a model → click Get
```

**Recommended models by RAM:**

```
4 GB RAM  →  Llama 3.2 1B  (fastest)
6 GB RAM  →  Llama 3.2 3B  ← best balance
8 GB RAM  →  Mistral 7B
12 GB RAM →  Llama 3.1 8B or DeepSeek R1 7B
```

<br/>

### Option B — OpenAI / Anthropic

1. Get an API key from [platform.openai.com](https://platform.openai.com) or [console.anthropic.com](https://console.anthropic.com)
2. Open Folio → Settings → AI → paste your key
3. Pick a model

> **Vision bonus:** OpenAI and Anthropic models can see the page you're reading. Lyra gets sent the current page as an image when you ask her about it. Ollama doesn't support this (yet).

<br/>

---

<br/>

## Keyboard shortcuts

| Key | Action |
|-----|--------|
| `F11` | Toggle Focus mode |
| `⌘/Ctrl + A` | Toggle Lyra panel |
| `Esc` | Close panels / Exit focus |
| `Select text` | Paint highlight or Ask Lyra |

<br/>

---

<br/>

## Build

```bash
# Clone
git clone https://github.com/Sabbirrahman43/folio.git
cd folio

# Install
npm install

# Dev mode (Vite hot reload + Electron)
npm run dev       # terminal 1
npm run electron  # terminal 2

# Build Windows installer
npm run build
# → release/Folio Setup 1.0.0.exe
```

**Requirements:** Node.js 18+, Windows 10/11 x64

<br/>

---

<br/>

## Stack

```
Electron 31     →  Desktop shell
React 18        →  UI
Vite 5          →  Build
Tailwind CSS    →  Styling
PDF.js          →  PDF rendering + text extraction
Ollama API      →  Local LLM inference
ElevenLabs API  →  Neural TTS
OpenAI API      →  GPT-4o (optional)
Anthropic API   →  Claude (optional)
```

<br/>

---

<br/>

## Roadmap

- [ ] EPUB support
- [ ] Book library / shelf view
- [ ] Lyra chat history per book
- [ ] Export highlights as Markdown
- [ ] Linux & macOS builds
- [ ] Ollama vision (when model support matures)

<br/>

---

<br/>

<div align="center">

Built by **[Sabbir Rahman](https://github.com/Sabbirrahman43)** · Bangladesh 🇧🇩

*If this saved you from reading alone, drop a ⭐*

<br/>

**[⬇ Download for Windows](https://github.com/Sabbirrahman43/Folio-5/releases)**

</div>
