# Week 7 Task – BabySoC Physical Design & Post-Route SPEF Generation

This document presents the complete physical design implementation of the BabySoC using OpenROAD, covering all stages from floorplanning to post-route parasitic extraction (SPEF generation). The objective of this task is to integrate the theoretical and practical aspects of digital design by executing a full RTL-to-GDSII flow on a real System-on-Chip (SoC).

Through this exercise, the BabySoC design undergoes floorplan definition, standard cell placement, routing, and parasitic extraction to reflect a realistic ASIC design process. Each stage is explored to understand how physical parameters—such as floorplan constraints, placement density, and routing topology—affect timing performance and design closure.

The outcome of this work is a fully placed and routed BabySoC layout, accompanied by a generated SPEF file that enables post-route Static Timing Analysis (STA). This provides insight into how parasitic effects influence signal delay and how accurate timing verification is performed in professional VLSI design environments.

Comprehensive screenshots, step-by-step procedures, and observations are documented to demonstrate the design flow, tools used, challenges encountered, and verification results.

### Setup and Prepare Project Directory
Clone or set up the directory structure as follows:
```txt
VSDBabySoC/
├── src/
│   ├── include/
│   │   ├── sandpiper.vh
│   │   └── other header files...
│   ├── module/
│   │   ├── vsdbabysoc.v      # Top-level module integrating all components
│   │   ├── rvmyth.v          # RISC-V core module
│   │   ├── avsdpll.v         # PLL module
│   │   ├── avsddac.v         # DAC module
│   │   └── testbench.v       # Testbench for simulation
└── output/
└── compiled_tlv/         # Holds compiled intermediate files if needed
```

### 🛠️ Cloning the Project

To begin, clone the VSDBabySoC repository using the following command:

```bash
cd ~/VLSI
git clone https://github.com/manili/VSDBabySoC.git
cd ~/VLSI/VSDBabySoC/
```
