# PCIe Gen3 Core — Transaction Layer & Data Link Layer Design and Verification

## Overview

This project focuses on the RTL design and functional verification of the Transaction Layer (TL) 
and Data Link Layer (DLL) of a reusable PCIe Gen3 core targeting SoC interconnect applications. 
The design and testbench were developed entirely from scratch in SystemVerilog, following 
industry-standard UVM based verification methodology.

---

## Architecture

### Transaction Layer (TL)
- TLP (Transaction Layer Packet) formation and parsing
- Support for Memory Read, Memory Write, and Completion TLP types
- Header generation with address, length, and tag fields
- Payload management and byte enable handling
- Credit based flow control for Posted, Non-Posted, and Completion TLP classes

### Data Link Layer (DLL)
- Sequence number assignment and tracking for every outgoing TLP
- LCRC generation and checking for error detection
- ACK/NAK mechanism for reliable TLP delivery
- Replay buffer for retransmission of unacknowledged TLPs
- Timeout based automatic replay triggering
- DLLP (Data Link Layer Packet) generation for ACK, NAK, and flow control updates

---

## Verification Environment

The testbench follows a UVM based layered architecture:
