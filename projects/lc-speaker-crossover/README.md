# LC Speaker Crossover
This is a simulated first-order passive speaker crossover built in LTspice, splitting an audio signal between a woofer and tweeter.
## Signal Chain
**1. Low-pass branch (woofer)**
An inductor (L=0.637mH) in series with an 8ohm resistor (modeling the woofer) forms the first-order low-pass filter, calculated for a target crossover frequency of 2kHz.

**2. High-pass branch (tweeter)**
A capacitor (C=9.95uF) in series with a second 8ohm resistor (modeling the tweeter) forms the first-order high-pass filter, calculated to target the same 2kHz crossover point.

**3. Verification**
Both branches are driven from the same source node and swept using .ac dec 100 20 20k, with voltage measured at each resistor to observe each branch's frequency response.
## Results
Cursor measurement at 2kHz on the tweeter branch reads -3.01dB, confirming the crossover point lands almost exactly at the calculated 2kHz target. 

## Possible Improvements
-Build a second-order crossover for a steeper rolloff (12dB/octave) and compare against this first-order design
-Extend to a three-way crossover (woofer/midrange/tweeter)
-Model driver impedance more realistically instead of using plain resistors

## Screenshots

| Screenshot | Shows |
|---|---|
| Screenshot_2026-04-29_174200.png | Woofer and tweeter voltage response, with cursor confirming -3.01dB at the 2kHz crossover point |
