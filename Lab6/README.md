# Lab 6: DC to DC Converter

Toby Werthan

11/12/2023

ENCE 3501

## Table of Contents
1. [Introduction](#introduction)
2. [Charge Pump](#nand)
    1. [Schematic](#nandSchem)
    2. [Simulation](#nandSim)
3. [Ring Oscillator](#not)
    1. [Schematic](#notSchem)
    2. [Simulation](#notSim)
4. [Voltage Regulator](#xor)
    1. [Schematic](#xorSchem)
    2. [Simulation](#xorSim)
5. [DC to DC Regulator](#fulladder)
    1. [Schematic](#fulladderSchem)
    2. [Simulation](#fulladderSim)
6. [Conclusion](#conclusion)

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

<h2> Charge Pump </h2> <a name="nand"></a>

<dl><dd><h3>Schematic</h3> <a name="nandSchem"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>    
    The first component created for the DC-to-DC regulator was a three-stage charge pump. This schematic will ideally have an output voltage three times that of the input. In this case, the input voltage is one volt, so the output of this schematic would be three volts.
</p>

<p align="center">
  <img width="525" height="600" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/34305b8e-0911-408d-b24a-5ed6cedf9bc3">
</p>

<p align="center">
    Figure 2 (Schematic of the NAND gate in Electric VLSI)
</p>

<p>    
    An icon was then generated from the schematic. This is an important step as the icon will be used to simulate the NAND gate. 
</p>

<p align="center">
  <img width="500" height="250" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/42c24cbd-69c0-46a0-bb0c-96e24d083bd7">
</p>
<p align="center">
    Figure 3 (Icon generated from the NAND schematic in Electric VLSI)
</p>

</dd></dl></dd></dl>

<dl><dd><h3>Simulation</h3> <a name="nandSim"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>
    The first simulation tests the switching point of the NAND gate. Ideally, the switching point of the inverter is half of vdd. The spice code puts 5V through one input and a pulse wave that goes from 0V to 5V, the transient is then recorded.
</p>
    
<p align="center">
  <img width="900" height="600" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/cd6ecc9d-3c43-4293-9798-0b4052aae2c3">
</p>
<p align="center">
    Figure 6 (Simulation schematic of the NAND gate switching point in Electric VLSI)
</p>

<p>
    A snippet of the spice code for the simulation is provided below:
</p>

        .include C5_models.txt
        
        vdd vdd 0 DC 5
        vin in 0 pulse(0v 5v 10n 1n 1n 40n 40n)
        .tran 0 40n
<p align="center">
    Figure 7 (Spice simulation code for the NAND gate switching point)
</p>

<p>
    The results of the simulation were successful because the switching point was roughly half of vdd. 
</p>

<p align="center">
  <img width="1500" height="500" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/23b8cb12-79da-4a20-861b-d4928ad37bd2">
</p>

<p align="center">
    Figure 8 (Simulation results of the NAND gate switching point in LTSpice)
</p>
    
</dd></dl></dd></dl>

<h2> Ring Oscillator </h2> <a name="not"></a>

<dl><dd><h3>Schematic</h3> <a name="notSchem"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>    
    A NOT gate was created in Electric VLSI. This will be used to construct the Full Adder in order to complete the lab. The schematic for the NOT gate can be seen in Figure 12.
</p>

<p align="center">
  <img width="525" height="600" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/d9f8f5bc-e984-4c6b-bbcc-9f5ed3cb6994">
</p>
<p align="center">
    Figure 12 (Schematic of the Inverter 1 in Electric VLSI)
</p>

<p>    
    An icon was then generated from the schematic. This is an important step as the icon will be used to simulate the inverter. 
</p>

<p align="center">
  <img width="500" height="250" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/38e16430-6d38-4873-8fb4-4c6c519ced8d">
</p>
<p align="center">
    Figure 13 (Icon generated from the Inverter 1 schematic in Electric VLSI)
</p>

</dd></dl></dd></dl>

<dl><dd><h3>Simulation</h3> <a name="notSim"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>
    The simulation of the NOT gate tests the switching point of the logic gate. A pulse wave of 5v is applied to the input of the NOT gate. The transient is then recorded. 
</p>
    
<p align="center">
  <img width="1000" height="600" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/f568cd0d-a0c1-4356-aa48-9e244c2535df">
</p>
<p align="center">
    Figure 16 (Simulation schematic of the NOT gate in Electric VLSI)
</p>

<p>
    A snippet of the spice code for the simulation is provided below:
</p>

        .include C5_models.txt
        
        vdd vdd 0 DC 5
        vin d_in 0 pulse(0v 5v 10n 1n 1n 40n 40n)
        .tran 0 40n
<p align="center">
    Figure 17 (Spice simulation code for the inverter switching point)
</p>

<p>
    The results of the simulation were successful because the switching point was roughly half of vdd. 
</p>

<p align="center">
  <img width="1000" height="500" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/cd568de1-1724-47e0-8d1c-4ba29473f9cc">
</p>
<p align="center">
    Figure 18 (Simulation results of the NOT gate switching point in LTSpice)
</p>

</dd></dl></dd></dl>

<h2> Voltage Regulator </h2> <a name="xor"></a>

<dl><dd><h3>Schematic</h3> <a name="xorSchem"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>    
    An XOR gate was created in Electric VLSI. This will be used to construct the Full Adder in order to complete the lab. The schematic for the XOR gate can be seen in Figure 19.
</p>

<p align="center">
  <img width="900" height="900" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/7c0d92c7-6ec9-40d0-9005-36d0c6d85327">
</p>
<p align="center">
    Figure 19 (Schematic of the XOR gate in Electric VLSI)
</p>

<p>    
    An icon was then generated from the schematic. This is an important step as the icon will be used to simulate the XOR gate. 
</p>

<p align="center">
  <img width="500" height="250" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/dde9b9c1-c6c0-49d1-98de-624d2a989074">
</p>
<p align="center">
    Figure 20 (Icon generated from the XOR gate schematic in Electric VLSI)
</p>

</dd></dl></dd></dl>

<dl><dd><h3>Simulation</h3> <a name="xorSim"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>
    The first simulation of the XOR gate tests the switching point of the logic gate. Ideally, the switching point of the XOR gate is half of vdd. The spice code puts a constant 5V through one input, and a pulse wave of 5V through the other. The transient is then recorded. 
</p>
    
<p align="center">
  <img width="800" height="600" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/4676facc-8625-40a3-927c-ebfce46a723e">
</p>
<p align="center">
    Figure 23 (Simulation schematic of the XOR gate in Electric VLSI)
</p>

<p>
    A snippet of the spice code for the simulation is provided below:
</p>

        .include C5_models.txt
        
        vdd vdd 0 DC 5
        vin d_in 0 pulse(0v 5v 10n 1n 1n 40n 40n)
        .tran 0 40n
<p align="center">
    Figure 24 (Spice simulation code for the XOR gate switching point)
</p>

<p>
    The results of the simulation were successful because the switching point was roughly half of vdd. 
</p>

<p align="center">
  <img width="1000" height="500" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/6f17f31c-f55a-4f8a-a859-8f4715f0b8d1">
</p>
<p align="center">
    Figure 25 (Simulation results of the XOR gate switching point in LTSpice)
</p>

</dd></dl></dd></dl>

<h2> DC to DC Converter </h2> <a name="fulladder"></a>

<dl><dd><h3>Schematic</h3> <a name="fulladderSchem"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>    
    The provided schematic consists of three NANDS and two XORS. To achieve the correct behavior of a full adder, the schematic was created using the previously created NAND and XOR schematics. The schematic can be seen in Figure 29. 
</p>

<p align="center">
  <img width="850" height="450" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/b05d288e-c591-4e32-985f-7a0a62349927">
</p>
<p align="center">
    Figure 29 (Schematic of the Full Adder in Electric VLSI)
</p>


</dd></dl></dd></dl>

<dl><dd><h3>Simulation</h3> <a name="fulladderSim"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>
    The first simulation of the Full Adder tests the logic values of the schematic. The spice code puts a 5V pulse wave through each input. The pulse wave on B has an offset of 5ns, while the pulse wave on Cin has an offset of 2ns. The transient is then recorded. This allows the output to be monitored in comparison to various input combinations. 
</p>

<p align="center">
  <img width="500" height="600" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/0f511a7c-adb7-44e5-8a13-b45405e5ebd0">
</p>
<p align="center">
    Figure 33 (Simulation schematic of the Full Adder schematic logic values in Electric VLSI)
</p>

<p>
    A snippet of the spice code for the simulation is provided below:
</p>

        .include C5_models.txt
        
        vdd vdd 0 DC 5
        va a 0 pulse(0v 5v 0n 1n 1n 10n 20n)
        vb b 0 pulse(0v 5v 5n 1n 1n 10n 20n)
        vcin cin 0 pulse(0v 5v 2n 1n 1n 10n 20n)
        .tran 0 60n
<p align="center">
    Figure 34 (Spice simulation code for the Full Adder schematic logic values)
</p>

<p>
    The results of the simulation were successful because the output of the schematic functioned as a conventional Full Adder. 
</p>

<p align="center">
  <img width="1000" height="500" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/0f383b13-c002-4385-80e5-9f9f1412c475">
</p>
<p align="center">
    Figure 35 (Simulation results of the Full Adder schematic logic values)
</p>

</dd></dl></dd></dl>

<h2>Conclusion</h3>  <a name="conclusion"></a>

<p>
    Lab 5 explored the creation of a more complex CMOS circuit, the Full Adder. The Full Adder was created through various sub-components that were created as a part of the lab as well. The construction of the Full Adder gives insight into the design of complex CMOS circuits in VLSI. 
</p>

