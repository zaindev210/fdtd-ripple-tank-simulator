# 2D Ripple Tank & Wave Interference Simulator (PECTAA ICS / FSc)

> **Suggested GitHub Repository Name:** `fdtd-ripple-tank-simulator`
>
> **Live Demo:** `[Insert Your GitHub Pages Link Here]`

A real-time 2D wave physics laboratory built in pure JavaScript and HTML5 Canvas for **PECTAA ICS / FSc Physics** demonstrations. Powered by a Finite-Difference Time-Domain (`FDTD`) wave equation solver over an `ImageData` pixel buffer, this simulator demonstrates wave superposition, constructive/destructive interference, single- and double-slit diffraction, Lloyd's mirror, parabolic focusing, and the Doppler effect.

## Key Features

- **2D FDTD Wave Solver (`WaveSolver`):** Integrates the 2D scalar wave equation across a `384 × 256` grid using `Float32Array` typed buffers and Courant–Friedrichs–Lewy (`CFL`) stability enforcement ($C \le 0.68$).

- **Mur's 1st-Order Absorbing & Reflective Boundaries:** Switch seamlessly between open-tank wave absorption and hard reflective perimeter walls.

- **4 Optical Visualization Palettes:**
  1. _Classic Ripple Tank (Water Caustics & Specular Slope Lighting)_

  2. _Phase Diverging (_$+\text{Crest}$ _/_ $-\text{Trough}$_)_

  3. _Wave Intensity / Energy (_$\langle u^2 \rangle$_)_ for inspecting stationary nodal hyperbolas

  4. _Optical Schlieren (Wavefront Gradient)_

- **Interactive Lab Tools & Virtual Probe Oscilloscope:** Paint or erase barrier slits, drag oscillating point sources in real time, splash the water surface, and measure live displacement $u(t)$ and path difference ($\Delta S = m\lambda$) with a movable probe.

- **6 One-Click Wave Presets:** Two-Source Interference, Young's Double-Slit, Single-Slit Diffraction, Doppler Effect (Moving Source), Lloyd's Mirror, and Parabolic Reflector Focusing.

## PECTAA Syllabus Wave Formulas

- **Fundamental Wave Equation:** $v = f\lambda \quad \left(T = \frac{1}{f}\right)$

- **Constructive Interference (Antinodes):** $\Delta S = m\lambda \quad (m = 0, 1, 2, \dots)$

- **Destructive Interference (Nodes):** $\Delta S = \left(m + \frac{1}{2}\right)\lambda$

- **Young's Double-Slit Fringe Spacing:** $\Delta y = \frac{\lambda L}{d}$

- **Doppler Effect (Moving Source):** $f' = \left(\frac{v}{v \mp v_s}\right)f$

### Computational Stencil (2D FDTD Leapfrog)

$$
u_{i,j}^{n+1} = 2u_{i,j}^n - u_{i,j}^{n-1} + C^2\left(u_{i+1,j}^n + u_{i-1,j}^n + u_{i,j+1}^n + u_{i,j-1}^n - 4u_{i,j}^n\right), \quad C = \frac{v\,\Delta t}{\Delta x} \le \frac{1}{\sqrt{2}}
$$

## Getting Started

1. **Clone the repository:**

   ```
   git clone https://github.com/zaindev210/fdtd-ripple-tank-simulator.git
   cd fdtd-ripple-tank-simulator

   ```

2. **Rename entry file & run locally:**
   Rename `ripple-tank.html` to `index.html` and open it in any web browser.

## License

Open-source under the **MIT License**.
