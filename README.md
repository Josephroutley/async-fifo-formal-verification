# async-fifo-formal-verification
This project focuses on designing a robust **asynchronous FIFO (First-In-First-Out)** memory buffer to handle safe data crossing between two unrelated clock domains (Clock Domain Crossing - CDC)

Unlike standard simulation-based verification, this project utilizes **Formal Verification** to mathematically prove the absence of metastability issues and pointer errors.

## Learning Objectives (NVIDIA Target Skills)
* **CDC Design:** Implementing Gray code pointer synchronizers to prevent metastability.
* **Formal Verification:** Using **SymbiYosys** to prove safety properties (assertions) rather than just simulating random vectors.
* **SystemVerilog Assertions (SVA):** Writing immediate and concurrent assertions for FIFO full/empty states.

## Architecture
* **Write Domain:** Handles data ingress and binary-to-gray conversion for the write pointer.
* **Read Domain:** Handles data egress and binary-to-gray conversion for the read pointer.
* **Synchronizers:** Double-flop synchronizers to pass Gray pointers between domains.
* **Memory:** Dual-port RAM inference.

## Tools & Tech Stack
* **Language:** SystemVerilog / Verilog-2005
* **Simulation:** Icarus Verilog
* **Formal Verification:** SymbiYosys (SBY) & Yosys
* **Waveform Viewer:** GTKWave

## Roadmap
- [ ] Implement Dual-Port RAM module.
- [ ] Implement Write and Read control logic with Binary/Gray conversion.
- [ ] Implement 2-stage synchronizers.
- [ ] **Formal Verification:** Define SVA properties (e.g., "Read pointer never overtakes Write pointer").
- [ ] **Formal Verification:** Run Bounded Model Checking (BMC) to prove design correctness.
