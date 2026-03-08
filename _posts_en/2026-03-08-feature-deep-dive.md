---
title: "SonicDNA Collector Feature Deep Dive — Unlock Your Gear's DNA"
date: 2026-03-08
---

Let's take an in-depth look at each feature of SonicDNA Collector and how to get the most out of them.

## Logarithmic Sweep Generation — The Heart of Measurement

Every measurement in SonicDNA Collector is built on **logarithmic sweep signals**. The app generates a continuous frequency sweep from 20Hz to 20kHz at a 96kHz sample rate.

Why logarithmic sweeps?

- **Wide dynamic range**: Far superior S/N ratio compared to white noise or impulse methods
- **Harmonic distortion separation**: Deconvolution cleanly separates the fundamental from distortion components
- **One sweep does it all**: A single measurement provides data for frequency response, impulse response, and more

Each sweep lasts 5 seconds, with 1-second silence buffers before and after. These silence periods are essential for accurately capturing the device's reverb tail and noise floor.

## Gain Staircase — Exposing Nonlinear Character

The magic of analog gear lies in how it behaves differently at various input levels. The Gain Staircase feature automatically runs multiple sweeps at progressively higher levels, capturing these changes.

### 5-Step Mode (~35 seconds)

| Step | Level | Purpose |
|------|-------|---------|
| 1 | -30dB | Behavior near noise floor |
| 2 | -24dB | Low-level characteristics |
| 3 | -18dB | Standard operating point |
| 4 | -12dB | High-level characteristics |
| 5 | -6dB | Saturation region |

This mode is sufficient for everyday measurements. Quickly assess the basic behavior of compressors, EQs, and other processors.

### 11-Step Mode (~77 seconds)

Covers the full range from -100dB to 0dB in 10dB steps. Ideal for tube amplifiers, tape machines, and other gear that exhibits different distortion characteristics across the entire dynamic range.

Output consists of individual WAV files for each level, plus a `metadata.json` file containing session information.

## Real-time Monitoring — See What You're Capturing

### Dual VU Meters

Output (playback) and input (recording) levels are displayed simultaneously. Color-coded bars give you instant status:

- **Green**: Safe levels
- **Yellow**: Caution (low headroom)
- **Red**: Near clipping

### Clipping Detection

The **[C]** indicator next to each meter signals that the signal has reached digital full scale. Input-side clipping means ADC overload — reduce your interface gain immediately.

### FFT Spectrum

Visualize the frequency distribution of your signal in real time. Watch the sweep move from low to high frequencies, and instantly spot any unexpected peaks or notches.

## Analysis Tools — Making Sense of Your Data

Extract meaningful insights from your recordings:

### Frequency Response
Plot the amplitude variation across frequencies after passing through the device. Perfect for verifying EQ curves and filter characteristics.

### THD (Total Harmonic Distortion)
Measure distortion at each input level. Objectively determine where saturation begins.

### THD+N
A comprehensive quality metric that includes both distortion and noise components.

### Impulse Response
Extract impulse responses from sweep data via deconvolution. Create IR data for convolution reverbs or verify phase characteristics.

### Gain Linearity
Plot output level against input level to evaluate device linearity. Also useful for visualizing compressor knee curves.

## Professional I/O — No Compromises

- **96kHz sample rate**: Captures harmonics beyond the audible range for more precise modeling
- **USB class-compliant**: No special drivers needed. Tested with ZOOM AMS-22 and similar interfaces
- **Low latency**: Minimal delay for real-time monitoring

## Debug Console — Instant Troubleshooting

The debug console at the bottom of the screen shows real-time events:

- Audio engine initialization, start, and stop
- Device detection and connection status
- Start/end timing for each sweep
- Errors and warnings

When something unexpected happens, the console log provides the clues you need to identify the cause.

## Summary

SonicDNA Collector is your tool for extracting the "DNA" of audio gear. The combination of logarithmic sweeps and gain staircase recording comprehensively captures everything from frequency response to nonlinear distortion characteristics.

For detailed usage instructions, check out the [User Manual](/manual/en/).

---

Questions or feedback? Reach out at **sonicdna@hakaru.net**.

## Related Articles

- [How to Measure Your Analog Gear's Frequency Response]({% post_url 2026-03-08-analog-gear-frequency-analysis %})
