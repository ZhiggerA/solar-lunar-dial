# ☀️🌙 Solar & Lunar Dial

A glassmorphism desktop widget that shows where the sun and moon are right now: a 24-hour astronomical clock with live twilight phases, moon phases, weather, and eclipse previews. Runs in any browser, or as a frameless Windows 11 desktop widget.

[![Live Demo](https://img.shields.io/badge/Live%20Demo-Open%20Widget-38bdf8?style=for-the-badge)](https://zhiggera.github.io/solar-lunar-dial/)
[![License: MIT](https://img.shields.io/badge/License-MIT-fbbf24?style=for-the-badge)](LICENSE)

**👉 [Try it in your browser](https://zhiggera.github.io/solar-lunar-dial/)**, no install needed.

<p align="center">
  <img src="docs/screenshot.png" alt="Solar & Lunar Dial widget showing the 24-hour sun and moon dial, weather card, and sunrise and sunset times" width="420">
</p>

---

## ✨ Features

- **24-hour sun & moon dial**: the sun travels around the dial in real time, and the sky wedge shows exactly when it's daylight at your location.
- **Accurate twilight phases**: Night, Astronomical, Nautical and Civil dawn/dusk, Sunrise, Golden Hour, and Day, with sky colors that blend between them.
- **Moon phases**: illumination percentage, phase name, traditional full moon names (Harvest Moon, Wolf Moon…), and Super/Micro Moon detection.
- **Live weather**: current temperature, daily high/low, and animated clouds, rain, or snow drawn right on the dial.
- **Time travel**: scroll or drag the dial to move through time and watch the sky change. Weather follows along, using forecasts up to 14 days ahead and historical data for past dates.
- **Eclipse previews**: jump to upcoming solar and lunar eclipses (2027–2028) to see a total eclipse or a blood moon on the dial.
- **Any city in the world**: search by name or use GPS.
- **4 layouts**: Full, Deskbar (wide), Compact, and Pure Orb.
- **Hover-to-wake**: the widget fades out when your mouse leaves and wakes up when you hover over it.
- **Ghost Chrome**: optionally hides the extra cards when idle, leaving only the dial.
- **Fully customizable**: idle and active opacity, glass tint, scale, and which panels to show.
- **Remembers your settings** between visits.
- **Native Windows 11 widget**: build a borderless desktop `.exe` with a system tray icon, right from the widget.

---

## 🧭 How to read the dial

| Part | What it shows |
| --- | --- |
| **Outer ring** | A 24-hour clock with **noon at the top** and **midnight at the bottom** |
| **Colored wedge** | Daylight, from sunrise to sunset. Its color matches the current sky |
| **Sun** ☀️ | The current time on the 24-hour ring |
| **Moon** 🌙 | Its distance from the sun around the ring shows the current moon phase |
| **Inner dial** | A regular 12-hour clock with a sweeping second hand |
| **Top pill** | The current sky phase and moon phase |

---

## 🖱️ Controls

| Action | How |
| --- | --- |
| Travel through time | **Scroll** on the dial, or **drag** around it |
| Jump to sunrise / noon / sunset | Click the times in the bottom strip |
| Preview an eclipse | Click **Eclipse** (click again for the next one) |
| Go to a specific date | Use the date picker |
| Back to the present | Click **Live Now** |
| Change city | Click the city name, type, press **Enter** |
| Use your location | Click the 🎯 GPS icon |
| Change layout | Click the ⊞ icon (top left, on hover) |
| Open settings | Click the ⚙️ icon (top right, on hover) |
| Move the widget | Drag the bar at the top (double-click to re-center) |
| Resize | Drag the bottom-right corner. Stretch it sideways to switch to Deskbar |

---

## 💻 Install as a Windows 11 desktop widget

Open the [live widget](https://zhiggera.github.io/solar-lunar-dial/), set it up the way you like, then click **⬇ Get Win11 .EXE**. Your current settings are baked into the build. There are three options:

### Option 2: PowerShell (recommended)
1. Click **1. Get .HTML** to download `SolarLunarWidget.html`.
2. Click **2. Copy PS Command**.
3. Open **Windows PowerShell**, paste, and press **Enter**.

`SolarLunarWidget.exe` appears on your Desktop and launches automatically.

### Option 1: One-click .bat
Click **Download Frameless .EXE Builder (.bat)** and double-click the downloaded file. Windows may show a SmartScreen warning since the file isn't signed; click **More info → Run anyway**.

### Option 3: Electron transparent overlay
For a fully see-through overlay. Requires [Node.js](https://nodejs.org) to be installed.

### Requirements
- Windows 10 or 11
- [Microsoft Edge WebView2 Runtime](https://developer.microsoft.com/microsoft-edge/webview2/) (preinstalled on Windows 11)
- An internet connection for the first build

### Using the desktop widget
- **Right-click the tray icon** for Always on Top, Center on Screen, and Exit.
- Drag anywhere on the widget's background to move it. Its position is remembered.

### Uninstall
Exit the widget from the tray icon, then delete:
- `SolarLunarWidget.exe` from your Desktop
- The folder `%LOCALAPPDATA%\SolarLunarWidget` (paste that path into File Explorer's address bar)

> 🔒 Curious what the build scripts do before running them? See [SECURITY.md](SECURITY.md) for a step-by-step explanation. No admin rights are needed and nothing is installed system-wide.

---

## <img src="docs/Screenshot_PureOrb.png" width="22" alt=""> Layouts

| Layout | Best for |
| --- | --- |
| **Full** | The complete experience with all cards |
| **Deskbar** | Wide screens, sitting along the top or bottom of your desktop |
| **Compact** | Smaller screens. Hides the telemetry strip |
| **Pure Orb** | A minimal round watch face. Hover to see the time and temperature |

---

## 🔐 Privacy

The widget has no tracking or analytics, and your settings are stored only in your own browser. It contacts:

- [Open-Meteo](https://open-meteo.com) for weather, using your chosen location's coordinates
- [Nominatim / OpenStreetMap](https://nominatim.org) only when you search for a city
- Your browser's location service only when you click the GPS icon

---

## 🛠️ Built with

- Plain HTML, CSS, and JavaScript in a **single file**, with no build step
- [SunCalc](https://github.com/mourner/suncalc) for sun and moon positions
- [Open-Meteo](https://open-meteo.com) for weather data
- [Tailwind CSS](https://tailwindcss.com) for some styling
- [Microsoft WebView2](https://developer.microsoft.com/microsoft-edge/webview2/) for the native Windows app

### Run it locally
```bash
git clone https://github.com/zhiggera/solar-lunar-dial.git
cd solar-lunar-dial
python -m http.server 8000
```
Then open http://localhost:8000. Add `?desktop=1` to the URL to preview desktop-app mode.

---

## 🤝 Contributing

Bug reports, ideas, and pull requests are welcome! Please read [CONTRIBUTING.md](CONTRIBUTING.md) first.

- 🐞 [Report a bug](https://github.com/zhiggera/solar-lunar-dial/issues/new?template=bug_report.yml)
- ✨ [Suggest a feature](https://github.com/zhiggera/solar-lunar-dial/issues/new?template=feature_request.yml)
- ♿ See [ACCESSIBILITY.md](ACCESSIBILITY.md) for known accessibility limitations and how to report barriers
- 📜 This project follows a [Code of Conduct](CODE_OF_CONDUCT.md)

---

## 📄 License

[MIT](LICENSE) © 2026 zhiggera
