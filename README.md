# Muhammad Imran - Intel CKT Training

## Table of contents
* [Day 1 - Fundamentals of VLSI Design and overview of Sand-to-Silicon ]



## Day 1
### Topic - Day 1 - Fundamentals of VLSI Design and overview of Sand-to-Silicon
<Details>
 <summary>Theory</summary>
 
### Theory 
**Overview of VLSI Design**
* **Packaged Chip**  
  -Packaging of silicon die with plastic case to protect the die
  * Examples types of packaging:
    * System in a package (SIP)
    * Dual in-line package (DIP)
    * Quad-flat no-leads (QFN)
    * Ball grid array (BGA)
  
  * **Die** 
    * Size is generally 1mmx1mm or 1mmx2mm
    * Made from a wafer which every single wafer consists of many die
    * **Inside the die:**  
  ![image](https://user-images.githubusercontent.com/121994033/210920544-118c0d99-ec97-4fcf-a49a-5fb883793df9.png)
      * Digital  
        Consists of Gates, Muxes, Decoders, Counters, Resistors, FSMs etc which all are made by standard cells using semi custom VLSI design flow.
      * Analog and RF
        * Consists of Clock: VCO and PLL; Voltage Ref. and Reg.: Bandgap reference, LDO, DC-DC converter; Data: PRBS generator; Amplifiers and Filters;  
          Interfaces: ADC and DAC  
        * All are made using custom VLSI flow  
      * Memory and Memory Controller  
        Consists of Static Random Access Memory (SRAM) and SRAM controller
  
  **VLSI Design Methodology**
    * **FPGA Based Design**
      * Faster prototyping and cost-effective
      * A typical FPGA chip consists,
        * Input/output buffers
        * Array of configurable logic blocks (CLBs)
        * Programmable interconnect structures
      * The programming of interconnects is accomplished by programming of RAM
      * Signal routing between the CLBs and the I/O blocks made by configurable switching matrice
    * **ASIC Design**
      * **Standard cell based design**
        * most prevalent full-custom design styles and requires development of a full-custom mask set.
        * commonly used logic cells are developed, characterized, and stored in a standard-cell library.
        * constant height for all cells in a same technology
        * can have several version for different fan-out driving capability

      * **Full custom design**
        * done without any library by designers
        * layouts, orientation, placement of transistor done by designers
        * developement cost is high
        * all analog and RF designs are full custom design
  
  **VLSI Design Quality**  
    * **Testability**  
      Design of testable chip  
    * **Yield and Manufacturability**  
      Yield: No. of tested of chips/Total no. of Chips    
      Functional Yield: Checks at lower speed  
      Parametric Yield: Checks at required speed
    * **Reliability**  
      ESD, EOS, Electromigration, Oxide breakdown, Power and ground bouncing, On-chip noise and cross-talk.
    * **Technology Upgradability**  
      Design style must be flexible to technology update so that the design can be use back with minimal cost. 
      Use advanced CAD tools to automatically generate physical layout.
  
  **Package Technology**
    -Chip designers should work closely with package designers to consider various packaging constraints, parasitic, length of bonding wire, no. of bonding pads.  
    * **Classification of Package**  
    * Pin-through-hole (PTH): holes drilled in PCB, not cost effective but soldering process in not inexpensive.
    * Surface Mount Technology (SMT): Directly soldered on the PCB, cost and space effective but expensive equipment's are needed for soldering
    * Plastic: Dominant for many years but it has the disadvantage of being permeable to environmental moisture.
    * Ceramic: Power consumption, performance and environmental requirements
![image](https://user-images.githubusercontent.com/121994033/210987021-f788bed8-7a79-4284-8db6-d7b5e91ada3b.png)

  **CAD Tools**  
  -Execute majority of the computation intensive parts of the design  
  Can be categorized into:
  * High-level synthesis
  * Logic synthesis
  * Circuit optimization
  * Layout
  * Placement and routing
  * Simulation
  * Design rules and checking
