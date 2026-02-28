# 🎵 Navidrome Power Plugins Pack

> A curated collection of powerful community plugins for Navidrome, organized with detailed descriptions and a unified installation guide.

This repository centralizes essential plugins that enhance:

- 🎤 Lyrics support  
- 🎮 Discord Rich Presence integration  
- 🤖 AI-powered music discovery  
- 🧠 ListenBrainz automation  

Designed for self-hosters who want to push Navidrome beyond the basics.

---

# 📚 Official Plugin Documentation

Before installing any plugin, review the official Navidrome plugin documentation:

🔗 https://www.navidrome.org/docs/usage/features/plugins/

---

## 🔗 Quick Links to Included Plugins

- 🧩 [navidrome-lrclib-plugin](https://github.com/kepelet/navidrome-lrclib-plugin)  
- 🎮 [discord-rich-presence-plugin](https://github.com/navidrome/discord-rich-presence-plugin)  
- 🤖 [AudioMuse-AI-NV-plugin](https://github.com/NeptuneHub/AudioMuse-AI-NV-plugin)  
- 🧠 [navidrome-listenbrainz-daily-playlist](https://github.com/kgarner7/navidrome-listenbrainz-daily-playlist)  

---

# 📦 Included Plugins

---

## 🧩 navidrome-lrclib-plugin  
🔗 https://github.com/kepelet/navidrome-lrclib-plugin  

Automatically fetches and stores song lyrics from an LRCLIB-compatible server during library scans.

### ✨ Features
- Retrieves lyrics from an external LRCLIB service  
- Saves lyrics into Navidrome metadata  
- Works during full or partial library scans  
- Makes lyrics available to compatible clients  
- Supports synchronized lyrics (when available)

### 💡 Why Use It?
Perfect for users who want a seamless, automatic lyrics experience without manually embedding `.lrc` files.

---

## 🎮 discord-rich-presence-plugin  
🔗 https://github.com/navidrome/discord-rich-presence-plugin  

Displays your currently playing track from Navidrome in Discord Rich Presence.

### ✨ Features
- Shows track name and artist  
- Displays album artwork  
- Shows real-time playback progress  
- Clears status automatically when playback stops  
- Supports per-user configuration  

### 💡 Why Use It?
Ideal for users who want to share their listening activity on Discord in real time.

---

## 🤖 AudioMuse-AI-NV-plugin  
🔗 https://github.com/NeptuneHub/AudioMuse-AI-NV-plugin  

Integrates AudioMuse-AI into Navidrome for AI-powered music recommendations and discovery.

### ✨ Features
- Instant Mix based on audio similarity  
- Artist similarity discovery  
- AI-powered radio mode  
- Intelligent metadata enrichment  

### 💡 Why Use It?
Great for users who want smarter music discovery without relying on external streaming services.

---

## 🧠 navidrome-listenbrainz-daily-playlist  
🔗 https://github.com/kgarner7/navidrome-listenbrainz-daily-playlist  

Automatically generates daily playlists in Navidrome based on your ListenBrainz listening history.

### ✨ Features
- Creates a fresh playlist every day  
- Uses ListenBrainz listening data  
- Personalized recommendations  
- Fully automated once configured  

### 💡 Why Use It?
Perfect for users who already scrobble to ListenBrainz and want dynamic, evolving playlists inside Navidrome.

---

# 🛠 Unified Installation Guide

Below is a generic installation workflow that works for most Navidrome plugins.

---

## 1️⃣ Locate Your Plugins Directory

Default example:

```bash
/var/lib/navidrome/plugins
