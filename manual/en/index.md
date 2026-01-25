# User Manual

Welcome to the SonicDNA Collector User Manual.

---

## Table of Contents

1. [Getting Started](#getting-started)
2. [Interface Overview](#interface-overview)
3. [Equipment Setup](#equipment-setup)
4. [Gain Calibration](#gain-calibration)
5. [Recording](#recording)
6. [Analysis](#analysis)
7. [Troubleshooting](#troubleshooting)

---

## Getting Started

### Requirements

- iPhone or iPad with iOS 17.0 or later
- USB audio interface (class-compliant)
- Lightning to USB or USB-C adapter (if needed)
- Audio cables for your equipment

### First Launch

1. Install SonicDNA Collector from the App Store
2. Grant microphone permission when prompted
3. Connect your audio interface
4. The app will automatically detect the interface

---

## Interface Overview

### Main Screen

```
┌─────────────────────────────────┐
│ [🎵] SonicDNA        [?] [📁]  │  ← Navigation
├─────────────────────────────────┤
│ [🎤 Input Device] [🔊 Output]  │  ← Device Selection
│ [📋 Device Name Input        ] │  ← Equipment Name
├─────────────────────────────────┤
│ OUTPUT  ████████░░░░  -12dB [C]│  ← Output VU
│ ▁▂▃▄▅▆▇█▇▆▅▄▃▂▁                │  ← Output Spectrum
├─────────────────────────────────┤
│ INPUT   ████████░░░░  -18dB [C]│  ← Input VU
│ ▁▂▃▄▅▆▇█▇▆▅▄▃▂▁                │  ← Input Spectrum
├─────────────────────────────────┤
│ DEBUG CONSOLE                  │
│ 06:30:15.123 Engine started    │  ← Real-time Logs
│ 06:30:15.456 Input: ZOOM AMS   │
├─────────────────────────────────┤
│ ● Ready              96.0 kHz  │  ← Status
├─────────────────────────────────┤
│ [5 STEPS]    [⏺]    [0dBFS]   │  ← Controls
│              Staircase          │
└─────────────────────────────────┘
```

### Controls

| Control | Function |
|---------|----------|
| **5 STEPS / 11 STEPS** | Select gain staircase mode |
| **Record Button** | Start/stop recording |
| **0dBFS** | Play/stop 1kHz test tone |
| **[?]** | Help screen |
| **[📁]** | Recordings library |

### Indicators

| Indicator | Meaning |
|-----------|---------|
| **Green bar** | Safe level |
| **Yellow bar** | High level (caution) |
| **Red bar** | Near clipping |
| **[C] Red** | Clipping detected! |

---

## Equipment Setup

### Signal Flow

```
┌──────────┐    ┌────────────┐    ┌─────────────┐    ┌──────────┐
│  iPhone  │───▶│ Audio I/F  │───▶│  Equipment  │───▶│ Audio I/F│───▶ iPhone
│  Output  │    │   Output   │    │   Under     │    │  Input   │    Input
└──────────┘    └────────────┘    │   Test      │    └──────────┘
                                  └─────────────┘
```

### Connection Steps

1. **Connect Audio Interface**
   - Use appropriate adapter for your device
   - Wait for iOS to recognize the interface

2. **Connect Equipment**
   - Audio interface output → Equipment input
   - Equipment output → Audio interface input

3. **Verify in App**
   - Check that input/output devices are detected
   - Device names appear in the header

---

## Gain Calibration

### Using the Test Tone

⚠️ **Warning**: The 0dBFS test tone is very loud!

1. **Lower your monitor volume first**
2. Tap the **0dBFS** button
3. Confirm the warning dialog
4. Observe the OUTPUT meter (should show 0dB)
5. Adjust equipment input gain
6. Observe the INPUT meter
7. Aim for -18dB to -12dB average
8. Tap **0dBFS** again to stop

### Avoiding Clipping

- **INPUT clipping** (red C on input) = Hardware damage risk!
  - Reduce audio interface gain immediately
  - Check equipment output level

- **OUTPUT clipping** (red C on output) = Normal for test tone
  - 0dBFS signal is full digital scale

---

## Recording

### Staircase Recording

The staircase recording plays multiple sweeps at progressively higher levels:

**5 Steps Mode** (Recommended)
- -30dB, -24dB, -18dB, -12dB, -6dB
- Total time: ~35 seconds
- Good for typical measurements

**11 Steps Mode** (Comprehensive)
- -100dB to 0dB in 10dB steps
- Total time: ~77 seconds
- Full dynamic range analysis

### Recording Process

1. Enter equipment name (e.g., "Neve 1073")
2. Select step count
3. Tap the red record button
4. Wait for completion
5. Find recording in library

### Output Files

Each session creates a folder containing:

```
GainStaircase_2026-01-25T15-30-00/
├── Sweep_-30dB.wav
├── Sweep_-24dB.wav
├── Sweep_-18dB.wav
├── Sweep_-12dB.wav
├── Sweep_-6dB.wav
└── metadata.json
```

---

## Analysis

### Built-in Analysis

Navigate to **Recordings** → Select a session → **Analysis**

Available measurements:
- **Frequency Response** - Plot of magnitude vs frequency
- **THD** - Total Harmonic Distortion at each level
- **Harmonics** - Individual harmonic levels

### Python Analysis Toolkit

For advanced analysis, use the included Python toolkit:

```bash
cd analysis/
python -m sonicdna analyze /path/to/session/
```

Features:
- Impulse response extraction
- Detailed frequency response plots
- THD+N measurement
- Export to various formats

---

## Troubleshooting

### No Audio Interface Detected

1. Check physical connection
2. Try different USB port/adapter
3. Restart the app
4. Check iOS Settings → Privacy → Microphone

### No Input Signal

1. Verify cable connections
2. Check equipment output level
3. Ensure interface gain is not at minimum
4. Check interface phantom power if needed

### Clipping During Recording

1. Reduce audio interface input gain
2. Lower equipment output level
3. Use a lower staircase range

### App Crashes

1. Close other audio apps
2. Restart the app
3. If persistent, reinstall the app

---

## Tips for Best Results

1. **Use short cables** - Minimize interference
2. **Disable iPhone sounds** - Silent mode recommended
3. **Consistent levels** - Don't adjust during recording
4. **Name your sessions** - Easy organization
5. **Multiple takes** - For critical measurements

---

[← Back to Support](../)
