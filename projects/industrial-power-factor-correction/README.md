# Industrial Power Factor Correction
This is a simulated inductive load (modeling an industrial motor) built in LTspice, demonstrating a lagging power factor and correcting it using a parallel capacitor.
## Signal Chain
**1. Inductive load**
A series R-L branch (R=10ohms, L=30mH) modeling a motor's equivalent circuit, driven by a 120V RMS/60Hz source. The load's impedance angle produces a lagging power factor.

**2. Power measurement**
Vrms and Irms are read directly from the simulation. Apparent power is calculated as S=Vrms*Irms, and real power is measured directly as the average of the instantaneous power trace (V*I).

**3. Correction capacitor**
A capacitor sized using Qc = P*tan(theta) is added in parallel across the full load supplying the reactive current the inductor demands so the source only needs to supply real power.


## Results
**Before correction**
-Vrms: 120.19V
-Irms: 7.9611A
-Real power (measured): 633.79W
-Apparent power: ~956.7VA
-Power factor: ~0.663
-Theoretical power factor (from impedance angle): ~0.66, matching the measured value closely

**After correction (132uF capacitor)**
-Irms: 5.2731A
-Real power (measured): 633.79W (unchanged, as expected — the capacitor is purely reactive and does no work)
-Apparent power: ~633.9VA
-Power factor: ~0.9998

Correction reduced total source current by about 34% (7.9611A to 5.2731A) while delivering the exact same real power, bringing the power factor from 0.663 to essentially unity. This is the concrete demonstration of why poor power factors are avoided in industry.
## Possible Improvements
-Model a variable/switched load to explore how correction sized for one operating point performs under different load conditions
-Add a bank of switched capacitors to simulate real industrial automatic PF correction systems
-Explore overcorrection (leading power factor) and its own drawbacks

## Screenshots

| Screenshot | Shows |
|---|---|
| Screenshot_2026-06-25_154002.png | Uncorrected voltage and current waveforms, showing the current lagging behind the voltage |
| Screenshot_2026-06-25_162850.png | Corrected voltage and current waveforms, now essentially in phase |
| Screenshot_2026-06-25_162711.png | Uncorrected vs. corrected circuits side by side, comparing current and instantaneous power traces |
