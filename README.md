# DE10-Standard FPGA UART XOR Encryption/Decryption

**Academic Team Project | ENGI 9865 – Advanced Digital Systems**  
**Memorial University of Newfoundland | 2026**

## Overview

This project explores UART communication and hardware–software integration on the DE10-Standard FPGA board using a simple XOR cipher. The team developed and documented a simulation design and an HPS-assisted hardware implementation.

This repository is a portfolio documentation summary based on the project final report. Original VHDL files, testbench, Quartus project, HPS software, and board configuration files are not currently included.

## System Architecture

The report describes the hardware communication path as:

**PC → UART → HPS → FPGA XOR module → HPS → UART → PC**

The Hard Processor System (HPS) runs Linux and interfaces with the FPGA through a memory-mapped bridge. The simulation design is described separately as UART receiver → XOR module → UART transmitter.

## XOR Operation

The project uses the fixed example key `0x5A`:

- Encryption: `ciphertext = plaintext XOR key`
- Decryption: `plaintext = ciphertext XOR key`
- Example: `0x41 XOR 0x5A = 0x1B`; applying the key again recovers `0x41`.

This fixed-key XOR operation is an educational demonstration, not secure encryption for real-world sensitive data.

## Tools and Hardware

- DE10-Standard FPGA development board
- VHDL
- Intel Quartus Prime
- ModelSim
- Linux on HPS
- PuTTY serial terminal
- MicroSD card and USB serial interface

## Verification Documented in the Report

The report describes a self-checking simulation testbench that compares expected and actual output and reports PASS or FAIL. Its worked simulation example uses input `0x41`, key `0x5A`, and expected output `0x1B`.

Selected hardware output values reported by the team:

| Input | Encrypted | Decrypted |
|---|---|---|
| 0x03 | 0x59 | 0x03 |
| 0x13 | 0x49 | 0x13 |
| 0x43 | 0x19 | 0x43 |
| 0x07 | 0x5D | 0x07 |
| 0x27 | 0x7D | 0x27 |

These are reported coursework observations, not results independently rerun for this repository.

## My Contributions

According to the team contribution statement, my work included:

- Project coordination and system architecture design
- VHDL development for UART and XOR modules
- Simulation and verification
- Report writing and overall project supervision

## Team

- **Fatema Tuj Johora:** Coordination, architecture, VHDL development, simulation, verification, and report writing.
- **Shammi Akter Shahinoor:** Testing and verification assistance, development environment setup, and report preparation.
- **Manpreet Kaur:** Hardware setup and implementation assistance, Linux/HPS testing support, and documentation.

## Scope and Reproducibility

The report documents successful simulation and hardware verification. The available materials do not provide a complete build package, measured latency or throughput, or all board-specific interface details needed to reproduce the implementation. No independent simulation or hardware testing has been performed during preparation of this portfolio summary.

## Skills Demonstrated

Project Coordination · Digital System Design · VHDL · FPGA · UART · Hardware–Software Integration · Simulation and Verification · Technical Documentation

## Author

**Fatema Tuj Johora**  
MASc Student, Computer Engineering  
Memorial University of Newfoundland

[GitHub Portfolio](https://github.com/FatemaTujJohora11)
