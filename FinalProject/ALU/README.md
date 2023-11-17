# Final Project: Arithmetic Logic Unit

Toby Werthan

11/17/2023

ENCE 3501

## Table of Contents
1. [Introduction](#introduction)
2. [Inverter](#inv)
    1. [Schematic](#invSchem)
    2. [Layout](#invLay)
    3. [Simulation](#invSim)
3. [Multiplexer](#mux)
    1. [Schematic](#muxSchem)
    2. [Layout](#muxLay)
    3. [Simulation](#muxSim)
4. [Full Adder](#fa)
    1. [Schematic](#faSchem)
    2. [Layout](#faLay)
    3. [Simulation](#faSim)
5. [Controlled Buffer](#buf)
    1. [Schematic](#bufSchem)
    2. [Layout](#bufLay)
    3. [Simulation](#bufSim)
6. [Arithmetic Logic Unit](#alu)
    1. [Schematic](#aluSchem)
    2. [Layout](#aluLay)
    3. [Simulation](#aluSim)
7. [Conclusion](#conclusion)

*Note: If images are hard to view, please click on them. A new tab will open, displaying the full-size image.*
    
<h2>Introduction</h2>  <a name="introduction"></a>

<dl><dd>

<p>
   The purpose of this lab was to create a DC-to-DC regulator in Electric VLSI. This lab only outlines the schematics and simulations of the individual components that make up the DC-to-DC regulator. The components outlined include a three-stage charge pump, a ring oscillator with an enabling capability, and a voltage regulator that works as a comparator. 
</p>

<p align="center">
  <img width="900" height="500" src="">
</p>

<p align="center">
    Figure 1 (Provided schematic of the DC-to-DC Regulator)
</p>

</dd><dl>







<h2> Inverter </h2> <a name="inv"></a>

<dl><dd><h3>Schematic</h3> <a name="invSchem"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>    
    SCHEMATIC DESCRIPTION
</p>

<p align="center">
  <img width="850" height="550" src="">
</p>

<p align="center">
    Figure 2 (SCHEMATIC TITLE)
</p>

<p>    
    ICON DESCRIPTION
</p>

<p align="center">
  <img width="300" height="250" src="">
</p>
<p align="center">
    Figure 3 (ICON TITLE)
</p>

</dd></dl></dd></dl>

<dl><dd><h3>Layout</h3> <a name="invLay"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>    
    LAYOUT DESCRIPTION
</p>

<p align="center">
  <img width="850" height="550" src="">
</p>

<p align="center">
    Figure 2 (LAYOUT TITLE)
</p>

<p>    
   3D DESCRIPTION
</p>

<p align="center">
  <img width="300" height="250" src="">
</p>
<p align="center">
    Figure 3 (3D TITLE)
</p>

</dd></dl></dd></dl>

<dl><dd><h3>Simulation</h3> <a name="invSim"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>
    SIMULATION DESCRIPTION
</p>
    
<p align="center">
  <img width="900" height="600" src="">
</p>
<p align="center">
    Figure 6 (SIMULATION TITLE)
</p>

<p>
    A snippet of the spice code for the simulation is provided below:
</p>

        .include cmosedu_models.txt
        
        vdd vdd 0 DC 1
        vosc osc 0 pulse(0 1 0 1p 1p 0.025 0.05)
        vosc2 osc2 0 pulse(0 1 0.025 1p 1p 0.025 0.05)
        .tran 0 1000 1m
<p align="center">
    Figure 7 (SPICE CODE TITLE)
</p>

<p>
    SIM RESULT DESCRIPTION
</p>

<p align="center">
  <img width="1500" height="500" src="">
</p>

<p align="center">
    Figure 8 (RESULT TITLE)
</p>
    
</dd></dl></dd></dl>






<h2> Multiplexer </h2> <a name="mux"></a>

<dl><dd><h3>Schematic</h3> <a name="muxSchem"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>    
    SCHEMATIC DESCRIPTION
</p>

<p align="center">
  <img width="850" height="550" src="">
</p>

<p align="center">
    Figure 2 (SCHEMATIC TITLE)
</p>

<p>    
    ICON DESCRIPTION
</p>

<p align="center">
  <img width="300" height="250" src="">
</p>
<p align="center">
    Figure 3 (ICON TITLE)
</p>

</dd></dl></dd></dl>

<dl><dd><h3>Layout</h3> <a name="muxLay"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>    
    LAYOUT DESCRIPTION
</p>

<p align="center">
  <img width="850" height="550" src="">
</p>

<p align="center">
    Figure 2 (LAYOUT TITLE)
</p>

<p>    
   3D DESCRIPTION
</p>

<p align="center">
  <img width="300" height="250" src="">
</p>
<p align="center">
    Figure 3 (3D TITLE)
</p>

</dd></dl></dd></dl>

<dl><dd><h3>Simulation</h3> <a name="muxSim"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>
    SIMULATION DESCRIPTION
</p>
    
<p align="center">
  <img width="900" height="600" src="">
</p>
<p align="center">
    Figure 6 (SIMULATION TITLE)
</p>

<p>
    A snippet of the spice code for the simulation is provided below:
</p>

        .include cmosedu_models.txt
        
        vdd vdd 0 DC 1
        vosc osc 0 pulse(0 1 0 1p 1p 0.025 0.05)
        vosc2 osc2 0 pulse(0 1 0.025 1p 1p 0.025 0.05)
        .tran 0 1000 1m
<p align="center">
    Figure 7 (SPICE CODE TITLE)
</p>

<p>
    SIM RESULT DESCRIPTION
</p>

<p align="center">
  <img width="1500" height="500" src="">
</p>

<p align="center">
    Figure 8 (RESULT TITLE)
</p>
    
</dd></dl></dd></dl>






<h2> Inverter </h2> <a name="fa"></a>

<dl><dd><h3>Schematic</h3> <a name="faSchem"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>    
    SCHEMATIC DESCRIPTION
</p>

<p align="center">
  <img width="850" height="550" src="">
</p>

<p align="center">
    Figure 2 (SCHEMATIC TITLE)
</p>

<p>    
    ICON DESCRIPTION
</p>

<p align="center">
  <img width="300" height="250" src="">
</p>
<p align="center">
    Figure 3 (ICON TITLE)
</p>

</dd></dl></dd></dl>

<dl><dd><h3>Layout</h3> <a name="faLay"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>    
    LAYOUT DESCRIPTION
</p>

<p align="center">
  <img width="850" height="550" src="">
</p>

<p align="center">
    Figure 2 (LAYOUT TITLE)
</p>

<p>    
   3D DESCRIPTION
</p>

<p align="center">
  <img width="300" height="250" src="">
</p>
<p align="center">
    Figure 3 (3D TITLE)
</p>

</dd></dl></dd></dl>

<dl><dd><h3>Simulation</h3> <a name="faSim"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>
    SIMULATION DESCRIPTION
</p>
    
<p align="center">
  <img width="900" height="600" src="">
</p>
<p align="center">
    Figure 6 (SIMULATION TITLE)
</p>

<p>
    A snippet of the spice code for the simulation is provided below:
</p>

        .include cmosedu_models.txt
        
        vdd vdd 0 DC 1
        vosc osc 0 pulse(0 1 0 1p 1p 0.025 0.05)
        vosc2 osc2 0 pulse(0 1 0.025 1p 1p 0.025 0.05)
        .tran 0 1000 1m
<p align="center">
    Figure 7 (SPICE CODE TITLE)
</p>

<p>
    SIM RESULT DESCRIPTION
</p>

<p align="center">
  <img width="1500" height="500" src="">
</p>

<p align="center">
    Figure 8 (RESULT TITLE)
</p>
    
</dd></dl></dd></dl>






<h2> Inverter </h2> <a name="buf"></a>

<dl><dd><h3>Schematic</h3> <a name="bufSchem"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>    
    SCHEMATIC DESCRIPTION
</p>

<p align="center">
  <img width="850" height="550" src="">
</p>

<p align="center">
    Figure 2 (SCHEMATIC TITLE)
</p>

<p>    
    ICON DESCRIPTION
</p>

<p align="center">
  <img width="300" height="250" src="">
</p>
<p align="center">
    Figure 3 (ICON TITLE)
</p>

</dd></dl></dd></dl>

<dl><dd><h3>Layout</h3> <a name="bufLay"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>    
    LAYOUT DESCRIPTION
</p>

<p align="center">
  <img width="850" height="550" src="">
</p>

<p align="center">
    Figure 2 (LAYOUT TITLE)
</p>

<p>    
   3D DESCRIPTION
</p>

<p align="center">
  <img width="300" height="250" src="">
</p>
<p align="center">
    Figure 3 (3D TITLE)
</p>

</dd></dl></dd></dl>

<dl><dd><h3>Simulation</h3> <a name="bufSim"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>
    SIMULATION DESCRIPTION
</p>
    
<p align="center">
  <img width="900" height="600" src="">
</p>
<p align="center">
    Figure 6 (SIMULATION TITLE)
</p>

<p>
    A snippet of the spice code for the simulation is provided below:
</p>

        .include cmosedu_models.txt
        
        vdd vdd 0 DC 1
        vosc osc 0 pulse(0 1 0 1p 1p 0.025 0.05)
        vosc2 osc2 0 pulse(0 1 0.025 1p 1p 0.025 0.05)
        .tran 0 1000 1m
<p align="center">
    Figure 7 (SPICE CODE TITLE)
</p>

<p>
    SIM RESULT DESCRIPTION
</p>

<p align="center">
  <img width="1500" height="500" src="">
</p>

<p align="center">
    Figure 8 (RESULT TITLE)
</p>
    
</dd></dl></dd></dl>






<h2> Inverter </h2> <a name="alu"></a>

<dl><dd><h3>Schematic</h3> <a name="aluSchem"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>    
    SCHEMATIC DESCRIPTION
</p>

<p align="center">
  <img width="850" height="550" src="">
</p>

<p align="center">
    Figure 2 (SCHEMATIC TITLE)
</p>

<p>    
    ICON DESCRIPTION
</p>

<p align="center">
  <img width="300" height="250" src="">
</p>
<p align="center">
    Figure 3 (ICON TITLE)
</p>

</dd></dl></dd></dl>

<dl><dd><h3>Layout</h3> <a name="aluLay"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>    
    LAYOUT DESCRIPTION
</p>

<p align="center">
  <img width="850" height="550" src="">
</p>

<p align="center">
    Figure 2 (LAYOUT TITLE)
</p>

<p>    
   3D DESCRIPTION
</p>

<p align="center">
  <img width="300" height="250" src="">
</p>
<p align="center">
    Figure 3 (3D TITLE)
</p>

</dd></dl></dd></dl>

<dl><dd><h3>Simulation</h3> <a name="aluSim"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>
    SIMULATION DESCRIPTION
</p>
    
<p align="center">
  <img width="900" height="600" src="">
</p>
<p align="center">
    Figure 6 (SIMULATION TITLE)
</p>

<p>
    A snippet of the spice code for the simulation is provided below:
</p>

        .include cmosedu_models.txt
        
        vdd vdd 0 DC 1
        vosc osc 0 pulse(0 1 0 1p 1p 0.025 0.05)
        vosc2 osc2 0 pulse(0 1 0.025 1p 1p 0.025 0.05)
        .tran 0 1000 1m
<p align="center">
    Figure 7 (SPICE CODE TITLE)
</p>

<p>
    SIM RESULT DESCRIPTION
</p>

<p align="center">
  <img width="1500" height="500" src="">
</p>

<p align="center">
    Figure 8 (RESULT TITLE)
</p>
    
</dd></dl></dd></dl>






<h2>Conclusion</h3>  <a name="conclusion"></a>

<p>
    CONCLUSION
</p>


