# TTS Pronunciation Practice

Desktop app for practicing English pronunciation with Text-to-Speech and IPA. Includes an English–Bangla dictionary.

<img width="639" height="745" alt="Image" src="https://github.com/user-attachments/assets/8ea55153-e1d5-4683-9ca9-c137c7c962be" />

## Features

- **TTS** – Hear words/phrases with system voices
- **IPA** – Phonetic transcription (CMU Dict)
- **Bangla** – English-to-Bangla meanings
- **Clipboard** – Optional: speak/show IPA when you copy text
- **History** – Recent words; settings for rate, volume, voice

## Quick Start

```bash
git clone https://github.com/needyamin/tts-pronunciation-practice.git
cd tts-pronunciation-practice
npm install
npm start
```

## Build

| Platform | Command | Output |
|----------|---------|--------|
| **Windows** (portable exe) | `npm run dist` | `dist/TTS Pronunciation Practice 1.0.0.exe` |
| **Linux** (AppImage) | `npm run dist:linux:docker` | `dist/TTS Pronunciation Practice-1.0.0.AppImage` |

### Linux AppImage (on Windows)

Use Docker. One command from project root:

```bash
npm run dist:linux:docker
```

Or manually:

```bash
docker build -f Dockerfile.linux-build -t tts-pronunciation-linux-builder .
docker run --rm -v "y:/Projects/tts-pronunciation-practice/dist:/app/dist" tts-pronunciation-linux-builder
```

Output: `dist/TTS Pronunciation Practice-1.0.0.AppImage` (~101 MB). Requires Docker Desktop.

**Alternatives:** Enable Windows Developer Mode, or run PowerShell as Administrator, then `npm run dist:linux`. Or use GitHub Actions to build on Linux.

### Using the Linux AppImage

1. Download `TTS Pronunciation Practice-1.0.0.AppImage`
2. `chmod +x "TTS Pronunciation Practice-1.0.0.AppImage"`
3. `./"TTS Pronunciation Practice-1.0.0.AppImage"`

No install needed. Needs Linux kernel 3.10+, GLIBC 2.17+, X11 or Wayland.

## Tech

Electron · Web Speech API · CMU Pronouncing Dictionary · Bangla dictionary (asset)

## License

ISC
