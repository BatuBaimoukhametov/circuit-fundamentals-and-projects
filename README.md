# Circuit Fundamentals and Projects

Self-directed study of circuit theory and power systems fundamentals, working through All About Circuits Vol. 1 and 2, extended into standalone applied projects using LTspice.

## Structure

- `/foundations` — LTspice simulations built while working through AAC Vol. 1-2, covering DC/AC circuit theory, filters, resonance, transformers, and three-phase/symmetrical components fundamentals (messy)
- `/projects` — Standalone applied projects extending that theory into real systems (see below)

## Projects

- **[AM Radio Transmit/Receive Link](projects/am-radio-link)** — simulated end-to-end AM modulation and demodulation using a real audio clip
- **[AC-DC Power Supply with Ripple Analysis](projects/ac-dc-power-supply)** — transformer-rectifier-filter power supply, ripple measured and validated against theory
- **[Resonant Wireless Power Transfer Link](projects/resonant-wireless-power-transfer)** — coupled resonant tanks demonstrating wireless power transfer and frequency splitting
- **[Industrial Power Factor Correction](projects/industrial-power-factor-correction)** — corrected a lagging power factor load using a calculated capacitor bank
- **[LC Speaker Crossover](projects/lc-speaker-crossover)** — first-order passive crossover verified against calculated crossover frequency

Each project folder contains its own LTspice schematic, a detailed README covering the build and results, and supporting screenshots.
