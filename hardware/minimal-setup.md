# Minimal Hardware Setup

The starter examples use a deliberately small hardware setup.

The goal is to focus on firmware architecture, timing behavior and code structure instead of complex peripherals.

## Required hardware

- Raspberry Pi Pico, Raspberry Pi Pico 2 or Adafruit Feather RP2040
- 1 push button
- 1 LED
- 1 LED resistor
- Breadboard
- Jumper wires
- USB cable

## Reference platform

The starter repository focuses on RP2040/RP2350-based boards.

The full NexusLab Real-Time Firmware Architecture Masterclass uses the same reference platform to demonstrate the path from simple superloops toward maintainable real-time firmware architecture.

## Suggested first experiment

The first firmware example uses a push button and an LED.

A simple application can be built from this setup:

- read the button
- update an internal state
- switch or toggle the LED
- observe timing and responsiveness

This is intentionally simple. The architectural value comes from how the firmware is structured, measured and improved step by step.
