# 🎸 Spotify Now Playing Widget

A glitch-style Spotify "Now Playing" widget for OBS/streaming.  
Features: dynamic color extraction, smart marquee text, genre display, and paused overlay. it works for Premium and Free Users

Make sure to edit everything yourself including your own time zone

## ⚙️ How to Customize

1. Download `index.html`
2. Open it in a text editor (Notepad, VS Code, etc.)
3. Edit the **4 lines** at the top of the `<script>` tag:

```javascript
const CONFIG_USER_ID = "your_spotify_user_id";
const CONFIG_ACCESS_TOKEN = "your_access_token";
const CONFIG_REFRESH_TOKEN = "your_refresh_token";
const CONFIG_REFRESH_URL = "https://yoursite.com/refresh_token.php";
