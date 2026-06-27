# 01 Blocking Superloop

This preview example demonstrates a typical starting point of many embedded firmware projects:

> A push button toggles an LED.

The application is intentionally small. The purpose is not the feature itself, but the firmware structure around it.

## Demo application

The firmware repeatedly performs three steps:

1. read the push button
2. update the internal LED state
3. write the LED output

A simple implementation often adds a blocking delay to slow down the loop or to make button handling easier.

```c
while (true) {
    bool button_pressed = read_button();

    if (button_pressed) {
        led_state = !led_state;
        write_led(led_state);
    }

    sleep_ms(100);
}
```
## Hardware idea

Minimal setup:

* RP2040/RP2350-based board
* 1 push button
* 1 LED
* 1 LED resistor
* breadboard and jumper wires

## What to observe

This simple firmware already raises important architecture questions:

* What happens if the button is pressed during sleep_ms(100)?
* How responsive is the application?
* What happens when a second input is added?
* Where should button debouncing happen?
* How would this scale to sensors, displays or communication interfaces?

## Why this matters

A blocking superloop can be a good starting point.

But as soon as more independent timing requirements are added, the firmware structure becomes more important than the individual feature.

The full Masterclass uses this example as the starting point for refactoring toward:

- non-blocking firmware
- event-driven state machines
- interrupt-driven event handling
- FreeRTOS-based firmware architecture
