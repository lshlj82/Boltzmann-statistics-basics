# Boltzmann Statistics: An Interactive Companion

An interactive web demo of the basic ideas and formalism of Boltzmann statistics, written for undergraduate statistical physics (Statistical Physics II, Chapter 6). It follows Prof. Sang Hoon Lee's lecture notes (Gyeongsang National University), which are based on Schroeder, *An Introduction to Thermal Physics*, §6.1–6.2.

The demo is one self-contained `index.html` file. It needs no build step and no dependencies.

> **Author of the lecture notes:** Prof. Sang Hoon Lee, Department of Physics, Gyeongsang National University  
> **Interactive demo:** created by **Claude Opus 5.5** (Anthropic) from Prof. Lee's lecture notes.

## Contents

| Section | What you can explore |
|---|---|
| **6.0 Isolated vs. reservoir** | An illustration of one oscillator (the system) in contact with a reservoir made of many oscillators (an Einstein solid). A live Monte Carlo simulation lets energy quanta hop between the oscillators, and the atom's energy histogram is compared with the exact count Ω<sub>R</sub>(q − n). You can isolate the atom to fix its energy. |
| **6.1 Boltzmann factor** | The exact probability ∝ Ω<sub>R</sub>(q − n) is compared with (1/Z) e<sup>−nε/k<sub>B</sub>T</sup> as the reservoir grows from 10 to 10,000 oscillators. |
| **Hydrogen excitation** | Relative populations of the n = 1, 2, 3 levels as a function of T, including degeneracy. There are presets for the Sun (5800 K) and for γ UMa (9500 K), tied to the Balmer absorption lines. |
| **Partition function** | Z for a two-state system, a toy 0/4ε/7ε atom, a harmonic oscillator, and hydrogen-like degenerate levels. Shows the limits Z → 1 as T → 0 and Z → number of states at high T. A slider shifts all energies by E<sub>0</sub> to show that probabilities don't change (also Problem 6.2). |
| **Problem 6.11** | ⁷Li nuclear spin populations in the Purcell–Pound experiment. Reversing the field suddenly produces T = −300 K. |
| **6.2 Averages and fluctuations** | The five-atom toy model from Problem 6.17, where you can move atoms between levels. A canonical-ensemble panel checks Ē = −∂ ln Z/∂β, the mean of E² from (1/Z) ∂²Z/∂β², and σ<sub>E</sub> = k<sub>B</sub>T √(C/k<sub>B</sub>) (Problems 6.16–6.18). You can also draw ensemble samples. |

## Running locally

Open `index.html` in any modern browser, or serve the folder:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Publishing with GitHub Pages

1. Push `index.html` and this `README.md` to a repository.
2. Go to **Settings → Pages**, choose **Deploy from a branch**, and select `main` / `root`.
3. The demo will be served at `https://<username>.github.io/<repository>/`.

## Technical notes

- Plain HTML, CSS, and JavaScript with Canvas 2D charts and an inline SVG illustration.
- Fonts come from Google Fonts (Source Serif 4, IBM Plex Sans) and fall back to system fonts when offline.
- The reservoir multiplicities use the Einstein-solid formula Ω(N, q) = (q + N − 1)! / [q! (N − 1)!], evaluated with a log-gamma function so that very large reservoirs don't overflow.
- Supports light and dark mode, mobile layouts, keyboard focus, and `prefers-reduced-motion` (the simulation starts paused).
- Energies are in units of ε unless labeled. k<sub>B</sub> = 8.617 × 10⁻⁵ eV/K.

## Reference

D. V. Schroeder, *An Introduction to Thermal Physics* (Addison-Wesley, 2000), Chapter 6.
