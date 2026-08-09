# NMOS Characterization

## Aim
To characterize a single NMOS transistor by obtaining its DC I–V behavior — output
characteristics (Id vs Vds) and transfer characteristics (Id vs Vgs) — using Cadence
Virtuoso and Spectre.

## Design Specifications
| Parameter | Value |
|---|---|
| Technology | gpdk090 (90 nm) |
| Device | `gpdk090_nmos1v` |
| Width (W) | 1 µ |
| Length (L) | 100 n |
| Multiplier (m) | 1 |
| Vds sweep | 0 – 1.2 V |
| Vgs sweep (parametric) | swept as a family of curves |

## Circuit Description
The test schematic (`NMOS_chara`) consists of a single NMOS device with:
- Drain connected to a DC voltage source `vds` (swept 0–1.2 V)
- Gate connected to a DC voltage source `vgs`
- Source and body tied to ground

This setup allows the drain current (`/NM0/D`) to be measured directly as a function
of Vds and Vgs.

## Simulation Procedure
1. Built the `NMOS_chara` test schematic with a single gpdk090 NMOS (W = 1µ, L = 100n)
   and independent DC sources for Vgs and Vds.
2. Ran a DC sweep of Vds (0 → 1.2 V) at a fixed Vgs to obtain the output
   characteristics (`I_vs_Vds.png`).
3. Repeated the Vds sweep for multiple Vgs values to obtain the family of output
   characteristic curves (`I_vs_Vds_Parametric.png`).
4. Ran a DC sweep of Vgs (0 → 1.2 V) at a fixed Vds to obtain the transfer
   characteristics (`I_vs_Vgs.png`).
5. Schematic view captured as `Layout.png`.

## Files in this folder
| File | Description |
|---|---|
| `I_vs_Vds.png` | Drain current vs Vds at a single Vgs |
| `I_vs_Vds_Parametric.png` | Family of Id–Vds curves for multiple Vgs values |
| `I_vs_Vgs.png` | Drain current vs Vgs (transfer characteristic) at a fixed Vds |
| `Layout.png` | Schematic editor view of the NMOS test circuit |

## Results
- The Id–Vds family plot shows the expected NMOS behavior: a linear (triode) region
  at low Vds followed by current saturation at higher Vds, with higher Vgs curves
  giving higher saturation current.
- The single Id–Vds curve reaches roughly 720 µA at Vds = 1.2 V for the chosen Vgs.
- The Id–Vgs transfer curve shows the current rising from near zero below threshold,
  through the sub-threshold/moderate-inversion region, and increasing steeply past
  roughly Vgs ≈ 0.4–0.5 V, consistent with square-law/strong-inversion behavior at
  higher Vgs.

## Observations
- The output characteristics confirm clear triode-to-saturation transition typical
  of long-channel MOSFET behavior.
- The transfer characteristic shows a soft threshold region rather than an abrupt
  turn-on, as expected for the gpdk090 device model.

## Conclusion
The DC characterization of the NMOS device was carried out successfully, and the
extracted I–V curves match expected first-order MOSFET behavior.

## Status
- Results/analysis PDF — to be added
- This folder is being treated as a standalone submission and does not follow the
  multi-subfolder structure used for other experiments.
