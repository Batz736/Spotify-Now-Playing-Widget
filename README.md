# 🎵 Spotify Now Playing Widget

> A clean, professional "Now Playing" display for your Spotify account. Designed for streamers, content creators, and anyone who wants to share what they're listening to.

---

## 🔗 Quick Links

| Link | Description |
|------|-------------|
| **[⚙️ Configuration Tool](https://batz736.github.io/Spotify-Now-Playing-Widget/configure/)** | **START HERE!** Use this easy tool to generate your tokens and get your custom widget URL. |
| **[📺 Live Widget Demo](https://batz736.github.io/Spotify-Now-Playing-Widget)** | The actual widget page. Copy this URL into OBS or your browser. |

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

## 🚀 How to Set Up (Easy Mode)

You don't need to be a coder to use this! Follow these 3 simple steps:

### Step 1: Generate Your Credentials
1. Click the **[Configuration Tool](https://batz736.github.io/Spotify-Now-Playing-Widget/configure/)**.
2. Follow the on-screen instructions to log in with Spotify.
3. The tool will generate your **User ID**, **Access Token**, and **Refresh Token**.
4. **Copy** the final "Widget URL" provided by the tool.

### Step 2: Add to OBS (for Streamers)
1. Open OBS Studio.
2. In the **Sources** dock, click **+** and select **Browser**.
3. Name it "Spotify Widget" and click OK.
4. In the **URL** field, paste the **Widget URL** you got from Step 1.
5. Set **Width** to `400` and **Height** to `600`.
6. Click **OK**. You should see your widget appear! 🎉

### Step 3: Test It
1. Play a song on Spotify (Desktop or Web).
2. Wait about 10–15 seconds.
3. The widget should update with your album art, title, and progress bar.

---

## 🕐 IMPORTANT: Change the Clock to YOUR Timezone ⏰

> ⚠️ **By default, the clock is set to Chicago Time (CDT).**  
> You likely want to change this to match **your local time** so your viewers see the correct clock!

### How to Change Your Timezone (Takes 30 Seconds)

1. Open the `index.html` file in any text editor (Notepad, TextEdit, VS Code, etc.).
2. Press `Ctrl+F` (Windows) or `Cmd+F` (Mac) to open the search bar.
3. Search for this exact text:  
   **`America/Chicago`**
4. You will find a section of code that looks like this:

```javascript
function updateClock() {
    const now = new Date();
    // 12-hour format, CDT (America/Chicago)
    const timeString = now.toLocaleTimeString('en-US', { 
        timeZone: 'America/Chicago',  // <--- CHANGE THIS LINE
        hour12: true, 
        hour: '2-digit', 
        minute: '2-digit', 
        second: '2-digit' 
    });
    els.clock.textContent = `${timeString} CDT`; // <--- AND UPDATE THIS LABEL
}
