# Day-1: Inception of open-source EDA, OpenLANE and Sky130 PDK

## SKY130_D1_SK2 - SoC design and OpenLANE
<br />

- ### `SKY_L1` - Introduction to all components of open-source digital asic design
    - Designing Digital ASIC in an automated way requires certain elements (all of them must be present from day-1):
        - `RTL IPs`: HDLs that are used to implement the design. For example, RISC-V is an RTL IP.
        - `EDA Tools`: Tools for electronic design automation. For example, Yosys, OpenSTA, OpenROAD, etc.
        - `PDK Data`: It is a collection of files that are used to communicate with the foundry. For example, Skywater 130nm PDK.
    - For open-source digital ASIC design, we need open-source:
        - `RTL IPs`: available on librecores.org, opencores.org, github.com, etc.
        - `EDA Tools`: such as Spice simulator, Magic and nowadays Qflow, OpenLANE, OpenROAD, etc.
        - `PDK Data`: such as Skywater 130nm PDK.
    - What is PDK?
        - PDK is the interface between the FAB and the designers.
        - It is a collection of files used to model fabrication process for EDA tools used to design an IC.
            - Process Design Rules: DRC, LVS, PEX, etc.
            - Device Models: SPICE, Verilog, etc.
            - Digital Standard Cell Libraries: LEF, Liberty, etc.
            - IO Libraries: LEF, Liberty, etc.
            - Technology Files: SPEF, etc.
            - and many more.
        - Google released the first-ever PDK for 130nm node in 2020 to the masses with Skywater.
    - Is `130 nm` fast?
        - Yes it is, some examples are:
            - Intel Pentium IV @ 3.46 GHz
            - OSU's single-chip RV32I CPU @ 327 MHz, meaning pipelined version can achieve > 1 GHz clock.
    - ASIC design flow: piece of software that carries out the design process, from RTL to GDSII.
    
    <br />

    <p align="center">
    <img src="../assets/day1_sk2_l1_asic_design_flow.png" alt="ASIC Design Flow"><br>
    Fig 1: ASIC Design Flow (source: SKY130_D1_SK2 > SKY_L1 video)
    </p>

    <br />

- ### `SKY_L2` - Simplified RTL2GDS flow
    1. `Synthesis`
        - Converts design RTL into a circuit made out of components from the `Standard Cell Library (SCL)`.
        - The resultant circuit is gate-level netlist which is functionally equivalent to the RTL code.
        - Standard cells have regular layout.
        - It is done using a tool called `Yosys`.
    2. `Floorplanning + Power Planning`
        - The objective here is to plan the silicon area for the design and also plan the robust power distribution network.
        - `Chip Floorplanning`: chip die is partitioned into different blocks.
        - `Macro Floorplanning`: each block is partitioned into different macros.
        - It is the process of placing the blocks of the design on the chip.
        <!-- - It is done using a tool called `graywolf`. -->
    
    <br />
