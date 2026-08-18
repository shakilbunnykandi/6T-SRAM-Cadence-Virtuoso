# 6T SRAM Cell Design and Stability Analysis 

## 📌 Project Overview
This repository contains the design, simulation, and stability analysis of a 6-Transistor (6T) SRAM (Static Random Access Memory) cell. The project was developed and simulated at the **Central Institute of Tool Design (CITD)** using industry-standard EDA tools to evaluate memory read/write stability and retention metrics.

---

## 🛠️ Tools & Technology
* **EDA Tool:** Cadence Virtuoso (Schematic Editor & Analog Design Environment L)
* **Simulator:** Spectre APS
* **Technology Node:** 45nm CMOS Process (`g45p1svt` / `g45n1svt`)
* **Supply Voltage:** 1.8V

---

## 📂 Repository Structure
* **`images/`**: Contains high-resolution screenshots of the schematic design and simulation plots (VTC and Butterfly curves).
* **`design/`**: Contains the exported Spectre netlist (`sram_netlist.scs`) for the memory cell.

---

## 📐 Circuit Architecture
The 6T SRAM cell is the fundamental building block of modern cache memory. The schematic implementation consists of:
* **Cross-coupled Inverters (Storage):** Two PMOS pull-up transistors and two NMOS pull-down transistors form a bistable latch that holds the complementary memory states (Q and Qb).
* **Access Transistors:** Two NMOS pass-transistors controlled by the Wordline (WL) connect the internal storage nodes to the Bitlines (BL and BLbar) for read and write operations.
* **Transistor Sizing:** Careful consideration was given to the Cell Ratio (CR) and Pull-Up Ratio (PR) to ensure non-destructive reads and successful writes.

---

## 📊 Simulation & Analysis

### 1. DC Analysis & Voltage Transfer Characteristics (VTC)
A rigorous DC voltage sweep was performed on the internal storage nodes (from 0V to 1.8V) using the Analog Design Environment (ADE L). This allowed for the observation of the switching thresholds and the voltage transfer characteristics of the internal inverters.

### 2. Static Noise Margin (SNM) & The Butterfly Curve
The primary metric for SRAM stability is the Static Noise Margin (SNM), which dictates the maximum amount of electrical noise the cell can tolerate before unintentionally flipping its state. 
* The VTC of the first inverter was superimposed with the inverse VTC of the second inverter to generate the classic **Butterfly Curve**.
* The symmetrical "eyes" of the butterfly plot confirm a robust and highly stable memory cell capable of retaining data under operational stress.

---

## 🚀 How to View
1. Navigate to the `images/` directory to view the Virtuoso schematic and the SNM simulation results.
2. The `design/sram_netlist.scs` file can be opened in any text editor to view the SPICE/Spectre netlist representation of the circuit.