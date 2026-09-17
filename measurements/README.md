# Tube Simulator 1.0.0 — Output measurements

These charts summarize measurements made from the digital audio output of Tube
Simulator 1.0.0. They are provided as reference material, not as a performance
specification or a guarantee for every host, sample rate, or setting.

## Method

- A single-channel sine signal was processed through the release audio path.
- The settled output was analysed after compensating for plug-in latency.
- Frequency and harmonic levels were calculated from the output waveform.
- No external DAC, ADC, amplifier, speaker, or room was included in the signal
  path.
- The measurements describe the plug-in's digital output and should not be read
  as measurements of a physical vacuum tube or transformer.

## Conditions

| Measurement | Conditions |
| --- | --- |
| Frequency response | Input −12 dBFS, 96 kHz, Auto 1x, 1 kHz reference, Standard and Full |
| Level sweep | 1 kHz, 48 kHz, Auto 2x, −40 to 0 dBFS, Standard and Full |
| Harmonic balance | 1 kHz, −12 dBFS, 48 kHz, Auto 2x, Standard and Full |
| Drive THD | 40 Hz, 48 kHz, Auto 2x, Full, Drive 0 / +6 / +12 dB |

Auto Level Match was off. Unless noted above, Drive was 0 dB and Output was at
its neutral setting.

## Files

- `frequency-response.png` — relative output gain from 10 Hz to 30 kHz
- `level-sweep.png` — output linearity and THD versus input level
- `harmonic-balance.png` — H2 through H5 relative to the fundamental
- `drive-thd-40hz.png` — output THD while increasing Drive at 40 Hz
- `freq_response.csv`, `level_sweep.csv`, `harmonics.csv`, and
  `drive_thd_40hz.csv` — the plotted values

The published Drive measurement contains output THD only. Other quantities are
not part of this public measurement set.

Copyright © 2026 moenium
