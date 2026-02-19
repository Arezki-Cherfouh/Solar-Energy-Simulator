# Solar Energy Simulator

Solar Energy Simulator lets you explore photovoltaic energy generation interactively. Use your phone's torch light to control the sun's position across a 180° arc, or let it move automatically in a bidirectional sweep. The solar panel charges a battery in real time, which you can use to power an LED light — and optionally enable motor-driven panel tracking that physically rotates the panel to follow the sun for maximum efficiency.

## Features

- **Torch Tracking** — point a flashlight or phone torch at your camera; OpenCV detects the bright light and maps its position to the sun's angle across the sky
- **Auto Mode** — when no torch is detected, the sun oscillates automatically across the full 180° arc
- **Solar Panel Visualization** — 36 photovoltaic cells light up progressively based on sun angle and alignment efficiency
- **Battery System** — charges from solar input, drains from LED and motor use; color-coded red/amber/green by charge level
- **Panel Tracking** — enable motorized tracking so the panel rotates across 180° to face the sun; draws 2W continuously and auto-disables when battery is empty
- **LED Control** — toggle an LED that draws 5W from the battery; auto-shuts off at 0% charge
- **AI Assistant** — ask questions about solar energy via the built-in chat interface
- **Real-time stats** — sun angle, power output (W), battery percentage, and charge/discharge status

## How It Works

Solar efficiency follows `sin(angle)` — peak output at 90° (zenith), zero at the horizons. Panel tracking adds a `cos(misalignment)` multiplier, so a perfectly aligned panel captures full output while a misaligned one loses proportionally. The motor costs energy to run, making tracking a strategic tradeoff rather than an automatic win.

## Running It

Open `solar-simulator.html` in any modern browser. Allow camera access when prompted to enable torch tracking. All processing runs client-side via OpenCV.js — no server required.

## Tech Stack

- **OpenCV.js** for real-time torch/bright-light detection via HSV thresholding and contour analysis
- **HTML5 Canvas** for sun arc rendering and light beam visualization
- **Vanilla JS** for simulation logic, battery model, and panel rotation
- **Groq API** for the solar energy AI assistant
