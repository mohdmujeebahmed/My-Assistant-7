
## ⭐ Star the Repository

If you like the project, consider giving it a ⭐ on GitHub.

It helps the project grow and motivates future development.

```text
███████╗ ████████╗ █████╗ ██████╗
██╔════╝ ╚══██╔══╝██╔══██╗██╔══██╗
█████╗      ██║   ███████║██████╔╝
██╔══╝      ██║   ██╔══██║██╔══██╗
███████╗    ██║   ██║  ██║██║  ██║
# ⚡ J.A.R.V.I.S — AI CORE

<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:ff8c42,50:ff5a5a,100:4fd1ff&height=220&section=header&text=J.A.R.V.I.S&fontSize=70&fontColor=ffffff&animation=fadeIn&fontAlignY=35&desc=Your%20Personal%20AI%20Command%20Interface&descAlignY=58&descSize=18" width="100%"/>

<br>

### `⚡ PERSONAL AI • VOICE CONTROL • COMMAND EXECUTION • FUTURISTIC UI`

<br>

<img src="https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white"/>
<img src="https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white"/>
<img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black"/>
<img src="https://img.shields.io/badge/Web_Speech_API-FF8C42?style=for-the-badge&logo=googlechrome&logoColor=white"/>
<img src="https://img.shields.io/badge/Responsive-4FD1FF?style=for-the-badge&logo=csswizardry&logoColor=white"/>

<br><br>

**A cinematic browser-based J.A.R.V.I.S-inspired AI interface with voice recognition, speech synthesis, animated system states, live audio visualization, command routing, and a futuristic HUD.**

<br>

[✨ Features](#-features) •
[🚀 Getting Started](#-getting-started) •
[🎙 Voice Commands](#-voice-commands) •
[🧠 How It Works](#-how-it-works) •
[🎨 UI](#-visual-system) •
[🔮 Roadmap](#-roadmap)

</div>

---

## 🖥️ The Experience

> **"Good evening, sir. All systems are nominal."**

J.A.R.V.I.S transforms a normal browser page into a futuristic AI command center.

The interface combines:

- 🌀 Animated AI core
- ✨ Particle background
- 📡 HUD scanline effects
- 🎙 Real-time microphone visualization
- 🗣 Browser speech recognition
- 🔊 Text-to-speech responses
- 🌐 Voice-controlled website launching
- ⚙️ Animated command execution
- 📊 Live activity monitoring
- 🧠 Local command routing
- 📱 Responsive mobile interface

The main interface contains a central animated core, system-status panels, activity monitoring, command input, and voice controls.

---

# ✨ Features

## 🌀 Cinematic AI Core

The center of the interface is an animated multi-ring AI core.

It contains:

```text
                 ╭──────────────╮
             ╭───┤   ORBITAL    ├───╮
           ╱     │     RINGS      │    ╲
          │      │                │     │
          │      │    ◉ CORE      │     │
          │      │                │     │
           ╲     │   J.A.R.V.I.S  │    ╱
             ╰───┤                ├───╯
                 ╰──────────────╯
```

The core dynamically changes state:

| State | Visual |
|---|---|
| `ONLINE` | Normal idle animation |
| `LISTENING` | Voice-reactive animation |
| `PROCESSING` | Accelerated rings |
| `EXECUTING` | Command execution state |
| `RESPONDING` | Speaking animation |
| `COMPLETE` | Completion state |

The project implements multiple independently animated rings, orbiting particles, glowing center effects, and state-dependent animation speeds.

---

# 🎙️ Voice Control

Click the microphone and talk naturally.

J.A.R.V.I.S uses the browser's:

```javascript
SpeechRecognition
```

to process voice commands.

Example:

```text
"Open GitHub"

"Open YouTube"

"Open my resume"

"Hello"

"Who are you?"

"What can you do?"

"What time is it?"
```

The microphone state changes the interface into:

```text
┌─────────────────────────────┐
│                             │
│         LISTENING           │
│            ...              │
│                             │
│       ◉  ◉  ◉  ◉  ◉        │
│                             │
└─────────────────────────────┘
```

The project also connects the microphone stream to an `AnalyserNode`, allowing the visualizer to react to actual audio amplitude instead of using a completely fake animation.

---

# 🔊 J.A.R.V.I.S Can Talk

Responses are spoken directly through the browser using:

```javascript
SpeechSynthesisUtterance
```

The voice is configured with a slightly lower pitch and natural speaking rate to create a more assistant-like response.

Example:

```text
YOU:
    Open GitHub

J.A.R.V.I.S:
    Processing...

    TARGET: GITHUB
    EXECUTING...
    ✓ CONNECTION ESTABLISHED
    ✓ BROWSER LAUNCHED
    ✓ GITHUB OPENED

    "Opening GitHub."
```

---

# 🌐 Website Commands

J.A.R.V.I.S currently includes command routes for:

| Command | Action |
|---|---|
| `open resume` | Opens the configured resume website |
| `open YouTube` | Opens YouTube |
| `open GitHub` | Opens GitHub |
| `play my favorite song` | Opens the configured song |
| Unknown command | Returns a voice response |

These routes are defined in the `ROUTES` command system.

### Adding another website

Simply add a new route:

```javascript
{
    test: t => /spotify/.test(t),
    name: "Spotify",
    url: "https://spotify.com"
}
```

Now J.A.R.V.I.S understands:

```text
"Open Spotify"
```

---

# 🧠 Conversational Commands

J.A.R.V.I.S isn't limited to opening websites.

It has a small conversational command engine:

```javascript
const TALK = [
    {
        test: t => /^(hi|hello|hey|yo)\b/.test(t),
        reply: () => pick([
            "Hello, sir.",
            "Hey there.",
            "Good to hear from you."
        ])
    }
];
```

Current conversational capabilities include:

- 👋 Greetings
- 🤖 Identity
- ❤️ Thanks
- 👋 Goodbye
- 🕐 Time
- 🧑‍💻 Capabilities

The conversational responses and capability scanner are implemented directly in the command-processing layer.

---

# ⚙️ Command Execution HUD

Every command passes through a visual execution sequence.

```text
COMMAND RECEIVED
        ↓
   PROCESSING
        ↓
   OPEN_URL
        ↓
 TARGET: GITHUB
        ↓
   EXECUTING...
        ↓
✓ CONNECTION ESTABLISHED
        ↓
✓ BROWSER LAUNCHED
        ↓
✓ GITHUB OPENED
        ↓
    COMPLETE
```

This creates the feeling of interacting with an actual AI operating system rather than a normal webpage.

---

# ✨ Visual System

The interface uses several layered visual effects.

### Particle Field

A continuously running `<canvas>` creates floating particles behind the interface.

### Scanlines

A subtle scanline overlay gives the HUD a futuristic display effect.

### Vignette

A radial vignette focuses attention toward the AI core.

### HUD Corners

Four animated-interface-style corner brackets frame the screen.

### Glass Panels

System and activity panels use:

```css
backdrop-filter: blur(14px);
```

combined with translucent borders and shadows to create a glass HUD appearance.

---

# 📊 Live System Monitor

The left panel provides system information:

```text
SYSTEMS

● AI CORE       ONLINE
● VOICE         READY
● BROWSER       READY
● AUTOMATION    READY
● MEMORY        LOCAL
```

The right panel displays recent activity:

```text
ACTIVITY

00:32  GitHub opened
00:31  Said: "Hello, sir."
00:29  Listed capabilities
00:27  YouTube opened
```

The activity log automatically keeps only the most recent entries.

---

# 🚀 Getting Started

## 1. Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/jarvis-ai.git
```

## 2. Enter the project

```bash
cd jarvis-ai
```

## 3. Open the application

You can simply open:

```text
index.html
```

in a modern browser.

For the best experience, use:

- Google Chrome
- Microsoft Edge

especially for browser speech-recognition support.

---

# 🎙️ Microphone Permissions

The browser may ask for microphone permission.

Select:

```text
Allow microphone access
```

If permission is blocked, J.A.R.V.I.S automatically falls back to typed commands.

The application also displays:

```text
READY
LISTENING
BLOCKED
ERROR
UNAVAILABLE
```

depending on browser microphone/recognition status.

---

# 🧩 Project Structure

```text
jarvis-ai/
│
├── index.html
└── README.md
```

Everything is currently contained inside a single HTML file:

```text
HTML
 ├── Interface
 ├── CSS
 │    ├── HUD
 │    ├── Animations
 │    ├── AI Core
 │    └── Responsive UI
 │
 └── JavaScript
      ├── Particles
      ├── Commands
      ├── Speech Recognition
      ├── Speech Synthesis
      ├── Audio Analyzer
      ├── Activity System
      └── State Machine
```

---

# 🧠 How It Works

The application follows a simple state-driven architecture:

```text
                 ┌─────────────┐
                 │     IDLE    │
                 └──────┬──────┘
                        │
                        ▼
                 ┌─────────────┐
                 │  LISTENING  │
                 └──────┬──────┘
                        │
                        ▼
                 ┌─────────────┐
                 │  PROCESSING │
                 └──────┬──────┘
                        │
                 ┌──────┴──────┐
                 ▼             ▼
          ┌────────────┐ ┌────────────┐
          │ EXECUTING  │ │ RESPONDING │
          └─────┬──────┘ └──────┬─────┘
                │               │
                └───────┬───────┘
                        ▼
                 ┌─────────────┐
                 │  COMPLETE   │
                 └──────┬──────┘
                        │
                        ▼
                 ┌─────────────┐
                 │     IDLE    │
                 └─────────────┘
```

The central `runCommand()` function determines whether a request is conversational, capability-related, or a website route, then updates the visual state accordingly.

---

# 🎨 Tech Stack

### Frontend

- HTML5
- CSS3
- Vanilla JavaScript

### Browser APIs

- Web Speech API
- Speech Recognition
- Speech Synthesis
- Web Audio API
- Canvas API
- MediaDevices API

### Design

- Glassmorphism
- HUD interface
- CSS animations
- Canvas particles
- Responsive layout
- Audio-reactive visualization

### Fonts

- Sora
- Space Mono

---

# 🔥 Why This Project?

Most voice-assistant demos look like:

```text
[ Button ]

"Listening..."
```

J.A.R.V.I.S takes a different approach.

The goal is to make the **entire interface feel alive**.

The AI core reacts.

The HUD reacts.

The waveform reacts.

The activity panel reacts.

The execution log reacts.

The voice reacts.

Everything is designed to make a simple browser application feel like a futuristic command system.

---

# 🔮 Roadmap

## v1.0 — Current

- [x] Futuristic HUD
- [x] Animated AI core
- [x] Particle background
- [x] Voice recognition
- [x] Speech synthesis
- [x] Audio-reactive core
- [x] Command routing
- [x] Website launching
- [x] Activity monitor
- [x] Responsive layout

## v2.0 — Planned

- [ ] Real AI API integration
- [ ] Persistent conversation history
- [ ] Weather commands
- [ ] News commands
- [ ] Web search
- [ ] Music controls
- [ ] Custom wake word
- [ ] More browser automation
- [ ] User-configurable commands
- [ ] Custom AI personalities

## v3.0 — Future

```text
┌─────────────────────────────────────────┐
│             J.A.R.V.I.S                 │
│                                         │
│  VOICE ────────┐                        │
│                ▼                        │
│          ┌────────────┐                  │
│          │ AI ENGINE  │                  │
│          └─────┬──────┘                  │
│                │                         │
│       ┌────────┼────────┐                │
│       ▼        ▼        ▼                │
│    SEARCH   AUTOMATE   MEMORY            │
│       │        │        │                │
│       └────────┼────────┘                │
│                ▼                         │
│          COMMAND CENTER                  │
└─────────────────────────────────────────┘
```

---

# ⭐ Contributing

Contributions are welcome.

```bash
git checkout -b feature/my-feature
```

Make your changes, test them, and open a pull request.

Ideas for contributions:

- New commands
- New animations
- Better voice handling
- AI integrations
- New themes
- Mobile improvements
- Accessibility improvements

---

# ⚠️ Browser Compatibility

Voice recognition depends on browser support for the Web Speech API.

Recommended:

| Browser | Experience |
|---|---|
| 🟢 Chrome | Full |
| 🟢 Edge | Full |
| 🟡 Other Chromium browsers | Depends |
| 🔴 Unsupported browsers | Typed commands still work |

Microphone permissions are required for live voice visualization and speech recognition.

---

# 👨‍💻 Author

<div align="center">

### Built with ⚡ + ☕ + JavaScript

**J.A.R.V.I.S — AI CORE**

*"At your service, sir."*

<br>

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:4fd1ff,50:ff8c42,100:ff5a5a&height=120&section=footer&animation=fadeIn" width="100%"/>

</div>

---

## ⭐ Star the Repository

If you like the project, consider giving it a ⭐ on GitHub.

It helps the project grow and motivates future development.

```text
███████╗ ████████╗ █████╗ ██████╗
██╔════╝ ╚══██╔══╝██╔══██╗██╔══██╗
█████╗      ██║   ███████║██████╔╝
██╔══╝      ██║   ██╔══██║██╔══██╗
███████╗    ██║   ██║  ██║██║  ██║
╚══════╝    ╚═╝   ╚═╝  ╚═╝╚═╝  ╚═╝

        J.A.R.V.I.S ONLINE
```
