# 🎵 Navidrome Power Plugins Pack

> A curated collection of the most powerful community plugins for Navidrome — with clear installation guides, configuration steps, and real-world usage examples.

This repository brings together essential plugins that enhance lyrics, Discord integration, and AI-powered music discovery.

---

# 📦 Included Plugins

- **LRCLIB Lyrics Integration**
- **Discord Rich Presence**
- **AudioMuse AI Music Intelligence**

Each section below explains what it does, why you want it, and how to install and use it properly.

---

# 🧩 1. Lyrics Automation — navidrome-lrclib-plugin

Automatically fetch and store song lyrics using an LRCLIB-compatible server.

### 🚀 What It Does

- Retrieves lyrics from an LRCLIB service
- Stores lyrics in Navidrome metadata
- Works during library scanning
- Enables lyrics display in compatible clients

### 📥 Installation

1. Download the `.ndp` file from:
   https://github.com/kepelet/navidrome-lrclib-plugin
2. Place the file in your Navidrome `plugins` directory.
3. Open Navidrome Admin.
4. Go to **Plugins → Rescan**.
5. Enable the plugin.

### ⚙️ Configuration

- Set your LRCLIB server URL in plugin settings.
- Trigger a **library rescan** to fetch lyrics.

### 🧠 When To Use

- If your music library does not include embedded lyrics.
- If you want automatic lyrics management.
- If you use clients that support lyrics display.

---

# 🎮 2. Discord Integration — discord-rich-presence-plugin

Show what you're listening to in real-time on Discord.

### 🚀 What It Does

- Displays track name, artist, and album art
- Shows playback progress
- Automatically clears when music stops
- Per-user configuration support

### 📥 Installation

1. Download the `.ndp` file from:
   https://github.com/navidrome/discord-rich-presence-plugin
2. Place it in your `plugins` directory.
3. Admin → **Plugins → Rescan**
4. Enable the plugin.

### ⚙️ Configuration

- Enter your Discord user token in the plugin settings.
- Start playback in Navidrome.
- Your Discord status updates automatically.

### 🧠 When To Use

- If you want social presence while listening.
- If you share music with friends.
- If you want a Spotify-like Discord integration for Navidrome.

---

# 🤖 3. AI Music Discovery — AudioMuse-AI-NV-plugin

Bring AI-powered music intelligence into Navidrome.

### 🚀 What It Does

- Instant Mix based on audio similarity
- Artist similarity discovery
- AI-powered radio mode
- Advanced music enrichment

### 📥 Installation

1. Download the `.ndp` file from:
   https://github.com/NeptuneHub/AudioMuse-AI-NV-plugin
2. Place it in your `plugins` directory.
3. Admin → **Plugins → Rescan**
4. Enable the plugin.

### ⚙️ Configuration

1. Install and run AudioMuse-AI backend.
2. Configure the API endpoint inside plugin settings.
3. Use supported clients to access AI features.

### 🧠 When To Use

- If you want Spotify-style recommendations.
- If you enjoy discovering similar tracks.
- If you want AI-driven playlist generation.

---

# 🛠 Full Installation Workflow (All Plugins)

```bash
# Example default plugins path
/var/lib/navidrome/plugins
