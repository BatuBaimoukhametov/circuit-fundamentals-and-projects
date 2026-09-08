# AC-DC Power Supply with Ripple Analysis
This is a simulation of a linear power supply which converts the AC you would get from a wall socket in to filtered DC. 
The end DC's ripple voltage is measured and compared to the theoretical. 
## Signal Chain
**1. AC source + transformer**
A `SINE(0 170 60)` source represents 120V RMS wall power at 60Hz. Two coupled inductors (K=1) step this down to a lower secondary voltage, simulating a step-down transformer.
**2. Full-wave bridge rectifier**
Four 1N4007 diodes arranged in a bridge configuration convert the AC secondary voltage into a pulsing DC output, (full-wave rectification), this doubles the ripple frequency to 120Hz compared to a half-wave design.
**3. Filter capacitor**
The 1000uF capacitor placed across the rectified output smooths the pulsing DC into steadier voltage.
## Results
Measured ripple voltage (via cursor readout across one steady-state cycle): ~1.03V
Theoretical ripple, calculated using Vripple ≈ Iload / (f x C):
-Average DC voltage ~14.85V
-Iload = V/R = 14.85V/100ohms ≈ 0.1485A
-f = 120Hz, C = 1000uF
-Vripple ≈ 0.1485 / (120 x 0.001) ≈ 1.24V
Measured and theoretical values are reasonably close, with the ~20% gap explained by the formula being a simplified approximation that assumes idealized linear discharge and doesn't fully account for the brief recharge window each cycle.
## Possible Improvements
-Try different capacitor values to confirm ripple scales inversely with C
-Add a voltage regulator stage to clean up the remaining ripple
-Add a load-switching element to observe ripple behavior under variable load

## Screenshots

| Screenshot | Shows |
|---|---|
| Screenshot_2026-05-22_200528.png | Transformer secondary output, confirming clean stepped-down 60Hz AC before rectification |
| Screenshot_2026-05-22_224104.png | Rectified but unfiltered output, showing full-wave rectification at 120Hz |
| Screenshot_2026-05-23_224525.png | Filtered DC output after adding the capacitor, showing the reduced ripple |
| Screenshot_2026-05-23_223110.png | Measurements of the ripple voltage|
