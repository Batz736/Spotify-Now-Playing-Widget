# 🎵 Spotify Now Playing Widget

> A clean, professional "Now Playing" display for your Spotify account. Designed for streamers, content creators, and anyone who wants to share what they're listening to.

---


## ✨ Features

| Feature | Description |
|---------|-------------|
| 🎵 **Track Display** | Shows song title, artist, album, and release year |
| 🎨 **Auto-Theming** | Pulls accent colors from album art for a coordinated look |
| 🔄 **Live Updates** | Refreshes automatically as your music changes |
| ⏱️ **Progress Bar** | Visual playback progress with elapsed/total time |
| 🎙️ **Podcast Support** | Works with both music tracks and podcast episodes |
| 🖼️ **OBS Ready** | Transparent background designed for browser overlays |
| 🕐 **Local Clock** | Displays current time in your configured timezone |
| 🎭 **Pause Indicator** | Shows a clear "PAUSED" state when playback stops |
| 🎬 **Smart Marquee** | Track titles scroll only if they overflow; otherwise stay static |

---

## 🚀 Quick Start Guide

> 💡 **Estimated time**: 15-20 minutes | **Skill level**: Beginner-friendly

### Step 1: Create a Spotify Developer App

1. Visit the [Spotify Developer Dashboard](https://developer.spotify.com/dashboard)
2. Log in with your Spotify account
3. Click **"Create an App"**
4. Fill in the details:
   - **App name**: `My Now Playing Widget` (or your choice)
   - **App description**: `Personal widget to display currently playing track`
   - ✅ Check the agreement box
5. Click **Create**
6. Go to **Settings** → Scroll to **Redirect URIs**
7. Add: `https://batz736.github.io/Spotify-Now-Playing-Widget/configure/`
8. Click **Add** → **Save**
9. Copy your **Client ID** and **Client Secret** (keep these private!)

### Step 2: Get Your Access & Refresh Tokens

> 🔑 Tokens authenticate the widget to read your playback data.

1. Visit this URL in your browser (replace `YOUR_CLIENT_ID`):
