---
title: "How to Measure Your Analog Gear's Frequency Response with iPhone"
date: 2026-03-08
tags: [SonicDNA Collector, analog gear, frequency response, measurement, audio]
---

Every piece of analog gear has a sonic fingerprint. Vintage compressors, tube preamps, tape machines — even two units of the same model can sound subtly different. Engineers and musicians have long relied on words like "warm," "punchy," or "silky" to describe these differences, but subjective descriptions only go so far. What if you could objectively measure and visualize the unique character of your gear?

The answer lies in **frequency response measurement**. In this guide, we'll cover everything from the fundamentals of frequency response to a practical method for measuring your analog equipment using just an iPhone and an audio interface.

## What Is Frequency Response?

Frequency response describes how an audio device handles signals across the audible spectrum. An ideal, perfectly transparent device would pass every frequency from 20Hz to 20kHz at exactly the same level. In practice, no analog device does this perfectly — and that's precisely what makes analog gear interesting.

A vintage Neve preamp might add a subtle low-end warmth below 200Hz while gently rolling off the highest frequencies. A tube compressor might introduce harmonic content that creates a characteristic presence peak around 3kHz. These deviations from a flat response are the "secret sauce" that gives each piece of gear its unique sonic identity.

Frequency response is typically displayed as a graph with frequency (Hz) on the horizontal axis and level (dB) on the vertical axis. A flat horizontal line indicates a neutral, transparent device. Curves, bumps, and roll-offs reveal the device's character.

### Why Measure Frequency Response?

Measuring your gear's frequency response offers several practical benefits:

- **Objective characterization**: Put numbers behind subjective impressions like "warm" or "bright"
- **Detect aging and degradation**: Regular measurements can reveal capacitor deterioration, tube wear, or transformer degradation before they become audible problems
- **Compare gear scientifically**: Evaluate different preamps, EQs, or processors under identical conditions
- **Optimize your signal chain**: Understanding each device's characteristics helps you build better recording chains
- **Verify repairs and maintenance**: Compare pre- and post-repair measurements to confirm a device has been restored to proper operation

## Traditional Measurement Methods and Their Limitations

Historically, measuring audio equipment frequency response has required specialized tools and considerable expertise.

### Dedicated Audio Analyzers

Instruments like Audio Precision systems can measure frequency response with extraordinary accuracy. However, these systems cost thousands to tens of thousands of dollars, putting them out of reach for most individual studios and audio enthusiasts. They also require training to operate correctly and are not portable.

### PC-Based Measurement Software

Software solutions such as REW (Room EQ Wizard) and ARTA (Audio Real-Time Analyzer) bring measurement capabilities to a standard computer. While more affordable than dedicated hardware, they come with their own challenges. Setting up a PC-based measurement system involves configuring audio interface routing, calibrating input and output levels, installing drivers, and navigating complex software interfaces. For studios where gear is permanently racked, bringing a laptop to the rack room and running cables every time you want to take a measurement is cumbersome.

### Basic Smartphone Apps

Some apps attempt frequency analysis using a phone's built-in microphone. While convenient, these are fundamentally limited by the phone's microphone characteristics — particularly in the low and high frequency extremes. The built-in microphone's own frequency response colors every measurement, making accurate equipment analysis impossible.

## A Modern Approach: iPhone + Audio Interface

Modern iPhones contain remarkably powerful processors capable of real-time audio processing at professional sample rates. When paired with a USB-C audio interface, an iPhone becomes a capable measurement platform with professional-grade analog-to-digital and digital-to-analog conversion.

### What You Need

- **iPhone** (USB-C models recommended)
- **Audio interface** (USB-C connection, 96kHz support preferred)
- **Appropriate cables** (for connecting to your gear under test)

### Basic Signal Path

The measurement setup follows a straightforward signal chain:

1. Connect the audio interface to your iPhone
2. Route the audio interface output to the input of the gear you want to measure
3. Connect the output of your gear back to the audio interface input

This creates a complete loop: iPhone → audio interface output → device under test → audio interface input → iPhone. The iPhone sends a precisely generated test signal through the device, then analyzes the returning signal to determine exactly how the device modified it.

## How Sweep Signals Work

The gold standard for frequency response measurement is the **sweep signal** — a sine wave that continuously changes frequency from low to high over a defined period.

### Why Sweeps Outperform Other Test Signals

**Compared to white noise**: White noise contains all frequencies simultaneously, but the energy is spread thin across the entire spectrum. This results in a relatively low signal-to-noise ratio at any individual frequency. A sweep concentrates all energy into one frequency at a time, delivering dramatically better S/N performance.

**Compared to impulses**: An impulse theoretically contains all frequencies, but generating a clean impulse requires an enormous peak level in an infinitesimally short time. In practice, this causes clipping and distortion. Sweeps achieve the same spectral coverage at moderate, safe signal levels over a longer time window.

### Logarithmic vs. Linear Sweeps

There are two types of frequency sweeps. A linear sweep changes frequency at a constant rate — spending equal time at every frequency range. A logarithmic sweep spends more time in the lower frequencies and accelerates through the higher frequencies. This matches human hearing perception, which is also logarithmic in nature, and is the standard for audio measurements.

Logarithmic sweeps have another critical advantage: through **deconvolution processing**, harmonic distortion products can be cleanly separated from the fundamental response. This means a single sweep measurement can simultaneously yield both the frequency response and the distortion characteristics of a device.

## Reading Your Measurement Results

Once you've captured a measurement, interpreting the resulting frequency response graph is essential for understanding your gear.

### Understanding the Graph

- **Horizontal axis (X)**: Frequency, displayed on a logarithmic scale. The left edge represents low frequencies (20Hz) and the right edge represents high frequencies (20kHz)
- **Vertical axis (Y)**: Level in decibels (dB), referenced to 0dB. Points above the reference indicate the device is boosting that frequency; points below indicate attenuation

### Common Response Patterns

**Flat response**: A nearly horizontal line across the spectrum indicates a transparent device that passes audio with minimal coloration. Typical of high-quality monitor preamps and modern converters.

**Low-frequency rise**: A gentle lift below 100Hz is characteristic of many vintage designs, particularly those using transformers in the signal path. This is often described as "warmth" or "body."

**High-frequency roll-off**: A gradual attenuation above 10kHz is common in transformer-coupled analog gear. This contributes to the "smooth" or "silky" quality that engineers often prize.

**Resonant peaks and dips**: Sharp peaks or dips at specific frequencies indicate resonances or filter characteristics. These are most prominent in devices with EQ circuits or tone controls, but can appear in any device with reactive components.

### Level-Dependent Behavior: Where Analog Gets Interesting

One of the most fascinating aspects of analog gear is that its frequency response can change depending on the input level. A preamp might measure nearly flat at low levels but develop a distinctive low-end bump and high-frequency saturation when driven hard. This nonlinear behavior — where the response depends on the signal level — is a defining characteristic of analog equipment and a major reason engineers reach for specific pieces of gear.

Capturing this behavior requires multiple sweep measurements at different input levels. Doing this manually means carefully adjusting levels between each measurement, which is tedious and error-prone.

## SonicDNA Collector: Precision Measurement Made Simple

**SonicDNA Collector** was built to bring all of these measurement capabilities together in a single, streamlined iPhone app.

### Precision Sweep Generation

SonicDNA Collector generates logarithmic sweep signals from 20Hz to 20kHz at a 96kHz sample rate. Each 5-second sweep is bracketed by 1-second silence buffers for accurate noise floor and reverb tail capture. The app performs deconvolution processing to extract both frequency response and harmonic distortion data from a single sweep.

### Gain Staircase: Automated Multi-Level Testing

Instead of manually adjusting levels and repeating measurements, the Gain Staircase feature automatically runs a series of sweeps at progressively increasing levels. This captures your gear's behavior from its linear region through saturation in a single automated sequence.

- **5-Step Mode**: Covers -30dB to -6dB in approximately 35 seconds
- **9-Step Mode**: Covers -30dB to -2dB in approximately 63 seconds

This reveals how your gear's frequency response, distortion characteristics, and overall behavior change as it's driven harder — the kind of data that would take much longer to collect manually.

### Real-Time Monitoring

During measurement, SonicDNA Collector displays real-time input and output levels along with spectral information. This makes it easy to verify your connections are correct, set appropriate levels before measuring, and detect any clipping or other issues instantly.

### WAV Export for Further Analysis

All measurement data can be exported as 96kHz/32-bit float WAV files. This lets you import your measurements into a DAW or specialized analysis software for deeper examination, comparison overlays, or archiving.

### Practical Use Cases

- **Vintage gear documentation**: Build a measurement library of every piece in your collection and track changes over time
- **Pre-purchase verification**: When buying used gear, verify it meets specifications before committing
- **Repair validation**: Measure before and after service to confirm proper restoration
- **Tube rolling comparisons**: Quantify the sonic differences between tube brands in the same amplifier
- **A/B testing**: Scientifically compare two pieces of gear that serve the same function in your signal chain

## Conclusion

Measuring your analog gear's frequency response transforms subjective impressions into objective data. What once required expensive laboratory equipment or complex PC setups can now be accomplished with an iPhone, an audio interface, and the right app.

Discover the unique sonic DNA of your analog gear — measure it, understand it, and make better-informed decisions about your signal chain.

[Download SonicDNA Collector on the App Store](https://apps.apple.com/app/sonicdna-collector/id6740519938)
