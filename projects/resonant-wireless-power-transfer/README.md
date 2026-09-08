# Resonant Wireless Power Transfer Link
This is a simulation of wireless energy transfer between two devices. An analysis of two mathematically coupled LC circuits at the same resonance frequency.
## Signal Chain
**1. Transmitter tank (series resonant)**
An AC source drives the series L1-C1 tank (L=10uH, C=253nF), tuned to resonate at 100kHz. This simulates a transmitter. 

**2. Receiver tank (parallel resonant)**
A second inductor L2 (10uH) is magnetically coupled to L1 via a coupling coefficient K, with no direct electrical connection between the two sides. L2 is paired with C2 (253nF) in parallel, feeding a 50ohm load resistor, simulating a receiver and the load. 

**3. Power measurement**
Power delivered to the load is calculated using `mag(I(Load))*sqrt(50)` plotted in dB, which corresponds to the standard 10*log10(P) power convention.

## Results
**Frequency sweep (K=0.3 fixed)**
The coupled system's actual resonant peak shifted to 105kHz, rather than the individually-calculated 100kHz due to frequency splitting.

| Frequency | Power (dB) |
|---|---|
| 60kHz | -104.42 |
| 80kHz | -97.79 |
| 100kHz | -82.61 |
| 105kHz (resonance) | -49.47 |
| 120kHz | -91.63 |
| 140kHz | -98.36 |

Moving just 5kHz off resonance (105kHz to 100kHz) drops power by 33.14dB, a power ratio of roughly 2060x.

**Coupling coefficient sweep (frequency allowed to track each peak)**

| Coupling (K) | Peak Frequency | Peak Power (dB) |
|---|---|---|
| 0.1 | 101kHz | -71.67 |
| 0.25 | 103kHz | -61.15 |
| 0.4 | 109kHz | -50.32 |
| 0.55 | 120kHz | -46.78 |
| 0.7 | 140kHz | -37.89 |

Increasing coupling from K=0.1 to K=0.7 improves peak power by 33.78dB (~2390x), consistent the fact that devices need to be brought close together to utilize wireless charging.
## Possible Improvements
-Test coupling values beyond 0.7 to see if the frequency shift continues or plateaus
-Add a rectifier and filter stage on the receiver side to convert the recovered AC into usable DC, similar to the AC-DC power supply project
-Model coil misalignment (not just distance) using a separate coupling parameter
-Add losses (series resistance) to each tank for a more realistic Q factor

## Screenshots

| Screenshot | Shows |
|---|---|
| Screenshot_2026-06-02_143941.png | Frequency sweep at K=0.3, cursor showing peak power at 105kHz |
| Screenshot_2026-06-02_145309.png | Coupling coefficient sweep (K=0.1 to 0.7), showing peak power and frequency both increasing with tighter coupling |
