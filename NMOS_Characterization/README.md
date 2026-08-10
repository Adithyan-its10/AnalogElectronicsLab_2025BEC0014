# NMOS Characterization

## Aim
To characterize a single NMOS transistor by obtaining its DC I–V behavior — output
characteristics (Id vs Vds) and transfer characteristics (Id vs Vgs) — using Cadence
Virtuoso and Spectre.

## Circuit Description
The test schematic (`NMOS_chara`) consists of a single NMOS device with:
- Drain connected to a DC voltage source `vds` (swept 0–1.2 V)
- Gate connected to a DC voltage source `vgs`
- Source and body tied to ground

Drain current is measured directly as a function
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
5. Schematic view captured as `Schematic.png`.

## Files in this folder
| File | Description |
|---|---|
| `I_vs_Vds.png` | Drain current vs Vds at a single Vgs |
| `I_vs_Vds_Parametric.png` | Family of Id–Vds curves for multiple Vgs values |
| `I_vs_Vgs.png` | Drain current vs Vgs (transfer characteristic) at a fixed Vds |
| `Schematic.png` | Schematic editor view of the NMOS test circuit |

## Conclusion
The DC characterization of the NMOS device was carried out successfully, plotted the I-V curves.

## Status
- Results/analysis PDF — to be added
