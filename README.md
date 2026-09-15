# Measured World Lab

Measured World Lab collects low-cost educational instruments and experiments that make ordinary physical phenomena observable and measurable.

The governing question is: **what quantity are we trying to observe, how well can we measure it, and is that enough for the purpose?**

## Instrument families

Representative areas include:

- **temperature** — simple digital temperature measurement;
- **mass** — low-cost electronic scales and load-cell experiments;
- **distance and motion** — ultrasonic and time-of-flight measurement;
- **conductivity** — classroom solution-conductivity investigations;
- **color and light** — simple colorimetry and optical measurement;
- **timing and frequency** — counters, oscillation, pendulum, ramp, and event timing;
- **browser instruments** — DMM-, frequency-meter-, and oscilloscope-style educational interfaces.

## Relationship to the estate

Measured World Lab is a reusable instrument layer.

- [core-10](https://github.com/RandoSY/core-10) supplies many of the educational questions and experiments.
- [software-defined-laboratory](https://github.com/RandoSY/software-defined-laboratory) supplies reusable endpoint and host patterns.
- [nugget-physical-computing](https://github.com/RandoSY/nugget-physical-computing) supplies the learning ladder for understanding how the instruments work.

An instrument should not be duplicated merely because several curricula use it.

## Design rules

- Prefer inexpensive, replaceable, understandable sensors.
- Calibrate when calibration materially improves the answer.
- State units, range, resolution, assumptions, and practical limits.
- Keep the measured quantity visible before adding derived conclusions.
- Reuse instruments across many experiments.
- Distinguish a classroom demonstration from a validated measuring instrument.

## Planned repository structure

- `temperature/`
- `mass/`
- `distance-motion/`
- `conductivity/`
- `color-light/`
- `timing-frequency/`
- `browser-instruments/`
- `calibration/`
- `validation/`

## Current state

**Lifecycle:** `active`

This repository is presently an organizational front door. Existing instrument designs, firmware, dashboards, and experiment notes still need to be migrated, deduplicated, and labeled according to their actual validation state.
