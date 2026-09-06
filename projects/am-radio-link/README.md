# AM Radio Transmit/Receive Link
A simulated end-to-end AM radio system built in LTspice, using a real audio clip as the input signal. From modulation through demodulation, an audible approximation of the original recording is recovered at an appropriate level to demonstrate the concept. 

## Signal Chain

**1. Audio source**
A downsized  8kHz version of the 2MB .wav file from (https://file-examples.com/index.php/sample-audio-files/sample-wav-download/) is fed into LTspice's `wavefile=` voltage source parameter, standing in for a microphone signal.

**2. Carrier**
A 50kHz `SINE` source represents the radio frequency the signal would be broadcast on (scaled down for manageable simulation size)

**3. Modulation**
A behavioural voltage source computes `V=(V(audio)+2)*V(carrier)`. The `+2` offset keeps the original audio signal positive for simple diode-based demodulation later. 

**4. Bandpass filter**
A series RLC network (R=100ohms, L=10mH, C=1nF) resonating at 50kHz simulates a receiver's tuning stage from a in practice noisier RF environment.

**5. Envelope detector**
A diode (1N4148) followed by the RC network (R=1kohm, C=47nF) rectifies the signal and smooths out the carrier ripple using its ~47us time constant. 

**6. DC blocking**
A high-pass filter (C=1uF, R=10kohm, corner ~16Hz) strops the DC offset left from the initial +2 shift and the diode's forward voltage drop. 

## Results
The recovered audio's envelope closely tracks the original clip's loud/quite pattern as verified by the bursts and pauses lining up when the two signals are plotted together. However, the recovered signal has a noticeably smaller amplitude and is audibly noisier than the original. Three causes of this specific to this circuit include:
-Incomplete carrier suppression
-Diode nonlinearity
-Signal loss through the chain
## Possible Improvements
-Increasing the envelope detector's capacitor to reduce carrier ripple
-Replace the diode/RC detector with a precision rectifier
-Adding an amplification stage to recover signal strength

## Screenshots

| Screenshot | Shows |
|---|---|
| [Screenshot_2026-05-05_163435.png](Screenshot_2026-09-05_163435.png) | Zoomed-in view (2ms window) of the modulated signal, confirming the ~50kHz carrier oscillation underneath the audio envelope |
| [Screenshot_2026-05-05_164643.png](Screenshot_2026-09-05_164643.png) | AC sweep of the bandpass filter, confirming resonant peak at ~50kHz |
| [Screenshot_2026-05-6_165353.png](Screenshot_2026-09-05_165353.png) | Filtered signal overlaid on the original modulated signal, confirming the bandpass stage passes it through intact |
| [Screenshot_2026-05-07_170134.png](Screenshot_2026-09-05_170134.png) | Envelope detector output vs. original audio, showing the recovered envelope tracking the source's loud/quiet pattern |
| [Screenshot_2026-09-05_170847.png](Screenshot_2026-09-05_170847.png) | Final recovered audio (after DC blocking) vs. original audio, the main before/after comparison |
