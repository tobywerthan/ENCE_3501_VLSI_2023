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
  <img width="900" height="500" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/e1b34333-5534-4a7e-a500-9dc2bd5943bc">
</p>

<p align="center">
    Figure 1 (Provided schematic of the DC-to-DC Regulator)
</p>

</dd><dl>

<h2> Inverter </h2> <a name="inv"></a>

<dl><dd><h3>Schematic</h3> <a name="invSchem"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>    
    The first component created for the DC-to-DC regulator was a three-stage charge pump. This schematic will ideally have an output voltage three times that of the input. In this case, the input voltage is one volt, so the output of this schematic would be three volts.
</p>

<p align="center">
  <img width="850" height="550" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/34305b8e-0911-408d-b24a-5ed6cedf9bc3">
</p>

<p align="center">
    Figure 2 (Schematic of the charge pump in Electric VLSI)
</p>

<p>    
    An icon was then generated from the schematic. This is an important step as the icon will be used to simulate the charge pump. 
</p>

<p align="center">
  <img width="300" height="250" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/42c24cbd-69c0-46a0-bb0c-96e24d083bd7">
</p>
<p align="center">
    Figure 3 (Icon generated from the charge pump schematic in Electric VLSI)
</p>

</dd></dl></dd></dl>

<dl><dd><h3>Simulation</h3> <a name="nandSim"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>
    The simulation of the charge pump tests the output voltage. Two pulse waves are fed into the charge pump that are out of phase from each other by 90 degrees. The inout voltage is also 1v. A transient is recorded of the output. 
</p>
    
<p align="center">
  <img width="900" height="600" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/cd6ecc9d-3c43-4293-9798-0b4052aae2c3">
</p>
<p align="center">
    Figure 6 (Simulation schematic of the charge pump in Electric VLSI)
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
    Figure 7 (Spice simulation code for the charge pump)
</p>

<p>
    The results of the simulation were successful in that the input voltage is increased significantly. However, as mentioned before, the ideal output voltage would be three volts. The low output seen in this result is most likely due to voltage loss calculations done in Electric VLSI. To remedy the low output voltage, more stages can be added to the charge pump's circuit allowing for the voltage to charge even more over time. 
</p>

<p align="center">
  <img width="1500" height="500" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/23b8cb12-79da-4a20-861b-d4928ad37bd2">
</p>

<p align="center">
    Figure 8 (Simulation results of the charge pump in LTSpice)
</p>
    
</dd></dl></dd></dl>

<h2>Conclusion</h3>  <a name="conclusion"></a>

<p>
    Lab 6 explored the creation of a DC-to-DC regulator. While the circuit is not fully functional, this lab provided a window into how self-sustaining circuits are designed and implemented. This also highlights how complex and difficult it can be to build a system like this in ELectric VLSI. 
</p>


