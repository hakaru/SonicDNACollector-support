# SonicDNA Collector Support

Welcome to SonicDNA Collector support page.

SonicDNA Collector is an audio measurement app designed for capturing the sonic characteristics of analog audio equipment for digital modeling purposes.

---

## 🎯 Overview

SonicDNA Collector generates logarithmic sweep signals while simultaneously recording, enabling detailed analysis of frequency response, harmonic distortion, and other characteristics of your audio equipment.

---

## ✨ Key Features

### 🎵 Logarithmic Sweep Generation
Generate professional-grade logarithmic sweep signals (20Hz - 20kHz) for accurate frequency response measurement.

### 📊 Gain Staircase Recording
Record multiple sweeps at different gain levels automatically:
- **5 Steps**: -30dB to -6dB (practical range)
- **11 Steps**: -100dB to 0dB (full dynamic range)

### 📈 Real-time Monitoring
- Dual VU meters for Input/Output levels
- FFT spectrum analyzer
- Clipping detection with visual indicators

### 🔧 Professional I/O
- Support for USB audio interfaces
- 96kHz sample rate
- Low-latency monitoring

### 🖥️ Debug Console
Real-time logging of audio engine status, device detection, and recording progress.

---

## 🔌 Setup Guide

### Equipment Connection

```
iPhone/iPad → Audio Interface → Equipment Under Test → Audio Interface → iPhone/iPad
   (Output)                        (Input)                              (Input)
```

1. Connect your USB audio interface to iPhone/iPad
2. Route audio interface output to equipment input
3. Route equipment output back to audio interface input
4. Launch SonicDNA Collector

### Gain Calibration

1. Tap **0dBFS** button to play test tone
2. ⚠️ **Warning**: Full-scale signal - start with low volume!
3. Adjust your audio interface gain until input meter shows appropriate level
4. Avoid input clipping (red "C" indicator)

---

## 📱 Recording Workflow

### Basic Recording

1. Enter device name (e.g., "Neve 1073", "LA-2A")
2. Select step count (5 or 11 steps)
3. Press the red record button
4. Wait for all sweeps to complete
5. Find recordings in the Recordings tab

### Understanding the Output

Each recording session creates a folder containing:
- Individual WAV files for each gain level
- `metadata.json` with session parameters
- Sample rate and device information

---

## 📊 Analysis

The recorded sweep files can be analyzed using:
- The built-in analysis tools
- Python analysis toolkit (included)
- Third-party audio analysis software

### Measurements Available
- Frequency Response
- THD (Total Harmonic Distortion)
- THD+N (THD plus Noise)
- Impulse Response extraction
- Gain linearity analysis

---

## ❓ FAQ

### What audio interfaces are supported?
Any class-compliant USB audio interface should work. Tested with ZOOM AMS-22.

### Why 96kHz sample rate?
Higher sample rate provides better frequency resolution and captures harmonics beyond the audible range for more accurate modeling.

### What does INPUT vs OUTPUT clipping mean?
- **INPUT clipping**: Hardware ADC overload - reduce interface gain
- **OUTPUT clipping**: Digital full-scale signal - normal for 0dBFS test tone

### How long is each sweep?
Each sweep is 5 seconds, with 1 second silence before and after. Total ~7 seconds per step.

---

## 📧 Contact

If you have questions or feedback, please contact us at:

📧 **sonicdna@hakaru.net**

---

## 🔗 Links

- [Privacy Policy](privacy)
- [User Manual](manual/en/)
- [Changelog](changelog/)
- [Blog](blog/en/)

---

© 2026 hakaru.net
