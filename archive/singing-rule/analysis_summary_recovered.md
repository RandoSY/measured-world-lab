# Singing Rule — Recovered Measured-Run Analysis

**Recovery provenance:** this analysis was recovered from the Dashboard Tier Evidence Appendix embedded in `Three_Tier_Virtual_Device_Architecture_With_Dashboard_Appendix_REFINED(1).pdf`. The appendix identifies the original source as `analysis_summary.txt` from `%DESKTOP%\Singing Rule\Data Runs\cantilever_beam_motion_analysis\` and identifies the input CSV as `m5stick_plus2_motion_2026-05-10T01-35-02-644Z.csv`.

**Important:** the raw CSV and original reproduction script have not yet been recovered as standalone Library files. This document preserves the surviving measured-run analysis and explicitly does not substitute later representative simulation for the missing raw record.

## Cantilever beam M5StickC Plus2 motion capture analysis

### Input CSV

`m5stick_plus2_motion_2026-05-10T01-35-02-644Z.csv`

### Basic capture

- Samples: **500**
- Duration: **49.90 s**
- Median sample period: **0.100 s**
- Effective sample rate: **10.00 Hz**
- Markers found: **0**

### Important limitation

- The run was captured at about 10 Hz, so the Nyquist limit is about 5 Hz.
- The dominant cantilever mode is therefore measurable only if it is below 5 Hz.
- The captured ringdown appears near 2.3 Hz, safely below Nyquist, but with only about 4.3 samples per cycle.
- That is enough to see the ringdown, but not enough for precision modal analysis.

### Waveform interpretation

- Two strong excitation/ringdown events are visible: one at the start of the capture and one around **t = 8.6–9.0 s**.
- The second event is the cleanest analysis window because the trace settles before and after it.
- Acceleration is dominated by `az` and by the acceleration resultant `|a|`.
- Gyro motion is dominated by `gx`.
- This is consistent with a clamped-ruler/cantilever experiment showing one major bending direction and one major rotational-rate axis.

### Dominant frequency estimates

- Full-record `dynamic_g` FFT peak: **2.340 Hz**
- Full-record `gx` FFT peak: **2.240 Hz**
- Second-ringdown `dynamic_g` FFT peak: **2.241 Hz**
- Second-ringdown `gx` FFT peak: **2.241 Hz**

## PCA / Eigen-analysis — all samples

### Acceleration covariance eigenvalues in g²

- λ1 = **0.0414161**
- λ2 = **7.47728e-05**
- λ3 = **3.16014e-05**

### Acceleration variance ratios

- PC1 = **99.744%**
- PC2 = **0.180%**
- PC3 = **0.076%**

### Acceleration PC1 eigenvector `[ax, ay, az]`

`[-0.00225, -0.09178, 0.99578]`

### Gyro covariance eigenvalues in (deg/s)²

- λ1 = **151.647**
- λ2 = **0.54789**
- λ3 = **0.00373129**

### Gyro variance ratios

- PC1 = **99.638%**
- PC2 = **0.360%**
- PC3 = **0.002%**

### Gyro PC1 eigenvector `[gx, gy, gz]`

`[-0.99896, -0.04477, -0.00910]`

## PCA / Eigen-analysis — second ringdown window, 8.3–14.0 s

### Acceleration covariance eigenvalues in g²

- λ1 = **0.0940736**
- λ2 = **0.000434817**
- λ3 = **7.25586e-06**

### Acceleration variance ratios

- PC1 = **99.532%**
- PC2 = **0.460%**
- PC3 = **0.008%**

### Acceleration PC1 eigenvector `[ax, ay, az]`

`[-0.01801, -0.10025, 0.99480]`

### Gyro covariance eigenvalues in (deg/s)²

- λ1 = **364.895**
- λ2 = **0.190306**
- λ3 = **0.00338028**

### Gyro variance ratios

- PC1 = **99.947%**
- PC2 = **0.052%**
- PC3 = **0.001%**

### Gyro PC1 eigenvector `[gx, gy, gz]`

`[-0.99940, -0.03365, -0.00833]`

## Plain-English eigenvector interpretation

- Acceleration PC1 points almost entirely along the device z-axis.
- Gyro PC1 points almost entirely along the negative device x-axis.
- PCA eigenvector sign is arbitrary: opposite signs represent the same mode axis.
- The overwhelming PC1 dominance means the ruler motion is essentially one-dimensional in the measured data.
- This is the modal/eigenvector story: the cantilever has a preferred bending mode, visible as a dominant acceleration axis and angular-rate axis.

## Recommended next improvements from the original analysis

1. Increase BLE sample rate if stable; **25–50 Hz** would improve the ringdown and FFT substantially.
2. Add a MARK button press exactly at release/pluck.
3. Use the same sensor mounting orientation each time.
4. Record ruler length, overhang length, mass placement, and clamp position.
5. Repeat with different overhang lengths; frequency should shift strongly with length.

## Still-active forensic targets

- `m5stick_plus2_motion_2026-05-10T01-35-02-644Z.csv`
- `analysis_summary.txt` original
- `reproduce_cantilever_analysis.py`
- `cantilever_beam_motion_analysis.zip`
- individual analysis PNGs referenced by the evidence appendix

If those originals are later found, preserve them alongside this recovered summary rather than replacing or rewriting this record.
