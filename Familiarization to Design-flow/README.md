# Familiarization to Design-flow — CMOS Inverter

## Aim
To get familiarized with the Cadence Virtuoso design flow — schematic capture, symbol
creation, testbench setup, transient simulation, and layout — using a CMOS inverter as
the reference circuit.

## Design Specifications
| Parameter | Value |
|---|---|
| Technology | gpdk090 (90 nm) |
| Supply voltage (VDD) | 1.2 V |
| PMOS width (W) | 240 n |
| PMOS length (L) | 100 n |
| NMOS width (W) | 120 n |
| NMOS length (L) | 100 n |
| Multiplier (m) | 1 (both devices) |
| Input pulse | v1 = 0, v2 = 1.2 V, rise time (tr) = 100 p |

## Circuit Description
The CMOS inverter (cell: `CMOS_Inverter`, library: `Adi_lab`) consists of a single
PMOS (`gpdk090_pmos1v`) and a single NMOS (`gpdk090_nmos1v`) connected in the standard
inverter topology:
- PMOS source tied to VDD, NMOS source tied to GND
- Gates of both devices tied together to the input `Vin`
- Drains of both devices tied together to the output `Vout`

A four-pin symbol (VDD, GND, Vin, Vout) was created for the inverter so it could be
instantiated as a block in the testbench schematic.

## Simulation Procedure
1. Built the inverter schematic in Virtuoso Schematic Editor using gpdk090 PMOS and
   NMOS devices, sized as above.
2. Generated a symbol view for the inverter (`CMOS_Inverter`) with Vin, Vout, VDD, and
   GND pins.
3. Built a testbench schematic (`tb_CMOS_Inverter`) instantiating the inverter, with:
   - A DC voltage source (V0 = 1.2 V) for VDD
   - A pulse voltage source (V1: 0 → 1.2 V, tr = 100p) driving Vin
4. Ran a transient simulation in ADE L (Spectre) and plotted Vin and Vout in the
   Virtuoso Visualization & Analysis (waveform) window.
5. Created the physical layout of the inverter in the Layout Editor, using Metal1,
   Poly, Nwell, Cont, and Via1 layers, with VDD, GND, Vin, and Vout pins brought out.

## Results
- The transient response shows `Vin` (top trace) as a periodic pulse switching
  between 0 V and 1.2 V with a period of about 20 ns.
- `Vout` (bottom trace) is the inverted, complementary square wave, correctly
  switching between 0 V and 1.2 V out of phase with `Vin`, confirming inverter
  functionality.
- The layout was completed with all four pins (VDD, GND, Vin, Vout) accessible and
  the PMOS/NMOS placed in their respective Nwell/substrate regions.

## Observations
- The output faithfully tracks the logical inversion of the input across all
  observed cycles (0–100 ns).
- The output transitions show a small propagation delay relative to the input
  transitions, as expected from a physical CMOS switching stage.

## Conclusion
The CMOS inverter design flow — schematic entry, symbol generation, testbench-based
transient verification, and layout — was successfully carried out in Cadence
Virtuoso, and the inverter was confirmed to function correctly at the schematic
(pre-layout) level.

## Status / Pending
- DRC report — to be updated (run attempted, not yet clean)
- LVS report — to be updated (run attempted, not yet clean)
- Extracted view / post-layout simulation — to be updated
- Report.pdf — to be updated
