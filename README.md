# Muhammad Imran - Intel CKT Training

## Table of contents
* [Day 1 - Fundamentals of VLSI Design and overview of Sand-to-Silicon ]
* [Day 2 - Details of IC Manufacturing Process ]
* [Day 3 - CMOS Fabrication Process in Deep Submicron and Ultra Deep Submicron Technology ]
* [Day 4 - Metal-Oxide-Semiconductor Structure ]
* [Day 5 - Metal-Oxide-Semiconductor FIELD EFFECT TRANSISTOR ]
* [Day 6 - MOSFET Intrinsic Capacitances ]
* [Day 7 - CMOS Inverter ]



## Day 1
### Topic - Fundamentals of VLSI Design and overview of Sand-to-Silicon
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
  </details>
  
 <Details>
 <summary>Assignment</summary>
 
 ### Assignment
 **RC Assignment**  
 ![image](https://user-images.githubusercontent.com/121994033/212216232-df6c4662-7c1c-49a0-ae07-ba81509ce382.png)
  </details>

## Day 2
### Topic - Details of IC Manufacturing Process
<details>
 <summary>Theory</summary>
 
### Theory 
**Analog IC Design Process**
![image](https://user-images.githubusercontent.com/121994033/211587318-48f31c1d-7a70-48c1-90a8-fa2c5472582c.png)

| Electrical Design | Physical Design | Test Design |  
| --- | --- | --- |
| process of going from the specification to a circuit solution | process of representing the electrical design in a layout consisting of many distinct geometrical rectangle at various levels | process of coordinating, planning and implementing the measurement of the analog integrated circuit performance |
| The electrical design requires active and passive device electrical models for creating the design, verifying the design and determining the robustness of the design | The physical design needs entering various geometries, follow DRC, LVS check and parasitic extraction | Types of test: Functional, Parametric, Static, Dynamic |

**Analog IC Design Process and its Relation with CAD and PDK**  
![image](https://user-images.githubusercontent.com/121994033/211595323-499f4d77-b1eb-47f9-8039-50dc1a877483.png)

**Role of Circuit Designer**  
 * Circuit Designer determine the implementation of the circuit which impact performance, power and cost
 * Design a practical circuit based on the device limits, technology constraints and physical implementations
 * Circuit designer should have very good understanding of layout design, so that in less iterations the design can be fridged.
 *  A good circuit designer should always discussed with the layout designer for better and efficient circuit design.
 
**CMOS Technology**  
 Why CMOS Technology?   
| Comparison Feature | BJT | MOSFET |  
| --- | --- | --- |
| Cut-off Frequency  | High | Less |
| Noise (at same thermal noise) | Less 1/f | More 1/f |
| DC Range of Operation | 9 decades of exponential current versus VBE | 2-3 decades of square law behaviour |
| Transconductance (Same Current) | Larger by 10X | Smaller by 10X |
| Small Signal Output Resistance | Slightly larger | Smaller for short channel |
| Switch Implementation | Poor | Good |
| Performance/Power Ratio | High | Low |
| Technology Improvement | Slower | Faster |
* Comparison made from digital viewpoint will side with CMOS. Since large volume mixed-mode technology will be driven by digital demands, CMOS is an obvious choice.  

**Categorization of the CMOS Technology**  
 * Submicron Technology: Lmin ??? 0.35 ??m
 * Deep Submicron Technology (DSM): 0.1 ??m ??? Lmin ??? 0.35 ??m
 * Ultra-Deep Submicron Technology (UDSM): Lmin ??? 0.1 ??m
 * BiCMOS Technology: Lmin = 0.5 ??m
 
 **CMOS Fabrication Process**  
 Process Steps:
 <Details>
 <summary>1. Wafer formation (sand-to-silicon)</summary>  
 
  * The basic raw material used in CMOS fabs is a wafer or disk of silicon, roughly 75 mm to 300 mm (12 inch) in diameter and less than 1 mm thick.  
  * Wafers are cut from boules, cylindrical ingots of singlecrystal silicon, that have been pulled from a crucible of pure molten silicon.  
  * Controlled amounts of impurities are added to the melt to provide the crystal with the required electrical properties.  
  * A seed crystal is dipped into the melt to initiate crystal growth.  
  * The seed is gradually withdrawn vertically from the melt while simultaneously being rotated.  
  * The molten silicon attaches itself to the seed and recrystallizes as it is withdrawn.  
  * The seed withdrawal and rotation rates determine the diameter of the ingot.  
  * Growth rates vary from 30 to 180 mm/hour.
  </details>
  
  <Details>
  <summary>2. Photolithography</summary> 
  
  * The patterning is achieved by a process called photolithography.  
  * The primary method for defining areas of interest (i.e., where we want material to be present or absent) on a wafer is by the use of photoresists.
  * The wafer is coated with the photoresist and subjected to selective illumination through the photomask.
  * A photomask is constructed with chromium (chrome) covered quartz glass. A UV light source is used to expose the photoresist.
  * A developer solvent is then used to dissolve the soluble unexposed photoresist, leaving islands of insoluble exposed photoresist.
   </details>

  <Details>
  <summary>3. Well and Channel Formation</summary>
  
  * N-well process: In a n-well process, the pMOS transistors are built in a n-well and the nMOS transistor is placed in the p-type substrate.
  * P-well process: In a p-well process, the nMOS transistors are built in a p-well and the pMOS transistor is placed in the n-type substrate. p-well processes were used to optimize the pMOS transistor performance.
  * Twin-well process: Twin-well processes accompanied the emergence of n-well processes. A twinwell process allows the optimization of each transistor type.
  * Triple-well process: The triple-well process has emerged to provide good isolation between analog and digital blocks in mixed-signal chips; it is also used to isolate high-density dynamic memory from logic.
  
  ![image](https://user-images.githubusercontent.com/121994033/211602633-20172bec-59b8-4a15-a366-4ad4c3a8796e.png)

  </details>
 
  <Details>
  <summary>4. Silicon Dioxide (Sio2) Deposition</summary>
  
  * Oxidation of silicon is achieved by heating silicon wafers in an oxidizing atmosphere. The following are some common approaches:
  * Wet Oxidation: when the oxidizing atmosphere contains water vapor.  
   ??? The temperature is usually between 900 ??C and 1000 ??C.  
   ??? Wet oxidation is a rapid process.  
  * Dry Oxidation: when the oxidizing atmosphere is pure oxygen  
   ??? Temperatures are in the region of 1200 ??C to achieve an acceptable growth rate.  
   ??? Dry oxidation forms a better quality oxide than wet oxidation.  
   ??? It is used to form thin, highly controlled gate oxides, while wet oxidation may be used to form thick field oxides.
   * Atomic Layer Deposition (ALD): when a thin chemical layer (material A) is attached to a surface and then a chemical (material B) is introduced to produce a thin layer of the required layer (i.e., SiO2??????this can also be used for other various dielectrics and metals).
  </details>
 
  <Details>
  <summary>5. Isolation</summary>

  * Individual devices in a CMOS process need to be isolated from one another so that they do not have unexpected interactions.
  * The transistor gate consists of a thin gate oxide layer.
  * The thick oxide used to be formed by a process called Local Oxidation of Silicon (LOCOS).
  * A problem with LOCOS-based processes is the transition between thick andthin oxide, which extended some distance laterally to form a so-called bird???s beak.
  * Starting around the 0.35 ??m node, shallow trench isolation (STI) was introduced to avoid the problems with LOCOS.
  * STI forms insulating trenches of SiO2 surrounding the transistors (everywhere except the active area).
  </details>
 
  <Details>
  <summary>6. Gate Oxide Creation</summary>
  
 * The next step in the process is to form the gate oxide for the transistors. As mentioned, this is most commonly in the form of silicon dioxide (SiO2).The transistor gate consists of a thin gate oxide layer
  </details>
 
  <Details>
  <summary>7. Gate and Source/Drain Formations</summary>
  
  * Grow gate oxide wherever transistors are required (area = source + drain + gate)??????elsewhere there will be thick oxide or trench isolation.
  * Deposit polysilicon on chip
  * Pattern polysilicon (both gates and interconnect)
  * Etch exposed gate oxide???i.e., the area of gate oxide where transistors are required that was not covered by polysilicon; at this stage, the chip has windows down to the well or substrate wherever a source/drain diffusion is required
  * Implant pMOS and nMOS source/drain regions
  </details>

 <Details>
 <summary>8. Contacts and Metallization</summary>
 
 * Contact cuts are made to source, drain, and gate according to the contact mask. These are holes etched in the dielectric after the source/drain formation.
 * Older processes commonly use aluminum (Al) for wires, although newer ones offer copper (Cu) for lower resistance.
 * Tungsten (W) can be used as a plug to fill the contact holes (to alleviate problems of aluminum not conforming to small contacts)
 </details>
 
 <Details>
 <summary>9. Passivation</summary>
 
 * The final processing step is to add a protective glass layer called passivation or over glass that prevents the ingress of contaminants.
 * Openings in the passivation layer, called overglass cuts, allow connection to I/O pads and test probe points if needed.
  </details>
  
 <Details>
 <summary>10. Metrology</summary>
 
 * Metrology is the science of measuring. Everything that is built in a semiconductor process has to be measured to give feedback to the manufacturing process.
 </details>

 <Details>
 <summary>CMOS Fabrication Process Step</summary>
 
![image](https://user-images.githubusercontent.com/121994033/211606638-09442548-1d50-46a1-b6dc-a2dc37640412.png) 

![image](https://user-images.githubusercontent.com/121994033/211606685-6ce9beb5-fc60-4975-a36b-adfc8605e3c4.png)  
Oxidation

![image](https://user-images.githubusercontent.com/121994033/211606709-9b708948-5f18-4aec-b53e-f5b0a987c124.png)  
Photoresist

![image](https://user-images.githubusercontent.com/121994033/211606728-9685a6f3-dca2-4de5-9870-7bd12cecdb04.png)  
Masking

![image](https://user-images.githubusercontent.com/121994033/211606765-dcc83290-7a1e-4586-a2fd-a69fce1a0db6.png)  
Photoresist removal

![image](https://user-images.githubusercontent.com/121994033/211606789-158fe8dd-511b-4fd8-bff4-4bc60fe20be1.png)  
Etching

![image](https://user-images.githubusercontent.com/121994033/211606836-7e382d75-9eaf-4ccb-b09e-5ce1b6f118fe.png)  
Ion Implantation

![image](https://user-images.githubusercontent.com/121994033/211606857-dba95dca-d9bf-4ac7-ac33-9a2b2b7d2a20.png)  
N-well formation

![image](https://user-images.githubusercontent.com/121994033/211606885-772a0042-8e7c-42a3-ad1d-071cee70a168.png)  

![image](https://user-images.githubusercontent.com/121994033/211606913-8b00becf-d1bc-4170-bd52-f0ade7aabe45.png)
Deposition of polysilicon

![image](https://user-images.githubusercontent.com/121994033/211606937-0f215741-6c3d-4c33-921d-e38374ad797f.png)  
N and P diffusion

![image](https://user-images.githubusercontent.com/121994033/211606963-91355afd-0c84-4ea3-8d6f-a954133c517f.png)  
Metallization

![image](https://user-images.githubusercontent.com/121994033/211606982-57936abe-4897-4216-b96f-ffd1a1982042.png)

 </details>
</details>

 <Details>
 <summary>Assignment</summary>
 
 1. 
 ![image](https://user-images.githubusercontent.com/121994033/211699505-091d8fd1-a522-4796-919f-fae2979e742b.png)  
 
 2.  
 ![image](https://user-images.githubusercontent.com/121994033/211699558-c9130263-01b1-4fca-bf34-0a64e1cc90aa.png)

 3.
 ![image](https://user-images.githubusercontent.com/121994033/211699704-a978982e-103c-4722-b065-37a2e9571ebf.png)

 4.  
 ![image](https://user-images.githubusercontent.com/121994033/211699797-a76b0057-97a5-418d-a351-1a90c14b52bf.png)

 5.  
 ![image](https://user-images.githubusercontent.com/121994033/211699816-49bc44d3-4181-4cce-891c-b70e2a743fb5.png) 
 
 6. 
 ![image](https://user-images.githubusercontent.com/121994033/211700480-8dd103af-0c9c-4e77-838f-85688fc2224e.png)

 7. 
 ![image](https://user-images.githubusercontent.com/121994033/211720250-fd536be4-5dfa-4d2f-bf37-ffb2fd4b5e32.png)

 8. 
 ![image](https://user-images.githubusercontent.com/121994033/211720305-a83f93ce-e799-486d-97ca-9d8278397028.png)
</details>
 
## Day 3
### Topic - CMOS Fabrication Process in Deep Submicron and Ultra Deep Submicron Technology
<details>
 <summary>Theory</summary>
 
### Theory ###
 
 **Disadvatage of Submicron CMOS**  
 Isolation of the transsistor using reverse bias pn junction is limiting the transistor size and becomes impractical
 
 **Local Oxidation of Silicon (LOCOS) Isolation Process**  
   * Local Oxidation of Silicon is the traditional isolation technique used in submicron processes.
        1. A very thin layer silicon dioxide is grown on the wafer, called as pad oxide. Then a layer of silicon nitride is deposited which is used as an oxide barrier
        2. Then photolithography is done to pattern and etch the nitride and pad oxide where the thick oxide will be grown  
        3. Then by thermal oxidation process thick oxide is grown in the exposed area.  
        4. The last step is the removal of the silicon nitride layer.  
        ![image](https://user-images.githubusercontent.com/121994033/212123709-d188c4cd-5246-47e2-98ab-ef9bac0d60a5.png)   
    * The limitation of this technique is the bird???s beak effect and the surface area which is lost to this encroachment
    * The advantages of LOCOS fabrication process is simple process flow and high oxide quality because the whole LOCOS structure is thermally grown
        
 **Sallow Trench Isolation (STI) Technology**
 * Shallow trench isolation (STI) allows closer spacing of transistors by eliminating the depletion region at the surface and Bird???s beak effect due to LOCOS process.
 * Sallow Trench Isolation (STI) isolation process is the preferred isolation process for deep-submicron process because it completely avoids Bird???s beak shape characteristics.
        a. Cover the wafer with pad oxide and silicon nitride.
        b. First etch nitride and pad oxide. Next, an anisotropic etch is made in the silicon to a depth of 0.4 to 0.5 microns.
        c. Grow a thin thermal oxide layer on the trench walls
        d. A CVD dielectric film is used to fill the trench
        e. A chemical mechanical polishing (CMP) step is used to polish back the dielectric layer until the nitride is reached. The nitride acts like a CMP stop layer.
        f. Densify the dielectric material at 900??C and strip the nitride and pad oxide.
        ![image](https://user-images.githubusercontent.com/121994033/212125269-d0d9beb3-d8e9-4408-9cd4-bd2e915f50c6.png)

  * STI is more suitable for the increased density in a small area because it allows forming smaller isolation regions.
  * The disadvantage is larger number of process steps.
        
 **Deep Submicron (DSM) CMOS Technology other uses**
   In addition to the NMOS and PMOS transistor, the DSM technology provides;
   * A deep n-well that can be utilized to reduce substrate noise coupling.
   * A MOS Varactor that can be used to make voltage controlled oscillators (VCOs).
   * Different kind of resistors like:
    * Diffused and/or implanted resistors
    * Well resistors
    * Poly resistors
    * Metal Resistors  
        ![image](https://user-images.githubusercontent.com/121994033/212126223-de0b33a7-7c1c-4642-8554-01fe64f1a5c4.png)  
   * At least 6 levels of metal that can form many useful structures such as inductors, capacitors, and transmission lines.
        
   **Different Types of Capacitor in DSM CMOS Technology**  
        ![image](https://user-images.githubusercontent.com/121994033/212126490-6b055532-4a1e-49bd-b54f-7e421a1dc2fa.png)
        ![image](https://user-images.githubusercontent.com/121994033/212126623-e9b3f8fa-160e-4c1f-92bf-427f75e8e059.png)
        
   **Typical Deep Submicron (DSM) CMOS Fabrication Process**  
     Major Fabrication Steps for a DSM CMOS Process  
      1) p and n wells  
      2) Shallow trench isolation  
      3) Threshold shift and anti-punch through implants  
      4) Thin oxide and gate polysilicon  
      5) Lightly doped drains and sources  
      6) Sidewall spacer  
      7) Heavily doped drains and sources  
      8) Siliciding (Salicide and Polycide)  
      9) Bottom metal, tungsten plugs, and oxide  
      10) Higher level metals, tungsten plugs/vias, and oxide  
      11) Top level metal, vias and protective oxide   

**Summary of Deep Submicron (DSM) CMOS Fabrication Process**    
   * DSM technology typically has a minimum channel length between 0.35??m and 0.1??m  
   * DSM technology addresses the problem of excessive depletion region widths in junction isolation techniques by using shallow trench isolation  
   * DSM technology may have from 4 to 8 levels of metal  
   * Lightly doped drains and sources are a key aspect of DSM technology  
        
**Ultra Deep Submicron (UDSM) CMOS Technology**
 * Minimum length is less than 0.1 microns
 * Minimum feature size less than 100 nanometers
 * 22 nm drawn length
 * 5 nm lateral diffusion (12 nm gate length)
 * 1 nm transistor gate oxide
 * 8 layers of copper interconnect
 * Specialized processing is used to increase drive capability and maintain low off currents
        
**Advantage of UDSM CMOS Technology**
 * Digital Viewpoint:
   * Improved Ion/Ioff
   * Reduced gate capacitance
   * Higher drive current capability
   * Reduced interconnect density
   * Reduction of active power
        
 * Analog Viewpoint:
   * More levels of metal
   * Higher cutoff frequency
   * Higher capacitance density
   * Reduced junction capacitance per transconductance
   * More speed
        
**Disadvantage of UDSM CMOS Technology**
 * Analog Viewpoint:
   * Reduction in power supply resulting in reduced headroom
   * Gate leakage currents
   * Reduced small signal intrinsic gain
   * Increased nonlinearity
   * Increased noise and poorer matching
</details>

 <details>
 <summary>Assignment</summary>
  
## Assignment ##
 
 <Details>
 <summary>1. List the five basic MOS fabrication processing steps and give the purpose or function of each step.</summary>
  
**Oxidation**  
Oxidation is the process by which a layer of silicon dioxide (SiO2) is formed on the surface of the silicon wafer. The oxide grows both into as well as on the silicon surface. This oxide is used to provide insulating and passivation layers.  
**Diffusion**  
Diffusion in semiconductor material is the movement of impurity atoms at the surface of the material into the bulk of the material at temperatures in the range of 800???1400??C. The main aim of the Diffusion Process in IC Fabrication is to change the Conductivity of silicon substrate over a depth.  
**Ion implantation**  
Ion implantation is the process by which ions of a particular dopant (impurity) are accelerated by an electric field to a high velocity and physically lodge within the semiconductor material. Ion implantation doping method used in semiconductors that introduces impurities into a semiconductor wafer, enabling conductivity.  
**Deposition**   
Deposition is layering of additional material on the wafer surface. These layers may be applied at various stages during the manufacturing process in order to form a mask, to act as a new layer for further junction formation, or to form an insulating layer between two or more conductive layers.  
**Etching**  
Etching removes layers of SiO2, metals, and polysilicon, according to the desired patterns delineated by the resist. The two major methods of etching are wet chemical etching or dry chemical etching.  
</details>
 <details>
 <summary>2. What is the difference between positive and negative photoresist and how is photoresist used?</summary>
  
Positive photoresists undergo weakening when exposed to irradiation, whereas negative photoresists are strengthened. Positive photoresist is used to create a mask where patterns exist (where the photomask is opaque to UV light). Negative photoresist creates a mask where patterns do not exist (where the photomask is transparent to UV light).  
</details>
 
 <details>
 <summary>3. Sketch the approximate cross sectional view of a NMOS transistor in a p-substrate. Identify each region and identify the connections at the top surface of the integrated circuit for the source, drain, gate and bulk/substrate.</summary> 
  
 ![image](https://user-images.githubusercontent.com/121994033/212135520-fc9a087e-02ef-4531-8845-317a9ad498ff.png)
</details>
 
 <details>
 <summary>4. Consider a mask that is opaque everywhere except for a transparent circle in the center. Metal is deposited on a substrate followed by an application of negative photoresist which is patterned with the mask described. After exposure, developing, and subsequent etching, what will remain?</summary> 
  
The remain is a circle in the center
 </details>
 <details>
  <summary>5. What is the difference between submicron, deep submicron and ultra-deep submicron process?</summary>

Submicron technology typically has a channel length below 1000nm.   
DSM technology typically has a minimum channel length between 350nm to 130nm.  
UDSM technology typically has a channel length below 100nm.  
 </details>
   
 <details>
  <summary>6. What are the advantages of ultra-deep submicron process over deep submicron process.</summary>

* Improved Ion/Ioff
* Reduced gate capacitance
* Higher drive current capability
* Reduced junction capacitance per transconductance
* Higher cutoff frequency
* More speed
   </details>
   
 <details>
 <summary>7. What is the difference between LOCOS and STI process?</summary>

The STI process starts in the same way as the LOCOS process. A shallow trench is etched into the silicon substrate in STI. After underetching of the oxide pad, also a thermal oxide in the trench is grown, the so-called liner oxide. But unlike with LOCOS, the thermal oxidation process is stopped after the formation of a thin oxide layer, and the rest of the trench is filled with a deposited oxide
 </details>
 
 <details>
 <summary>8. Why for body connection a heavily doped n+ or p+ is used?</summary>
  
A heavily doped N+ or P+ diffusion is made for the metallic contact. This creates a conductive junction between the metal and the semiconductor, thus giving a good electrical contact to the bulk.
 </details>
 
 <details>
 <summary>9. What is use of silicide and poolside?</summary>

They function as interconnect between N+ or P+ diffusion to the metal later
 </details>
 
 <details>
 <summary>10. Which process steps used for control threshold voltage and punch-through effect?</summary>
  
Oxidation and Diffusion
 </details>
 
 <details>
 <summary>11. Draw a top view, front view and 3D view of a CMOS inverter and annotate the length and width of both PMOS and NMOS transistor.</summary>
  
 ![image](https://user-images.githubusercontent.com/121994033/212135567-a7b86633-5a3c-4c27-9406-7d7d03067813.png)
 </details>
 
 <details>
 <summary>12. Why sidewall spacer are used in DSM technology?</summary>

To insulate the drain and source metal contacts from the gate of the transistor.
  </details>
 
 <details>
 <summary>13. What are the advantages of Deep N-well technology over n-well technology?</summary>

The deep N well has the effect of decreasing the noise coupling through it to the substrate and giving the advantage of fully isolated NMOS devices while in n-well, capacitive coupling of noise from the well to the substrate means more noise reaches the supply.
 </details>
 
<details>
 <summary>14. What is passivation layer?</summary>

Passivation layers is a layer normally used protect the active semiconductor surface from the surrounding environment.
 </details>
 
 <details> 
 <summary>15. What is Bird???s beak in LOCOS process and what is the impact on the transistor performance?</summary>
 
A bird's beak effect is commonplace in LOCOS. As the oxide grows, the nitride mask, which is meant to block the oxide from growing everywhere, is slightly bent due to stress caused by the oxide pushing the nitride as it grows. The encroachment of field oxide in the active region reduces the area available to form a transistor and therefore it limits device scaling and device density in VLSI cuts which will limit the device performance.
 </details> 
</details>

## Day 4
### Topic - Metal-Oxide-Semiconductor Structure
<details>
 <summary>Theory</summary>
 
### Theory ###

 **Metal-Oxide-Semiconductor (MOS) Device Structure**  
 MOS structure - capacitance will change with voltage
 MOM structure - capacitance is constant
 ![image](https://user-images.githubusercontent.com/121994033/212618575-c310661a-8f0f-4429-b417-feffea0be902.png)
 ![image](https://user-images.githubusercontent.com/121994033/212618640-d0dd85a2-9bf4-42ba-b0af-9fb5ade12cc6.png)
Fabrication:  
* Oxidation: process to create SiO2 on top of Silicon.
* Metallization: process to deposit poly-silicon on top of SiO2
Device Structure:  
* Gate and substrate are different material so there is a contact potential between them. This expressed as metal to semiconductor work function (??ms)
* Interface: between SiO2 and Silicon

 **Ideal MOS Junction or Capacitor**  
 * No charge in the device if V= 0
 * Substrate is uniformly doped
 
   * Metal-to-semiconductor work function = 0
   * Interface trapped charge = 0
   * Oxide trapped charge = 0
   * Fixed charge at the interface = 0
   * Mobile charge in the oxide = 0
   
   **Case1: Accumulation Mode of Operation**
    * Accumulation Mode (V < 0):
      * Pile of majority carrier at the interface
      * Charge at the surface directly proportional to voltage  
        ![image](https://user-images.githubusercontent.com/121994033/212622907-40b5b8f5-f0a5-40f5-bc19-bc4671a7af5c.png)
       
    **Case2: Depletion Mode of Operation**
    * Depletion Mode (0 < V < VT):
      * The semiconductor surface starts to deplete and the type of charge at the surface is ???ve (due to acceptor ions) and gradually increase with the increase of voltage.  
      * The voltage at which the surface carrier concentration is exactly equal to bulk carrier concentration, is called weak inversion voltage and form this point the weak inversion started
      * Charge at the surface directly proportional to voltage
      * The voltage at which the surface concentration exactly equal to the bulk concentration, that is called threshold voltage
      * This is called inversion point and at this point depletion mode ends and strong inversion started.
      ![image](https://user-images.githubusercontent.com/121994033/212623238-88616000-a44b-42c9-b250-70356b721e67.png)  

    **Case3: Strong Inversion Mode of Operation**
    * Strong Inversion Mode (V ??? VT):
      * At threshold voltage a channel form at the surface of the semiconductor due to inversion charges.
      * Before threshold voltage the charge comes from negatively charged ionized acceptors.
      * After threshold voltage, the more charge comes from the electrons rather than depleting the holes.
      * The extra negative charge required for the semiconductor is comes from the mobile electrons which are very close to the surface.
      ![image](https://user-images.githubusercontent.com/121994033/212623758-eb930dc1-09f9-4dd9-9511-a7bbe87abe68.png)
     
    **Summary of the MOS Operation Modes**
     Depletion Mode (V > 0):
      * Flat band voltage is 0 for ideal MOS structure
      * Flat band means flatness of conduction and valence band edges at semiconductor surface
      ![image](https://user-images.githubusercontent.com/121994033/212627683-5a411c0e-e1cb-45e1-add9-37a34a88d7ca.png)

    **Q-V Characteristics of MOS Structure**
    ![image](https://user-images.githubusercontent.com/121994033/212628086-e5391f10-b4f4-413b-aa1e-5751c654ff3f.png)

    **C-V Characteristics of MOS Structure**
    ![image](https://user-images.githubusercontent.com/121994033/212628208-1e7f8445-a13c-42d1-825c-549a7d1c323f.png)   

    **Non Ideal MOS Structure**
    Effect of fixed charge Qf
    * To cerate a zero charge on silicon a negative voltage is required to give at gate terminal.
    * By applying a negative volute at gate the surface charge at silicon will be zero.
    * Zero charge in the semiconductor corresponds to flat-band condition of a MOS junction
    ![image](https://user-images.githubusercontent.com/121994033/212628647-f9944feb-b9e2-4693-8a9a-d7d43ca5052a.png)
    ![image](https://user-images.githubusercontent.com/121994033/212628614-9537f8c8-6320-4935-8fa7-76391e8a4fcb.png)
    
    Effect of work metal-semiconductor work function difference ??ms
    * Electrons are always moves from higher energy level to lower energy level.
    * Electrons are transferred through wire. 
    * To remove the electrons from semiconductor surface we have to provide a ???ve voltage to the gate.
    ![image](https://user-images.githubusercontent.com/121994033/212628929-535e5753-d822-40fe-a14d-ba16cf9c2f38.png)
    ![image](https://user-images.githubusercontent.com/121994033/212628905-7194733b-47a2-4119-8824-756b442d9adc.png)

 </details>
 
<details>
 <summary>Assignment</summary>
 
### Assignment ###


1. What are the main differences between ideal and real MOS structure? 

 - Effect of Oxide fixed charge QF and metal to semiconductor work function difference
   * There are some negative charges deposited at the surface  of the semiconductor. This negative charge at teh interface causes a band bending at the semiconductor interface without giving any voltage to the MOS structure
   * A negative voltage need to be applied at the gate terminal of the MOS structure to remove the negative charges from the surface of the semiconductor.
 
2. What are the different modes of operation in a MOS junction? 

* Accumulation
* Depletion
* Strong Inversion

3. What is the difference between weak inversion and strong inversion of a MOS junction?

	Weak inversion is when V < VT while strong inversion is when V ??? VT
 
4. What is metal-to-semiconductor work function? 

The fermi level energy difference between metal and semiconductor

5. For a heavily n-doped poly-silicon metal and a p-substrate semiconductor, what will be the metal-to-semiconductor work function? Positive or negative?  
	
    Positive
 
6. For a heavily p-doped poly-silicon metal and a n-substrate semiconductor, what will be the metal-to-semiconductor work function? Positive or negative?  

    Negative
 
7. What is threshold voltage of a MOS junction? Express threshold voltage for a non-ideal MOS junction. 

    Threshold voltage is the voltage at which the surface concentration exactly equal to the bulk concentration 
    ???????? = ???????????????????????????? + ???????????? = ?????????? + ?????? + ???????????/????0???? + ??????s
 
8. If the oxide (SiO2) increases for a MOS structure, the threshold voltage will increase or decrease?   

    Threshold voltage will increase

9. Instead of a lightly doped p-substrate, if you use a heavily doped p-substrate in a MOS structure then what will be the change in threshold voltage? Will it increase or decrease?   

    The threshold voltage will increase

10. Describe, why MOS capacitance stay minimum at very high frequency and back to high value at low frequency. 
* Once the capacitance is in inversion at high frequency, mobile carriers at the interface cannot be change easily because mobile carriers are the minority carriers.
* Minority carriers are thermally generated. The majority carriers are derived from the ionized impurity, but minority carriers are obtained by thermal generation.  Therefore, it will take time to generate required number of minority carriers
* Changing the voltage very fast will not provide sufficient time for the minority carriers to be generated. Therefore, rapid change in voltage inversion majority  carrier concentration can change very quickly.


</details>

	
## Day 5
### Topic - Metal-Oxide-Semiconductor FIELD EFFECT TRANSISTOR
<details>
 <summary>Theory</summary>
 
### Theory ###

**Metal-Oxide-Semiconductor Field Effect Transistor (MOSFET)**   
   ![image](https://user-images.githubusercontent.com/121994033/213080924-ff152e2c-eb59-4bee-8ca0-487f7e4b311d.png)
	
**MOSFET Operation (N-Channel Enhancement)**  
	![image](https://user-images.githubusercontent.com/121994033/213084648-e068e88d-feea-4dda-96e4-aea6268049fc.png)

  * **Cutoff**  
    * Application: Switch    
	 	![image](https://user-images.githubusercontent.com/121994033/213081601-95c68695-c7d5-4945-b08b-7d6852604de8.png)
	
  * **Linear**  
    * Application: Switch and linear resistor    
	 	![image](https://user-images.githubusercontent.com/121994033/213082158-b8ee403e-fea3-464f-84a8-48678e22cf68.png)   
  * **Saturation**  
    * Application: Amplifier and constant current source    
	 	![image](https://user-images.githubusercontent.com/121994033/213082422-6cd9d64a-4d92-4203-9c4f-b38d532d3145.png)  

**MOSFET Operation (P-Channel Enhancement)**   
	![image](https://user-images.githubusercontent.com/121994033/213084757-28b1c008-e153-431e-bd9e-a4ee2142e96e.png)  
	![image](https://user-images.githubusercontent.com/121994033/213084875-8e6cdf15-6bf8-419a-8eb2-fb11f8d29bdc.png)   
	
ID-VGS Characteristics  
![image](https://user-images.githubusercontent.com/121994033/213100946-89a9d7ce-8d93-4f9e-a516-be4706f3ac54.png)  
* Vgs increase, ideally there is no current
* due to some weak inversion, there is some current
* after reaching Vt, Id increase drastically and increase Vds
* Changing Vds also vary the characteristics because increasing Vds will increase Id
	
ID-VGS Characteristics with Body Bias  
![image](https://user-images.githubusercontent.com/121994033/213101049-1293d7b3-838d-42ca-b272-8b7a41ed29fa.png)  
* Body should always be less than source
* If body is positive and source negative, it will be a diode and current will flow from body to source
* If there is body bias, the threshold voltage increase
* VTO- 0 body bias
	
ID-VDS Characteristics  
![image](https://user-images.githubusercontent.com/121994033/213101097-0bab6fa3-b5da-4712-857e-7de49cf03aec.png)  
* Vds<Vgs-Vt linear region
* Vds=Vgs-Vt saturation, act as constant current source ideally

	
ID-VDS Characteristics: Channel Length Modulation  
![image](https://user-images.githubusercontent.com/121994033/213101181-4762ecd0-ee9e-499b-b794-7b09a8776cd5.png)  
* Higher VDS will increase depletion region.
* channel length decrease because depletion region increase.
* Current will increase when channel length decrease 
 
	
	
 </details>

## Day 6
### Topic - MOSFET Intrinsic Capacitances

<details>
 <summary>Theory</summary>
 
### Theory ###

**MOSFET Intrinsic Capacitances**
 
**Cutoff Region**  
![image](https://user-images.githubusercontent.com/121994033/214527391-b1893799-3470-4c9f-a911-309fbb701803.png)  
* Cgso: gate-source overlap capacitance.
* Cgdo: gate-drain overlap capacitance.
* Cdb: drain-bulk reverse bias junction capacitance.
* Csb: source-bulk reverse bias junction capacitance.
* Cgb: gate-bulk oxide capacitance
* No channel relate capacitance because of no channel.
* No channel formed in cutoff	In cutoff, no channel
* depletion region formed due to bias voltage Vds
* source depletion is smaller than drain, Csb constant because the voltage does not change
* Cgso - gate to source overlap, it is constant
* Cgb - oxide capacitance, C=A/d
 
**Linear Region**
![image](https://user-images.githubusercontent.com/121994033/214527773-2912ec7f-a49a-42b9-8724-471e692354ba.png)
* Cgso: gate-source overlap capacitance.
* Cgdo: gate-drain overlap capacitance.
* Cdb: drain-bulk reverse bias junction capacitance.
* Csb: source-bulk reverse bias junction capacitance.
* Cgsch: gate-channel oxide capacitance at source side.
* Cgdch: gate-channel oxide capacitance at source side.
* Cch-b: channel-bulk capacitance
* There are additional capacitance compared to cutoff due to channel form between source and drain

**Saturation Region**  
![image](https://user-images.githubusercontent.com/121994033/214528230-01ba84ef-39e0-47d0-8c92-448ff1cd63f4.png)  
* Cgso: gate-source overlap capacitance.
* Cgdo: gate-drain overlap capacitance.
* Cdb: drain-bulk reverse bias junction capacitance.
* Csb: source-bulk reverse bias junction capacitance.
* Cgsch: gate-channel oxide capacitance at source side.
* Cch-b: channel-bulk capacitance
* Cdb change because depletion region is bigger
* There is no Cgdch due to pinch off 

</details>

 <details>
 <summary>Assignment</summary>
 
### Assignment ###
	
  + **[Assignment-MOSFET with Capacitor](https://github.com/ImranAbdHakim/intel-ckt-training/blob/main/Assignment%20Day%206%20circuit%20training.pdf)**

<details>
 <summary>NMOS characteristic</summary>

Ids-Vgs characteristics
 * Vgs = sweep 0 to 1.2
 * Vds = 1.2  
 ![image](https://user-images.githubusercontent.com/121994033/218509268-1069c15b-24fd-406e-b401-3a4e55138728.png)
 
Vt from graph  
 * Vt=~0.46V  
 ![image](https://user-images.githubusercontent.com/121994033/218632645-4a29518c-eae8-4e84-9765-ed59ba9942b9.png)  

Ids-Vgs Char. at different Vds  
 ![image](https://user-images.githubusercontent.com/121994033/218511205-e8dd7e69-0e19-4408-b121-c51c562fdf72.png)
 
Ids-Vds characteristics  
 ![image](https://user-images.githubusercontent.com/121994033/218512186-4a235021-736e-4547-a8b2-a8807b5d4e43.png)

Ids-Vds char. at different Vgs  
![image](https://user-images.githubusercontent.com/121994033/218513599-01f4ad70-7779-46d9-8bef-01bd163a46c2.png)

Ids at different corner  
 ![image](https://user-images.githubusercontent.com/121994033/219098058-e5ef4225-e010-45de-9f15-7629236ec178.png)


</details>

<details>
 <summary>PMOS characteristic</summary>

Isd-Vsg characteristics  
 ![image](https://user-images.githubusercontent.com/121994033/218510135-5d65fc36-fb33-45e5-b5a5-e4de48149267.png)
 
Isd-Vsg Char. at different Vds  
 ![image](https://user-images.githubusercontent.com/121994033/218510643-d591e6f8-1ea7-4090-a315-56968a8f6181.png)

Isd-Vsd characteristics  
 ![image](https://user-images.githubusercontent.com/121994033/218510755-e75bd645-ccd6-4b82-9224-378ff7e1ae7c.png)
 
Isd-Vsd char. at different Vgs
 ![image](https://user-images.githubusercontent.com/121994033/218510885-65604dfb-54e8-43fb-a8d6-3bfe3791c5d6.png)

Isd at different corner
 ![image](https://user-images.githubusercontent.com/121994033/219089363-934a8518-2096-4b17-8b2e-8441e32d8052.png)

Vth at different corner  
 ![image](https://user-images.githubusercontent.com/121994033/219092937-673c2063-5313-4d88-ba66-c1d385ba1c26.png)

	

</details>
</details> 
	
## Day 7
### Topic - CMOS Inverter

<details>
 <summary>Theory</summary>
 
### Theory ###

**CMOS Inverter :**    
![image](https://user-images.githubusercontent.com/121994033/214999323-8f3f8a53-3e86-45dd-afd4-75a0c52d34ca.png)  
  * 1980 CMOS come to market 
  * The CMOS Inverter is the core of all digital designs
  * Analyze with respect to: 
	* Cost: Expressed by the complexity and area
	* Integrity and robustness: Expressed by the static (steady-state) behavior. Static current 
	* Performance: Determined by the dynamic (or transient) response.
	* Energy Efficiency: Set by the energy and power consumption. 

![image](https://user-images.githubusercontent.com/121994033/214999830-c491768a-f2b8-4f9c-8f37-9a6d186aa77e.png)

  * When input is HIGH, PMOS will turn off while NMOS will be on. The PMOS act likes open circuit switch while NMOS act likes a resistor
  * When input is LOW, PMOS will turn on while NMOS will turn off. The NMOS act likes open circuit switch while PMOS act likes a resistor

![image](https://user-images.githubusercontent.com/121994033/215003525-e9f2bc9a-5fc2-44e5-9e02-e5e421ad4a8b.png)  
	
Properties CMOS Inverter from Switched Level View:
  * Rail-to-rail swing: results high noise margin
  * Logic levels are independent of device sizes (ratioless)
  * In steady state there is always exist a path with a fine resistance between the output and either VDD or Ground. This results low output impedance and less sensitive to noise.
  * Input impedance of the CMOS inverter is extremely high. Theoretically, a single inverter can drive infinite number of gates
  * No direct path exit between supply and ground. Static power almost zero.
	
**Voltage transfer characteristics**
![image](https://user-images.githubusercontent.com/121994033/215004387-9cfd025a-098d-4edd-ad23-4c08849ca9f5.png)

![image](https://user-images.githubusercontent.com/121994033/215004511-bd351141-7a2b-4ad3-b815-c9cd701a3494.png)

**Noise Margin**  
![image](https://user-images.githubusercontent.com/121994033/215004541-ebecb626-1131-434a-ac77-08f8b8c799f1.png)
* How much noise the inverter can tolerate
* delta V - noise
if input 0 + noise - output is 1 : that noise is tolerable
* slope is steep, less transition region, more noise margin

**Dynamic Behavior**  
  * High performance CMOS circuit should have less propagation delay, less rise time and less fall time.
  * Propagation delay of the CMOS inverter is determined by the time it takes to charge and discharge the load capacitance CL through the PMOS and NMOS transistors   	  respectively.
  * If CL increases;
    * Propagation delay (PD) increases
    * Output rise time (Trise) increases
    * Output fall time (Tfall) increases
  * The above observation suggests that getting CL as small as possible is crucial to the realization to the high performance CMOS Circuits
  * Need to understand the major components of the load capacitance.  
![image](https://user-images.githubusercontent.com/121994033/215006101-6195294c-b735-4b74-be2c-185c3ea213b0.png)

  Intrinsic Capacitance
  * Cdbp, Cdbn : drain-bulk capacitance  
  * Cgdp, Cgdn: gate-drain overlap capacitance.  
  Wiring Capacitance  
  * Cw: Interconnect wiring capacitance  
  Fanout Capasitance  
  * Cgsp, Cgsn: source-bulk reverse bias junction capacitance.  

  * Cload = Cint + Cwiring + Cfanout
	
![image](https://user-images.githubusercontent.com/121994033/215006361-b217aef6-902a-448d-9d10-07fe0b2a3024.png)  
![image](https://user-images.githubusercontent.com/121994033/215006344-2d427c27-9a1e-435f-9aab-a9727628054d.png)

Rise Time :
  The time required for the output voltage to rise from 10% to 90% of the supply voltage.  
![image](https://user-images.githubusercontent.com/121994033/215007625-0204c3ce-bd23-4fab-b0b6-8a99db6bbf5e.png)

Fall Time :
  The time required the output voltage to fall from 90% to 10% of the supply voltage.  
![image](https://user-images.githubusercontent.com/121994033/215007705-fc28b988-1049-4ac8-bca4-1f95251e9b7c.png)

**Propagation Delay**
  * Input to output delay during the signal transition (at 50%)
  * Tplh: Propagation delay at low to high transition at output.
  * Tphl: Propagation delay at high to low transition at output.  
![image](https://user-images.githubusercontent.com/121994033/215007959-6556b541-485c-4d5e-9df5-957ba501dc2b.png)  
![image](https://user-images.githubusercontent.com/121994033/215007981-ce04ef36-1373-4319-8ccc-b7dce8276334.png)

Calculation: 
  * One way to compute propagation delay of the inverter is to integrate the capacitor charge (discharge) current.
  * ????_????=???1_????1^????2??????(????_???? (????))/(????(????)) ???????????
    Where ????=??????????????????????? (???????????????????????????????????)  ???????????????????????????? 
	????=???????????????????????????? ???????????????? ??????????? ????????????????????????????????????
	????1=???????????????????????????? ????????????????????????????
	????2=???????????????????? ????????????????????????????
  * Exact computation of above equation is difficult, as both ????_???? (????) and ????(????) are non-linear functions of V.
  * Deriving the propagation delay of the resulting circuit is now straight forward and is nothing more than the analysis of a first-order linear RC network
![image](https://user-images.githubusercontent.com/121994033/215008111-25937fca-6012-422f-887b-71dfbadc1d5c.png)

Propagation Delay (Tp) of a gate can be minimized in following ways 
1. Reduce C_L
  * Internal diffusion capacitance
  * Interconnect capacitance
  * Fanout capacitance
2. Increase the  W/L   ratio of transistors
  * This is most powerful and effective performance optimization tool in the hands of the designer.
  * Be careful,  W/L  ratio proportional to C_L: once intrinsic capacitance starts dominating  C_L increasing gate size does not longer help in reducing the delay.
    * Increase area (self loading)
    * Increase the fanout factor of the driving gate
3. Increase VDD
  * Delay of a gate can be modulated by modifying the supply voltage

![image](https://user-images.githubusercontent.com/121994033/215008303-662229a3-cb78-4639-a72b-dcad00263808.png)

![image](https://user-images.githubusercontent.com/121994033/215009572-e7714d2d-a08e-411f-8cea-d1b4fa678b86.png)  
![image](https://user-images.githubusercontent.com/121994033/215009583-3b73b774-8f5e-4df9-9ea8-9d8026d83b57.png)  
![image](https://user-images.githubusercontent.com/121994033/215009592-34ae9066-1d6c-4692-8643-3e6c6153ac78.png)  
![image](https://user-images.githubusercontent.com/121994033/215009631-468b5f0f-2c98-4af0-a0e4-d34140a37fee.png)  
 
![image](https://user-images.githubusercontent.com/121994033/215009649-222b4302-fcdb-4081-be8a-8fb7507edf40.png)

**Static Power Consumption**

  * The static or steady state power dissipation of a circuit is expressed as;
  * ????_(????????????????.)=????_(????????????????.) ????_????????
  * Ideally, ????_(????????????????.)=0 as the PMOS and NMOS devices are never on simultaneously in steady state operation.
  * But a leakage current flowing through the reverse biased diode junctions of the transistor, located between source and drain and the substrate.
  * In general the leakage currents are very small and can be ignored. However the junction currents are caused by thermally generated carriers.
  * Sub-threshold Current: Drain-to-source current even when Vgs is smaller than the threshold voltage,  
![image](https://user-images.githubusercontent.com/121994033/215009803-494e07cb-5fec-496c-a8b9-5e0577fc9bcf.png)  
	
**Power Dissipation Summary**

The total power of the CMOS inverter is expressed as the sum of the its three components:
????_????????????????????=????_????????????+????_????????+????_(????????????????.)
????_????????????= Dominant
????_????????= Can be kept within bounds under the designers control
????_(????????????????.)= Ignorable but significant in sub-micron and deep sub-micron technologies.  
![image](https://user-images.githubusercontent.com/121994033/215009932-8f9784f9-dc1d-41f4-ab86-447beb596e4e.png)  

</details> 

 <details>
 <summary>Assignment</summary>
 
### Assignment ###
	
  + **[Assignment-CMOS Characterization](https://github.com/ImranAbdHakim/intel-ckt-training/blob/main/assignment%20day%207.pdf)**
 </details>

## Day 8
### Topic - MOSFET Parameter Extraction, Scaling, Short Channel Effects and PVT Variations

<details>
 <summary>Theory</summary>
 
### Theory ###
MOSFET Parameter Extraction 

![image](https://user-images.githubusercontent.com/121994033/217016056-f55036f0-1ffa-492d-82a7-c0baa1bda833.png)  
![image](https://user-images.githubusercontent.com/121994033/217016146-9fcd489a-663b-4f32-8805-5871a563f675.png)  
![image](https://user-images.githubusercontent.com/121994033/217016212-5007a2e0-063c-4ae5-bed1-06c9bd306c04.png)  
![image](https://user-images.githubusercontent.com/121994033/217016281-d506315b-e459-4075-b02e-33a6e8663abf.png)

MOSFET Scaling 

![image](https://user-images.githubusercontent.com/121994033/217017100-ac81c781-b572-42fd-8905-0339be7c382f.png)  
??? Dennard scaling, also known as MOSFET scaling, is a law in semiconductor electronics that states that as transistors become smaller, their power density remains constant while both voltage and current decrease proportionally with length.
??? The process of reducing the size of MOSFET is referred to as scaling.
??? There are two methods for reducing size: full scaling and constant voltage scaling.

![image](https://user-images.githubusercontent.com/121994033/217017538-afb1c353-2468-4efa-b7ae-79ee226e54be.png)
![image](https://user-images.githubusercontent.com/121994033/217017598-f9686c94-107b-4f74-aff3-df333a829965.png)

* In many practical cases, constant-voltage scaling is favored over constant-field scaling due to external constraints on voltage levels.
* However, it should be noted that constant-voltage scaling leads to an increase in drain current density and power density by a factor of S^3.
* This significant rise in current and power density can ultimately lead to significant reliability issues for the scaled transistor, including electromigration, hot-carrier degradation, oxide breakdown, and electrical over-stress.

transistor get smaller, power density stays constant, voltage and current scale downward with length

short channel effect 

??? A MOSFET is considered short when the channel length is similar in magnitude to the depletion-layer widths (????????????, ????????????) of the source and drain junction.
??? Alternatively, a MOSFET can be defined as a short-channel device if the effective channel length (????????????????) is approximately equal to the source and drain junction depth ????j.

??? The short channel effects in a MOSFET device are caused by two physical factors:
	1. The restrictions on electron drift in the channel,
	2. The alteration of the threshold voltage as a result of the shortening of the channel length.
	
??? Seven types of short channel effect
	* drain induced barrier lowering and punch through
	* Mobility degradation or surface scattering
	* velocity saturation
	* impact ionization
	* hot electrons
	* sub-threshold conduction
	* Vt roll-off
	
* In small MOSFETs, the potential barrier is influenced by both VGS (gate-to-source voltage) and VDS (drain-to-source voltage).
* If the drain voltage increases, the potential barrier in the channel decreases, resulting in drain-induced barrier lowering (DIBL).
* The reduction of the potential barrier eventually enables electron flow between the source and drain, even when the gate-to-source voltage is below the threshold voltage.
* The current that flows in the channel under these conditions (VGS<VT0) is known as the subthreshold current.

* As the channel length decreases due to the expansion of the depletion layer into the channel region, the longitudinal electric field component (????????) increases and the surface mobility (??) becomes dependent on the field.
* In a MOSFET, the carrier transport occurs within the narrow inversion layer, and surface scattering (collisions experienced by electrons as they are accelerated towards the interface by ????????) reduces mobility.
* The electrons have difficulty moving parallel to the interface, resulting in an average surface mobility that is about half that of the bulk mobility, even for small values of ????????.

* At low ????????, the electron drift velocity (????????????) in the channel increases linearly with the electric field intensity. But as ???????? rises above 104 V/cm, the drift velocity increases more gradually and approaches a saturation value of ???????????????????????? = 107 cm/s at ???????? = 105 V/cm and 300 K.
* Short-channel devices are also impacted by velocity saturation, which decreases the transconductance in saturation mode.
* It is important to note that in short-channel devices, the drain current is limited by velocity saturation, not pinch off. This occurs when the dimensions are scaled without lowering the bias voltages.

* Impact ionization is a process where an electron-hole pair is generated due to high longitudinal electric field.
* The holes are then swept into the bulk.
* The potential drop created by the hole current results in a bulk-to-source forward bias.
* This leads to additional electron injection and increased carrier flow into the drain.

* High electric fields can also cause issues known as "hot electrons."
* The high energy of these hot electrons can accumulate over time and degrade the performance of the device.
* This can lead to an increase in the threshold voltage and have a negative impact on the device.

* Sub-threshold conduction refers to the behavior of the device when the gate voltage is below the threshold voltage (Vgs < Vt).
* In this weak inversion regime, the current decreases exponentially with a straight line appearance on a logarithmic scale.
* The sub-threshold leakage current increases with increasing drain-to-source voltage (Vds) due to drain-induced barrier lowering.
* The drain junction leakage sets a lower limit on the drain-source current (Ids), and this is further exacerbated by the negative gate voltage.

![image](https://user-images.githubusercontent.com/121994033/217020602-4b2f6aa8-e96e-4821-8aac-9f961dd6a4de.png)  
![image](https://user-images.githubusercontent.com/121994033/217020472-22a011c3-fd39-4ffa-8b4c-286aff2e8657.png)  
![image](https://user-images.githubusercontent.com/121994033/217020527-afc1977d-9504-4777-ba55-23b6c2473204.png)

</details> 

## Day 9
### Topic - Combinational Digital Logic Circuits

<details>
 <summary>Theory</summary>
 
 **Combinational Logic**
 
 * The output of the circuit is related to its current input signals by some Boolean expression
 * The gates coming under combinational logics are:  
    basic gates: NOT, AND, OR   
    universal gates : NAND, NOR  
    special gates : X-OR, XNOR  
    complex gates : AOI, OAI, adders, subtractors, multiplexers, decoders and transmission gate.  
 * There are numerous circuit styles to implement a given logic function. As with the inverter, the common design matrics by which a gate is evaluated are speed, power and area
 * Most used style is static CMOS where it is an extension of CMOS inverter.
 
 **Complementary MOS Logic**
 * A static CMOS is a combination of the pull-up network (PUN) and pull-down network (PDN).
 * The function of the PUN is to provide the connection between the output and VDD anytime the output of the logic gate is meant to be High.
 * The function of the PDN is to provide the connection between the output and GND anytime the output of the logic gate is meant to be Low.
 * At one time, only one connection is conducting
 * A transistor can be thought of as a switch controlled by its gate terminal.
 * An NMOS transistor is ON when the controlling signal is high and is OFF when the controlling signal is low while the PMOS is vice versa.
 * PUN is constructed using PMOS devices, while PDN is constructed using NMOS devices because NMOS is strong '0' passer while PMOS is strong '1' passer.
 
 ![image](https://user-images.githubusercontent.com/121994033/217707670-e06ec479-b162-40e3-bc05-b36c50995416.png)

 * Pull-up and pull-down networks of a complementary CMOS structure are dual networks.
 * The number of transistors required to implement an N-Input logic gate is 2N.
![image](https://user-images.githubusercontent.com/121994033/217708681-e4d497ea-b26b-438b-943d-24424aebea67.png)

**Static Properties of Complementary CMOS Gates**

Complementary CMOS gates inherits all the nice properties of the basic CMOS inverters  
??? Rail-to-rail swing, ???????????? = ???????????? and ???????????? = 0  
??? No static power dissipation  
??? VTC and noise margin analysis is little bit complicated as these parameters depends upon the data inputs applied to gate.   
![image](https://user-images.githubusercontent.com/121994033/217709563-4682000a-c9fc-457d-ad04-46ab424f0156.png)  
![image](https://user-images.githubusercontent.com/121994033/217709585-4b00e21c-4a33-43b8-874e-9419312fba7d.png)  

**Propagation Delay of Complementary CMOS Gates**
* The computation of propagation delay proceeds in a fashion similar to static inverters.
* For delay analysis, each transistor is modeled as a resistor in series with an ideal switch.

![image](https://user-images.githubusercontent.com/121994033/217711418-88ddb9ac-c8da-41cf-b00c-0cbd7108bf6f.png)

![image](https://user-images.githubusercontent.com/121994033/217711532-d22216a4-d824-451d-867b-b83ab2eb684f.png)
![image](https://user-images.githubusercontent.com/121994033/217711570-fb5ab93e-d1ff-485e-b016-a2ad47b9b703.png)

* For NAND gate, to make ??????????????????????????????????? = ??????????????????????????????? , we have to reduce the resistance of PDN devices of NAND gate to half of the previous.
* This can be possible if the size of the PDN devices will be two times of the previous.
* This is the same with NOR gate except that the PUN will be two times of the previous.
* Therefore, to get the same delay as the inverter NOR implementation required more area compared to NAND implementation. So, NAND implementation is preferred over NOR implementation.


**Complex Logic Circuit**

* AND-OR-INVERT (AOI) logic : enables the sum of products realization of a Boolean function in one logic stage.
* OR-AND-INVERT (OAI) logic : ??? The OAI gates on the other hand, enables the product-of-sums realization of a Boolean function in one logic stage.
* The pull-down network of AOI gate consists of parallel branches of series connected NMOS driver transistors.

**Transmission Gate**

* One NMOS and one PMOS transistor connected in parallel.
* Gate voltages applied to these two transistors are also set to be complementary signals.
* Bi-directional switch between the nodes A and B, that is controlled by signal C.
* CMOS TG is also used to make combinational circuit to reduce transistor counts
* CMOS TG is used in latch and Flip-flops.

![image](https://user-images.githubusercontent.com/121994033/217724843-eaa96fb8-ad11-4d8f-8578-51139665271d.png)

</details> 

## Day 10
### Topic - Sequential Digital Logic Circuits

<details>
 <summary>Theory</summary>
 
 * Sequential logic circuits retain past input values in addition to current input values, influencing their output. They possess memory and are categorized by    regenerative circuits, which can be classified as bistable, monostable, and astable circuits. Bistable circuits are the most commonly utilized and are responsible for creating latches, flip-flops, registers, and memory elements.
 ![image](https://user-images.githubusercontent.com/121994033/221726217-8e0b7d68-6d67-4ac2-815a-136b9d8e3ad9.png)
 
 ![image](https://user-images.githubusercontent.com/121994033/221726332-292c0595-78b2-4414-94ef-c0a70d86fa6a.png)
 
 ![image](https://user-images.githubusercontent.com/121994033/221726454-a4387640-5218-464c-ae31-226bb60ba256.png)
 
 ![image](https://user-images.githubusercontent.com/121994033/221726568-e126cd78-1058-4abf-a674-aaa8a3f9cd48.png)
 
 ![image](https://user-images.githubusercontent.com/121994033/221726625-44bfa561-2f7c-43ba-9ac4-c4da3998baa0.png)
 
 ![image](https://user-images.githubusercontent.com/121994033/221726679-558e6992-34a1-4c33-86f7-78e98ae90cc2.png)

 ![image](https://user-images.githubusercontent.com/121994033/221726736-8e9995d6-0cfe-41f8-82e5-dd0c2330fa75.png) 

 ![image](https://user-images.githubusercontent.com/121994033/221726801-500bd244-4d24-419a-86ef-8e860122beff.png)
 
 ![image](https://user-images.githubusercontent.com/121994033/221726897-6cd16f67-a79d-4674-8a58-47ca73a4aaa4.png)
 
 ![image](https://user-images.githubusercontent.com/121994033/221726952-8249714a-6cea-48bb-9be6-44bf2761e433.png)
 This is the robust transparent latch that addresses all of the deficiencies mentioned so far.
??? The latch is static
??? All nodes swing rail-to-rail
??? Sate noise isolated from output noise
??? Input drives transistor gate rather than diffusion.

![image](https://user-images.githubusercontent.com/121994033/221727070-d6b93e2c-6dd5-42c7-b793-cbfde8c43a82.png)

![image](https://user-images.githubusercontent.com/121994033/221727156-6ed5a0d6-d589-4f40-bf8b-7c36d23346e5.png)

![image](https://user-images.githubusercontent.com/121994033/221727212-0a6e2adc-6751-4be0-8049-a38da30d1084.png)

??? Setup Time: It is defined as the minimum amount of time before the
clock???s active edge that the data must be
stable for it to be latched correctly.
??? Any violation may cause incorrect data
to be captured, which is known as setup
violation.
??? Hold Time: It is defined as the
minimum amount of time after the
clock???s active edge during which data
must be stable.
??? Violation in this case may cause
incorrect data to be latched, which is
called as hold violation.  
![image](https://user-images.githubusercontent.com/121994033/221727601-53e06291-af65-47da-9c48-b9155037ceae.png)  
??? When CK=High, input D is traverse through 1-2-3-4 and reflected at node 5 after some time.
??? The time that it takes D to reach node 5 is called the setup time.
??? When CK=Low, TG1 is switched OFF and TG2 is switched ON. Therefore, the LHS latching circuit
kicks into action latching the value present at node D and producing it in the output (Q=D)
??? Any data sent before the setup time, will produce a stable value at node 5. This defines the reason for the
setup time within a flop.

![image](https://user-images.githubusercontent.com/121994033/221727729-fb0e684c-9a12-4614-a4e8-be6a2e96ebb5.png)

</details> 







 
