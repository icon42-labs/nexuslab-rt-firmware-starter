# Architecture Preview

Most embedded firmware projects start with a simple superloop.

That is a good starting point.

A superloop is easy to understand, easy to debug and often the fastest way to bring up new hardware.

The problems usually start when more responsibilities are added:

- buttons need debouncing
- sensors need timing
- displays need periodic updates
- communication interfaces need responsiveness
- different parts of the firmware need different timing behavior

At that point, firmware that once looked simple can become hard to extend, hard to test and hard to reason about.

## The NexusLab architecture path

The NexusLab Real-Time Firmware Architecture Masterclass follows a step-by-step path:

1. blocking superloop
2. non-blocking firmware
3. event-driven state machines
4. interrupt-driven event handling
5. FreeRTOS-based firmware architecture

This starter repository only shows the initial problem space.

The full Masterclass demonstrates how to transform a simple embedded application into a maintainable real-time firmware architecture.

## Reference platform

The reference implementation uses RP2040/RP2350-based boards.

The architectural ideas are designed to be portable, but this starter repository focuses on the RP2040/RP2350 implementation.
