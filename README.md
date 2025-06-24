# Synchronous FIFO – Verilog

## Overview
This project implements a **Synchronous FIFO (First-In-First-Out) buffer** in Verilog. It supports data communication between two synchronous clock domains (same clock source), using a circular buffer with read/write pointers, full/empty detection, and parameterized data width and depth.

This FIFO is essential for buffering and pipelining data in digital systems, SoCs, and communication interfaces.

---

## Module Structure

### `fifo_sync.v` – RTL Design
- **FIFO Memory Array**  
  Circular buffer implemented using a register array with parameterized depth and width.

- **Write/Read Pointers**  
  Used to track positions for data insertion and retrieval. Includes wrap-around logic.

- **Status Flags**  
  `full`, `empty`, and optionally `almost_full`, `almost_empty` signals for buffer state management.

- **Data Handling Logic**  
  Handles valid `write_en` and `read_en` operations based on FIFO state.

---

### `fifo_tb.v` – Testbench
- Simulates data push/pop operations at the same clock rate.
- Validates correct order of data retrieval and pointer update logic.
- Includes corner cases such as buffer full, empty, and wrap-around behavior.

---

## Features
- **Synchronous design** with single clock input.
- Parameterizable `DATA_WIDTH` and `FIFO_DEPTH`.
- Accurate **full/empty detection** and pointer-based indexing.
- **Write and read enable** logic to control data flow.
- Verified using waveform analysis for correctness and edge cases.

---

## ▶How to Run
1. Open `fifo_sync.v` and `fifo_tb.v` in a Verilog simulator like ModelSim or EDA Playground.
2. Set `fifo_tb` as the top-level module.
3. Simulate and observe data in/out behavior, pointer movement, and full/empty signal toggling.
4. Use `$dumpfile`, `$dumpvars`, and GTKWave for waveform analysis.

---

## 🛠 Tools Used
- **Verilog HDL**  
- **Simulation**: EDA Playground, ModelSim, GTKWave  
- **Verification**: Testbench with controlled write/read scenarios

---

## Learning Outcomes
- Mastered synchronous FIFO design at RTL level.
- Gained understanding of pointer logic, wrap-around, and flag generation.
- Applied modular Verilog practices for reliable communication block design.

---

## Author
**Sarath Srinivasan**  
B.Tech in Electrical Engineering  
Aspiring VLSI Engineer

---

## Tags
`verilog` `fifo` `digital-design` `synchronous` `rtl` `buffer` `communication` `hardware`
