# Lab4_CM2022 — HTML5 Sensor Fusion (Polar Verity Sense)

Web-based lab that streams accelerometer and gyroscope data from a **Polar Verity Sense** armband over Web Bluetooth, applies filtering and sensor fusion, and plots the results live on HTML5 canvases.

## Contents

| File | Description |
|------|-------------|
| `HTML5_PolarVeritySense_HT25.html` | Main application page (canvas plots, start/stop/save buttons) |
| `polar.js` | Polar Verity Sense SDK: Web Bluetooth connection, PMD control, streaming |
| `filter.js` | Filtering and sensor-fusion tasks (1A cadence, 1B roll, etc.) |

## Lab instructions

The full lab assignment is available here: [Assignment 4 CM2024 HT26.pdf](Assignment%204%20CM2024%20HT26.pdf)

## Run the app

### Online (GitHub Pages)

The app is published via GitHub Pages:

**https://jonaswillen.github.io/Lab4_CM2022/HTML5_PolarVeritySense_HT25.html**

> Web Bluetooth requires a **secure context (HTTPS)**, which GitHub Pages provides — this is why the app works when hosted on GitHub Pages but not when opened directly from a local file.

### Locally

Because of the Web Bluetooth HTTPS requirement, serve the files over HTTPS or use a local HTTPS server, then open `HTML5_PolarVeritySense_HT25.html` in your browser.

## Browser support

Web Bluetooth is required. Supported in Chrome, Edge, and Opera on desktop, and Chrome on Android (see [caniuse.com/web-bluetooth](https://caniuse.com/web-bluetooth)). Not supported in Firefox or Safari.
