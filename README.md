# CMOS-Full-Adder-Layout-gpdk090
This repository contains the custom IC design, transistor-level schematic, physical layout, and DRC/LVS physical verification of a 1-bit CMOS Full Adder standard cell using **Cadence Virtuoso** on Generic PDK 90nm (**GPDK090**).

---

## 1. Specifications & Design Highlights
- **Process Technology:** Generic PDK 90nm (GPDK090)
- **Supply Voltage ($V_{DD}$):** 1.2 V
- **Logic Topology:** 2 × XOR_2 gates + 3 × NAND_2 gates
- **Layout Architecture:**
  - Standard cell layout style with continuous horizontal $V_{DD}$ and $GND$ rails on **Metal 1**.
  - Guard rings and substrate/well tap contacts integrated to mitigate latch-up.
  - Signal routing implemented using **Poly**, **Metal 1**, and cross-cell routing jumpers on **Metal 2**.
- **Physical Verification:** Clean DRC (Design Rule Check) and LVS (Layout Versus Schematic).

---

## 2. Gate-Level Schematic
Logic implementation of the 1-bit Full Adder:
- $S = A \oplus B \oplus C_{in}$
- $C_{out} = (A \cdot B) + (C_{in} \cdot (A \oplus B))$ (synthesized via NAND-NAND equivalent logic)

![Schematic](schematic.png)

---

## 3. Physical Layout
Full custom standard cell layout adhering to 90nm design rules:

![Layout](layout.png)

---

## 4. Verification & Results
- **DRC:** 0 DRC violations.
- **LVS:** Netlist extracted from layout matches transistor schematic completely (*Schematic and Layout Match*).
