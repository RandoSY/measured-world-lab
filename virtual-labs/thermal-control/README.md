# Virtual Breadboard Thermal Control Lab — recovered v2.x package

This directory preserves a working historical browser laboratory and its programmer documentation.

## Preserved artifacts

- `source/virtual_breadboard_thermal_lab_v2_2.html.gz` — lossless gzip archive of the recovered 98,066-byte self-contained browser application. Decompress it to restore `virtual_breadboard_thermal_lab_v2_2.html` exactly.
- `docs/Virtual_Breadboard_Thermal_Control_Lab_Programmers_Guide_v2_3.md.gz` — lossless gzip archive of the repository-native Markdown conversion of the recovered v2.3 programmer guide.

## Laboratory model

The simulator rehearses a real breadboard workflow: read a virtual thermal node on A0, convert ADC count to voltage and temperature, decide what the controller should do, and drive a heater abstraction by PWM on D9. It supports Arduino and CircuitPython teaching modes, guided source generation, an educational IDE, diagnostics, data export, and transition to real hardware.

The historical guide identifies the runnable HTML as `virtual_breadboard_thermal_lab_v2_2.html` even though the guide itself is v2.3; both names are therefore retained rather than silently normalized.

## Validation boundary

The browser artifact is recovered source, not a certification of any particular physical heater circuit. The guide specifically warns that its convenient 5 V teaching model must be adjusted for real 3.3 V CircuitPython hardware where applicable.
