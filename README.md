# Advanced-Physical-Design-using-OpenLane-SKY130


This is a 5 day workshop done on Advanced Physical design which is a crucial part of VLSI design flow using open source tools. In a nutshell, we take a netlist & produced GDSII file for picorv32a, a RISC-V based CPU core using OpenLANE with SKY130nm PDK.

![214589941-6ce8de10-2e46-478b-8223-7591b4d2285c](https://user-images.githubusercontent.com/83575446/215591609-7271d498-57a8-4c6f-9b6f-cf7b7ea07f07.png)


# Table of Contents  
 - [DAY 1: Inception of Open-source EDA, OpenLane and Sky130 PDK](https://github.com/Haritha266/Advanced-Physical-Design-using-OpenLane-SKY130#day-1---inception-of-open-source-eda-openlane-and-sky130-pdk)
   - [ASIC design Flow](https://github.com/Haritha266/Advanced-Physical-Design-using-OpenLane-SKY130#asic-design-flow)
   - [What is Openlane?](https://github.com/Haritha266/Advanced-Physical-Design-using-OpenLane-SKY130#what-is-openlane)
   - [OpenLane Directory Hierarchy](https://github.com/Haritha266/Advanced-Physical-Design-using-OpenLane-SKY130#openlane-directory-hierarchy)
   - [Lab [Day 1] - Determine Flip-flop Ratio](https://github.com/Haritha266/Advanced-Physical-Design-using-OpenLane-SKY130#lab-day-1---determine-flip-flop-ratio)
   
 - [DAY 2: Good Floorplan vs Bad Floorplan and Introduction to Library Cells](https://github.com/Haritha266/Advanced-Physical-Design-using-OpenLane-SKY130#day-2-good-floorplan-vs-bad-floorplan-and-introduction-to-library-cells)
   - [Floorplan Stage](https://github.com/Haritha266/Advanced-Physical-Design-using-OpenLane-SKY130#floorplan-stage)
   - [Placement Stage](https://github.com/Haritha266/Advanced-Physical-Design-using-OpenLane-SKY130#placement-stage)
   - [Lab [Day 2] - Determine Die Area](https://github.com/Haritha266/Advanced-Physical-Design-using-OpenLane-SKY130#lab-day-2---determine-die-area)
    - [Library Characterization](https://github.com/Haritha266/Advanced-Physical-Design-using-OpenLane-SKY130#library-characterization)
    - [Timing Characterization](https://github.com/Haritha266/Advanced-Physical-Design-using-OpenLane-SKY130#timing-characterization)
     
 - [DAY 3: Design a Library Cell using Magic Layout and Ngspice Characterization](https://github.com/Haritha266/Advanced-Physical-Design-using-OpenLane-SKY130#day-3-design-a-library-cell-using-magic-layout-and-ngspice-characterization)
   - [Designing a Library Cell](https://github.com/Haritha266/Advanced-Physical-Design-using-OpenLane-SKY130#designing-a-library-cell)
     - [SPICE Deck Netlist Description](https://github.com/Haritha266/Advanced-Physical-Design-using-OpenLane-SKY130#spice-deck-netlist-description)
     - [SPICE Analysis for Switching Threshold and Propagation Delay](https://github.com/Haritha266/Advanced-Physical-Design-using-OpenLane-SKY130#spice-analysis-for-switching-threshold-and-propagation-delay)
   - [CMOS Fabrication Process (16-Mask CMOS Process)](https://github.com/Haritha266/Advanced-Physical-Design-using-OpenLane-SKY130#cmos-fabrication-process-16-mask-cmos-process)
   - [Lab [DAY 3] - Introduction to Sky130 basic layers layout and LEF using inverter](https://github.com/Haritha266/Advanced-Physical-Design-using-OpenLane-SKY130#lab-day-3---introduction-to-sky130-basic-layers-layout-and-lef-using-inverter)
   
 - [DAY 4: Pre-layout Timing Analysis and Importance of Good Clock Tree](https://github.com/Haritha266/Advanced-Physical-Design-using-OpenLane-SKY130#day-4-pre-layout-timing-analysis-and-importance-of-good-clock-tree)
   - [Lab [Day 4] - Extracting the LEF File](https://github.com/Haritha266/Advanced-Physical-Design-using-OpenLane-SKY130#lab-day-4---extracting-the-lef-file)
   - [Plug-in the Customized Inverter Cell to OpenLane](https://github.com/Haritha266/Advanced-Physical-Design-using-OpenLane-SKY130#plug-in-the-customized-inverter-cell-to-openlane)
   - [Delay Table](https://github.com/Haritha266/Advanced-Physical-Design-using-OpenLane-SKY130#delay-table)
   - [Fix Negative Slack](https://github.com/Haritha266/Advanced-Physical-Design-using-OpenLane-SKY130#fix-negative-slack)
   - [Locating the Custom Inverter Cell in Layout](https://github.com/Haritha266/Advanced-Physical-Design-using-OpenLane-SKY130#locating-the-custom-inverter-cell-in-layout)
   - [Setup Timing Analysis](https://github.com/Haritha266/Advanced-Physical-Design-using-OpenLane-SKY130#setup-timing-analysis-)
   - [Clock Tree Synthesis Stage](https://github.com/Haritha266/Advanced-Physical-Design-using-OpenLane-SKY130#clock-tree-synthesis-stage)
   - [Timing Analysis with Real Clocks](https://github.com/Haritha266/Advanced-Physical-Design-using-OpenLane-SKY130#timing-analysis-with-real-clocks)
   - [Multi-corner STA for Post-CTS](https://github.com/Haritha266/Advanced-Physical-Design-using-OpenLane-SKY130#multi-corner-sta-for-post-cts)
    
 - [DAY 5: Final Steps for RTL2GDS using TritonRoute and OpenSTA](https://github.com/Haritha266/Advanced-Physical-Design-using-OpenLane-SKY130#day-5-final-steps-for-rtl2gds-using-tritonroute-and-opensta)
   - [Maze Routing - Lee's Algorithm](https://github.com/Haritha266/Advanced-Physical-Design-using-OpenLane-SKY130#maze-routing---lees-algorithm)
   - [DRC Cleaning](https://github.com/Haritha266/Advanced-Physical-Design-using-OpenLane-SKY130#drc-cleaning)
   - [Routing Stage and TritonRoute](https://github.com/Haritha266/Advanced-Physical-Design-using-OpenLane-SKY130#routing-stage-and-tritonroute)
   - [Lab [Day 5] - Power Distribution Network (PDN) and routing](https://github.com/Haritha266/Advanced-Physical-Design-using-OpenLane-SKY130#lab-day-5---power-distribution-network-pdn-and-routing)
   - [SPEF Extraction and GDSII Streaming](https://github.com/Haritha266/Advanced-Physical-Design-using-OpenLane-SKY130#spef-extraction-and-gdsii-streaming)
   

### Day 1 - Inception of open-source EDA, OpenLANE and Sky130 PDK

A chip generally consists of PADS (where signals go in & out through pads), core (where logic gates sits) and Die (size of chip)

The core of the chip will contain two types of blocks as follows:
 - **Foundry IP Blocks** (e.g. ADC, DAC, PLL, and SRAM) = blocks which requires some amount of intelligent techniques to build which can only be designed by foundries.
 - **Macro blocks** (e.g. RISC-V SOC and SPI) = pure digital logic blocks compared to IP's which might require some analog parts. 

 Open Source Digital ASIC Design requires three open-source components:  
- **RTL Designs** = github.com, librecores.org, opencores.org
- **EDA Tools** = OpenROAD, OpenLANE,QFlow  
- **PDK** = Google + Skywater 130nm Production PDK

![Screenshot (277)](https://user-images.githubusercontent.com/83575446/215494429-0618b809-56e7-4206-bb10-d468faebf570.png)


**PDK (Process Design Kit)** = A set of data files and documents which serves as the interface between the designer and the fab. This includes cell libraries, IO libraries, design rules (DRC, LVS, etc.)

### ASIC design Flow:
- **Sythesis** : RTL is converted into a gate level netlist made up of components of standard cell libary (SCL). 
- **Floor Planning/ Power Planning** : Objective is to plan silicon area and create robust power distribution network. The power network usually uses the upper metal layer which are thicker than lower layer and thus lower resistance. This lowers the IR drop problem
 - **Placement** : There are two steps, first is global placement which is the general optimal positons for cells  and might not be legal. Next is detailed placement which is the actual legal placements of the cells from global placement.
 - **Clock tree synthesis** : it delivers clock to all clock cells with minimum skew & latency and is usually a tree (H-tree, X-tree ... )
 - **Routing** : Use horizontal and vertical wires to connect cells together. The router uses PDK information (thickness, pitch, width,vias) for each metal layer to do the routing. The Sky130 defines 6 routing layers. It do global routing (use coarse grain grids) and detailed routing (use fine grain grids).
 - **Verification before sign-off** : Involves physical verification like DRC and LVS and timing verification. Design Rule Checking or DRC ensures final layout honors all design rules and Layout versus Schematic or LVS ensures final layout matches the gate level netlist from synthesis phase. Timing verification ensures timing constraints are met.
![Screenshot (279)](https://user-images.githubusercontent.com/83575446/215494588-e33e8ebd-0c3c-4187-b807-b04f41de1946.png)

## What is Openlane?

 [OpenLane](https://github.com/The-OpenROAD-Project/OpenLane) = An open-source ASIC development flow reference. It consists of multiple open-source tools needed for the whole RTL to GDSII flow. This is tuned epecially for Sky130 PDK. It also works for OSU 130nm. It is recommended to read the [OpenLANE documentation](https://openlane.readthedocs.io/en/latest/)  before moving forward.
 
 ![image](https://user-images.githubusercontent.com/87559347/182759711-6b9352ec-7652-4589-af31-53a409eb2830.png)

- The input for the whole flow are the rtl files, sdc file, and PDK files. The output is GDSII/LEF file.

- Yosys is used to convert the HDL to gate level netlist using generic components. The [ABC script](http://people.eecs.berkeley.edu/~alanmi/abc/) is then used to map the generic components to the standard cell library of the PDK. These ABC scripts is used to make various synthesis strategies (using the Synthesis Exploration) which can optimize the design either with least area or best timing.  

- The Logic Equivalency Cheking (LEC) is used to compare the resulting netlist after optimization of place and route to the gate level netlist from synthesis phase

- Antenna Rules Violation = long wire segments will act as antennna and will accumulate charges, this might damage the connected transistor gates. Solution is to either use bridging or antenna diode insertion to leak away the charges  

### OpenLane Directory Hierarchy:

``` 
├── OOpenLane             -> directory where the tool can be invoked (run docker first)
│   ├── designs          -> All designs must be extracted from this folder
│   │   │   ├── picorv32a -> Design used as case study for this workshop
│   |   |   ├── ...
|   |   ├── ...
├── pdks                 -> contains pdk related files 
│   ├── skywater-pdk     -> all Skywater 130nm PDKs
│   ├── open-pdks        -> contains scripts that makes the commerical PDK (which is normally just compatible to commercial tools) to also be compatible with the open-source EDA tool
│   ├── sky130A          -> pdk variant made especially compatible for open-source tools
│   │   │  ├── libs.ref  -> files specific to node process (timing lib, cell lef, tech lef) for example is `sky130_fd_sc_hd` (Sky130nm Foundry Standard Cell High Density)  
│   │   │  ├── libs.tech -> files specific for the tool (klayout,netgen,magic...) 
```

Inside a specific design folder contains a `config.tcl` which overrides the default settings on OpenLANE. These configurations are specific to a design (e.g. clock period, clock port, verilog files...). The priority order for the OpenLANE settings:
1. sky130_xxxxx_config.tcl in `OpenLane/designs/[design]/`
2. config.tcl in `OpenLane/designs/[design]/`
3. Default values in `OpenLane/configuration/`

### Lab [Day 1] - Determine Flip-flop Ratio:
The task is to find the flip-flop ratio ratio for the design `picorv32a`. This is the ratio of the number of flip flops to the total number of cells. For the OpenLane installation, the steps are very straight forward and can be found on the [OpenLane repo](https://github.com/The-OpenROAD-Project/OpenLane).

**1. Run OpenLANE:**
 - `cd work/tools/openlane_working_dif/openlane` = set this directory
 - `docker` = Open the docker platform inside the `openlane/`
 - `% flow.tcl -interactive` = run script for automating the whole RTL to GDSII flow but in step by step `-interactive` mode
 - `% package require openlane 0.9` = retrives all dependencies for running v0.9 of OpenLANE  
 
<img width="458" alt="o" src="https://user-images.githubusercontent.com/83575446/215518032-3000c1da-d551-4fdd-aa31-a780750e3a03.png">
 
**2. Design Setup Stage:**
 - `% prep -design picorv32a` = Setup the filesystem where the OpenLANE tools can dump the outputs. This also creates a `run/` folder inside the specific design directory which contains the command log files, results, and the reports dump by each tools. These folders will be empty for now except for lef files generated by this design setup stage. This merged the [cell LEF files](https://teamvlsi.com/2020/05/lef-lef-file-in-asic-design.html) `.lef` and [technology LEF files](https://teamvlsi.com/2020/05/lef-lef-file-in-asic-design.html) `.tlef` generating `merged.nom.lef` inside `run/tmp/`
 
<img width="959" alt="1" src="https://user-images.githubusercontent.com/83575446/215518224-44e7fca5-08c9-4f3f-ace0-dec2caefb226.png">

**3. Run synthesis:**
 - `% run_synthesis` = Run yosys RTL synthesis, ABC scripts (for technology mapping), and OpenSTA.  
 
 <img width="728" alt="0 calci" src="https://user-images.githubusercontent.com/83575446/215518318-dec3390f-e0de-4c29-9ebf-19cf3acb4b66.png">

 
**The flipflop ratio is (number of flip flops)/(total number of cells) is 1613/14876 = 0.10843. Or 10.843%**

After running synthesis, inside the `runs/[date]/results/synthesis` is `picorv32a_synthesis.v` which is the mapping of the netlist to standard cell library using ABC. The `runs/[date]/reports/synthesis` will contain synthesis statistic reports and static timing analysis reports. The `runs/[date]/synthesis/logs` contains log files for the terminal output dumps for running yosys and OpenSTA.

# DAY 2: Good Floorplan vs Bad Floorplan and Introduction to Library Cells

### Floorplan Stage:

1. Define height and width of core and die.   
Core is where the logic blocks are placed and this seats at the center of the die. The width and height depends on dimensions of each standard cells on the netlist.
Utilization factor is (area occupied by netlist)/(total area of the core)
In practical scenario, utilization factor is 0.5 to 0.6. This is space occupied by netlist only, the remaining space is for routing and more additional cells. 
Aspect ratio is (height)/(width)
Aspect ratio of core, so only aspect ratio of 1 will produce a square core shape.

2. Define location of Preplaced Cell.   
These are reusable complex logicblocks or modules or IPs or macros that is already implemented (memory, clock-gating cell, mux, comparator...) . The placement on the core is user-defined and must be done before placement and routing (thus preplaced cells). The automated place and route tools will not be able to touch and move these preplaced cells so this must be very well defined

3. Surround preplaced cells with decoupling capacitors. 
The complex preplaced logicblock requires a high amount of current from the powersource for current switching. But since there is a distance between the main powersource and the logicblock, there will be voltage drop due to the resistance and inductance of the wire. This might cause the voltage at the logicblock to be not within the [noise margin](https://www.electronics-tutorial.net/digital-logic-families/noise-margin/) range anymore (logic is unstable). The solution is to use decoupling capacitors near the logic block, this capacitor will send enough current needed by the logicblock to switch within the noise margin range.

![image](https://user-images.githubusercontent.com/87559347/183011079-5f08eb01-28cf-4617-bcbc-f8f26eacc83d.png)

4. Power Planning
Decoupling capactor for sourcing logic blocks with enough current is not feasible to be applied all over the chip but only on the critical elements (preplaced complex logicblocks). Large number of elements switching to logic 0 might cause ground bounce due to large amount of current that needs to be sink at the same time, and switcing to logic 1 might cause voltage droop due to not enough current from the powersource to source needed current of all elements. Ground bounce and voltage droop might cause the voltage to not be within the noise margin range. The solution is to have multiple powersource taps (power mesh) where elements can source current from the nearest VDD and sink current to the nearest VSS tap. This is the reason why most chips have multiple powersource pins.

5. Pin Placement
The input and output ports are placed on the space between the core and the die. The placements of the ports depens on where the cells connected to those ports are placed on the core. The clock port is thicker(least resistance path) than data ports since this clock must be capable to drive the whole chip.

6. Logical Cell Placement Blockage
This makes sure that the automated placement and routing tool does not place any cell on the pin locations of the die.

Below are all 6  steps for floor planning:  

![image](https://user-images.githubusercontent.com/87559347/183446309-a0714ec5-0619-4327-bdfe-890c19cc97e0.png)


### Placement Stage:
1. Bind the netlist to a physical cell with real dimensions. The physical cell will come from a library that can provide multiple options for shapes, dimensions, and delay for same cells. 
2. Next is placement of those physical cells to the floorplan. The flip flops must be placed as near as possible to the input and output pins to reduce timing delay. 
3. Optimize placement to maintain signal integrity. This is where we estimate wirelength and capacitance (C=EA/d) and based on that insert repeaters/buffers. The wirelength will form a resistanace which will cause unnecessary voltage drop and a capacitance which will cause a slew rate that might not be permissible for fast current switching of logic gates. The solution to reduce resistance and capacitance is to insert buffers for long routes that will act as intermediary and separate a single long wire to multilple ones. Sometime we also do abutment where logic cells are placed very close to each other (almost zero delay) if it has to run at high frequency (2GHz). Crisscrossing of routes is a normal condition for PnR since we can use separate metal layer (using vias) for crisscrossed path.
4. After placement optimization, We will setup timing analysis using idle clock (zero delay for wires and has no clock buffer related delays) considering we have not yet done CTS.   

The goal of placement is not yet on timing but on congestion. Also, standard cells are not placed on floorplan stage, it is done on Placement stage. Macros or preplaced cells are the ones placed on floorplan stage.Macros or preplaced cells are placed on floorplan stage.

![image](https://user-images.githubusercontent.com/87559347/183224947-67a29c54-9a18-45a4-bbd1-9132bcebc304.png)  

Placement is done on two stages:
 - Global Placement = placement with no legalizations and goal is to reduce wirelength. It uses Half Perimeter Wirelength (HPWL) reduction model. 
 - Detailed Placement = placement with legalization where the standard cells are placed on stadard rows, abutted, and must have no overlaps    

### Lab [Day 2] - Determine Die Area: 

**1. Set configuration variables.** Before running floorplan stage, the configuration variables or switches must be configured first. The configuration variables are on `openlane/configuration`:  

```
.
├── README.md      
├── checkers.tcl
├── cts.tcl
├── floorplan.tcl  
├── general.tcl
├── lvs.tcl
├── placement.tcl
├── routing.tcl
└── synthesis.tcl 

```  

The  `README.md` describes all configuration variables for every stage and the tcl files contain the default OpenLANE settings. All configurations accepted by the current run is on `openlane/designs/picorv32a/runs/config.tcl`. This may come either from (with priority order):
 - PDK specific configuration inside the design folder
 - `config.tcl` inside the design folder
 - System default settings inside `openlane/configurations`
 
**2. Run floorplan on OpenLane:** `% run floor_plan`

**3. Check the results.** The output of this stage is `runs/[date]/results/floorplan/picorv32a.floorplan.def` which is a [design exchange format](https://teamvlsi.com/2020/08/def-file-in-vlsi-design-exchange.html), containing the die area and positions. 
```
...........
DESIGN picorv32a ;
UNITS DISTANCE MICRONS 1000 ;
DIEAREA ( 0 0 ) ( 660685 671405 ) ;
............
```
The die area here is in database units and 1 micron is equivalent to 1000 database units. **Thus area of the die is (660685/1000)microns\*(671405/1000)microns = 443587 microns squared.** 

**4. View the layout on magic**. Open def file using `magic` as follows: 

<img width="794" alt="directory" src="https://user-images.githubusercontent.com/83575446/215528630-edf4e34d-f3c8-4ba5-8de5-0ef0d3939f87.png">

Then the following window opens

<img width="955" alt="6 floorplan" src="https://user-images.githubusercontent.com/83575446/215527011-b7b45518-6af1-4db2-865b-3913f707b5b8.png">

To center the view, press "s" to select whole die then press "v" to center the view. Point the cursor to a cell then press "s" to select it, zoom into it by pressing 'z". Type "what" in `tkcon` to display information of selected object. These objects might be IO pin, decap cell, or well taps as shown below.  

<img width="802" alt="tkcon" src="https://user-images.githubusercontent.com/83575446/215530325-b50072f3-0fdf-4493-babe-474794dcbd7f.png">

 Useful Magic commands are listed on the [Magic Commands section](https://github.com/AngeloJacobo/OpenLANE-Sky130-Physical-Design-Workshop#magic-commands).

**5 Run placement:** `% run_placement`. This commmand is a wrapper which does global placement (performed by RePlace tool), Optimization (by Resier tool), and detailed placement (by OpenDP tool). It displays hundreds of iterations displaying HPWL and OVFL. The algorithm is said to be converging if the overflow is decreasing. It also checks the legality. 

**6. View the output of this stage**. The output of this stage is `runs/[date]/results/placement/picorv32a.placement.def.` To see actual layout after placement, open def file using `magic`:  

```
magic -T /home/kunalg123/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read picorv32a.placement.def
```  
The placement is as follows

<img width="668" alt="placement" src="https://user-images.githubusercontent.com/83575446/215532046-100d8a25-504c-4fbb-af2c-dd549ab45aee.png">

### Library Characterization:
Of all RTL-to-GDSII stages, one common thing that the EDA tool always need is data from the library of gates which keeps all standards cells (and, or, buffer gates,...), macros, IPs, decaps, etc. Same cells might have different flavors inside the library (different sizes, delays, threshold voltage). Bigger cell sizes means bigger drive strength to drive longer and thicker wires. Bigger threshold voltage (due to bigger size) will take more time to switch(slower clock) than those with smaller threshold voltage.  

A single cell needs to go through the cell design flow. The inputs to make a single cell comes from the foundry Process Design Kits:
 - DRC & LVS Rules = tech files and poly subtrate paramters (CUSTOME LAYOUT COURSE)
 - SPICE Models  = Threshold, linear regions, saturation region equations with added foundry parameters. Including NMOS and PMOS parameteres (Ciruit Deisgn and Spice simulation Course)
 - User defined Spec = Cell height (separation between power and ground rail), Cell width (depends on drive strength), supply voltage, metal layer requirement (which metal layer the cell needs to work)

The library cell developer must adhere to the rules given on the inputs so that when the cell is used on a real design, there will be no errors. Next is design the library cell:
1. Design the circuit function (Output: circuit design language (CDL))
2. Model the pmos and nmos that meets input library requirement
3. Layout the design using Euler's path and sticky diagram to produce best area. This can be done on `magic` layout tool.The outputs are:
   - GDSII (layout file)
   - LEF (defines the width and height of cell)
   - extract spice netlist .cir (parasitics of each element of cell: resistance, capacitance)
 Afte design is characterization using GUNA software, where the outputs are timing, noise, and power characterization.
 
 ### Timing Characterization:
 
It contains :
Propogation Delay - (out_thr)-time(in_thr)
Transition Time - time(slew_high_rise_thr)-time(slew_low_rise_thr)} or time(slew_high_fall_thr)-time(slew_low_fall_thr)
 
Below are the timing variables for slew. This is two inverters in series, red is output of first inverter and blue is output of second inverter:  

![image](https://user-images.githubusercontent.com/87559347/183231913-a9b3826b-5139-4bdc-b12b-3495b87cd8b9.png)

Below are the timing variables for propagation delay. The red is input waveform and blue is output waveform of the buffer. The left side is rise delay and right side is fall delay.

![image](https://user-images.githubusercontent.com/87559347/183232515-fe3cef76-8a2f-475d-9a64-392fc2fda111.png)

Negative propagation delay is unexpected. That means the output comes before the input so designer needs to choose correct threshold point to produce positive delay. Delay threshold is usually 50% and slew rate threshold is usually 20%-80%.

# DAY 3: Design a Library Cell using Magic Layout and Ngspice Characterization

### Designing a Library Cell:
1. SPICE deck = component connectivity (basically a netlist) of the CMOS inverter.
2. SPICE deck values = value for W/L (0.375u/0.25u means width is 375nm and lengthis 250nm). 
3. PMOS should be wider in width(2x or 3x) than NMOS. 
4. The gate and supply voltages are normally a multiple of length (in the example, gate voltage can be 2.5V)  
5. Add nodes to surround each component and name it. This will be used in SPICE to identify a component.    

### SPICE Deck Netlist Description:  

![image](https://user-images.githubusercontent.com/87559347/183240195-608727e5-2d04-4e44-ab4a-2df545cd13ea.png)

**Notes:**
 - Syntax for the PMOS and NMOS descriptiom:
     - `[component name] [drain] [gate] [source] [substrate] [transistor type] W=[width] L=[length]`
 - All components are described based on nodes and its values
 - `.op` is the start of SPICE simulation operation where Vin will be sweep from 0 to 2.5 with 0.5 steps
 - `tsmc_025um_model.mod` is the model file containing the technological parameters for the 0.25um NMOS and PMOS

### SPICE Analysis for Switching Threshold and Propagation Delay:
CMOS robustness depends on:  

1. Switching threshold = Vin is equal to Vout. This the point where both PMOS and NMOS is in saturation or kind of turned on, and leakage current is high. If PMOS is thicker than NMOS, the CMOS will have higher switching threshold (1.2V vs 1V) while threshold will be lower when NMOS becomes thicker.
2. Propagation delay = rise or fall delay
 ### CMOS Fabrication Process (16-Mask CMOS Process):  
 **1. Selecting a substrate** = Layer where the IC is fabricated. Most commonly used is P-type substrate  
 **2. Creating active region for transistor** = Separate the transistor regions using SiO2 as isolation
  - Mask 1 = Covers the photoresist layer that must not be etched away (protects the two transistor active regions)
  - Photoresist layer = Can be etched away via UV light  
  - Si3N4 layer = Protection layer to prevent SiO2 layer to grow during oxidation (oxidation furnace)  
  - SiO2 layer = Grows during oxidation (LOCOS = Local Oxidation of Silicon) and will act as isolation regions between transistors or active regions  
3. N-Well and P-Well Fabrication = Fabricate the substrate needed by PMOS (N-Well) and NMOS (P-Well)  
  - Phosporus (5 valence electron) is used to form N-well  
  - Boron (3 valence electron) is used to form P-Well.  
  - Mask 2 protects the N-Well (PMOS side) while P-Well (NMOS side) is being fabricated then Mask 3 while N-Well (PMOS side) is being fabricated
4. Formation of Gate = Gate fabrication affects threshold voltage. Factors affecting threshold voltage includes:    
    Main parameters are:
  - Doping Concentration = Controlled by ion implantation (Mask 4 for Boron implantation in NMOS P-Well and Mask 5 for Arsenic implantation in PMOS N-Well)
  - Oxide capacitance = Controlled by oxide thickness  (SiO2 layer is removed then rebuilt to the desire thickness)  
  - Mask 6 is for gate formation using polysilicon layer.
5. Lightly Doped Drain formation = Before forming the source and drain layer, lightly doped impurity is added: 
  - Mask 7 for N- implantation (lightly doped N-type) for NMOS 
  - Mask 8 for P- implantation (lightly doped P-type) for PMOS.  
Heavily doped impurity (N+ for NMOS and P+ for PMOS) is for the actual source and drain but the lightly doped impurity will help maintain spacing between the source and drain and prevent hot electron effect and short channel effect. 
6. Source and Drain Formation = Mask 9 is for N+ implantation and Mask 10 for P+ implantation  
 - Channeling is when implantations dig too deep into substrate so add screen oxide before implantation
 - The side-wall spacers maintains the N-/P- while implanting the N+/P+    
7. Form Contacts and Interconnects =  TiN is for local interconnections and also for bringing contacts to the top. TiS2 is for the contact to the actual Drain-Gate-Source. Mask 11 is for etching off the TiN interconnect for the first layer contact. 
8. Higher Level Metal Formation = We need to planarize first the layer via CMP before adding a metal interconnect. Aluminum contact is used to connect the lower contact to higher metal layer. Process is repeated until the contact reached the outermost layer.
 - Mask 12 is for first contact hole
 - Mask 13 is for first Aluminum contact layer
 - Mask 14 is for second contact hole
 - Mask 15 is for second Aluminum contact layer. Mask 16 is for making contact to topmost layer. 
 
![image](https://user-images.githubusercontent.com/87559347/187158161-4d230654-5102-4225-8e58-d6d8ed950990.png)

### Lab [DAY 3] - Introduction to Sky130 basic layers layout and LEF using inverter:
  
1. Clone [vsdstdcelldesign](https://github.com/nickson-jose/vsdstdcelldesign). 
2. Copy the techfile `sky130A.tech` from `pdks/sky130A/libs.tech/magic/` to directory of the cloned repo. In the below figure, you can see tech file getting added to vsdstdcelldesign

<img width="959" alt="7 techfile added" src="https://user-images.githubusercontent.com/83575446/215544859-deadc35e-d812-47dd-acd1-6a84c83f1502.png">

3. View the mag file using magic `magic -T sky130A.tech sky130_inv.mag &`:  

<img width="457" alt="inverter" src="https://user-images.githubusercontent.com/83575446/215546262-98a5d2f0-c150-4f14-a9e0-7bca19b5caf3.png">

4. Try DRC at top tool bar to find the DRC violations and type `what` in tkcon window to find the error

<img width="958" alt="11 dimensions of grid" src="https://user-images.githubusercontent.com/83575446/215548187-5df11006-b78c-4ee8-8458-0191aa7421ee.png">

### Extraction of SPICE file & Slew Rate and Propagation Delay Characterization 

1. Make an extract file `.ext` by typing `extract all` in the tkon terminal. 
2. Extract the `.spice` file from this ext file by typing `ext2spice cthresh 0 rthresh 0` then `ext2spice` in the tcon terminal.  

<img width="960" alt="10 spice created" src="https://user-images.githubusercontent.com/83575446/215549589-55e619df-34ac-4060-ad89-6c34ea426a58.png">

3. Modify the spice file to be able to plot a transient response
4. Change the grid size by checking in layout

<img width="958" alt="11 dimensions of grid" src="https://user-images.githubusercontent.com/83575446/215550902-cb4c00c1-86e0-4753-a13a-92bccb914956.png">

5. Include pmos, nmos libraries from `\vsdstdcelldesign-master\libs\nshort.lib` and `\vsdstdcelldesign-master\libs\nphort.lib` which are the spice model files for nmos and pmos
6. Rename the pmos and nmos names

<img width="959" alt="12 pmos name" src="https://user-images.githubusercontent.com/83575446/215551628-bb865cca-7ce9-482d-b300-c49a7f1d6ac6.png">

8. Change C3(Cload) to 2fF(increase it) to get the higher delay
9. Define ground, supply & input signals

```
* SPICE3 file created from sky130_inv.ext - technology: sky130A

.option scale=0.01u
.include ./libs/pshort.lib
.include ./libs/nshort.lib

* .subckt sky130_inv A Y VPWR VGND
M0 Y A VGND VGND nshort_model.0 ad=1435 pd=152 as=1365 ps=148 w=35 l=23
M1 Y A VPWR VPWR pshort_model.0 ad=1443 pd=152 as=1517 ps=156 w=37 l=23
C0 A VPWR 0.08fF
C1 Y VPWR 0.08fF
C2 A Y 0.02fF
C3 Y VGND 0.18fF
C4 VPWR VGND 0.74fF
* .ends

* Power supply 
VDD VPWR 0 3.3V 
VSS VGND 0 0V 

* Input Signal
Va A VGND PULSE(0V 3.3V 0 0.1ns 0.1ns 2ns 4ns)

* Simulation Control
.tran 1n 20n
.control
run
.endc
.end
```  

10. Open the spice file by typing `ngspice sky130A_inv.spice`. 
11. Generate a graph using `plot y vs time a` :  

<img width="959" alt="13 spice graph" src="https://user-images.githubusercontent.com/83575446/215551955-d3adaaf5-198b-4e70-a4bc-d153f6e50401.png">

Using this transient response, we will now characterize the cell's slew rate and propagation delay:  
- Rise Transition [output transition time from 20%(0.66V) to 80%(2.64V)]:
    - **Tr_r = 2.19981ns - 2.15739ns = 0.04242 ns**  

- Fall Transition [output transition time from 80%(2.64V) to 20%(0.66V)]:
   - **Tr_f = 4.0672ns - 4.04007ns = 0.02713ns**   

- Rise Delay [delay between 50%(1.65V) of input to 50%(1.65V) of output]:
   - **D_r = 2.18197ns - 2.15003ns = 0.03194ns**   

- Fall Delay [delay between 50%(1.65V) of input to 50%(1.65V) of output]:
   - **D_f = 4.05364ns - 4.05001ns =0.00363ns** 

# DAY 4: Pre-layout Timing Analysis and Importance of Good Clock Tree

To convert grid into track information it should follow the below rules :
  - The i/p & o/p ports must lie on intersection of vertical & horizantal tracks
  - The width of standard cell should be power multiple of track path
  - The height should be odd multiple of track vertical pitch
  - The width of standard cell is odd multiple of X pitch
  
### Lab [Day 4] - Extracting the LEF File:  

PnR tool does not need all informations from the `.mag` file like the logic part but only PnR boundaries, power/ground ports, and input/output ports. This is what a [LEF file](https://teamvlsi.com/2020/05/lef-lef-file-in-asic-design.html) actually contains. So the next step is to extract the LEF file from Magic. But first, we need to follow guidelines of the PnR tool for the standard cells:
 - The input and output ports lies on the intersection of the horizontal and vertical tracks (ensure the routes can reach that ports). 
 - The width of the standard cell must be odd multiple of the tracks horizontal pitch and height must be odd multiples of tracks vertical pitch   
 
 To check these guidelines, we need to change the grid of Magic to match the actual metal tracks. The `pdks/sky130A/libs.tech/openlane/sky130_fd_sc_hd/tracks.info` contains those metal informations.   
 
 <img width="960" alt="14 tracks info" src="https://user-images.githubusercontent.com/83575446/215556315-8d59fee5-ea2a-48ea-8d9a-e533bb952f91.png">

1. Use `grid` command inside the tkon terminal to match the tracks informations:  

![image](https://user-images.githubusercontent.com/87559347/188419121-ce050fc7-6984-4266-9b24-47002934fc83.png)

2. Exract the LEF file from magfile. To do that give cell a custom name & save the mag file with a new filename `save sky130_myinverter.mag`

3. Tye `lef write` on the tcon terminal. It will generate a LEF file with same name as the magfile `sky130_myinverter.lef`. Inside that LEF file is: 
 
<img width="960" alt="16 lib files created" src="https://user-images.githubusercontent.com/83575446/215557475-d3881523-a41d-4e2b-8f98-dcc698741f5a.png">

### Plug-in the Customized Inverter Cell to OpenLane:

1. Copy the extracted lef file `sky130_myinverter.lef`  from `/openlane/vsdstdcelldesign/libs` to the src directory of picorv32a. 

```
cp sky130_myinverter.lef harithah931/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/src
```

2. Add the folowing to `config.tcl` inside the picorv32a:    
```  
set ::env(LIB_SYNTH) "$::env(OPENLANE_ROOT)/designs/picorv32a/scr/sly130_fd_sc_hd__typical.lib"
set ::env(LIB_FASTEST) "$::env(OPENLANE_ROOT)/designs/picorv32a/scr/sly130_fd_sc_hd__fast.lib"
set ::env(LIB_SLOWEST) "$::env(OPENLANE_ROOT)/designs/picorv32a/scr/sly130_fd_sc_hd__slow.lib"
set ::env(LIB_TYPICAL) "$::env(OPENLANE_ROOT)/designs/picorv32a/scr/sly130_fd_sc_hd__typical.lib"

set ::env(EXTRA_LEFS) [glob $::env(OPENLANE_ROOT)/designs/$::env(DESIGN_NAME)/src/*.lef]
```

This sets the liberty file that will be used for ABC mapping of synthesis (`LIB_SYNTH`) and for STA (`_FASTEST`,`_SLOWEST`,`_TYPICAL`) and also the extra LEF files (`EXTRA_LEFS`) for the customized inverter cell. The whole `config.tcl` then is:  

<img width="484" alt="config" src="https://user-images.githubusercontent.com/83575446/215561636-36f9e070-6619-4305-b204-c71a811ba1d1.png">

3. Run docker and prepare the design picorv32a. Plug the new lef file to the OpenLANE flow via:  

```
set lefs [glob $::env(DESIGN_DIR)/src/*.lef]
add_lefs -src $lefs
```  

4. Next `run_synthesis` 
5. Observe the worst negative slack value

<img width="958" alt="17 slack(wns) value" src="https://user-images.githubusercontent.com/83575446/215565638-f84bc5ee-053f-42e1-911c-f39f11803d4d.png">

### Delay Table:  

In order to avoid large skew between endpoints of a clock tree (signal arrives at different point in time):
 - Buffers on the same level must have same capacitive load to ensure same timing delay or latency on the same level. 
 - Buffers on the same level must also be the same size (different buffer sizes -> different W/L ratio -> different resistance -> different RC constant -> different delay).    
 
 ![image](https://user-images.githubusercontent.com/87559347/188773408-e503023f-0288-4993-a68a-5f20bccb886c.png)


Buffers on different level will have different capacitive load and buffer size but as long as they are the same load and size on the same level, the total delay for each clock tree path will be the same thus skew will remain zero. **This means different levels will have varying input transition and output capacitive load and thus varying delay.** 

Delay tables are used to capture the timing model of each cell and is included inside the liberty file. The main factor in delay is the output slew. The output slew in turn depends on **capacitive load** and **input slew**. The input slew is a function of previous buffer's output cap load and input slew and it also has its own transition delay table.

![image](https://user-images.githubusercontent.com/87559347/188783693-423bd170-dd0b-4f2f-9652-8fae9418df31.png)

Notice how skew is zero since delay for both clock path is x9'+y15.

### Fix Negative Slack:

1. Let us change some variables to minimize the negative slack. We will now change the variables "on the flight". Use `echo $::env(SYNTH_STRATEGY)` to view the current value of the variables before changing it:  
```
% echo $::env(SYNTH_STRATEGY)
AREA 0
% set ::env(SYNTH_STRATEGY) "DELAY 0"
% echo $::env(SYNTH_BUFFERING)
1
% echo $::env(SYNTH_SIZING)
0
% set ::env(SYNTH_SIZING) 1
% echo $::env(SYNTH_DRIVING_CELL)
sky130_fd_sc_hd__inv_2
```  
With `SYNTH_STRATEGY` of `Delay 0`, the tool will focus more on optimizing/minimizing the delay, index can be 0 to 3 where 3 is the most optimized for timing (sacrificing more area). `SYNTH_BUFFERING` of 1 ensures cell buffer will be used on high fanout cells to reduce delay due to high capacitance load. `SYNTH_SIZING` of 1 will enable cell sizing where cell will be upsize or downsized as needed to meet timing. `SYNTH_DRIVING_CELL` is the cell used to drive the input ports and is vital for cells with a lot of fan-outs since it needs higher drive strength (larger driving cell needed).

2. Slack got reduced

<img width="957" alt="18 slack reduced" src="https://user-images.githubusercontent.com/83575446/215566059-5d850cda-8b09-4ad0-909b-3610df1a58b3.png">

3. Next, follow the below commands

```
init_floorplan
place_io
global_placement_or
detailed_placement
tap_decap_or
detailed_placement
```

### Locating the Custom Inverter Cell in Layout:  

1. Search for instance of cell `sky130_myinverter` inside the DEF file after placement stagee

`/home/harithah931/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/29-01_06-33/tmp/merged.lef`

2. Open the def file via magic:

`magic -T /home/harithah931/Desktop/OpenLane/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.nom.lef def read picorv32.def &`

<img width="272" alt="my custom cell" src="https://user-images.githubusercontent.com/83575446/215568902-31aa0b08-69a9-45a6-a71f-81a689acc124.png">

### Setup Timing Analysis :

1. Create the pre_sta.conf and save it in the openlane folder.

```
set_cmd_units -time ns -capacitance pF -current mA -voltage V -resistance kOhm -distance um
read_liberty -min /home/abhinavprakash1999/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/src/sky130_fd_sc_hd__slow.lib
read_liberty -max /home/abhinavprakash1999/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/src/sky130_fd_sc_hd__fast.lib
read_verilog /home/abhinavprakash1999/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/29-01_16-21/results/synthesis/picorv32a.synthesis_cts.v
link_design picorv32a
read_sdc /home/abhinavprakash1999/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/src/my_base.sdc
report_checks -path_delay min_max -fields {slew trans net cap input_pin}
report_tns
report_wns
```

2. Creating my_base.sdc and save this file in the src folder of picorv32a folder

```
set ::env(CLOCK_PORT) clk
set ::env(CLOCK_PERIOD) 12.000
set ::env(SYNTH_DRIVING_CELL) sky130_fd_sc_hd__inv_8
set ::env(SYNTH_DRIVING_CELL_PIN) Y
set ::env(SYNTH_CAP_LOAD) 17.65
create_clock [get_ports $::env(CLOCK_PORT)]  -name $::env(CLOCK_PORT)  -period $::env(CLOCK_PERIOD)
set IO_PCT  0.2
set input_delay_value [expr $::env(CLOCK_PERIOD) * $IO_PCT]
set output_delay_value [expr $::env(CLOCK_PERIOD) * $IO_PCT]
puts "\[INFO\]: Setting output delay to: $output_delay_value"
puts "\[INFO\]: Setting input delay to: $input_delay_value"


set clk_indx [lsearch [all_inputs] [get_port $::env(CLOCK_PORT)]]
#set rst_indx [lsearch [all_inputs] [get_port resetn]]
set all_inputs_wo_clk [lreplace [all_inputs] $clk_indx $clk_indx]
#set all_inputs_wo_clk_rst [lreplace $all_inputs_wo_clk $rst_indx $rst_indx]
set all_inputs_wo_clk_rst $all_inputs_wo_clk


# correct resetn
set_input_delay $input_delay_value  -clock [get_clocks $::env(CLOCK_PORT)] $all_inputs_wo_clk_rst
#set_input_delay 0.0 -clock [get_clocks $::env(CLOCK_PORT)] {resetn}
set_output_delay $output_delay_value  -clock [get_clocks $::env(CLOCK_PORT)] [all_outputs]

# TODO set this as parameter
set_driving_cell -lib_cell $::env(SYNTH_DRIVING_CELL) -pin $::env(SYNTH_DRIVING_CELL_PIN) [all_inputs]
set cap_load [expr $::env(SYNTH_CAP_LOAD) / 1000.0]
puts "\[INFO\]: Setting load to: $cap_load"
set_load  $cap_load [all_outputs]
```
### Clock Tree Synthesis Stage:
There are three parameters that we need to consider when building a clock tree:
- Clock Skew = In order to have minimum skew between clock endpoints, clock tree is used. This results in equal wirelength (thus equal latency/delay) for every path of the clock. 
- Clock Slew = Due to wire resistance and capacitance of the clock nets, there will be slew in signal at the clock endpoint where signal is not the same with the original input clock signal anymore. This can be solved by clock buffers. Clock buffer differs in regular cell buffers since clock buffers has equal rise and fall time. 
- Crosstalk = Clock shielding prevents crosstalk to nearby nets by breaking the coupling capacitance between the victim (clock net) and aggresor (nets near the clock net), the shield might be connected to VDD or ground since those will not switch. Shileding can also be done on critical data nets.

![image](https://user-images.githubusercontent.com/87559347/190031283-3bc25c79-f622-4b58-a448-95982d32612d.png)

- Use `run_cts` command in openlane to run clock tree synthesis

<img width="793" alt="cts" src="https://user-images.githubusercontent.com/83575446/215576302-53ca7d41-6ab7-47d2-beef-e5b76efca422.png">

- Then following files created `picorv32a.cts.def` and `picorv32a.cts.def.png` 

<img width="960" alt="19 cts" src="https://user-images.githubusercontent.com/83575446/215577044-da29ce95-4866-4e56-9039-8081af4e7c65.png">

### Timing Analysis with Real Clocks:
Setup and hold analysis with real clock will now include clock buffer delays:
- In setup analysis, the point is that the data must arrive first before the clock rising edge to properly latch that data. Setup violation happens when path is slow. This is affected by parameters such as combinational delay, clock buffer delay, time period, setup time, and setup uncertainty (jitter).

- Hold analysis is the delay that the MUX2 model inside the flip flop needs to move the data to outside. This is the time that the launch flop must hold the data before it reaches the capture flop. Hold analysis is done on the same rising clock edge for launch and capture flop unlike in setup analysis where it spans between two rising clock edges. Hold violation happens when path is too fast. This is affected by parameters such as combinational delay, clock buffer delays, and hold time. (time period and setup uncertainty does not matter since launch and capture flops will receive the same rising clock edges fo hold analysis)

### Multi-corner STA for Post-CTS:
We will now do STA for post clock tree synthesis to include effect of clock buffers. Similar to pre-layout STA, this will done on OpenROAD (which will then call OpenSTA):  
- `write_db` and `read_db`is done before running STA tool, this creates a database file using LEF file and resulting DEF file of the last stage.
- Multi-corner STA must read both min library (for hold analysis) and max library (for setup analysis) unlike in single corner STA where only the typical library is read. 
- SDC file used is the same for single and multi-corner. 
- Since this is post-CTS STA, `set_propagated_clock` is used. `set_propagated_clock` propagates clock latency throughout a clock network, resulting in more accurate skew and timing results throughout the clock network. This is done  postlayout, after final clock tree generation, unlike in prelayout where ideal clock is used thus no clock latency.
- Also instead of manually running these commands, we can just simply do `source /openlane/scripts/openroad/sta_multi_corner.tcl` inside OpenROAD which runs the readily-made tcl script of OpenROAD commmands for running multi-corner STA. The result might be slightly different from the result above since the settings for `sta_multi_corner.tcl` is much more comprehensive.
- Run the following commands
```
openroad
read_db pico_cts.db
read_verilog /openLANE_flow/designs/picorv32a/runs/29-01_16-21/results/synthesis/picorv32a.synthesis_cts.v
read_liberty $::env(LIB_SYNTH_COMPLETE)
link_design picorv32a
read_sdc /openLANE_flow/designs/picorv32a/src/my_base.sdc
set_propagated_clock [all_clocks]
report_checks -path_delay min_max -format full_clock_expanded -digits 4
```
- Skew report

<img width="218" alt="skew" src="https://user-images.githubusercontent.com/83575446/215572349-358ac9cd-7156-481c-bb2e-848cba9b98d4.png">

# DAY 5: Final Steps for RTL2GDS using TritonRoute and OpenSTA

Routing means connecting source and desination with best possible path

### Maze Routing - Lee's Algorithm:
- The shortest path is one that follows a steady increment of one (1-to-9 on the example below). There might be multiple path like this but the best path that the tool will choose is one with less bends. The route should not be diagonal and must not overlap an obstruction such as macros. 
- This algorithm however has high run time and consume a lot of memory thus more optimized routing algorithm is preferred (but the principles stays the same where route with shortest path and less bends is preferred)  

 <img width="461" alt="maze" src="https://user-images.githubusercontent.com/83575446/215582808-440267fd-7026-480d-9d26-f0ef3cc16f6c.png">

### DRC Cleaning:
DRC cleaning is the next step after routing. DRC cleaning is done to ensure the routes can be fabricated and printed in silicon faithfully. Most DRC is due to the constraints of the photolitographic machine for chip fabrication where the wavelength of light used is limited. There are thousands of DRC and some DRC are:
1. Minimum wire width
2. Minimum wire pitch (center to center spacing)
3. Minimum wire spacing (edge to edge spacing)
4. Signal short = this can be solved my moving the route to next layer using vias. This results in more DRC (Via width, Via Spacing, etc.). Higher metal layer must be wider than lower metal layer and this is another DRC.  

### Routing Stage and TritonRoute:
OpenLane routing stage consists of two stages:
 - Global Routing - Form routing guides that can route all the nets. The tool used is FastRoute
 - Detailed Routing - Uses the global routing's guide to actually connect the pins with least amount of wire and bends. The tool used is TritonRoute.
 
 **Triton Route**
 - Performs detailed routing and honors the pre-processed route guides (made by global route) and uses MILP based (Mixed  Integer Linear Programming algorithm) panel routing scheme(uses panel as the grid guide for routing) with intra-layer parallel routing (routing happens simultaneously in a single layer) and inter-layer sequential layer (routing starts from bottom metal layer to top metal layer sequentially and not simultaneously). 
 - Honors preferred direction of a layer. Metal layer direction is alternating (metal layer direction is specified in the LEF file e.g. met1 Horizontal, met2 Vertical, etc.) to reduce overlapping wires between layer and reduce potential capacitance which can degrade the signal.  

### Lab [Day 5] - Power Distribution Network (PDN) and routing

Check the last def file created using `echo $::env(CURRENT_DEF)` command in docker

- run `gen_pdn`

<img width="796" alt="pdn" src="https://user-images.githubusercontent.com/83575446/215584512-c5bf1e4c-27b7-4da6-b168-1f503103a1df.png">

- run `run_routing`

<img width="795" alt="routing" src="https://user-images.githubusercontent.com/83575446/215584837-34b28892-4530-45d8-bea3-3525dff66b50.png">

- This will do both global and detailed routing, this will take multiple optimization iterations until the DRC violation is reduced to zero. 

 
 ### SPEF Extraction and GDSII Streaming:
 
 Now that we verified the routing, run post-routing STA with `run_parasitics_sta`.
 - First, this will do a [SPEF (Standard Parasitics Extraction Format) extraction](https://www.physicaldesign4u.com/2020/05/standard-parasitic-extraction-format.html) of the parasitics resistance and capacitance. 
 - Then multi-corner STA will be done with the extracted SPEF.  
 - SPEF extraction and multi-corner STA will be done on all three corners (min, max, nom).   
 
 The delay due to the real-world parasitics will most likely worsen the slack for both hold and setup analysis. The extracted SPEF can be located under `runs/[date]/results/routing` and the STA log files under `runs/[date]/logs/signoff`. Timing ECO can be done to reduce the slack to the desired levels.
 
The last stage will be to extract the GDS file ready for fabrication, simply run `run_magic`. It creates the following file ` picrrv32a.gds.png`

![picorv32a gds](https://user-images.githubusercontent.com/83575446/216117766-148abfa9-3212-457f-ad1a-f46dca4b983b.png)


## Acknowledgements
 - [Kunal Ghosh - Co-founder of VSD](https://www.udemy.com/user/anagha/)
 - [Nickson Jose - Workshop Instructor](https://www.udemy.com/user/nickson-jose/)
 
 
## Inquiries  
Connect with me at my linkedin: https://www.linkedin.com/in/haritha-gopisetty/
