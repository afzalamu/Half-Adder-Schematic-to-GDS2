# Half-Adder Design: Schematic to GDSII using GPDK90 in Cadence

This repository contains the complete design flow for a Half Adder, starting from schematic creation to GDSII generation, using Cadence tools with the GPDK90 process library. A half adder is a fundamental digital circuit that performs binary addition on two single-bit inputs, generating a sum and a carry output. This project covers schematic design, layout, design rule checks (DRC), layout versus schematic checks (LVS), and RC extraction.

## Project Overview

### Half Adder: Definition and Truth Table
A half adder is a combinational circuit that adds two single-bit binary numbers (A and B). It produces two outputs: 
- **Sum (S)**: Result of the binary addition.
- **Carry (C)**: Represents any overflow into the next higher bit.

**Truth Table:**
| Input A | Input B | Sum (S) | Carry (C) |
|---------|---------|---------|-----------|
|    0    |    0    |    0    |     0     |
|    0    |    1    |    1    |     0     |
|    1    |    0    |    1    |     0     |
|    1    |    1    |    0    |     1     |

### Design Flow
This project follows a standard ASIC design flow for digital circuits:
1. **Schematic Creation**
2. **Symbol and Testbench Setup**
3. **Pre-Layout Simulation**
4. **Layout Creation (DRC and LVS checks)**
5. **Post-Layout Simulation**
6. **RC Extraction**
7. **GDSII Generation**

---

## Detailed Process and Results

### 1. Schematic Creation
The initial schematic of the Half Adder was created using GPDK90 in Cadence. The schematic forms the base for further simulations and layout design.

**Schematic Diagram:**
![Half Adder Schematic](https://github.com/user-attachments/assets/00923989-1dde-4d5b-8b71-0a2181dc0191)

### 2. Symbol and Testbench Creation
A symbol view was generated for the Half Adder, and a testbench was set up to verify its functionality through transient and delay analysis.

**Symbol and Testbench:**
![Symbol and Testbench](https://github.com/user-attachments/assets/d8422d98-7c68-4a3a-b8d2-64bae14c28c7)

### 3. Pre-Layout Simulation Results
Simulations were run to verify the functionality and performance of the Half Adder. Critical parameters like delay from input **A** to **Sum** and **Carry** were analyzed.

**Simulation Results (Pre-Layout):**
![Pre-Layout Simulation](https://github.com/user-attachments/assets/9ab37a3b-e11f-4f6c-a241-c7b88515beca)

**Delay from Terminal 'A' to 'Sum':**
![Delay - A to Sum (Pre-Layout)](https://github.com/user-attachments/assets/91d700cb-5a6f-40de-9f8a-76f71ceb1a94)

**Delay from Terminal 'A' to 'Carry':**
![Delay - A to Carry (Pre-Layout)](https://github.com/user-attachments/assets/ac552859-603e-41d6-b3ca-c16ec74ae6de)

### 4. Layout Creation and Verification
The Half Adder layout was designed using Cadence Virtuoso with GPDK90. After completing the layout, **Design Rule Check (DRC)** and **Layout Versus Schematic (LVS)** checks were performed to ensure compliance and correctness.

**DRC and LVS Checks:**
- DRC: Passed successfully
- LVS: Passed successfully

**DRC Result:**
![DRC Check](https://github.com/user-attachments/assets/a98d56ba-acae-41c9-b535-312d6ab57201)

**LVS Result:**
![LVS Check](https://github.com/user-attachments/assets/05c56b9b-169f-49f6-a5ba-1af14ce5995f)
![LVS Result](https://github.com/user-attachments/assets/f11fec58-ec9a-4a97-8e9c-7f61242a4637)

### 5. Post-Layout Simulation Results
After layout, post-layout simulations were conducted to examine performance changes due to parasitic elements. Delays from terminal **A** to **Sum** and **Carry** were analyzed again.

**Post-Layout Simulation Results:**
![Post-Layout Simulation](https://github.com/user-attachments/assets/d9d5d402-7495-4ff2-9a50-d0e519cebbba)

**Delay from Terminal 'A' to 'Sum':**
![Delay - A to Sum (Post-Layout)](https://github.com/user-attachments/assets/bf54cd52-1052-47ac-b387-09bc7a3d3f06)

**Delay from Terminal 'A' to 'Carry':**
![Delay - A to Carry (Post-Layout)](https://github.com/user-attachments/assets/6311ec04-24c4-4b5a-befd-b59a1c18e538)

### 6. RC Extraction
RC extraction was performed to capture parasitic capacitance and resistance, ensuring post-layout simulations reflect realistic circuit behavior.

**RC Extraction Results:**
![RC Extraction](https://github.com/user-attachments/assets/db28cb5c-65da-45f0-b065-6a7b3e0a2d1c)
![RC Extracted Layout](https://github.com/user-attachments/assets/04c702be-350b-4455-bda9-f7c3a8190268)

### 7. GDSII Generation
The final design was exported in GDSII format for tape-out or further processing steps.

**GDSII Output:**
![GDSII File](https://github.com/user-attachments/assets/2f2b756f-2c7c-4b31-9c69-2753e695b38c)

---

## Technical Details

### Important Definitions
- **DRC (Design Rule Check):** Ensures that the layout complies with specific design rules set by the fabrication process.
- **LVS (Layout Versus Schematic):** Verifies that the layout corresponds accurately to the schematic netlist.
- **RC Extraction:** Process of modeling parasitic resistances (R) and capacitances (C) after layout, which impact signal delay and power consumption.
- **GDSII Format:** A binary format for transferring IC layout data to silicon foundries.

---

## Tools Used
- **Cadence Virtuoso** for Schematic, Layout, and GDSII generation
- **Spectre Simulator** for pre- and post-layout simulations
- **GPDK90**: A generic process design kit based on 90 nm technology

---

This repository provides all files required for each design step. Please feel free to clone or download the repository for educational or reference purposes.

