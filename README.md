# 🎵 Spotify Now Playing Widget (Premium Users Only)

> A clean, professional "Now Playing" display for your Spotify account. Designed for streamers, content creators, and anyone who wants to share what they're listening to.

![Widget Preview](https://i.imgur.com/EMjinIo.png)

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


## 🚀 Quick Start (No Coding Required!)

Follow these 3 simple steps to get your widget running in under 5 minutes.

### Step 1: Create a Spotify App
*You need this so Spotify knows it's okay to share your music info with the widget.*

1. Go to the [Spotify Developer Dashboard](https://developer.spotify.com/dashboard).
2. Log in with your Spotify account.
3. Click **"Create App"**.
   - **App Name:** `Batista736's Spotify Widget` .
   - **App Description:** `Widget for my stream`.
   - **Redirect URI:** This is important! Paste exactly this:
     ```text
     https://batz736.github.io/Spotify-Now-Playing-Widget/configure/
     ```
**Which API/SDKs are you planning to use?** Check Web API 
     
4. Click **Save**.
5. On the next screen, click **"Settings"** (top right).
6. Find **Client ID** and click **"View Client Secret"**.
   - 👉 **Copy both of these codes.** You will need them in Step 2.

### Step 2: Generate Your Widget Link
*Use our easy tool to connect your account securely.*

1. Click here to open the **[Configuration Tool](https://batz736.github.io/Spotify-Now-Playing-Widget/configure/)**.
2. Paste your **Client ID** and **Client Secret** into the boxes.
3. Click **"Connect Spotify"**.
4. A Spotify window will pop up asking for permission. Click **"Agree"**.
5. You will see a green **"Authorization Complete"** screen.
6. Click the big green **" Copy Link"** button.

### Step 3: Add to OBS
1. Open OBS Studio.
2. In the **Sources** box, click the **+** icon and select **Browser**.
3. Name it `Spotify Widget` and click OK.
4. In the **URL** field, **Paste** the link you copied in Step 2.
5. Set **Width** to `400` and **Height** to `600`.
6. Click **OK**.

🎉 **Done!** Play a song on Spotify, and it should appear on your stream!

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
```
Replace 'America/Chicago' with your city's code from the list below:

```javascript
New York / Miami
'America/New_York'
Los Angeles / Seattle
'America/Los_Angeles'
London / UK
'Europe/London'
Paris / Berlin
'Europe/Paris'
Tokyo
'Asia/Tokyo'
Sydney
'Australia/Sydney'
```
Save the file and refresh your Browser Source in OBS.
---

## ❓ Troubleshooting

| Problem | Solution |
| :--- | :--- |
| **Widget says "Waiting..."** | 1. Make sure Spotify is actually playing music.<br>2. Did you wait 10 seconds? It takes a moment to load.<br>3. Try refreshing the Browser Source in OBS (Right-click source → Refresh). |
| **Clock is wrong** | You skipped the "Fix Your Clock Timezone" step above! Go back and edit the `index.html` file. |
| **Colors aren't changing** | This is normal if you are testing locally. Once hosted on GitHub Pages or OBS, it usually works fine. |
| **Token Expired Error** | The link generated in Step 2 lasts for **1 hour**. If it stops working after an hour, just go back to the [Configuration Tool](https://batz736.github.io/Spotify-Now-Playing-Widget/configure/) and generate a new link. |
---

## ❓ Do I Need to Edit the Code?

**Short answer: No!** 

If you use the **[Configuration Tool](https://batz736.github.io/Spotify-Now-Playing-Widget/configure/)**, the widget will work immediately—**no code editing required**.

### How It Works:
1. The Config Tool generates a special URL like: https://batz736.github.io/Spotify-Now-Playing-Widget?uid=123&token=abc&cid=xyz
2. You paste that URL into OBS.
3. The widget automatically reads your credentials from the URL parameters.
4. ✨ It just works!

### When Would You Edit the Code?
Only if you want to:
- 🔁 Set up **permanent auto-refresh** (requires PHP backend)
- 💻 Host the files on your own server
- 🛠️ Customize the widget's appearance or behavior

For 99% of users, the Config Tool is all you need!
---

## 🔐 Security Reminder

| Method | Where Tokens Are Stored | Token Expiry |
|--------|------------------------|--------------|
| **Config Tool (Easy)** | In the OBS Browser Source URL | ~1 hour (reconnect to refresh) |
| **Hardcoded + PHP (Advanced)** | In `index.html` + server-side PHP script | Forever (auto-refreshes) |

> ⚠️ **Never commit real tokens to a public GitHub repo!** If you hardcode values, use a **private repository** or environment variables.

---

## ✅ Summary for Your Users

1. **Go to [Config Tool](https://batz736.github.io/Spotify-Now-Playing-Widget/configure/)** → Enter credentials → Connect Spotify → Copy Link → Paste in OBS → **Done!** 🎉
2. **Don't touch the code** unless you want permanent auto-refresh or custom tweaks.
3. **Only edit `index.html`** if you need to change the timezone (search for `America/Chicago`).

> That's it! 🎵✨
