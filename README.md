# Lab4_CM2022 — HTML5 Sensor Fusion (Polar Verity Sense)

Web-based lab that streams accelerometer and gyroscope data from a **Polar Verity Sense** armband over Web Bluetooth, applies filtering and sensor fusion, and plots the results live on HTML5 canvases.

## Contents

| File | Description |
|------|-------------|
| `HTML5_PolarVeritySense.html` | Main application page (canvas plots, start/stop/save/load buttons) |
| `polar.js` | Polar Verity Sense SDK: Web Bluetooth connection, PMD control, streaming |
| `filter.js` | Filtering and sensor-fusion tasks (1A cadence, 1B roll, etc.) |

## Lab instructions

The full lab assignment is available here: [Assignment 4 CM2024 HT26.pdf](Assignment%204%20CM2024%20HT26.pdf)

## Run the app

### Online (GitHub Pages)

The app is published via GitHub Pages:

**https://jonaswillen.github.io/Lab4_CM2022/HTML5_PolarVeritySense.html**

> Web Bluetooth requires a **secure context (HTTPS)**, which GitHub Pages provides — this is why the app works when hosted on GitHub Pages but not when opened directly from a local file.

### Locally

Because of the Web Bluetooth HTTPS requirement, serve the files over HTTPS or use a local HTTPS server, then open `HTML5_PolarVeritySense.html` in your browser.

## Record and replay

Click **Start Record** to capture all incoming sensor data, then **Stop Record** to stop and automatically save the full recording as `6DOF.json`. The replay loops the recording through the same filtering pipeline (`filter()`) at the recorded sample rate of 52 Hz, updating the canvas plots just like live sensor data. Use **Stop sensor** to pause the replay.

**SensorLogger exports** are also supported: the same button accepts a `SensorLogger.json` file (iOS/Android SensorLogger app). It is converted automatically — accelerometer (m/s²) is used as-is and gyroscope (rad/s) is converted to deg/s to match the Polar stream — and then loops at 52 Hz the same way.

## Versioning

The app displays a small version number (e.g. `Version 0.01`) at the bottom of the page. Every merge to `main` bumps the version — the number shown on the [GitHub Pages site](https://jonaswillen.github.io/Lab4_CM2022/HTML5_PolarVeritySense.html) tells you whether the latest deployment is live.

| Version | Description |
|---------|-------------|
| 0.02 | Load and replay `SensorLogger.json` recordings (acc m/s², gyro rad/s → deg/s) |
| 0.01 | Start/Stop Record, full-length `6DOF.json` save, 52 Hz looping replay |

## Browser support

Web Bluetooth is required. Supported in Chrome, Edge, and Opera on desktop, and Chrome on Android (see [caniuse.com/web-bluetooth](https://caniuse.com/web-bluetooth)). Not supported in Firefox or Safari.
