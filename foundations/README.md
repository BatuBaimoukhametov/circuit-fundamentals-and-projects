# Foundations: All About Circuits Vol. 1 & 2

Circuit simulations built in LTspice while working through Tony Kuphaldt's *All About Circuits*, Volumes 1 (DC) and 2 (AC). These aren't standalone projects, they're simulations I used to test and grasp concepts from the textbook and which I later implement in bigger simulations in `/projects`.

| Topic                         | File                            | Notes                                                                 |
| ----------------------------- | ------------------------------- | --------------------------------------------------------------------- |
| Resistive attenuators         | `Attenuators.asc`               | Several resistor networks that cut a 60 Hz sine exactly in half       |
| Symmetrical components        | `Symetrical_components_test.asc`| Three-phase set with sequence network and injected current            |
| Transformer coupling          | `Transformer_Test.asc`          | Two tightly coupled 10 mH pairs (K=0.99) under transient drive        |
| Diode-RC bridge               | `Bridge_circuit_doubleT.asc`    | Double-T path with diodes and unequal capacitors under .tran          |
| RL load response              | `Different_loads_test.asc`      | 500 Ω + 200 mH series combination driven by 10 V 60 Hz                |
| Three-phase power system      | `3_Source_power_system.asc`     | Two three-phase sources feeding identical 1.44 Ω loads                |
| Isolation transformer         | `Transformer_Isolation.asc`     | 1 kH primary / 100 H secondary (K=0.99) with secondary excitation     |
| Passive filters               | `Filters.asc`                   | RL low-pass, RC high-pass and mixed sections swept in frequency       |
| RLC resonance                 | `Resonance_filters.asc`         | Series and parallel tanks (1 H/1 µF and 100 mH/10 µF) under AC        |
| Twin-T notch filter           | `Twin-T_Band-stop_Filter.asc`   | Twin-T (200 Ω / 2 µF / 1 µF) producing a clear stop-band              |
| LC notch filter               | `Notch_Filter_1k.asc`           | 110 mH + 0.23 µF series combination tuned near 1 kHz                  |
| Parallel LC tank              | `AC_LC_parallel.asc`            | 100 mH ‖ 10 µF with near-zero series R, linear frequency sweep        |
| Parallel tank (duplicate)     | `Tank_circuit.asc`              | Same 100 mH ‖ 10 µF tank under identical AC analysis                  |
| Series LC resonance           | `AC_LC_series.asc`              | 100 mH + 10 µF driven at its calculated resonant frequency            |
| Inductor transient            | `Inductor_Transient.asc`        | 2 H inductor + 0.1 Ω with UIC and forced initial conditions           |
| Basic analog sources          | `Analog_test.asc`               | Pulse, dual-phase sines and pure DC sources into resistive loads      |
| Capacitor transient           | `Analog_capacitor.asc`          | Large capacitor + series resistor under 1 Hz sine                     |
| Inductor phase lag            | `Analog_inductor.asc`           | 2 H inductor with explicit .meas statements for phase difference      |
| Fourier synthesis             | `Fourier_Proof.asc`             | Odd harmonics (1–11) summed to reconstruct a square wave              |
| Pulse vs sine comparison      | `Faurier_Test.asc`              | 50 Hz square pulse and pure sine compared through a diode             |
| Tank antiresonance            | `Antiresonance.asc`            | Same LC tanks with resistor placed in series or parallel              |
| Inductor DC/AC behavior       | `Inductor_test.asc`             | Ideal versus lossy inductors under step and 1 Hz sine                 |
| Capacitor charge/discharge    | `Capacitor_test.asc`            | Large capacitor charging plus pulsed current-source discharge         |
| AC bridge balance             | `Bridge_advance_balance.asc`    | L–C bridge with values chosen for null at 400 Hz                      |

*Extended, standalone applications of these concepts (radio systems, power supplies, protection logic) are in [`/projects`](../projects).*
